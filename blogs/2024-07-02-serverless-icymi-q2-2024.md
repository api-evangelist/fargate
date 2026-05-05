---
title: "Serverless ICYMI Q2 2024"
url: "https://aws.amazon.com/blogs/compute/serverless-icymi-q2-2024/"
date: "Tue, 02 Jul 2024 15:57:10 +0000"
author: "Julian Wood"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p>Welcome to the 26th edition of the AWS Serverless ICYMI (in case you missed it) quarterly recap. Every quarter, we share all the most recent product launches, feature enhancements, blog posts, webinars, live streams, and other interesting things that you might have missed!</p> 
<p>In case you missed our last ICYMI, check out what happened last quarter&nbsp;<a href="https://aws.amazon.com/blogs/compute/serverless-icymi-q1-2024/" rel="noopener" target="_blank">here</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22515" style="width: 620px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/ICYMI2024Q2.png"><img alt="Calendar" class="size-full wp-image-22515" height="179" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/ICYMI2024Q2.png" width="610" /></a>
 <p class="wp-caption-text" id="caption-attachment-22515">Calendar</p>
</div> 
<h2>EDA Day – London 2024</h2> 
<p>The AWS Serverless DA team hosted the third <a href="https://gotoldn.com/2024-eda-aws-day" rel="noopener" target="_blank">Event-Driven Architecture (EDA) Day</a>&nbsp;in London on May 14th. This event brought together prominent figures in the event-driven architecture community, AWS, and customer speakers.</p> 
<p>EDA Day covered 13&nbsp;sessions, 2 workshops, and a Q&amp;A panel. <a href="https://twitter.com/boyney123" rel="noopener" target="_blank">David Boyne</a> was the keynote speaker with a talk “Complexity is the Gotcha of Event-Driven Architecture”. There were AWS speakers including Matthew Meckes, Natasha Wright, Julian Wood, Gillian Amstrong, Josh Kahn, Veda Ramen, and Uma Ramadoss. There was also an impressive lineup of guest speakers, <a href="https://x.com/dfrasca80" rel="noopener" target="_blank">Daniele Frasca</a>, <a href="https://x.com/davidand393" rel="noopener" target="_blank">David Anderson</a>, <a href="https://x.com/ryancormack" rel="noopener" target="_blank">Ryan Cormack</a>, <a href="https://twitter.com/serverlesssarah" rel="noopener" target="_blank">Sarah Hamilton</a>, <a href="https://twitter.com/sheenbrisals" rel="noopener" target="_blank">Sheen Brisals</a>, <a href="https://www.linkedin.com/in/marcinsodkiewicz/" rel="noopener" target="_blank">Marcin Sodkiewicz</a>, and <a href="https://x.com/ellerbyben" rel="noopener" target="_blank">Ben Ellerby</a>.</p> 
<p>Videos are available on <a href="https://www.youtube.com/playlist?list=PLEx5khR4g7PJO9-CeWVBJ8If1C4jg7brx" rel="noopener" target="_blank">YouTube</a></p> 
<div class="mceTemp"></div> 
<div class="wp-caption aligncenter" id="attachment_22518" style="width: 628px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/EDADay.jpg"><img alt="EDA Day London" class="size-full wp-image-22518" height="377" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/EDADay.jpg" width="618" /></a>
 <p class="wp-caption-text" id="caption-attachment-22518">EDA Day London</p>
