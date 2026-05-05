---
title: "Serverless ICYMI Q4 2023"
url: "https://aws.amazon.com/blogs/compute/serverless-icymi-q4-2023/"
date: "Tue, 09 Jan 2024 13:28:03 +0000"
author: "Eric Johnson"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p>Welcome to the 24th edition of the AWS Serverless ICYMI (in case you missed it) quarterly recap. Every quarter, we share all the most recent product launches, feature enhancements, blog posts, webinars, live streams, and other interesting things that you might have missed!</p> 
<p>In case you missed our last ICYMI, check out what happened last quarter&nbsp;<a href="https://aws.amazon.com/blogs/compute/serverless-icymi-q3-2023/" rel="noopener" target="_blank">here</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22063" style="width: 791px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.00.36 PM.png"><img alt="2023 Q4 Calendar" class="wp-image-22063" height="282" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.00.36 PM.png" width="781" /></a>
 <p class="wp-caption-text" id="caption-attachment-22063">2023 Q4 Calendar</p>
</div> 
<h2>ServerlessVideo</h2> 
<div class="wp-caption aligncenter" id="attachment_22064" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.02.24 PM.png"><img alt="ServerlessVideo at re:Invent 2024" class="wp-image-22064" height="645" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.02.24 PM.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-22064">ServerlessVideo at re:Invent 2024</p>
</div> 
<p>ServerlessVideo is a demo application built by the AWS Serverless Developer Advocacy team to stream live videos and also perform advanced post-video processing. It uses several AWS services including <a href="https://serverlessland.com/step-functions" rel="noopener" target="_blank">AWS Step Functions</a>, <a href="https://serverlessland.com/eventbridge" rel="noopener" target="_blank">Amazon EventBridge</a>, <a href="https://serverlessland.com/lambda" rel="noopener" target="_blank">AWS Lambda</a>, <a href="https://aws.amazon.com/ecs/" rel="noopener" target="_blank">Amazon ECS</a>, and <a href="https://aws.amazon.com/bedrock/" rel="noopener" target="_blank">Amazon Bedrock</a> in a serverless architecture that makes it fast, flexible, and cost-effective. Key features include an event-driven core with loosely coupled microservices that respond to events routed by EventBridge. Step Functions orchestrates using both Lambda and ECS for video processing to balance speed, scale, and cost. There is a flexible plugin-based architecture using Step Functions and EventBridge to integrate and manage multiple video processing workflows, which include GenAI.</p> 
<p>ServerlessVideo allows broadcasters to stream video to thousands of viewers using <a href="https://aws.amazon.com/ivs/" rel="noopener" target="_blank">Amazon IVS</a>. When a broadcast ends, a Step Functions workflow triggers a set of configured plugins to process the video, generating transcriptions, validating content, and more. The application incorporates various microservices to support live streaming, on-demand playback, transcoding, transcription, and events. Learn more about the project and watch videos from reinvent 2023 at <a href="https://video.serverlessland.com/" rel="noopener" target="_blank">video.serverlessland.com</a>.</p> 
<h2>AWS Lambda</h2> 
<p><a href="https://aws.amazon.com/lambda" rel="noopener" target="_blank">AWS Lambda</a> enabled <a href="https://aws.amazon.com/about-aws/whats-new/2023/10/aws-lambda-ipv6-outbound-connections-vpc/" rel="noopener" target="_blank">outbound IPv6 connections from VPC-connected Lambda functions</a>, providing virtually unlimited scale by removing IPv4 address constraints.</p> 
<p>The AWS Lambda and <a href="https://aws.amazon.com/serverless/sam" rel="noopener" target="_blank">AWS SAM</a> teams also added support for <a href="https://aws.amazon.com/about-aws/whats-new/2023/10/lambda-test-events-aws-sam-cli/" rel="noopener" target="_blank">sharing test events across teams using AWS SAM CLI</a> to improve collaboration when testing locally.</p> 
<p>AWS Lambda introduced <a href="https://docs.aws.amazon.com/lambda/latest/dg/foundation-iac.html" rel="noopener" target="_blank">integration</a> with <a href="https://aws.amazon.com/application-composer/" rel="noopener" target="_blank">AWS Application Composer</a>, allowing users to view and export Lambda function configuration details for infrastructure as code (IaC) workflows.</p> 
<p>AWS added <a href="https://aws.amazon.com/blogs/compute/introducing-advanced-logging-controls-for-aws-lambda-functions/" rel="noopener" target="_blank">advanced logging controls</a> enabling adjustable JSON-formatted logs, custom log levels, and configurable CloudWatch log destinations for easier debugging. AWS enabled <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/aws-lambda-troubleshoot-errors-timeouts-init-restore-phases/" rel="noopener" target="_blank">monitoring of errors and timeouts occurring during initialization and restore phases</a> in CloudWatch Logs as well, making troubleshooting easier.</p> 
<p>For Kafka event sources, AWS enabled <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/aws-lambda-failed-event-destinations-kafka-event-source-mappings/" rel="noopener" target="_blank">failed event destinations</a> to prevent functions stalling on failing batches by rerouting events to SQS, SNS, or S3. AWS also <a href="https://aws.amazon.com/blogs/compute/scaling-improvements-when-processing-apache-kafka-with-aws-lambda/" rel="noopener" target="_blank">enhanced Lambda auto scaling for Kafka event sources</a> in November to reach maximum throughput faster, reducing latency for workloads prone to large bursts of messages.</p> 
<p>AWS launched support for <a href="https://aws.amazon.com/blogs/compute/python-3-12-runtime-now-available-in-aws-lambda/" rel="noopener" target="_blank">Python 3.12</a> and <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/aws-lambda-support-java-21/" rel="noopener" target="_blank">Java 21</a> Lambda runtimes, providing updated libraries, smaller deployment sizes, and better AWS service integration. AWS also introduced a <a href="https://aws.amazon.com/about-aws/whats-new/2023/12/aws-lambda-connectivity-rds-proxy-console/" rel="noopener" target="_blank">simplified console workflow</a> to automate complex network configuration when connecting functions to Amazon RDS and RDS Proxy.</p> 
<p>Additionally in December, AWS <a href="https://aws.amazon.com/blogs/aws/aws-lambda-functions-now-scale-12-times-faster-when-handling-high-volume-requests/" rel="noopener" target="_blank">enabled faster individual Lambda function scaling</a> allowing each function to rapidly absorb traffic spikes by scaling up to 1000 concurrent executions every 10 seconds.</p> 
<h2>Amazon ECS and AWS Fargate</h2> 
<p>In Q4 of 2023, AWS introduced several new capabilities across its serverless container services including <a href="https://aws.amazon.com/ecs/" rel="noopener" target="_blank">Amazon ECS</a>, <a href="https://aws.amazon.com/fargate/" rel="noopener" target="_blank">AWS Fargate</a>, <a href="https://aws.amazon.com/apprunner/" rel="noopener" target="_blank">AWS App Runner</a>, and more. These features help improve application resilience, security, developer experience, and migration to modern containerized architectures.</p> 
<p>In October, Amazon ECS <a href="https://aws.amazon.com/about-aws/whats-new/2023/10/amazon-ecs-applications-resiliency-unpredictable-load-spikes/" rel="noopener" target="_blank">enhanced its task scheduling</a> to start healthy replacement tasks before terminating unhealthy ones during traffic spikes. This prevents going under capacity due to premature shutdowns. Additionally, App Runner launched <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/aws-app-runner-supports-ipv6-public-inbound-traffic/" rel="noopener" target="_blank">support for IPv6 traffic</a> via dual-stack endpoints to remove the need for address translation.</p> 
<p>In November, AWS Fargate enabled ECS tasks to <a href="https://docs.aws.amazon.com/AmazonECS/latest/userguide/container-considerations.html?trk=3d9bf291-787b-4280-bb00-c4a8e441a748&amp;sc_channel=el#fargate-tasks-soci-images" rel="noopener" target="_blank">selectively use SOCI lazy loading</a> for only large container images in a task instead of requiring it for all images. Amazon ECS also added <a href="https://docs.aws.amazon.com/AmazonECS/latest/APIReference/ECS_Idempotency.html" rel="noopener" target="_blank">idempotency support for task launches</a> to prevent duplicate instances on retries. <a href="https://aws.amazon.com/guardduty/" rel="noopener" target="_blank">Amazon GuardDuty</a> <a href="https://aws.amazon.com/blogs/aws/introducing-amazon-guardduty-ecs-runtime-monitoring-including-aws-fargate/" rel="noopener" target="_blank">expanded threat detection to Amazon ECS and Fargate</a> workloads which users can easily enable.</p> 
<p>Also in November, the open source <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/finch-generally-available-macos/" rel="noopener" target="_blank">Finch container tool for macOS</a> became generally available. <a href="https://runfinch.com/" rel="noopener" target="_blank">Finch</a> allows developers to build, run, and publish Linux containers locally. A new website provides tutorials and resources to help developers get started.</p> 
<p>Finally in December, <a href="https://docs.aws.amazon.com/migrationhub-orchestrator/latest/userguide/what-is-migrationhub-orchestrator.html" rel="noopener" target="_blank">AWS Migration Hub Orchestrator</a> added new capabilities for <a href="https://aws.amazon.com/blogs/modernizing-with-aws/containerize-asp-net-application-using-aws-migration-hub-orchestrator/" rel="noopener" target="_blank">replatforming applications to Amazon ECS using guided workflows</a>. App Runner also improved integration with Route 53 domains to <a href="https://aws.amazon.com/about-aws/whats-new/2023/10/aws-app-runner-improvements-custom-domains/" rel="noopener" target="_blank">automatically configure required records when associating custom domains</a>.</p> 
<h2>AWS Step Functions</h2> 
<p>In Q4 2023, <a href="https://aws.amazon.com/step-functions/" rel="noopener" target="_blank">AWS Step Functions</a> announced the <a href="https://aws.amazon.com/blogs/compute/introducing-aws-step-functions-redrive-a-new-way-to-restart-workflows/" rel="noopener" target="_blank">redrive capability for Standard Workflows</a>. This feature allows failed workflow executions to be redriven from the point of failure, skipping unnecessary steps and reducing costs. The redrive functionality provides an efficient way to handle errors that require longer investigation or external actions before resuming the workflow.</p> 
<p>Step Functions also launched support for <a href="https://aws.amazon.com/blogs/aws/external-endpoints-and-testing-of-task-states-now-available-in-aws-step-functions/" rel="noopener" target="_blank">HTTPS endpoints in AWS Step Functions</a>, enabling easier integration with external APIs and SaaS applications without needing custom code. Developers can now connect to third-party HTTP services directly within workflows. Additionally, AWS released a new <a href="https://aws.amazon.com/blogs/aws/external-endpoints-and-testing-of-task-states-now-available-in-aws-step-functions/" rel="noopener" target="_blank">test state capability that allows testing individual workflow states before full deployment</a>. This feature helps accelerate development by making it faster and simpler to validate data mappings and permissions configurations.</p> 
<p>AWS announced <a href="https://aws.amazon.com/blogs/aws/build-generative-ai-apps-using-aws-step-functions-and-amazon-bedrock/" rel="noopener" target="_blank">optimized integrations</a> between AWS Step Functions and <a href="https://aws.amazon.com/bedrock" rel="noopener" target="_blank">Amazon Bedrock</a> for orchestrating generative AI workloads. Two new API actions were added specifically for invoking Bedrock models and training jobs from workflows. These integrations simplify building prompt chaining and other techniques to create complex AI applications with foundation models.</p> 
<p>Finally, the Step Functions Workflow Studio is now <a href="https://aws.amazon.com/blogs/aws/aws-step-functions-workflow-studio-is-now-available-in-aws-application-composer/" rel="noopener" target="_blank">integrated</a> in the <a href="https://aws.amazon.com/application-composer/" rel="noopener" target="_blank">AWS Application Composer</a>. This unified builder allows developers to design workflows and define application resources across the full project lifecycle within a single interface.</p> 
<h2>Amazon EventBridge</h2> 
<p><a href="https://aws.amazon.com/eventbridge/" rel="noopener" target="_blank">Amazon EventBridge</a> announced support for <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/amazon-eventbridge-partner-integrations-adobe-stripe/" rel="noopener" target="_blank">new partner integrations</a> with Adobe and Stripe. These integrations enable routing events from the Adobe and Stripe platforms to over 20 AWS services. This makes it easier to build event-driven architectures to handle common use cases.</p> 
<h2>Amazon SNS</h2> 
<p>In Q4, <a href="https://aws.amazon.com/sns" rel="noopener" target="_blank">Amazon SNS</a> added <a href="https://aws.amazon.com/blogs/compute/archiving-and-replaying-messages-with-amazon-sns-fifo/" rel="noopener" target="_blank">native in-place message archiving for FIFO topics</a> to improve event stream durability by allowing retention policies and selective replay of messages without provisioning separate resources. Additional message filtering operators were also introduced including <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/amazon-sns-message-additional-filtering-operators/" rel="noopener" target="_blank">suffix matching, case-insensitive equality checks, and OR logic</a> for matching across properties to simplify routing logic implementation for publishers and subscribers. Finally, <a href="https://aws.amazon.com/about-aws/whats-new/2023/12/amazon-sns-configuring-delivery-status-logging-aws-cloudformation/" rel="noopener" target="_blank">delivery status logging was enabled through AWS CloudFormation</a>.</p> 
<h2>Amazon SQS</h2> 
<p><a href="https://aws.amazon.com/sqs" rel="noopener" target="_blank">Amazon SQS</a> has introduced several major new capabilities and updates. These improve visibility, throughput, and message handling for users. Specifically, Amazon SQS enabled <a href="https://aws.amazon.com/cloudtrail/" rel="noopener" target="_blank">AWS CloudTrail</a> <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/amazon-sqs-support-logging-data-events-aws-cloudtrail/" rel="noopener" target="_blank">logging of key SQS APIs</a>. This gives customers greater visibility into SQS activity. Additionally, SQS <a href="https://aws.amazon.com/about-aws/whats-new/2023/11/amazon-sqs-throughput-quota-fifo-high-throughput-mode/" rel="noopener" target="_blank">increased the throughput quota for the high throughput mode of FIFO queues</a>. This was significantly increased in certain Regions. It also boosted throughput in Asia Pacific Regions. Furthermore, Amazon SQS added <a href="https://aws.amazon.com/blogs/aws/announcing-throughput-increase-and-dead-letter-queue-redrive-support-for-amazon-sqs-fifo-queues/" rel="noopener" target="_blank">dead letter queue redrive support</a>. This allows you to redrive messages that failed and were sent to a dead letter queue (DLQ).</p> 
<h2>Serverless at AWS re:Invent</h2> 
<div class="wp-caption aligncenter" id="attachment_22065" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.04.24 PM.png"><img alt="Serverless videos from re:Invent" class="wp-image-22065" height="166" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.04.24 PM.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-22065">Serverless videos from re:Invent</p>
</div> 
<p>Visit the <a href="https://www.youtube.com/@ServerlessLand" rel="noopener" target="_blank">Serverless Land YouTube channel</a> to find a list of serverless and serverless container sessions from reinvent 2023. Hear from experts like Chris Munns and Julian Wood in their popular session, <em>Best practices for serverless developers</em>, or Nathan Peck and Jessica Deen in <em>Deploying multi-tenant SaaS applications on Amazon ECS and AWS Fargate.</em></p> 
<h2>EDA Day Nashville</h2> 
<div class="wp-caption aligncenter" id="attachment_22066" style="width: 790px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.05.53 PM.png"><img alt="EDA Day Nashville" class="wp-image-22066" height="269" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.05.53 PM.png" width="780" /></a>
 <p class="wp-caption-text" id="caption-attachment-22066">EDA Day Nashville</p>
