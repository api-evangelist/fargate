---
title: "Simplifying developer experience with variables and JSONata in AWS Step Functions"
url: "https://aws.amazon.com/blogs/compute/simplifying-developer-experience-with-variables-and-jsonata-in-aws-step-functions/"
date: "Fri, 22 Nov 2024 19:57:46 +0000"
author: "Chris McPeek"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p><em>This post is written by Uma Ramadoss, Principal Specialist SA, Serverless and Dhiraj Mahapatro, Principal Specialist SA, Amazon Bedrock</em></p> 
<p><a href="https://aws.amazon.com/step-functions/">AWS Step Functions</a> is introducing variables and <a href="https://docs.jsonata.org/overview.html">JSONata</a> data transformations. Variables allow developers to assign data in one state and reference it in any subsequent steps, simplifying state payload management without the need to pass data through multiple intermediate states. With JSONata, an open source query and transformation language, you now perform advanced data manipulation and transformation, such as date and time formatting and mathematical operations.</p> 
<p>This blog post explores the powerful capabilities of these new features, delving deep into simplifying data sharing across states using variables and reducing data manipulation complexity through advanced JSONata expressions.</p> 
<h2>Overview</h2> 
<p>Customers choose Step Functions to build complex workflows that involve multiple services such as <a href="https://aws.amazon.com/lambda/">AWS Lambda</a>, <a href="https://aws.amazon.com/fargate/">AWS Fargate</a>, <a href="https://aws.amazon.com/bedrock/">Amazon Bedrock</a>, and HTTP API integrations. Within these workflows, you build states to interface with these various services, passing input data and receiving responses as output. While you can use Lambda functions for date, time, and number manipulations beyond Step Functions’ intrinsic capabilities, these methods struggle with increasing complexity, leading to payload restrictions, data conversion burdens, and more state changes. This affects the overall cost of the solution. You use variables and JSONata to address this.</p> 
<p>To illustrate these new features, consider the same business use case from the <a href="https://aws.amazon.com/blogs/compute/using-jsonpath-effectively-in-aws-step-functions/">JSONPath blog</a>, a customer onboarding process in the insurance industry. A potential customer provides basic information, including names, addresses, and insurance interests, while signing up. This Know-Your-Customer (KYC) process starts a Step Functions workflow with a payload containing these details. The workflow decides the customer’s approval or denial, followed by sending a notification.</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">{
  "data": {
    "firstname": "Jane",
    "lastname": "Doe",
    "identity": {
      "email": "jdoe@example.com",
      "ssn": "123-45-6789"
    },
    "address": {
      "street": "123 Main St",
      "city": "Columbus",
      "state": "OH",
      "zip": "43219"
    },
    "interests": [
      {"category": "home", "type": "own", "yearBuilt": 2004, "estimatedValue": 800000},
      {"category": "auto", "type": "car", "yearBuilt": 2012, "estimatedValue": 8000},
      {"category": "boat", "type": "snowmobile", "yearBuilt": 2020, "estimatedValue": 15000},
      {"category": "auto", "type": "motorcycle", "yearBuilt": 2018, "estimatedValue": 25000},
      {"category": "auto", "type": "RV", "yearBuilt": 2015, "estimatedValue": 102000},
      {"category": "home", "type": "business", "yearBuilt": 2009, "estimatedValue": 500000}
    ]
  }
}
</code></pre> 
</div> 
<p>The original workflow diagram illustrates the workflow without new features, while the new workflow diagram shows the workflow built by applying variables and JSONata. Access the workflows in the <a href="https://github.com/aws-samples/serverless-account-signup-service/tree/jsonata-variables">GitHub repository</a> from the <code>main</code> (original workflow) and <code>jsonata-variables</code> (new workflow) branches.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/1-jsonata.png"><img alt="Image of Original Workflow." class="alignnone size-full wp-image-23062" height="738" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/1-jsonata.png" width="647" /></a></p> 
<p><em>Figure 1: Original Workflow</em></p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/2-jsonata.png"><img alt="Image of New Workflow." class="alignnone size-full wp-image-23061" height="750" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/2-jsonata.png" width="577" /></a></p> 
<p><em>Figure 2: New Workflow</em></p> 
<h2>Setup</h2> 
<p>Follow the steps in the <a href="https://github.com/aws-samples/serverless-account-signup-service/tree/jsonata-variables">README</a> to create this state machine and cleanup once testing is complete.</p> 
<h2>Simplifying data sharing with variables</h2> 
<p>Variables allow you to instantiate or assign state results to a variable that is referenced in future states. In a single state, you assign multiple variables with different values, including static data, results of a state, JSONPath or JSONata expressions, and intrinsic functions. The following diagram illustrates how variables are assigned and used inside a state machine:</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/3-jsonata.png"><img alt="Image of Variable assignment and scope." class="alignnone size-full wp-image-23060" height="479" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/3-jsonata.png" width="841" /></a></p> 
<p><em>Figure 3: Variable assignment and scope</em></p> 
<h3>Variable scope</h3> 
<p>In Step Functions, variables have a scope similar to programming languages. You define variables at different levels, with inner scope and outer scope. Inner scope variables are defined inside map, parallel, or nested workflows and these variables are only accessible within their specific scope. Alternatively, you set outer scope variables at the top level. Once assigned, these variables can be accessed from any downstream state irrespective of their order of execution in the future<em>. </em>However, as of the release of this blog, distributed map state cannot reference variables in outer scopes. The <a href="http://docs.aws.amazon.com/step-functions/latest/dg/workflow-variables.html#variable-scope">user guide on variable scope</a> elaborates on these edge cases.</p> 
<p>Variable assignment and usage<br /> To set a variable’s value, use the special field <strong>Assign</strong>. The JSONata part of this blog post further down explains the purpose of <strong>{%%}</strong>.</p> 
<div> 
 <pre><code class="lang-json">"Assign": {
  "inputPayload": "{% $states.context.Execution.Input %}",
  "isCustomerValid": "{% $states.result.isIdentityValid and $states.result.isAddressValid %}"
} </code></pre> 
</div> 
<p>Use a variable by writing a dollar sign ($) before its name.</p> 
<div> 
 <pre><code class="lang-json">{
  "TableName": "AccountTable",
  "Item": {
    "email": {
      "S": "{% $inputPayload.data.email %}"
    },
    "firstname": {
      "S": "{% $inputPayload.data.firstname %}"
    },....
} 
</code></pre> 
</div> 
<h2>Simplifying data manipulations with JSONata</h2> 
<p><a href="https://docs.jsonata.org/overview.html">JSONata</a> is a lightweight query and transformation language for Json data. JSONata offers more capabilities compared to JSONPath within Step Functions.</p> 
<p>Setting <code>QueryLanguage</code> to <code>“JSONata”</code> and using {%%} tags for JSONata expressions allows you to leverage JSONata within a state machine. <a href="http://docs.aws.amazon.com/step-functions/latest/dg/transforming-data.html">Apply this configuration</a> at the top level of the state machine or at each task level. JSONata at the task level gives you fine-grained control of choosing JSONata vs JSONPath. This approach is valuable for complex workflows where you want to simplify a subset of states with JSONata and continue to use JSONPath for the rest. JSONata provides you with more functions and operators than JSONPath and intrinsic functions in Step Functions. <a href="http://docs.aws.amazon.com/step-functions/latest/dg/transforming-data.html#converting-from-jsonpath-to-jsonata">Activating the QueryLanguage attribute</a> as JSONata at the state machine level disables JSONPath, therefore, restricting the use of <code>InputPath</code>, <code>Parameters</code>,&nbsp; <code>ResultPath</code>, <code>ResultSelector</code>, and <code>OutputPath</code>. Instead of these JSONPath parameters, JSONata uses <code>Arguments</code> and <code>Output</code>.</p> 
<h2>Optimizing simple states</h2> 
<p>One of the first things to notice in the new state machine is that the <code>Verification</code> process does not use Lambda functions anymore as seen in the following comparison:</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/4-jsonata.png"><img alt="Image of Lambda functions replaced with Pass states." class="alignnone size-full wp-image-23059" height="304" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/4-jsonata.png" width="1461" /></a></p> 
<p><em>Figure 4: Lambda functions replaced with Pass states</em></p> 
<p>In the previous approach, a Lambda function is used to validate email and SSN using regular expressions:</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-js">const ssnRegex = /^\d{3}-?\d{2}-?\d{4}$/;
const emailRegex = /^[a-zA-Z0-9._-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,4}$/;

exports.lambdaHandler = async event =&gt; {
  const { ssn, email } = event;
  const approved = ssnRegex.test(ssn) &amp;&amp; emailRegex.test(email);

  return {
    statusCode: 200,
    body: JSON.stringify({ 
      approved,
      message: `identity validation ${approved ? 'passed' : 'failed'}`
    })
  }
};</code></pre> 
</div> 
<p>With JSONata, you define regular expressions directly in the state machine’s <a href="https://docs.aws.amazon.com/step-functions/latest/dg/concepts-amazon-states-language.html">Amazon States Language</a> (ASL). You use a <code>Pass</code> state and <code><a href="https://docs.jsonata.org/string-functions#match">$match()</a></code> from JSONata to validate the email and the SSN.</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">{
  "StartAt": "Check Identity",
   "States": {
    "Check Identity": {
      "Type": "Pass",
      "QueryLanguage": "JSONata",
      "End": true,
      "Output": {
        "isIdentityValid": "{% $match($states.input.data.identity.email, /^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\\.[a-zA-Z]{2,}$/) and $match($states.input.data.identity.ssn, /^(\\d{3}-?\\d{2}-?\\d{4}|XXX-XX-XXXX)$/) %}"
      }
    }
   }
}
</code></pre> 
</div> 
<p>The same applies to validate the address inside a <code>Pass</code> state using sophisticated JSONata string functions like <code>$length</code>, <code>$trim</code>, <code>$each</code>, and <code>$not</code> from JSONata:</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">{
  "StartAt": "Check Address",
  "States": {
    "Check Address": {
      "Type": "Pass",
      "QueryLanguage": "JSONata",
      "End": true,
      "Output": {
        "isAddressValid": "{% $not(null in $each($states.input.data.address, function($v) { $length($trim($v)) &gt; 0 ? $v : null })) %}"
      }
    }
  }
}
</code></pre> 
</div> 
<p>When using JSONata, <code>$states</code> becomes a <a href="http://docs.aws.amazon.com/step-functions/latest/dg/transforming-data.html#reserved-variable-states">reserved variable</a>.</p> 
<h2>Result aggregation</h2> 
<p>Previously with JSONPath, using an expression outside of a <code>Choice</code> state was not available. That is not the case anymore with JSONata. The parallel state, in the example, gathers identity and address verification results from each sub-step. You merge the results into a boolean variable <code>isCustomerValid</code>.</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">"Verification": {
  "Type": "Parallel",
  "QueryLanguage": "JSONata",
  ...
  "Assign": {
    "inputPayload": "{% $states.context.Execution.Input %}",
    "isCustomerValid": "{% $states.result.isIdentityValid and $states.result.isAddressValid %}"
  },
  "Next": "Approve or Deny?"
}</code></pre> 
</div> 
<p>The crucial part to note here is the access to results via <code>$states.result</code> and use of AND <a href="https://docs.jsonata.org/boolean-operators">boolean-operator</a> inside {%%}. This ultimately makes the downstream <code>Choice</code> state, which uses this variable, simpler. <a href="https://docs.jsonata.org/path-operators">Operators in JSONata</a> give you flexibility to write expressions like these wherever possible, which reduces the need of a compute layer to process simple data transformations.</p> 
<p>Additionally, the <code>Choice</code> state becomes simpler to use with flexible JSONata operators and expressions, as long as the expressions within <strong>{%%}</strong> result in a true or false value.</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">"Approve or Deny?": {
  "Type": "Choice",
  "QueryLanguage": "JSONata",
  "Choices": [
    {
      "Next": "Add Account",
      "Condition": "{% $isCustomerValid %}"
    }
  ],
  "Default": "Deny Message"
}
</code></pre> 
</div> 
<h2>Intrinsic functions as JSONata functions</h2> 
<p>Step Functions provides built-in JSONata functions to enable parity with <a href="https://docs.aws.amazon.com/step-functions/latest/dg/intrinsic-functions.html">Step Functions’ intrinsic functions</a>. The DynamoDB <code>putItem</code> step shows how you use <code>$uuid()</code> that has the same functionality as <code>States.UUID()</code> intrinsic function. You also get JSONata specific functions on date and time. The following state shows the use of <code>$now()</code> to get the current timestamp as ISO-8601 as a string before inserting this item to the DynamoDB table.</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">"Add Account": {
  "Type": "Task",
  "QueryLanguage": "JSONata",
  "Resource": "arn:aws:states:::dynamodb:putItem",
  "Arguments": {
    "TableName": "AccountTable",
    "Item": {
      "PK": {
        "S": "{% $uuid() %}"
      },
      "email": {
        "S": "{% $inputPayload.data.identity.email %}"
      },
      "name": {
        "S": "{% $inputPayload.data.firstname &amp; ' ' &amp; $inputPayload.data.lastname  %}"
      },
      "address": {
        "S": "{% $join($each($inputPayload.data.address, function($v) { $v }), ', ') %}"
      },
      "timestamp": {
        "S": "{% $now() %}"
      }
    }
  },
  "Next": "Interests"
}
</code></pre> 
</div> 
<p>Notice that you don’t apply the <code>.$</code> notation in <code>S.$</code> anymore as JSONata expressions reduces developer pain while building state machine ASL. Explore the <a href="http://docs.aws.amazon.com/step-functions/latest/dg/transforming-data.html#jsonata-functions-provided-by-sfn">additional JSONata functions</a> accessible within Step Functions.</p> 
<h2>Advanced JSONata</h2> 
<p>JSONata’s flexibility stems from its pre-built functions, <a href="https://docs.jsonata.org/higher-order-functions">higher-order functions</a> support, and <a href="https://docs.jsonata.org/programming">functional programming constructs</a>. With JSONPath, you used the advanced expressions <code>"InputPath": "$..interests[?(@.category==home)]"</code> to filter Home insurance related interests from the interests array. JSONata does much more than <a href="https://github.com/aws-samples/serverless-account-signup-service/blob/jsonata-variables/statemachine/application_service.asl.json#L85">filtering</a>. For example, you look for home insurance interests, totalAssetValue of the category type as home, and refer to existing fields like name and email as JSONata variables:</p> 
<div class="hide-language"> 
 <pre style="padding-left: 40px;"><code class="lang-json">(
    $e := data.identity.email;
    $n := data.firstname &amp; ' ' &amp; data.lastname;
    
    data.interests[category = 'home']{
      'customer': $n,
      'email': $e,
      'totalAssetValue': $sum(estimatedValue),
      category: {type: yearBuilt}
    }
)
</code></pre> 
</div> 
<p>The result JSON will be:</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">{
  "customer": "Jane Doe",
  "email": "jdoe@example.com",
  "totalAssetValue": 1400000,
  "home": {
    "own": 2004,
    "business": 2009
  }
}
</code></pre> 
</div> 
<p>By following these steps, you ascend one level by collecting all of the insurance interests and their aggregated results. Notice that the category filter is no longer present.</p> 
<div class="hide-language"> 
 <pre style="padding-left: 40px;"><code class="lang-json">(
    $e := data.identity.email;
    $n := data.firstname &amp; ' ' &amp; data.lastname;
    
    data.interests{
      'customer': $n,
      'email': $e,
      'totalAssetValue': $sum(estimatedValue),
      category: {type: yearBuilt}
    }
)
</code></pre> 
</div> 
<p>which results in:</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">{
  "customer": "Jane Doe",
  "email": "jdoe@example.com",
  "totalAssetValue": 1549000,
  "home": {
    "own": 2004,
    "business": 2009
  },
  "auto": {
    "car": 2012,
    "motorcycle": 2018,
    "RV": 2015
  },
  "boat": {
    "snowmobile": 2020
  }
}
</code></pre> 
</div> 
<h2>Discovering complex expressions</h2> 
<p><a href="https://try.jsonata.org/">Use the JSONata playground</a> with your sample data to discover detailed and complex expressions that fit your requirements. The following is an example of using the JSONata playground:</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/5-jsonata.png"><img alt="Image of JSONata playground." class="alignnone size-full wp-image-23058" height="703" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/5-jsonata.png" width="1195" /></a></p> 
<p><em>Figure 5: JSONata playground</em></p> 
<h2>Considerations</h2> 
<h3>Variable Size</h3> 
<p>The maximum size of a single variable is 256Kib. This limit helps you bypass the Step Functions payload size restriction by letting you store state outputs in separate variables. While each individual variable can be up to 256Kib in size, the total size of all variables within a single <code>Assign</code> field cannot exceed 256Kib. Use <code>Pass</code> states to workaround this limitation, however, the total size of all stored variables cannot exceed 10MiB per execution.</p> 
<h3>Variable visibility</h3> 
<p>Variables are a powerful mechanism to simplify the data sharing across states. Prefer them over <code>ResultPath</code>, <code>OutputPath</code> or JSONata’s <code>Output</code> fields because of their ease of use and flexibility. There are two situations where you might still use <code>Output</code>. First, you can’t access inner-scoped variables in the outer scope. In these cases, fields in <code>Output</code> can help share data between different workflow levels. Second, when sending a response from the final state of the workflow, you may need to use fields in <code>Output</code> fields. The following transition diagram from JSONPath to JSONata provides additional details:</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/6-jsonata.png"><img alt="Image of Transition from JSONPath to JSONata." class="alignnone size-full wp-image-23057" height="489" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/11/21/6-jsonata.png" width="1150" /></a></p> 
<p><em>Figure 6: Transition from JSONPath to JSONata</em></p> 
<p>Additionally, variables assigned to a specific state are not accessible in that same state:</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">"Assign Variables": {
  "Type": "Pass",
  "Next": "Reassign Variables",
  "Assign": {
    "x": 1,
    "y": 2
  }
},
"Reassign Variables": {
  "Type": "Pass",
  "Assign": {
    "x": 5,
    "y": 10,
      ## The assignment will fail unless you define x and y in a prior state.
      ## otherwise, the value of z will be 3 instead of 15.
    "z": "{% $x+$y %}"
  },
  "Next": "Pass"
}
</code></pre> 
</div> 
<h3>Best practices</h3> 
<p>Step Functions’ <a href="https://aws.amazon.com/about-aws/whats-new/2024/08/validation-api-step-functions/">validation API</a> provides semantic checks for workflows, allowing for early problem identification. To ensure safe workflow updates, it’s best to combine the validation API with <a href="https://aws.amazon.com/blogs/compute/deploying-state-machines-incrementally-with-versions-and-aliases-in-aws-step-functions/">versioning and aliases</a> for incremental deployment.</p> 
<p>Multi-line expressions in JSONata are not valid JSON. Therefore, use <a href="https://github.com/aws-samples/serverless-account-signup-service/blob/jsonata-variables/statemachine/application_service.asl.json#L85">a single line</a> as string delimited by a semicolon “;” where the last line returns the expression.</p> 
<h3>Mutually exclusive</h3> 
<p>Use of <code>QueryLanguage</code> type is mutually exclusive. Do not mix JSONPath/intrinsic functions and JSONata during variable assignments. For example, the below task fails because the variable <code>b</code> uses JSONata, whereas <code>c</code> uses an intrinsic function.</p> 
<div> 
 <pre style="padding-left: 40px;"><code class="lang-json">"Store Inputs": {
  "Type": "Pass",
  "QueryLanguage": "JSONata"
  "Assign": {
    "inputs": {
      "a": 123,
      "b": "{% $states.input.randomInput %}",
      "c.$": "States.MathRandom($.start, $.end)"
    }
  },
  "Next": "Average"
}
</code></pre> 
</div> 
<p>To <a href="http://docs.aws.amazon.com/step-functions/latest/dg/workflow-variables.html#using-variables-in-jsonpath-states">use variables with JSONPath</a>, set the <code>QueryLanguage</code> to <code>JSONPath</code> or remove this attribute from the task definition.</p> 
<h2>Conclusion</h2> 
<p>With variables and JSONata, AWS Step Functions now elevates the developer’s experience to write elegant workflows with simpler code in Amazon States Language (ASL) that matches with the normal programming paradigm. Developers can now build faster and write cleaner code by cutting out extra data transformation steps. These capabilities can be used in both new and existing workflows, giving you the flexibility to upgrade from JSONPath to JSONata and variables.</p> 
<p>Variables and JSONata are available at no additional cost to customers in all the AWS regions where AWS Step Functions is available. For more information, refer to the user guide for <a href="http://docs.aws.amazon.com/step-functions/latest/dg/transforming-data.html">JSONata</a> and <a href="http://docs.aws.amazon.com/step-functions/latest/dg/workflow-variables.html">variables</a>, as well as the <a href="https://github.com/aws-samples/serverless-account-signup-service/tree/jsonata-variables">sample application</a> in the <code>jsonata-variables</code> branch.</p> 
<p>To expand your serverless knowledge, visit&nbsp;<a href="https://serverlessland.com/" rel="noopener" target="_blank">Serverless Land</a>.</p>