</div> 
<h2>The future of Serverless</h2> 
<p>There has been a lot of talk about the future of serverless, with this year being the 10<sup>th</sup> anniversary of <a href="https://aws.amazon.com/lambda/" rel="noopener" target="_blank">AWS Lambda</a>. Eric Johnson addresses the topic in his ServerlessDays Milan keynote, “<a href="https://youtu.be/l6jWJ35tDR4?t=196" rel="noopener" target="_blank">Now serverless is all grown up, what’s next</a>”.</p> 
<h2>AWS Lambda</h2> 
<p>AWS launched support for the latest release of <a href="https://aws.amazon.com/about-aws/whats-new/2024/04/aws-lambda-ruby-3-3/" rel="noopener" target="_blank">Ruby 3.3</a> is based on the new&nbsp;<a href="https://aws.amazon.com/blogs/compute/introducing-the-amazon-linux-2023-runtime-for-aws-lambda/" rel="noopener" target="_blank">Amazon Linux 2023 runtime</a>. The Ruby 3.3 runtime also provides access to the latest Ruby language features.</p> 
<p>There is a new guide on <a href="https://docs.aws.amazon.com/lambda/latest/dg/runtimes-list-deprecated.html" rel="noopener" target="_blank">how to retrieve data about Lambda functions that use a deprecated runtime</a>.</p> 
<p>Learn how to <a href="https://aws.amazon.com/blogs/compute/running-code-after-returning-a-response-from-an-aws-lambda-function/" rel="noopener" target="_blank">run code after returning a response from an AWS Lambda function</a>. This post shows how to return a synchronous function response as soon as possible, yet also perform additional asynchronous work after you send the response. For example, you may store data in a database or send information to a logging system.</p> 
<p>See how you can <a href="https://aws.amazon.com/blogs/compute/using-the-circuit-breaker-pattern-with-aws-lambda-extensions-and-amazon-dynamodb/" rel="noopener" target="_blank">use the circuit-breaker pattern</a> with Lambda extensions and <a href="https://aws.amazon.com/dynamodb/" rel="noopener" target="_blank">Amazon DynamoDB</a>. The circuit breaker pattern can help prevent cascading failures and improve overall system stability.</p> 
<div class="wp-caption aligncenter" id="attachment_22511" style="width: 1034px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Circuit-breaker-pattern.png"><img alt="Circuit-breaker pattern" class="size-large wp-image-22511" height="425" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Circuit-breaker-pattern-1024x425.png" width="1024" /></a>
 <p class="wp-caption-text" id="caption-attachment-22511">Circuit-breaker pattern</p>
</div> 
<p>Lambda functions now scale up to 12X faster in the <a href="https://aws.amazon.com/about-aws/whats-new/2024/04/aws-lambda-functions-12x-faster-govcloud-us-regions/" rel="noopener" target="_blank">AWS GovCloud (US) Regions</a>.</p> 
<p>Powertools for AWS Lambda (Python) <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/powertools-aws-lambda-python-support-agents-bedrock/" rel="noopener" target="_blank">adds support for Agents</a> for <a href="https://aws.amazon.com/bedrock/" rel="noopener" target="_blank">Amazon Bedrock</a>.</p> 
<p>The <a href="https://docs.aws.amazon.com/sdk-for-javascript/v2/developer-guide/welcome.html" rel="noopener" target="_blank">AWS SDK for JavaScript v2</a> enters <a href="https://aws.amazon.com/blogs/developer/announcing-end-of-support-for-aws-sdk-for-javascript-v2/" rel="noopener" target="_blank">maintenance mode</a> on September 8, 2024 and reaches end-of-support on September 8, 2025.</p> 
<p><a href="https://aws.amazon.com/cloudwatch/" rel="noopener" target="_blank">Amazon CloudWatch</a> Logs introduced <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/amazon-cloudwatch-logs-announces-live-tail-streaming-cli-support/" rel="noopener" target="_blank">Live Tail streaming CLI support</a>.</p> 
<h2>Amazon ECS and AWS Fargate</h2> 
<p>You can now secure <a href="https://aws.amazon.com/ecs/" rel="noopener" target="_blank">Amazon Elastic Container Service (Amazon ECS)</a> workloads on <a href="https://aws.amazon.com/fargate/" rel="noopener" target="_blank">AWS Fargate</a> with customer managed keys (CMKs). Once you add your keys to&nbsp;<a href="https://aws.amazon.com/kms/" rel="noopener" target="_blank">AWS Key Management Service</a>&nbsp;(AWS KMS), you can use these to encrypt the underlying ephemeral storage of an Amazon ECS task on AWS Fargate.</p> 
<p><a href="https://aws.amazon.com/blogs/containers/windows-containers-on-aws-fargate-launch-time-improvements/" rel="noopener" target="_blank">Windows containers on AWS Fargate now start faster</a>, up to 42% for Windows Server 2022 Core. AWS has optimized the Windows Server AMIs, introduced <a href="https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/concepts.html" rel="noopener" target="_blank">EC2 fast launch</a>&nbsp;with pre-provisioned snapshots, and reduced network latency.</p> 
<p><a href="https://aws.amazon.com/about-aws/whats-new/2022/11/amazon-ecs-service-connect/" rel="noopener" target="_blank">Amazon ECS Service Connect</a>&nbsp;is a networking capability to simplify service discovery, connectivity, and traffic observability for Amazon ECS. You can now <a href="https://aws.amazon.com/blogs/containers/proactive-scaling-of-amazon-ecs-services-using-amazon-ecs-service-connect-metrics/" rel="noopener" target="_blank">proactively scale Amazon ECS services by using custom metrics</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22510" style="width: 1034px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/ECS-Connect-custom-metrics.png"><img alt="ECS Connect custom metrics" class="size-large wp-image-22510" height="639" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/ECS-Connect-custom-metrics-1024x639.png" width="1024" /></a>
 <p class="wp-caption-text" id="caption-attachment-22510">ECS Service Connect custom metrics</p>
