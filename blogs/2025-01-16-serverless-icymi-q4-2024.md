---
title: "Serverless ICYMI Q4 2024"
url: "https://aws.amazon.com/blogs/compute/serverless-icymi-q4-2024/"
date: "Thu, 16 Jan 2025 21:29:37 +0000"
author: "Eric Johnson"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p>Welcome to the 27<sup>th</sup> edition of the AWS Serverless ICYMI (in case you missed it) quarterly recap. At the end of a quarter, we share the most recent product launches, feature enhancements, blog posts, webinars, live streams, and other interesting things that you might have missed!</p> 
<p>In case you missed our last ICYMI, check out what happened in Q2&nbsp;<a href="https://aws.amazon.com/blogs/compute/serverless-icymi-q2-2024/" rel="noopener" target="_blank">here</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_23222" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-1-1.png"><img alt="Calendar showing October through December 2024" class="wp-image-23222" height="216" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-1-1.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23222">2024 Q4 calender</p>
</div> 
<h2>Serverless at re:Invent 2024</h2> 
<p>AWS re:Invent 2024 had 60,000 in-person attendees and 400,000 online viewers for the keynotes. The conference delivered 1,900 sessions from 3,500 speakers and included 546 AWS service and feature announcements.</p> 
<p>The serverless content consisted of two tracks: Serverless (SVS) and App Integration (API). These tracks included 70 unique sessions and attracted nearly 11,000 attendees. <a href="https://catalog.workshops.aws/serverlesspresso/en-US">Serverlesspresso</a>, the coffee shop powered by serverless technology, operated in two locations during the event: the Expo Hall and the certification lounge.</p> 
<div class="wp-caption aligncenter" id="attachment_23224" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-2-1.png"><img alt="Crowd of people standing around the AWS reI:nvent expo hall waiting to order coffee at the Serverlesspresso booth." class="wp-image-23224" height="350" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-2-1.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23224">Serverlesspresso booth in the expo hall</p>
</div> 
<p>Videos are available on <a href="https://www.youtube.com/watch?v=WquDOzxGDCQ&amp;list=PLJo-rJlep0ECCB8xQegq2YRLNZOztV6Yf">Serverless Land YouTube</a>.</p> 
<h2>AWS Lambda and Amazon Elastic Container Service (Amazon ECS) 10-year anniversary.</h2> 
<p>AWS marked significant milestones in serverless computing, celebrating 10 years of <a href="https://aws.amazon.co/lambda">AWS Lambda</a> and <a href="https://aws.amazon.com/ecs">Amazon ECS</a>. Lambda now serves over 1.5 million monthly customers and processes tens of trillions of requests each month. Amazon ECS launches more than 2.4 billion container tasks weekly and is used by over 65% of new AWS container customers.</p> 
<p>AWS is commemorating this anniversary with insights from AWS Serverless Heroes, product leads, principal engineers, and AWS leadership sharing their perspectives on serverless evolution and future directions. These stories and insights are available at <a href="https://aws.amazon.com/serverless/10th-anniversary/">https://aws.amazon.com/serverless/10th-anniversary/</a>.</p> 
<h2>AWS Lambda</h2> 
<p>The AWS Lambda team has spent a significant amount of time improving the Lambda development experience. Several enhancements have been made in the console as well as the local development experience.</p> 
<div class="wp-caption aligncenter" id="attachment_23225" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-3-2.png"><img alt="Screen capture of the new AWS Lambda console with Code-OSS" class="wp-image-23225" height="371" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-3-2.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23225">Code-OSS as the new AWS Lambda inline editor</p>
</div> 
<p>Lambda has launched a significant upgrade to its console by integrating Code-OSS, the open-source version of Visual Studio Code, delivering a familiar development experience directly in the cloud. The new Lambda Code Editor supports viewing larger function packages up to 50 MB, features a split-screen interface for simultaneous code editing and testing, and includes built-in <a href="https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/what-is.html">Amazon Q Developer</a> AI assistance for real-time coding suggestions. This enhancement comes at no additional cost and prioritizes accessibility with features like screen reader support and keyboard navigation. The update bridges the gap between cloud and local development by simplifying the process of downloading function code and AWS SAM templates, ultimately providing developers with a more streamlined and familiar serverless development experience. Watch <a href="https://youtu.be/fm1wg2U4sJU?si=c-yG6VEvl7dVHCwI" rel="noopener" target="_blank">the video</a> explaining the changes in detail.</p> 
<p>Additionally, the Lambda console enhances developer experience with two new features: a built-in <a href="https://aws.amazon.com/blogs/compute/simplifying-lambda-function-development-using-cloudwatch-logs-live-tail-and-metrics-insights/">CloudWatch Metrics Insights dashboard that surfaces key function metrics, and CloudWatch Logs Live Tail support</a> for real-time log streaming and analysis, enabling faster troubleshooting without leaving the Lambda environment.</p> 
<div class="wp-caption aligncenter" id="attachment_23230" style="width: 791px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-5-2.png"><img alt="Screen capture of the new top 10 functions in the new AWS Lambda console" class="wp-image-23230" height="228" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-5-2.png" width="781" /></a>
 <p class="wp-caption-text" id="caption-attachment-23230">Top 10 Functions</p>