</div> 
<p>The AWS Serverless Developer Advocacy team hosted an event-driven architecture (EDA) day conference on October 26, 2023 in Nashville, Tennessee. This inaugural GOTO EDA day convened over 200 attendees ranging from prominent EDA community members to AWS speakers and product managers. Attendees engaged in 13 sessions, two workshops, and panels covering EDA adoption best practices. The event built upon 2022 content by incorporating additional topics like messaging, containers, and machine learning. It also created opportunities for students and underrepresented groups in tech to participate. The full-day conference facilitated education, inspiration, and thoughtful discussion around event-driven architectural patterns and services on AWS.</p> 
<p>Videos from EDA Day are now available on the <a href="https://www.youtube.com/@ServerlessLand" rel="noopener" target="_blank">Serverless Land YouTube channel</a>.</p> 
<h2>Serverless blog posts</h2> 
<h3>October</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/filtering-events-in-amazon-eventbridge-with-wildcard-pattern-matching/" rel="noopener" target="_blank">Filtering events in Amazon EventBridge with wildcard pattern matching</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/enhancing-runtime-security-and-governance-with-the-aws-lambda-runtime-api-proxy-extension/" rel="noopener" target="_blank">Enhancing runtime security and governance with the AWS Lambda Runtime API proxy extension</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/archiving-and-replaying-messages-with-amazon-sns-fifo/" rel="noopener" target="_blank">Archiving and replaying messages with Amazon SNS FIFO</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/sending-and-receiving-webhooks-on-aws-innovate-with-event-notifications/" rel="noopener" target="_blank">Sending and receiving webhooks on AWS: Innovate with event notifications</a></li> 
</ul> 
<h3>November</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/orchestrating-dependent-file-uploads-with-aws-step-functions/" rel="noopener" target="_blank">Orchestrating dependent file uploads with AWS Step Functions</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-faster-polling-scale-up-for-aws-lambda-functions-configured-with-amazon-sqs/" rel="noopener" target="_blank">Introducing faster polling scale-up for AWS Lambda functions configured with Amazon SQS</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/scaling-improvements-when-processing-apache-kafka-with-aws-lambda/" rel="noopener" target="_blank">Scaling improvements when processing Apache Kafka with AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-the-amazon-linux-2023-runtime-for-aws-lambda/" rel="noopener" target="_blank">Introducing the Amazon Linux 2023 runtime for AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/enhanced-amazon-cloudwatch-metrics-for-amazon-eventbridge/" rel="noopener" target="_blank">Enhanced Amazon CloudWatch metrics for Amazon EventBridge</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/the-serverless-attendees-guide-to-aws-reinvent-2023/" rel="noopener" target="_blank">The serverless attendee’s guide to AWS re:Invent 2023</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-logging-support-for-amazon-eventbridge-pipes/" rel="noopener" target="_blank">Introducing logging support for Amazon EventBridge Pipes</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/converting-apache-kafka-events-from-avro-to-json-using-eventbridge-pipes/" rel="noopener" target="_blank">Converting Apache Kafka events from Avro to JSON using EventBridge Pipes</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/node-js-20-x-runtime-now-available-in-aws-lambda/" rel="noopener" target="_blank">Node.js 20.x runtime now available in AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/managing-aws-lambda-runtime-upgrades/" rel="noopener" target="_blank">Managing AWS Lambda runtime upgrades</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-aws-step-functions-redrive-a-new-way-to-restart-workflows/" rel="noopener" target="_blank">Introducing AWS Step Functions redrive to recover from failures more easily</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/triggering-aws-lambda-function-from-a-cross-account-amazon-managed-streaming-for-apache-kafka/" rel="noopener" target="_blank">Triggering AWS Lambda function from a cross-account Amazon Managed Streaming for Apache Kafka</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/aws-integrated-application-test-kit/" rel="noopener" target="_blank">Introducing the AWS Integrated Application Test Kit (IATK)</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-advanced-logging-controls-for-aws-lambda-functions/" rel="noopener" target="_blank">Introducing advanced logging controls for AWS Lambda functions</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-support-for-read-only-management-events-in-amazon-eventbridge/" rel="noopener" target="_blank">Introducing support for read-only management events in Amazon EventBridge</a></li> 
</ul> 
<h3>December</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/python-3-12-runtime-now-available-in-aws-lambda/" rel="noopener" target="_blank">Python 3.12 runtime now available in AWS Lambda</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-amazon-mq-cross-region-data-replication-for-activemq-brokers/" rel="noopener" target="_blank">Introducing Amazon MQ cross-Region data replication for ActiveMQ brokers</a></li> 
</ul> 
<h2>Serverless container blog posts</h2> 
<h3>October</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/start-spring-boot-applications-faster-on-aws-fargate-using-soci/" rel="noopener" target="_blank">Start Spring Boot applications faster on AWS Fargate using SOCI</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/pbs-speeds-deployment-and-reduces-costs-with-aws-fargate/" rel="noopener" target="_blank">PBS speeds deployment and reduces costs with AWS Fargate</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/scale-to-15000-tasks-in-a-single-amazon-elastic-container-service-ecs-cluster/" rel="noopener" target="_blank">Scale to 15,000+ tasks in a single Amazon Elastic Container Service (ECS) cluster</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/run-time-sensitive-workloads-on-ecs-fargate-with-clock-accuracy-tracking/" rel="noopener" target="_blank">Run time sensitive workloads on ECS Fargate with clock accuracy tracking</a></li> 
</ul> 
<h3>November</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/a-deep-dive-into-amazon-ecs-task-health-and-task-replacement/" rel="noopener" target="_blank">A deep dive into Amazon ECS task health and task replacement</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/securing-api-endpoints-using-amazon-api-gateway-and-amazon-vpc-lattice/" rel="noopener" target="_blank">Securing API endpoints using Amazon API Gateway and Amazon VPC Lattice</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/serverless-containers-at-aws-reinvent-2023/" rel="noopener" target="_blank">Serverless containers at AWS re:Invent 2023</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/migration-considerations-cloud-foundry-to-amazon-ecs-with-aws-fargate/" rel="noopener" target="_blank">Migration considerations – Cloud Foundry to Amazon ECS with AWS Fargate</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/build-generative-ai-apps-on-amazon-ecs-for-sagemaker-jumpstart/" rel="noopener" target="_blank">Build Generative AI apps on Amazon ECS for SageMaker JumpStart</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/how-smartsheet-optimized-cost-and-performance-with-aws-graviton-and-aws-fargate/" rel="noopener" target="_blank">How Smartsheet optimized cost and performance with AWS Graviton and AWS Fargate</a></li> 
</ul> 
<h3>December</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/aws-app-runner-improves-performance-for-image-based-deployments/" rel="noopener" target="_blank">AWS App Runner improves performance for image-based deployments</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/use-smb-storage-with-windows-containers-on-aws-fargate/" rel="noopener" target="_blank">Use SMB storage with Windows containers on AWS Fargate</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/a-deep-dive-into-resilience-and-availability-on-amazon-elastic-container-service/" rel="noopener" target="_blank">A deep dive into resilience and availability on Amazon Elastic Container Service</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/run-monte-carlo-simulations-at-scale-with-aws-step-functions-and-aws-fargate/" rel="noopener" target="_blank">Run Monte Carlo simulations at scale with AWS Step Functions and AWS Fargate</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/effective-use-amazon-ecs-lifecycle-events-with-amazon-cloudwatch-logs-insights/" rel="noopener" target="_blank">Effective use: Amazon ECS lifecycle events with Amazon CloudWatch Logs Insights</a></li> 
</ul> 
<h2>Serverless Office Hours</h2> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.07.20 PM.png"><img alt="Serverless office hours: Q4 videos" class="aligncenter wp-image-22067" height="506" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.07.20 PM.png" width="780" /></a></p> 
<h3>October</h3> 
<ul> 
 <li>Oct 3 – <a href="https://www.youtube.com/live/msncNOYwtoM?feature=shared" rel="noopener" target="_blank">Governance in depth for serverless apps</a></li> 
 <li>Oct 10 – <a href="https://www.youtube.com/live/1qtJ9hk4exE?feature=shared" rel="noopener" target="_blank">Serverless observability</a></li> 
 <li>Oct 17 – <a href="https://www.youtube.com/live/DxiEicDNoSM?feature=shared" rel="noopener" target="_blank">Super serverless tools with Lars Jacobsson</a></li> 
 <li>Oct 24 – <a href="https://www.youtube.com/live/jqiOY0UM_EI?feature=shared" rel="noopener" target="_blank">Building GenAI apps</a></li> 
 <li>Oct 31 – <a href="https://www.youtube.com/live/Uml4IyhQ6Hk?feature=shared" rel="noopener" target="_blank">Visually build AWS applications</a></li> 