</div> 
<h2>AWS Step Functions</h2> 
<p>The <a href="https://aws.amazon.com/step-functions/" rel="noopener" target="_blank">AWS Step Functions</a> <a href="https://docs.aws.amazon.com/step-functions/latest/dg/test-state-isolation.html" rel="noopener" target="_blank">TestState API</a> allows you to test individual states independently and to integrate testing into your preferred development workflows. Learn how to <a href="https://aws.amazon.com/blogs/compute/accelerating-workflow-development-with-the-teststate-api-in-aws-step-functions/" rel="noopener" target="_blank">accelerate workflow development to iterate faster</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22509" style="width: 572px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Step-Functions-TestState-API.jpg"><img alt="Step Functions TestState API" class="size-full wp-image-22509" height="316" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Step-Functions-TestState-API.jpg" width="562" /></a>
 <p class="wp-caption-text" id="caption-attachment-22509">Step Functions TestState API</p>
</div> 
<h2>Amazon EventBridge</h2> 
<p><a href="https://aws.amazon.com/eventbridge/" rel="noopener" target="_blank">Amazon EventBridge</a> Pipes now supports event delivery through <a href="https://aws.amazon.com/privatelink/" rel="noopener" target="_blank">AWS PrivateLink</a>. You can send events from an event source located in an <a href="https://aws.amazon.com/vpc/" rel="noopener" target="_blank">Amazon Virtual Private Cloud</a> (VPC) to a Pipes target without traversing the public internet.</p> 
<p><a href="https://docs.aws.amazon.com/timestream/latest/developerguide/what-is-timestream.html" rel="noopener" target="_blank">Amazon Timestream for LiveAnalytics</a> is now an <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/amazon-timestream-liveanalytics-eventbridge-pipes-target/" rel="noopener" target="_blank">EventBridge Pipes target</a>. Timestream for LiveAnalytics is a fast, scalable, purpose-built time series database that makes it easy to store and analyze trillions of time series data points per day.</p> 
<p>EventBridge has a new <a href="https://www.youtube.com/playlist?list=PLEx5khR4g7PJO9-CeWVBJ8If1C4jg7brx" rel="noopener" target="_blank">console dashboard</a> which provides a centralized view of your resources, metrics, and quotas. The console has an <a href="https://aws.amazon.com/about-aws/whats-new/2024/04/amazon-eventbridge-console-enhancements/" rel="noopener" target="_blank">improved Learn page and other console enhancements</a>. When using the CloudFormation template export for Pipes, you can also generate the IAM role. There is a new Rules tab in the Event Bus detail page, and the monitoring tab in the Rule detail page now includes additional metrics.</p> 
<p>EventBridge Scheduler has some <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/amazon-eventbridge-scheduler-api-request-metrics-improved-observability/" rel="noopener" target="_blank">new API request metrics for improved observability</a>.</p> 
<h2>Generative AI</h2> 
<p><a href="https://aws.amazon.com/bedrock/" rel="noopener" target="_blank">Amazon Bedrock</a> is a fully managed Generative AI service that offers a choice of high-performing foundation models (FMs) from leading AI companies through a single API. Bedrock now supports new models, including <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/anthropic-claude-3-5-sonnet-model-bedrock/" rel="noopener" target="_blank">Anthropic’s Claude 3.5</a>, <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/ai21-labs-jamba-instruct-model-amazon-bedrock/" rel="noopener" target="_blank">AI21 Labs’ Jamba-Instruct</a>, <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/amazon-titan-text-premier-amazon-bedrock/" rel="noopener" target="_blank">Amazon Titan Text Premier</a>.</p> 
<p>The new Bedrock <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/amazon-bedrock-new-converse-api/" rel="noopener" target="_blank">Converse API</a> provides a consistent way to invoke Amazon Bedrock models and simplifies multi-turn conversations. There is also a JavaScript <a href="https://community.aws/content/2dtauBCeDa703x7fDS9Q30MJoBA/amazon-bedrock-converse-api-developer-guide" rel="noopener" target="_blank">tutorial</a> to walk you through sending requests to the Converse API using the Javascript SDK.</p> 
<p><a href="https://aws.amazon.com/q/developer/" rel="noopener" target="_blank">Amazon Q Developer</a> <a href="https://aws.amazon.com/blogs/aws/amazon-q-developer-now-generally-available-includes-new-capabilities-to-reimagine-developer-experience/" rel="noopener" target="_blank">is now generally available</a>. Amazon Q Developer, part of the <a href="https://aws.amazon.com/q/" rel="noopener" target="_blank">Amazon Q</a> family, is a generative AI–powered assistant for software development. Amazon Q is available in the AWS Management Console and as an integrated development environment (IDE) extension for <a href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.amazon-q-vscode" rel="noopener" target="_blank">Visual Studio Code</a>, <a href="https://marketplace.visualstudio.com/items?itemName=AmazonWebServices.AWSToolkitforVisualStudio2022" rel="noopener" target="_blank">Visual Studio</a>, and <a href="https://plugins.jetbrains.com/plugin/24267-amazon-q/" rel="noopener" target="_blank">JetBrains</a> IDEs. Amazon Q Developer has knowledge of your AWS account resources and can help understand your costs.</p> 
<div class="wp-caption aligncenter" id="attachment_22508" style="width: 634px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Amazon-Q-list-Lambda-functions.jpg"><img alt="Amazon Q list Lambda functions" class="size-full wp-image-22508" height="694" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Amazon-Q-list-Lambda-functions.jpg" width="624" /></a>
 <p class="wp-caption-text" id="caption-attachment-22508">Amazon Q list Lambda functions</p>