</div> 
<p>Lambda now supports <a href="https://aws.amazon.com/blogs/developer/structured-logging-for-net-lambda/">native JSON structured logging for .NET managed runtime applications</a>, improving log searchability and analysis capabilities without requiring manual configuration of logging libraries.</p> 
<p>Lambda has expanded its runtime support by adding <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/aws-lambda-support-python-313/">Python 3.13</a> and <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/aws-lambda-support-nodejs-22/">Node.js 22</a> as both managed runtimes and container base images, providing access to the latest language features and ensuring long-term support through October 2029 and April 2027, respectively.</p> 
<p><a href="https://aws.amazon.com/blogs/aws/aws-lambda-snapstart-for-python-and-net-functions-is-now-generally-available/">Lambda SnapStart capability is now available for Python and .NET runtimes</a>, delivering sub-second startup performance for latency-sensitive applications by caching initialized execution environments.</p> 
<div class="wp-caption aligncenter" id="attachment_23231" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-6.png"><img alt="Diagram of how SnapStart works compared to not having SnapStart" class="wp-image-23231" height="283" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-6.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23231">SnapStart support comparison</p>
</div> 
<p>New <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/amazon-cloudwatch-metrics-aws-lambda-esms/">CloudWatch metrics for Lambda Event Source Mappings</a> provide enhanced visibility into event processing states for <a href="https://aws.amazon.com/sqs">Amazon Simple Queue Service (SQS)</a>, <a href="https://aws.amazon.com/kinesis">Amazon Kinesis</a>, and <a href="https://aws.amazon.com/dynamodb">Amazon DynamoDB</a> event sources, helping customers monitor and troubleshoot event processing issues.</p> 
<p>Lambda introduces <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/aws-lambda-provisioned-mode-kafka-esms/">Provisioned Mode for Kafka event source mappings</a>, allowing customers to optimize throughput by configuring dedicated event polling resources for applications with stringent performance requirements.</p> 
<p>Finally, Lambda introduces an enhanced <a href="https://aws.amazon.com/blogs/compute/introducing-an-enhanced-local-ide-experience-for-aws-lambda-developers/">local development experience through the AWS Toolkit</a> for Visual Studio Code, streamlining the serverless application development workflow. The update features a new Application Builder interface that guides developers through environment setup, offers sample applications, and provides quick-action buttons for common tasks like build, deploy, and invoke operations. Developers can now efficiently iterate on their code with features such as configurable build settings, step-through debugging, and the ability to sync local changes quickly to the cloud or perform full deployments. The toolkit integrates with <a href="https://aws.amazon.com/infrastructure-composer/">AWS Infrastructure Composer</a> for visual application building and includes comprehensive local testing capabilities with shareable test events. This enhancement simplifies the Lambda development process by enabling developers to author, test, debug, and deploy serverless applications without leaving their preferred IDE environment.</p> 
<div class="wp-caption aligncenter" id="attachment_23232" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-7.png"><img alt="Screen capture of the getting started experience for serverless in a local IDE" class="wp-image-23232" height="354" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-7.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23232">Local IDE getting started</p>
</div> 
<h2>Amazon ECS and AWS Fargate</h2> 
<p>AWS introduces <a href="https://aws.amazon.com/blogs/containers/optimize-compute-resources-on-amazon-ecs-with-predictive-scaling/" rel="noopener" target="_blank">Predictive Scaling for Amazon ECS Service Auto Scaling</a>, a new feature that uses machine learning algorithms to anticipate and prepare for demand surges. The feature complements existing reactive scaling methods by using ML algorithms trained on millions of data points to learn application-specific demand patterns. Operating in both Forecast Only and Forecast And Scale modes, the system requires a minimum of 24 hours of data and achieves optimal performance after two weeks of historical data collection.</p> 
<div class="wp-caption aligncenter" id="attachment_23245" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/Picture11-1.png"><img alt="Screen capture of creating a predictive policy" class="wp-image-23245" height="462" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/Picture11-1.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23245">Create a scaling policy with predictive scaling</p>
</div> 
<p>The solution particularly benefits applications with cyclical traffic patterns, recurring usage intervals, and long initialization times. Implementation begins through the Amazon ECS console, where users start in Forecast Only mode to validate predictions before transitioning to Forecast And Scale mode. The feature updates forecasts every 6 hours and can predict capacity needs up to 48 hours ahead, working alongside existing auto scaling policies to improve application availability while optimizing resource usage and costs. Users can configure and monitor the system through the Amazon ECS console, SDK, or CLI.</p> 
<p>AWS also enhances observability for containerized applications with <a href="https://aws.amazon.com/about-aws/whats-new/2024/10/enhanced-monitoring-applications-amazon-ecs-application-signals/">CloudWatch Application Signals for Amazon ECS</a>, adding infrastructure metrics correlation to existing traces and logs monitoring, enabling operators to identify and resolve performance issues across their application stack.</p> 
<p>Amazon ECS adds <a href="https://aws.amazon.com/blogs/containers/improving-deployment-visibility-for-amazon-ecs-services/">service revision and deployment history tracking</a>, allowing customers to monitor changes, track ongoing deployments, and debug deployment failures for long-running applications deployed after October 25, 2024.</p> 
<div class="wp-caption aligncenter" id="attachment_23233" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-8.png"><img alt="A graph explaining the flow for service order and history" class="wp-image-23233" height="291" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-8.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23233">Service revisions and deployment history</p>
</div> 
<p>Amazon ECS expands testing capabilities by supporting network fault injection experiments on <a href="https://aws.amazon.com/fargate/">AWS Fargate</a> through <a href="https://aws.amazon.com/fis/">AWS Fault Injection Service</a>, enabling developers to verify application resilience using six different types of fault injection actions, including network disruptions and resource stress testing.</p> 
<h2>Amazon EventBridge</h2> 
<p><a href="https://aws.amazon.com/eventbridge">Amazon EventBridge</a> announces significant performance improvements, <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/amazon-eventbridge-improvement-latency-event-buses/">reducing end-to-end latency by up to 94%</a> from 2,235ms to 129.33ms at P99, enabling faster event processing for time-sensitive applications like fraud detection and gaming.</p> 
<p>Amazon EventBridge and AWS Step Functions now <a href="https://aws.amazon.com/blogs/aws/securely-share-aws-resources-across-vpc-and-account-boundaries-with-privatelink-vpc-lattice-eventbridge-and-step-functions/">integrate with private APIs through AWS PrivateLink and Amazon VPC Lattice</a>, enabling secure connectivity between cloud and on-premises applications without custom networking code.</p> 
<div class="wp-caption aligncenter" id="attachment_23235" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-9-1.png"><img alt="Screen capture of the Amazon EventBridge create connection screen showing the new Private option" class="wp-image-23235" height="497" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-9-1.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23235">Connections to Private APIs</p>
</div> 
<p>EventBridge API destinations introduces <a href="https://aws.amazon.com/about-aws/whats-new/2024/12/amazon-eventbridge-api-oauth-token-refresh/">proactive OAuth token refresh for public and private authorization endpoints</a>, helping prevent delays and errors by automatically refreshing tokens before expiration.</p> 
<h2>AWS Step Functions</h2> 
<p><a href="https://aws.amazon.com/step-functions">AWS Step Functions</a> introduces the ability to <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/infrastructure-code-template-generation-aws-step-functions/">export workflows as CloudFormation or SAM templates directly from the AWS console</a>, enabling repeatable provisioning across accounts. Developers can export and customize templates from existing workflows, and use AWS Infrastructure Composer to visually connect workflows with other AWS resources.</p> 
<p>Step Functions also adds <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/aws-step-functions-variables-jsonata-transformations/">Variables and JSONata support</a> to enhance workflow development. Variables allow data assignment and reference between states, simplifying payload management, while <a href="https://jsonata.org/">JSONata</a> provides advanced data transformation capabilities, including date formatting and mathematical operations. These features reduce the need for custom code and intermediate states, making it easier to build distributed serverless applications. Watch the <a href="https://youtu.be/aoKt7Aw2a1I?si=R6kVVlFVmEELNv2k" rel="noopener" target="_blank">in depth video</a> to learn more.</p> 
<div class="wp-caption aligncenter" id="attachment_23237" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-10-1.png"><img alt="Screen capture of AWS Step Function workflow studio using JSONata and variables in an example" class="wp-image-23237" height="283" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-10-1.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23237">JSONata and variables</p>
</div> 
<h2>Amazon Kinesis</h2> 
<p>Amazon Kinesis introduces significant updates to its client libraries. The <a href="https://aws.amazon.com/blogs/big-data/reduce-your-compute-costs-for-stream-processing-applications-with-kinesis-client-library-3-0/">new Kinesis Client Library (KCL) 3.0 reduces compute costs by up to 33%</a> through enhanced load balancing, while the <a href="https://aws.amazon.com/about-aws/whats-new/2024/12/kinesis-producer-library-aws-sdk-java-2-x/">Kinesis Producer Library (KPL) 1.0 improves performance and security</a>. Both libraries now support <a href="https://github.com/aws/aws-sdk-java-v2">AWS SDK for Java 2.x</a> and eliminate dependencies on SDK for Java 1.x, enabling seamless upgrades without requiring application code changes.</p> 
<div class="wp-caption aligncenter" id="attachment_23238" style="width: 790px;">
 <img alt="Screen capture of CPU usage metrics" class="wp-image-23238" height="565" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-11-1.png" width="780" />
 <p class="wp-caption-text" id="caption-attachment-23238">KCL 3.0 metrics</p>