</ul> 
<h3>November</h3> 
<ul> 
 <li>Nov 7 – <a href="https://www.youtube.com/live/mzDFXRWZphI?feature=shared" rel="noopener" target="_blank">Bring chaos into serverless</a></li> 
 <li>Nov 14 – <a href="https://www.youtube.com/live/2uvqHVwGlE4?feature=shared" rel="noopener" target="_blank">Ampt: Just write code!</a></li> 
 <li>Nov 21 – <a href="https://www.youtube.com/live/hNUDGh0W6h0?feature=shared" rel="noopener" target="_blank">pre:Invent 2023</a></li> 
</ul> 
<h3>December</h3> 
<ul> 
 <li>Dec 5 – <a href="https://www.youtube.com/live/j0B-OtBMRjM?feature=shared" rel="noopener" target="_blank">Step Functions: what’s new</a></li> 
 <li>Dec 19 – <a href="https://www.youtube.com/live/_gf4rxXfu9w?feature=shared" rel="noopener" target="_blank">2023 Year in review</a></li> 
</ul> 
<h2>Containers from the Couch</h2> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.09.21 PM.png"><img alt="Containers from the Couch" class="aligncenter wp-image-22068" height="473" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.09.21 PM.png" width="780" /></a></p> 
<h3>October</h3> 
<ul> 
 <li>Oct 12 – <a href="https://www.youtube.com/live/CZJPqk9WVFM?feature=shared" rel="noopener" target="_blank">Introducing ContainersOnAWS.com</a></li> 
 <li>Oct 26 – <a href="https://www.youtube.com/live/mM8GZXAxsZY?feature=shared" rel="noopener" target="_blank">Amazon ECS Console v2 updates</a></li> 