</div> 
<p>You can use Amazon Q Developer to <a href="https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/feature-dev.html" rel="noopener" target="_blank">develop code features</a> and transform code to <a href="https://aws.amazon.com/blogs/aws/upgrade-your-java-applications-with-amazon-q-code-transformation-preview/" rel="noopener" target="_blank">upgrade Java applications</a>. Amazon Q Developer also offers <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/amazon-q-inline-completions-command-line/" rel="noopener" target="_blank">inline completions in the command line</a>. For more information, see <a href="https://aws.amazon.com/blogs/machine-learning/reimagining-software-development-with-the-amazon-q-developer-agent/" rel="noopener" target="_blank">Reimagining software development with the Amazon Q Developer Agent</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22507" style="width: 634px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Amazon-Q-code-features.jpg"><img alt="Amazon Q code features" class="size-full wp-image-22507" height="396" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/Amazon-Q-code-features.jpg" width="624" /></a>
 <p class="wp-caption-text" id="caption-attachment-22507">Amazon Q code features</p>
</div> 
<p><a href="https://aws.amazon.com/bedrock/knowledge-bases/" rel="noopener" target="_blank">Knowledge Bases for Amazon Bedrock</a> now let you <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/knowledge-bases-amazon-bedrock-configure-guardrails/" rel="noopener" target="_blank">configure Guardrails</a>, <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/knowledge-bases-amazon-bedrock-configure-parameters/" rel="noopener" target="_blank">configure inference parameters</a>, and <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/knowledge-bases-amazon-bedrock-observability-logs/" rel="noopener" target="_blank">offers observability logs</a>.</p> 
<h2>Storage and data</h2> 
<p><a href="https://aws.amazon.com/s3/" rel="noopener" target="_blank">Amazon S3</a> <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/amazon-s3-no-charge-http-error-codes/" rel="noopener" target="_blank">no longer charges for several HTTP error codes</a> if initiated from outside your individual AWS account or AWS Organization.</p> 
<p>You can <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/detect-malware-object-uploads-amazon-s3-guardduty/" rel="noopener" target="_blank">automatically detect malware</a> in new object uploads to S3 with <a href="https://aws.amazon.com/guardduty/" rel="noopener" target="_blank">Amazon GuardDuty</a>.</p> 
<p><a href="https://aws.amazon.com/efs/" rel="noopener" target="_blank">Amazon Elastic File System (Amazon EFS)</a> <a href="Amazon%20EFS%20increases%20maximum%20per-client%20throughput%20to%201.5%20GiB/s" rel="noopener" target="_blank">now support up to 1.5 GiB/s of throughput per client</a>, a 3x increase over the previous limit of 500 MiB/s.</p> 
<p>Discover architectural patterns for real-time analytics using <a href="https://aws.amazon.com/kinesis/" rel="noopener" target="_blank">Amazon Kinesis</a> Data Streams in <a href="https://aws.amazon.com/blogs/big-data/architectural-patterns-for-real-time-analytics-using-amazon-kinesis-data-streams-part-1/" rel="noopener" target="_blank">part 1</a> and <a href="https://aws.amazon.com/blogs/big-data/architectural-patterns-for-real-time-analytics-using-amazon-kinesis-data-streams-part-2-ai-applications/" rel="noopener" target="_blank">part 2</a> and see how to <a href="https://aws.amazon.com/blogs/big-data/optimize-write-throughput-for-amazon-kinesis-data-streams/" rel="noopener" target="_blank">optimize write throughput</a>.</p> 
<h2>Amazon API Gateway</h2> 
<p><a href="https://aws.amazon.com/api-gateway/" rel="noopener" target="_blank">Amazon API Gateway</a> now allows you to <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/amazon-api-gateway-integration-timeout-limit-29-seconds/" rel="noopener" target="_blank">increase the integration timeout</a> beyond the prior limit of 29 seconds. You can raise the integration timeout for Regional and private REST APIs, but this might require a reduction in your account-level throttle quota limit. This launch can help with workloads that require longer timeouts, such as Generative AI use cases with Large Language Models (LLMs).</p> 
<p>You can also now use <a href="https://aws.amazon.com/about-aws/whats-new/2024/06/amazon-api-gateway-apis-amazon-verified-permissions/" rel="noopener" target="_blank">Amazon Verified Permissions to secure API Gateway</a> REST APIs when using an Open ID connect (OIDC) compliant identity provider. You can now control access based on user attributes and group memberships, without writing code.</p> 
<h2>AWS AppSync</h2> 
<p>You can now invoke your <a href="https://aws.amazon.com/appsync/" rel="noopener" target="_blank">AWS AppSync</a> data sources <a href="https://aws.amazon.com/about-aws/whats-new/2024/05/aws-appsync-events-asynchronous-lambda-function-invocations/" rel="noopener" target="_blank">in an event-driven manner</a>. Previously, you could only invoke Lambda functions synchronously from AWS AppSync. AWS AppSync can now trigger Lambda functions in Event mode, asynchronously decoupling the API response from the Lambda invocation, which helps with long-running operations.</p> 
<p>AWS AppSync now <a href="https://aws.amazon.com/about-aws/whats-new/2024/04/aws-appsync-application-headers-lambda-authorizer-functions/" rel="noopener" target="_blank">passes application request headers</a> to Lambda custom authorizer functions. You can make authorization decisions based on the value of the authorization header, and the value of other headers that were sent with the request from the application client.</p> 
<p>Learn <a href="https://aws.amazon.com/blogs/mobile/best-practices-for-aws-appsync-graphql-apis/" rel="noopener" target="_blank">best practices for AWS AppSync GraphQL APIs</a>. See how to how to optimize the security, performance, coding standards, and deployment of your AWS AppSync API. AWS AppSync also has <a href="https://aws.amazon.com/about-aws/whats-new/2024/04/aws-appsync-increases-service-quota-adds-subscription/" rel="noopener" target="_blank">increase quotas</a>, and <a href="https://aws.amazon.com/about-aws/whats-new/2024/02/aws-appsync-amazon-cloudwatch-metrics-enhanced-monitoring/" rel="noopener" target="_blank">new metrics</a></p> 
<h2>AWS Amplify</h2> 
<p><a href="https://aws.amazon.com/amplify/" rel="noopener" target="_blank">AWS Amplify</a> Gen 2 is <a href="https://aws.amazon.com/blogs/mobile/amplify-gen2-ga/" rel="noopener" target="_blank">now generally available</a>. This now provides a code-first developer experience for building full-stack apps using TypeScript. Amplify Gen 2 allows you to express app requirements like the data models, business logic, and authorization rules in TypeScript.</p> 
<div class="wp-caption aligncenter" id="attachment_22506" style="width: 610px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/AWS-Amplify-Gen2.gif"><img alt="AWS Amplify Gen2" class="size-full wp-image-22506" height="374" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/AWS-Amplify-Gen2.gif" width="600" /></a>
 <p class="wp-caption-text" id="caption-attachment-22506">AWS Amplify Gen2</p>