</div> 
<h2>Amazon MQ</h2> 
<p><a href="https://aws.amazon.com/amazon-mq">Amazon MQ</a> adds <a href="https://aws.amazon.com/about-aws/whats-new/2024/12/amazon-mq-aws-privatelink/">support for AWS PrivateLink</a>, enabling customers to access Amazon MQ API endpoints directly from their VPC through <a href="https://docs.aws.amazon.com/vpc/latest/privatelink/create-interface-endpoint.html">interface VPC endpoints</a>, eliminating the need for internet access and providing enhanced security through AWS’s internal network infrastructure.</p> 
<h2>Amazon Finch</h2> 
<p>AWS announces <a href="https://aws.amazon.com/about-aws/whats-new/2024/10/finch-linux-container-development-platform/">general availability of Linux support</a> for <a href="https://runfinch.com/docs/managing-finch/linux/installation/#generic">Finch</a>, an open source container development tool that simplifies building, running, and publishing Linux containers across all major operating systems. The release includes support for the Finch Daemon with Docker API compatibility and is available through RPM packages for Amazon Linux 2 and Amazon Linux 2023.</p> 
<h2>Amazon Simple Queue Service (SQS)</h2> 
<p><a href="https://aws.amazon.com/sqs">Amazon SQS</a> increases the in-flight message limit for <a href="https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-fifo-queues.html">FIFO queues</a> from 20,000 to 120,000 messages, enabling higher concurrent message processing. This enhancement allows customers to scale their receivers and process up to six times more messages simultaneously, provided they have sufficient publish throughput.</p> 
<h2>Amazon Managed Streaming for Apache Kafka(Amazon MSK)</h2> 
<p><a href="https://aws.amazon.com/msk">Amazon MSK</a> now introduces Managed Streaming for Apache Flink <a href="https://aws.amazon.com/blogs/big-data/build-up-to-date-generative-ai-applications-with-real-time-vector-embedding-blueprints-for-amazon-msk/">blueprints to simplify real-time AI application development</a>. The service enables vector-embedding generation through <a href="https://aws.amazon.com/bedrock">Amazon Bedrock</a>, streamlining the integration of streaming data with generative AI models. Using a straightforward configuration process, users can generate and index vector embeddings in <a href="https://aws.amazon.com/opensearch-service/">Amazon OpenSearch</a>, while leveraging <a href="https://www.langchain.com/">LangChain’s</a> data chunking capabilities for enhanced data retrieval efficiency. The service handles all integration aspects between MSK, embedding models, and Amazon OpenSearch vector stores.</p> 
<h2>AWS Amplify</h2> 
<p><a href="https://aws.amazon.com/amplify">AWS Amplify</a> launches the <a href="https://aws.amazon.com/blogs/mobile/build-fullstack-ai-apps-in-minutes-with-the-new-amplify-ai-kit/">Amplify AI kit for Amazon Bedrock</a>, providing fullstack developers with tools to integrate AI capabilities into web applications. The kit includes a customizable React UI component, secure Bedrock access, and context-sharing features, enabling developers to implement chat, search, and summarization functionalities without machine learning expertise.</p> 
<h2>AWS AppSync</h2> 
<p><a href="https://aws.amazon.com/appsync/">AWS AppSync</a> launches <a href="https://aws.amazon.com/blogs/mobile/announcing-aws-appsync-events-serverless-websocket-apis/">AppSync Events</a>, enabling developers to broadcast real-time data to multiple subscribers through serverless WebSocket APIs. The service eliminates the need to build and manage WebSocket infrastructure while providing secure, scalable event broadcasting capabilities. Developers can create APIs that automatically scale and integrate with services like Amazon EventBridge. The system supports features such as channel namespaces, event handlers, and multiple authorization modes, and is available in all regions where AWS AppSync operates. Users only pay for API operations and real-time connection minutes used.</p> 
<div class="wp-caption aligncenter" id="attachment_23239" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-12-1.png"><img alt="Screen capture from the AWS AppSync console to create a new Event API." class="wp-image-23239" height="382" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-12-1.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23239">Creating an AppSunc Event API</p>
</div> 
<h2>Amazon API Gateway</h2> 
<p><a href="https://aws.amazon.com/api-gateway">Amazon API Gateway</a> released a significant enhancement to Amazon API Gateway, enabling customers to manage private REST APIs using <a href="https://aws.amazon.com/about-aws/whats-new/2024/11/amazon-api-gateway-custom-domain-name-private-rest-apis/">custom private DNS names</a>. This highly requested feature allows API providers to use user-friendly domain names like private.example.com, while maintaining TLS encryption for security. The implementation process involves creating a private custom domain, configuring certificates through <a href="https://aws.amazon.com/certificate-manager/">AWS Certificate Manager</a> (ACM), mapping private APIs, and setting resource policies. The feature supports cross-account sharing through <a href="https://aws.amazon.com/ram/">AWS Resource Access Manager</a> (AWS RAM) and is now available in all AWS Regions, including AWS GovCloud (US).</p> 
<h2>Serverless blog posts</h2> 
<h2>October</h2> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/designing-serverless-integration-patterns-for-large-language-models-llms/">Designing Serverless Integration Patterns for Large Language Models (LLMs)</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/simplifying-lambda-function-development-using-cloudwatch-logs-live-tail-and-metrics-insights/">Simplifying Lambda function development using CloudWatch Logs Live Tail and Metrics Insights</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-an-enhanced-in-console-editing-experience-for-aws-lambda/">Introducing an enhanced in-console editing experience for AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-an-enhanced-local-ide-experience-for-aws-lambda-developers/">Introducing an enhanced local IDE experience for AWS Lambda developers</a></li> 
</ul> 
<h2>November</h2> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/python-3-13-runtime-now-available-in-aws-lambda/">Python 3.13 runtime now available in AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/the-serverless-attendees-guide-to-aws-reinvent-2024/">The serverless attendee’s guide to AWS re:Invent 2024</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/serverless-containers-at-aws-reinvent-2024/">Serverless containers at AWS re:Invent 2024</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/implementing-custom-domain-names-for-private-endpoints-with-amazon-api-gateway/">Implementing custom domain names for private endpoints with Amazon API Gateway</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/node-js-22-runtime-now-available-in-aws-lambda/">Node.js 22 runtime now available in AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-new-event-source-mapping-esm-metrics-for-aws-lambda/">Introducing new Event Source Mapping (ESM) metrics for AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/how-infinitium-reduced-fraud-detection-time-by-95-with-amazon-ecs-and-aws-fargate-on-aws-graviton/">How Infinitium reduced fraud detection time by 95% with Amazon ECS and AWS Fargate on AWS Graviton</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/improving-deployment-visibility-for-amazon-ecs-services/">Improving deployment visibility for Amazon ECS services</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/simplifying-developer-experience-with-variables-and-jsonata-in-aws-step-functions/">Simplifying developer experience with variables and JSONata in AWS Step Functions</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/automating-event-validation-with-amazon-eventbridge-schema-discovery/">Automating event validation with Amazon EventBridge Schema Discovery</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/implementing-transactions-using-jms2-0-in-amazon-mq-for-activemq/">Implementing transactions using JMS2.0 in Amazon MQ for ActiveMQ</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/optimize-compute-resources-on-amazon-ecs-with-predictive-scaling/">Optimize compute resources on Amazon ECS with Predictive Scaling</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-provisioned-mode-for-kafka-event-source-mappings-with-aws-lambda/">Introducing Provisioned Mode for Kafka Event Source Mappings with AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/transforming-istio-into-an-enterprise-ready-service-mesh-for-amazon-ecs/">Transforming Istio into an enterprise-ready service mesh for Amazon ECS</a></li> 
</ul> 
<h2>Serverless Office Hours</h2> 
<div class="wp-caption aligncenter" id="attachment_23240" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-13.png"><img alt="Image from YouTube from the latest four Serverless Office Hours" class="wp-image-23240" height="231" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/01/16/image-13.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-23240">Serverless office hours videos</p>
</div> 
<h3>October</h3> 
<ul> 
 <li>Oct 1 – <a href="https://www.youtube.com/live/lew3--SaD2A?si=5sFrEWmN029ONNip">Fullstack apps with Amplify Gen 2</a></li> 
 <li>Oct 8 – <a href="https://www.youtube.com/live/GRQkpe1sBFk?si=_i38b96yJhXFSmKL">Step Functions + containers</a></li> 
 <li>Oct 22 – <a href="https://www.youtube.com/live/uCSRG4q3psY?si=_FJU_Aum5RMhEvSF">GraphQL fun with AppSync</a></li> 
 <li>Oct 29 – <a href="https://www.youtube.com/live/cQUw-FYkpBY?si=fm7x7jahhaj7-oPj">Serverless testing with Pawel Zubkiewicz</a></li> 