</ul> 
<h3>November</h3> 
<ul> 
 <li>Nov 9 – <a href="https://www.youtube.com/live/1glvMLqX8bg?feature=shared" rel="noopener" target="_blank">ECS Builder Series – John Mille (Sainsbury’s)</a></li> 
 <li>Nov 16 – <a href="https://www.youtube.com/live/JEEs-ZWt7GI?feature=shared" rel="noopener" target="_blank">Diving into Finch 1.0</a></li> 
</ul> 
<h3>December</h3> 
<ul> 
 <li>Dec 15 – <a href="https://www.youtube.com/live/MuT7xKZnF2Q?feature=shared" rel="noopener" target="_blank">Cost optimization on AWS Fargate</a></li> 
</ul> 
<h2>FooBar</h2> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.10.33 PM.png"><img alt="FooBar" class="aligncenter wp-image-22069" height="461" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/01/09/Screenshot-2024-01-09-at-12.10.33 PM.png" width="780" /></a></p> 
<h3>October</h3> 
<ul> 
 <li>Oct 5 – <a href="https://youtu.be/P9Lnf4GMUsI?feature=shared" rel="noopener" target="_blank">Build Applications with Bedrock and Lambda</a></li> 
 <li>Oct 12 – <a href="https://youtu.be/zhI8-Xxc9rY?feature=shared" rel="noopener" target="_blank">Kinesis Data Streams and Lambda in production – What to do when something fails</a></li> 
 <li>Oct 26 – <a href="https://youtu.be/n-2C5hWB1os?feature=shared" rel="noopener" target="_blank">Build applications with generative AI and Serverless – Amazon Bedrock and AWS Lambda Node.js</a></li> 