</div> 
<p>Amplify has a <a href="https://aws.amazon.com/blogs/mobile/amplify-storage-now-with-fullstack-typescript-powered-by-amazon-s3/" rel="noopener" target="_blank">new experience for file storage</a>. This <a href="https://aws.amazon.com/blogs/mobile/amplify-functions-create-serverless-functions-using-typescript-powered-by-aws-lambda/" rel="noopener" target="_blank">post</a> explores using Lambda to create serverless functions for Amplify using TypeScript. There are also new <a href="https://aws.amazon.com/blogs/mobile/team-workflows-amplify/" rel="noopener" target="_blank">team environment workflows</a>.</p> 
<h2>Serverless blog posts</h2> 
<h3>April</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/architecting-for-disaster-recovery-on-aws-outposts-racks-with-aws-elastic-disaster-recovery/" rel="noopener" target="_blank">Architecting for Disaster Recovery on AWS Outposts Racks with AWS Elastic Disaster Recovery</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/accelerating-workflow-development-with-the-teststate-api-in-aws-step-functions/" rel="noopener" target="_blank">Accelerating workflow development with the TestState API in AWS Step Functions</a></li> 
</ul> 
<h3>May</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/running-code-after-returning-a-response-from-an-aws-lambda-function/" rel="noopener" target="_blank">Running code after returning a response from an AWS Lambda function</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/using-the-circuit-breaker-pattern-with-aws-lambda-extensions-and-amazon-dynamodb/" rel="noopener" target="_blank">Using the circuit-breaker pattern with AWS Lambda extensions and Amazon DynamoDB</a></li> 
</ul> 
<h3>June</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/securing-amazon-ecs-workloads-on-aws-fargate-with-customer-managed-keys/" rel="noopener" target="_blank">Securing Amazon ECS workloads on AWS Fargate with customer managed keys</a></li> 
</ul> 
<h2>Serverless container blog posts</h2> 
<h3>April</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/unlocking-aws-fargate-feature-for-attaching-amazon-ebs-volumes-to-ecs-tasks/" rel="noopener" target="_blank">Unlocking AWS Fargate feature for attaching Amazon EBS Volumes to ECS Tasks</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/dynamically-create-repositories-upon-image-push-to-amazon-ecr/" rel="noopener" target="_blank">Dynamically create repositories upon image push to Amazon ECR</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/applying-generative-ai-to-cve-remediation-early-vulnerability-patching-in-continuous-integration-pipelines/" rel="noopener" target="_blank">Applying Generative AI to CVE remediation – early vulnerability patching in Continuous Integration Pipelines</a></li> 
</ul> 
<h3>May</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/windows-containers-on-aws-fargate-launch-time-improvements/" rel="noopener" target="_blank">Windows Containers on AWS Fargate: Launch time improvements</a></li> 
</ul> 
<h3>June</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/proactive-scaling-of-amazon-ecs-services-using-amazon-ecs-service-connect-metrics/" rel="noopener" target="_blank">Proactive scaling of Amazon ECS services using Amazon ECS Service Connect Metrics</a></li> 
</ul> 
<h2>Serverless Office Hours</h2> 
<div class="wp-caption aligncenter" id="attachment_22505" style="width: 634px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/SOH2024Q2.png"><img alt="Serverless Office Hours" class="size-full wp-image-22505" height="402" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/SOH2024Q2.png" width="624" /></a>
 <p class="wp-caption-text" id="caption-attachment-22505">Serverless Office Hours</p>