</ul> 
<h3>November</h3> 
<ul> 
 <li>Nov 5 – <a href="https://www.youtube.com/live/ir_NfpX4-o8?si=UB_qPkCPRgx-eRCl">Stripe event destinations</a></li> 
 <li>Nov 12 – <a href="https://www.youtube.com/live/AJaJk9I94Kk?si=YjoHP5JKOlWFRrbd">10 years of Lambda &amp; ECS</a></li> 
 <li>Nov 19 – <a href="https://www.youtube.com/live/V4FpISXTi0o?si=msE64bf93ajGNoDS">Enhancing Lambda DevEx</a></li> 
 <li>Nov 25 – <a href="https://www.youtube.com/live/owL56oqbWEg?si=NAB4sUzKQvX2EaAi">pre:Invent 2024</a></li> 
</ul> 
<h2>Still looking for more?</h2> 
<p>The&nbsp;<a href="http://aws.amazon.com/serverless" rel="noopener" target="_blank">Serverless landing page</a>&nbsp;has more information. The&nbsp;<a href="https://aws.amazon.com/lambda/resources/?aws-lambda-resources-blog.sort-by=item.additionalFields.createdDate&amp;aws-lambda-resources-blog.sort-order=desc" rel="noopener" target="_blank">Lambda resources page</a>&nbsp;contains case studies, webinars, whitepapers, customer stories, reference architectures, and even more Getting Started tutorials.</p> 
<p>You can also&nbsp;follow the Serverless Developer Advocacy team on X (formerly Twitter)&nbsp;to see the latest news, follow conversations, and interact with the team.</p> 
<ul> 
 <li>Eric Johnson:&nbsp;<a href="https://twitter.com/edjgeek" rel="noopener" target="_blank">@edjgeek</a></li> 
 <li>Julian Wood:&nbsp;<a href="https://twitter.com/julian_wood" rel="noopener" target="_blank">@julian_wood</a></li> 
 <li>Marcia Villalba:&nbsp;<a href="https://twitter.com/mavi888uy/" rel="noopener" target="_blank">@mavi888uy</a></li> 
 <li>Romain Jourdan:&nbsp;<a href="https://x.com/rjourdan_net" rel="noopener" target="_blank">@rjourdan_net</a></li> 
</ul> 
<p>And finally, visit the&nbsp;<a href="http://serverlessland.com/" rel="noopener" target="_blank">Serverless Land</a>&nbsp; for all your serverless needs.</p>