</ul> 
<h3>November</h3> 
<ul> 
 <li>Nov 2 – <a href="https://youtu.be/k2CTnIDFHu8?feature=shared" rel="noopener" target="_blank">Lambda response streaming | get faster responses from AWS Lambda</a></li> 
 <li>Nov 9 – <a href="https://youtu.be/NDtrk9Pm9w0?feature=shared" rel="noopener" target="_blank">Stream responses back from Bedrock using Lambda response streaming</a></li> 
</ul> 
<h3>December</h3> 
<ul> 
 <li>Dec 7 – <a href="https://youtu.be/Na8Orgzb2TM?feature=shared" rel="noopener" target="_blank">Build generative AI apps using AWS Step Functions and Amazon Bedrock</a></li> 
 <li>Dec 14 – <a href="https://youtu.be/AGrJsF3G_1E?feature=shared" rel="noopener" target="_blank">Test State API for Step Functions</a></li> 
 <li>Dec 21 – <a href="https://youtu.be/HtmIW566Vac?feature=shared" rel="noopener" target="_blank">Invoke external endpoints from AWS Step Functions</a></li> 
</ul> 
<h2>Still looking for more?</h2> 
<p>The&nbsp;<a href="http://aws.amazon.com/serverless" rel="noopener" target="_blank">Serverless landing page</a>&nbsp;has more information. The&nbsp;<a href="https://aws.amazon.com/lambda/resources/?aws-lambda-resources-blog.sort-by=item.additionalFields.createdDate&amp;aws-lambda-resources-blog.sort-order=desc" rel="noopener" target="_blank">Lambda resources page</a>&nbsp;contains case studies, webinars, whitepapers, customer stories, reference architectures, and even more Getting Started tutorials.</p> 
<p>You can also&nbsp;follow the Serverless Developer Advocacy team on Twitter&nbsp;to see the latest news, follow conversations, and interact with the team.</p> 
<table> 
 <tbody> 
  <tr> 
   <td style="vertical-align: top;"> 
    <ul> 
     <li>James Beswick:&nbsp;<a href="https://twitter.com/jbesw" rel="noopener" target="_blank">@jbesw</a></li> 
     <li>Eric Johnson:&nbsp;<a href="https://twitter.com/edjgeek" rel="noopener" target="_blank">@edjgeek</a></li> 
     <li>Ben Smith:&nbsp;<a href="https://twitter.com/benjamin_l_s" rel="noopener" target="_blank">@benjamin_l_s</a></li> 
     <li>Julian Wood:&nbsp;<a href="https://twitter.com/julian_wood" rel="noopener" target="_blank">@julian_wood</a></li> 
     <li>Marcia Villalba:&nbsp;<a href="https://twitter.com/mavi888uy/" rel="noopener" target="_blank">@mavi888uy</a></li> 
     <li>David Boyne:&nbsp;<a href="https://twitter.com/boyney123" rel="noopener" target="_blank">@boyney123</a></li> 
    </ul> </td> 
   <td style="vertical-align: top;"> 
    <ul> 
     <li>Jeramiah Dooley <a href="https://twitter.com/jdooley_clt" rel="noopener" target="_blank">@jdooley_clt</a></li> 
     <li>Jessica Deen <a href="https://twitter.com/jldeen" rel="noopener" target="_blank">@jldeen</a></li> 
     <li>Kyle Davis <a href="https://fosstodon.org/@linux_mclinuxface" rel="noopener" target="_blank">@linux_mclinuxface</a></li> 
     <li>Maish Saidel-Keesing <a href="https://twitter.com/maishsk" rel="noopener" target="_blank">@maishsk</a></li> 
     <li>Nathan Peck <a href="https://twitter.com/nathankpeck" rel="noopener" target="_blank">@nathanpeck</a></li> 
     <li>Olly Pomeroy <a href="https://www.linkedin.com/in/oliver-p/" rel="noopener" target="_blank">@oliver-p</a></li> 
     <li>Scott Coulton <a href="https://twitter.com/scottcoulton" rel="noopener" target="_blank">@scottcoulton</a></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table> 
<p>And finally, visit the <a href="http://serverlessland.com/" rel="noopener" target="_blank">Serverless Land</a> and <a href="http://containersonaws.com/" rel="noopener" target="_blank">Containers on AWS</a> websites for all your serverless and serverless container needs.</p>