</div> 
<p>April</p> 
<ul> 
 <li>Apr 2 – <a href="https://www.youtube.com/watch?v=jcktUgozJj8" rel="noopener" target="_blank">Building Serverless Applications with Terraform</a></li> 
 <li>Apr 9 – <a href="https://www.youtube.com/watch?v=UBvChiIrww0" rel="noopener" target="_blank">Developing with Wing Cloud</a></li> 
 <li>Apr 16 – <a href="https://www.youtube.com/watch?v=qerfsVEXyps" rel="noopener" target="_blank">Combining serverless messaging services</a></li> 
 <li>Apr 23 – <a href="https://www.youtube.com/watch?v=baBTMAXNS50" rel="noopener" target="_blank">Real-time web and mobile backends</a></li> 
 <li>Apr 30 – <a href="https://www.youtube.com/watch?v=GTtfUZbGUrk" rel="noopener" target="_blank">Connecting Confluent to AWS</a></li> 
</ul> 
<p>May</p> 
<ul> 
 <li>May 7 – <a href="https://www.youtube.com/watch?v=2QYlxx13j5A" rel="noopener" target="_blank">Develop and test locally with LocalStack</a></li> 
 <li>May 14 – <a href="https://www.youtube.com/watch?v=D1_ygMC-roc" rel="noopener" target="_blank">Building a personalized GenAI webapp</a></li> 
 <li>May 21 – <a href="https://www.youtube.com/watch?v=jV0tIqS2_Q4" rel="noopener" target="_blank">Serverless GenAI using Bedrock Claude 3</a></li> 
 <li>May 28 – <a href="https://www.youtube.com/watch?v=Lus02Lv-nA8" rel="noopener" target="_blank">Serverless Platform Engineering</a></li> 
</ul> 
<p>June</p> 
<ul> 
 <li>June 4 – <a href="https://www.youtube.com/watch?v=xhNJ0cXG3O8" rel="noopener" target="_blank">Simplifying serverless with the CDK</a></li> 
 <li>June 11 – <a href="https://www.youtube.com/watch?v=1Dk4AWzzm-s" rel="noopener" target="_blank">Learn Serverless with Educloud Academy</a></li> 
 <li>June 18 – <a href="https://www.youtube.com/watch?v=-qgIhz8r-m4" rel="noopener" target="_blank">Integrating time-series databases</a></li> 
 <li>June 25 – <a href="https://www.youtube.com/watch?v=A_lRY3W5V2E" rel="noopener" target="_blank">Deploy frontends with the CloudFront Hosting Toolkit</a></li> 
</ul> 
<h2>Containers from the Couch</h2> 
<div class="wp-caption aligncenter" id="attachment_22504" style="width: 478px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/CFTC.png"><img alt="Containers from the Couch" class="size-full wp-image-22504" height="276" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/CFTC.png" width="468" /></a>
 <p class="wp-caption-text" id="caption-attachment-22504">Containers from the Couch</p>
</div> 
<p>April</p> 
<ul> 
 <li>Apr 11 – <a href="https://www.youtube.com/watch?v=Che17VtPaFk" rel="noopener" target="_blank">Using Amazon Q to build and operate your ECS workloads</a></li> 
 <li>April 25 <a href="https://www.youtube.com/watch?v=9ztE-w1rmcA" rel="noopener" target="_blank">Containers in AWS Lambda</a></li> 
</ul> 
<p>May</p> 
<ul> 
 <li>May 9 – <a href="https://www.youtube.com/watch?v=EN6mlTX71Ts" rel="noopener" target="_blank">OPA on AWS</a></li> 
</ul> 
<h2>FooBar Serverless</h2> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/FooBarServerless2024Q2.png"><img alt="" class="aligncenter size-full wp-image-22503" height="276" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/07/02/FooBarServerless2024Q2.png" width="468" /></a></p> 
<h3>April</h3> 
<ul> 
 <li>Apr 4 – <a href="https://www.youtube.com/watch?v=UN3_abQ_AvY" rel="noopener" target="_blank">How to integrate with any service or manual processes with Step Functions?</a></li> 
 <li>Apr 11 – <a href="https://www.youtube.com/watch?v=He-CHl2tlgo" rel="noopener" target="_blank">Automating video dubbing with AWS Step Functions and Artificial Intelligence</a></li> 
 <li>Apr 18 – <a href="https://www.youtube.com/watch?v=dQWIvM6d-2E" rel="noopener" target="_blank">The Future of Solutions Architect: How Generative AI will impact their work?</a></li> 
 <li>Apr 25 – <a href="https://www.youtube.com/watch?v=-SkiwLUnNzQ" rel="noopener" target="_blank">Unveiling the Role of AWS Solutions Architect</a></li> 
</ul> 
<h3>February</h3> 
<ul> 
 <li>May 2 – <a href="https://www.youtube.com/watch?v=lDEbFPKGozA" rel="noopener" target="_blank">Understanding the SAGA pattern with AWS Step Functions – With Demo</a></li> 
 <li>May 9 – <a href="https://www.youtube.com/watch?v=GzjMFOlwIvk" rel="noopener" target="_blank">Working in the cloud – New series!</a></li> 
 <li>May 16 – <a href="https://www.youtube.com/watch?v=0EXGfdt_ZqQ" rel="noopener" target="_blank">What does a Software Engineer in the Cloud actually do? | Working in the cloud</a></li> 
 <li>May 23 – <a href="https://www.youtube.com/watch?v=NCsD_OqFq-w" rel="noopener" target="_blank">How did you get your first job working with cloud computing? | Working in the cloud</a></li> 
 <li>May 30 – <a href="https://youtube.com/watch?v=_jDtSPrBESo" rel="noopener" target="_blank">From Junior Developer to Cloud Expert | Working in the cloud</a></li> 
</ul> 
<h3>June</h3> 
<ul> 
 <li>Jun 6 – <a href="https://www.youtube.com/watch?v=eyosHp8J6og" rel="noopener" target="_blank">What is your cloud job about? | Working in the cloud</a></li> 
 <li>Jun 13 – <a href="https://www.youtube.com/watch?v=leuLuyYJ3Xg" rel="noopener" target="_blank">Journey to the Cloud | Working in the cloud</a></li> 
 <li>June 27 – <a href="https://www.youtube.com/watch?v=btJGIcUVvVQ" rel="noopener" target="_blank">Pathways to Cloud Excellence: Insights from Top Industry Experts | Working in the cloud</a></li> 
</ul> 
<h2>Still looking for more?</h2> 
<p>The&nbsp;<a href="http://aws.amazon.com/serverless" rel="noopener" target="_blank">Serverless landing page</a>&nbsp;has more information. The&nbsp;<a href="https://aws.amazon.com/lambda/resources/?aws-lambda-resources-blog.sort-by=item.additionalFields.createdDate&amp;aws-lambda-resources-blog.sort-order=desc" rel="noopener" target="_blank">Lambda resources page</a>&nbsp;contains case studies, webinars, whitepapers, customer stories, reference architectures, and even more Getting Started tutorials.</p> 
<p>You can also&nbsp;follow the Serverless Developer Advocacy team on X (formerly Twitter)&nbsp;to see the latest news, follow conversations, and interact with the team.</p> 
<ul> 
 <li>Eric Johnson:&nbsp;<a href="https://twitter.com/edjgeek" rel="noopener" target="_blank">@edjgeek</a></li> 
 <li>Julian Wood:&nbsp;<a href="https://twitter.com/julian_wood" rel="noopener" target="_blank">@julian_wood</a></li> 
 <li>Marcia Villalba:&nbsp;<a href="https://twitter.com/mavi888uy/" rel="noopener" target="_blank">@mavi888uy</a></li> 
 <li>Olly Pomeroy <a href="https://www.linkedin.com/in/oliver-p/" rel="noopener" target="_blank">@oliver-p</a></li> 
 <li>Romain Jourdan: <a href="https://x.com/rjourdan_net" rel="noopener" target="_blank">@rjourdan_net</a></li> 
</ul> 
<p>And finally, visit the <a href="http://serverlessland.com/" rel="noopener" target="_blank">Serverless Land</a> and <a href="http://containersonaws.com/" rel="noopener" target="_blank">Containers on AWS</a> websites for all your serverless and serverless container needs.</p>
