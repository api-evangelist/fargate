---
title: "Serverless ICYMI Q1 2024"
url: "https://aws.amazon.com/blogs/compute/serverless-icymi-q1-2024/"
date: "Mon, 01 Apr 2024 18:49:21 +0000"
author: "Julian Wood"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p>Welcome to the 25th edition of the AWS Serverless ICYMI (in case you missed it) quarterly recap. Every quarter, we share all the most recent product launches, feature enhancements, blog posts, webinars, live streams, and other interesting things that you might have missed!</p> 
<p>In case you missed our last ICYMI, check out what happened last quarter&nbsp;<a href="https://aws.amazon.com/blogs/compute/serverless-icymi-q4-2023/" rel="noopener" target="_blank">here</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22394" style="width: 624px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/2024-Q1-calendar.png"><img alt="2024 Q1 calendar" class="size-full wp-image-22394" height="194" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/2024-Q1-calendar.png" width="614" /></a>
 <p class="wp-caption-text" id="caption-attachment-22394">2024 Q1 calendar</p>
</div> 
<h2>Adobe Summit</h2> 
<p>At the <a href="https://business.adobe.com/summit/adobe-summit.html" rel="noopener" target="_blank">Adobe Summit</a>, the AWS Serverless Developer Advocacy team <a href="https://github.com/aws-samples/automated-image-processing-at-scale" rel="noopener" target="_blank">showcased a solution</a> developed for the NFL using AWS serverless technologies and Adobe Photoshop APIs. The system automates image processing tasks, including background removal and dynamic resizing, by integrating <a href="https://serverlessland.com/step-functions" rel="noopener" target="_blank">AWS Step Functions</a>, <a href="https://serverlessland.com/lambda" rel="noopener" target="_blank">AWS Lambda</a>, <a href="https://serverlessland.com/eventbridge" rel="noopener" target="_blank">Amazon EventBridge</a>, and AI/ML capabilities via <a href="https://aws.amazon.com/rekognition/" rel="noopener" target="_blank">Amazon Rekognition</a>. This solution reduced image processing time from weeks to minutes and saved the NFL significant costs. Combining cloud-based serverless architectures with advanced machine learning and API technologies can optimize digital workflows for cost-effective and agile digital asset management.</p> 
<div class="wp-caption aligncenter" id="attachment_22393" style="width: 634px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Adobe-Summit-ServerlessVideo.png"><img alt="Adobe Summit ServerlessVideo" class="size-full wp-image-22393" height="292" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Adobe-Summit-ServerlessVideo.png" width="624" /></a>
 <p class="wp-caption-text" id="caption-attachment-22393">Adobe Summit ServerlessVideo</p>
</div> 
<p>ServerlessVideo is a demo application to stream live videos and also perform advanced post-video processing. It uses several AWS services, including Step Functions, Lambda, EventBridge, <a href="https://aws.amazon.com/ecs/" rel="noopener" target="_blank">Amazon ECS</a>, and <a href="https://aws.amazon.com/bedrock/" rel="noopener" target="_blank">Amazon Bedrock</a> in a serverless architecture that makes it fast, flexible, and cost-effective. The team used ServerlessVideo to interview attendees about the conference experience and Adobe and partners about how they use Adobe. Learn more about the project and watch videos from Adobe Summit 2024 at <a href="https://video.serverlessland.com/" rel="noopener" target="_blank">video.serverlessland.com</a>.</p> 
<h2>AWS Lambda</h2> 
<p>AWS launched support for the latest long-term support release of <a href="https://aws.amazon.com/blogs/compute/introducing-the-net-8-runtime-for-aws-lambda/" rel="noopener" target="_blank">.NET 8</a>, which includes API enhancements, improved&nbsp;<a href="https://learn.microsoft.com/en-us/dotnet/core/deploying/native-aot/?tabs=net7%2Cwindows" rel="noopener" target="_blank">Native Ahead of Time</a>&nbsp;(Native AOT) support, and improved performance.</p> 
<div class="wp-caption aligncenter" id="attachment_22392" style="width: 532px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/AWS-Lambda-.NET-8.png"><img alt="AWS Lambda .NET 8" class="size-full wp-image-22392" height="192" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/AWS-Lambda-.NET-8.png" width="522" /></a>
 <p class="wp-caption-text" id="caption-attachment-22392">AWS Lambda .NET 8</p>
</div> 
<p>Learn how to <a href="https://aws.amazon.com/blogs/compute/comparing-design-approaches-for-building-serverless-microservices/" rel="noopener" target="_blank">compare design approaches for building serverless microservices</a>. This post covers the trade-offs to consider with various application architectures. See how you can apply single responsibility, Lambda-lith, and read and write functions.</p> 
<p>The <a href="https://aws.amazon.com/blogs/compute/re-platforming-java-applications-using-the-updated-aws-serverless-java-container/" rel="noopener" target="_blank">AWS Serverless Java Container</a> has been updated. This makes it easier to modernize a legacy Java application written with frameworks such as Spring, Spring Boot, or JAX-RS/Jersey in Lambda with minimal code changes.</p> 
<div class="wp-caption aligncenter" id="attachment_22391" style="width: 742px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/AWS-Serverless-Java-Container.png"><img alt="AWS Serverless Java Container" class="size-full wp-image-22391" height="303" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/AWS-Serverless-Java-Container.png" width="732" /></a>
 <p class="wp-caption-text" id="caption-attachment-22391">AWS Serverless Java Container</p>
</div> 
<p>Lambda has <a href="https://aws.amazon.com/about-aws/whats-new/2024/02/aws-lambda-stream-queue-based-event-sources/" rel="noopener" target="_blank">improved the responsiveness</a> for configuring Event Source Mappings (ESMs) and Amazon EventBridge Pipes with event sources such as self-managed <a href="https://kafka.apache.org/" rel="noopener" target="_blank">Apache Kafka</a>, <a href="https://aws.amazon.com/msk/" rel="noopener" target="_blank">Amazon Managed Streaming for Apache Kafka (MSK)</a>, <a href="https://aws.amazon.com/documentdb/" rel="noopener" target="_blank">Amazon DocumentDB</a>, and <a href="https://aws.amazon.com/amazon-mq/" rel="noopener" target="_blank">Amazon MQ</a>.</p> 
<p><a href="https://aws.amazon.com/blogs/architecture/chaos-engineering-in-the-cloud/" rel="noopener" target="_blank">Chaos engineering</a>&nbsp;is a popular practice for building confidence in system resilience. However, many existing tools assume the ability to alter infrastructure configurations, and cannot be easily applied to the serverless application paradigm. You can use the&nbsp;<a href="https://aws.amazon.com/fis/" rel="noopener" target="_blank">AWS Fault Injection Service</a>&nbsp;(FIS) to automate and manage chaos experiments <a href="https://aws.amazon.com/blogs/compute/automating-chaos-experiments-with-aws-fault-injection-service-and-aws-lambda/" rel="noopener" target="_blank">across different Lambda functions</a> to provide a reusable testing method.</p> 
<h2>Amazon ECS and AWS Fargate</h2> 
<p><a href="https://aws.amazon.com/ecs/" rel="noopener" target="_blank">Amazon Elastic Container Service (Amazon ECS)</a> now provides <a href="https://aws.amazon.com/blogs/containers/amazon-ecs-enables-easier-ec2-capacity-management-with-managed-instance-draining/" rel="noopener" target="_blank">managed instance draining</a> as a built-in feature of Amazon ECS capacity providers. This allows Amazon ECS to safely and automatically drain tasks from <a href="https://aws.amazon.com/ec2/" rel="noopener" target="_blank">Amazon Elastic Compute Cloud (Amazon EC2)</a> instances that are part of an Amazon EC2 Auto Scaling Group associated with an Amazon ECS capacity provider. This simplification allows you to remove custom lifecycle hooks previously used to drain Amazon EC2 instances. You can now perform infrastructure updates such as rolling out a new version of the ECS agent by seamlessly using Auto Scaling Group instance refresh, with Amazon ECS ensuring workloads are not interrupted.</p> 
<p><a href="https://github.com/aws/credentials-fetcher" rel="noopener" target="_blank">Credentials Fetcher</a>&nbsp;makes it easier to run containers that depend on Windows authentication when using Amazon EC2. Credentials Fetcher&nbsp;now integrates with&nbsp;Amazon ECS, using either the Amazon EC2 launch type, or <a href="https://aws.amazon.com/fargate/" rel="noopener" target="_blank">AWS Fargate</a> serverless compute launch type.</p> 
<p><a href="https://aws.amazon.com/about-aws/whats-new/2022/11/amazon-ecs-service-connect/" rel="noopener" target="_blank">Amazon ECS Service Connect</a> is a networking capability to simplify service discovery, connectivity, and traffic observability for Amazon ECS. You can now more easily <a href="https://aws.amazon.com/blogs/containers/secure-amazon-elastic-container-service-workloads-with-amazon-ecs-service-connect/" rel="noopener" target="_blank">integrate certificate management</a> to encrypt service-to-service communication using Transport Layer Security (TLS). You do not need to modify your application code, add additional network infrastructure, or operate service mesh solutions.</p> 
<div class="wp-caption aligncenter" id="attachment_22390" style="width: 1034px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Amazon-ECS-Service-Connect.jpg"><img alt="Amazon ECS Service Connect" class="size-large wp-image-22390" height="473" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Amazon-ECS-Service-Connect-1024x473.jpg" width="1024" /></a>
 <p class="wp-caption-text" id="caption-attachment-22390">Amazon ECS Service Connect</p>
</div> 
<p><a href="https://aws.amazon.com/blogs/containers/distributed-machine-learning-with-amazon-ecs/" rel="noopener" target="_blank">Running distributed machine learning (ML) workloads on Amazon ECS</a> allows ML teams to focus on creating, training and deploying models, rather than spending time managing the container orchestration engine. Amazon ECS provides a great environment to run ML projects as it supports&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-gpu.html#ecs-gpu-specifying" rel="noopener" target="_blank">workloads that use NVIDIA GPUs</a>&nbsp;and provides<a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-optimized_AMI.html" rel="noopener" target="_blank">&nbsp;optimized images</a>&nbsp;with pre-installed NVIDIA Kernel drivers and Docker runtime.</p> 
<p>See how to <a href="https://aws.amazon.com/blogs/containers/build-preview-environments-for-amazon-ecs-applications-with-aws-copilot/" rel="noopener" target="_blank">build preview environments</a> for Amazon ECS applications with <a href="https://aws.github.io/copilot-cli/" rel="noopener" target="_blank">AWS Copilot</a>. AWS Copilot is an open source command line interface that makes it easier to build, release, and operate production ready containerized applications.</p> 
<p>Learn techniques for automatic scaling of your <a href="https://aws.amazon.com/pm/ecs" rel="noopener" target="_blank">Amazon Elastic Container Service</a>&nbsp; (Amazon ECS) container workloads to enhance the end user experience. This <a href="https://aws.amazon.com/blogs/containers/scale-your-amazon-ecs-using-different-aws-native-services/" rel="noopener" target="_blank">post</a> explains how to use <a href="https://docs.aws.amazon.com/autoscaling/application/userguide/what-is-application-auto-scaling.html" rel="noopener" target="_blank">AWS Application Auto Scaling</a>&nbsp;which helps you configure automatic scaling of your Amazon ECS service. You can also use <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-connect.html" rel="noopener" target="_blank">Amazon ECS Service Connect</a>&nbsp;and&nbsp;<a href="https://aws.amazon.com/otel/" rel="noopener" target="_blank">AWS Distro for OpenTelemetry</a>&nbsp;(ADOT) in Application Auto Scaling.</p> 
<h2>AWS Step Functions</h2> 
<p>AWS workloads sometimes require access to data stored in on-premises databases and storage locations. Traditional solutions to establish connectivity to the on-premises resources require inbound rules to firewalls, a VPN tunnel, or public endpoints. Discover how to use the&nbsp;<a href="https://aws.amazon.com/what-is/mqtt/#seo-faq-pairs" rel="noopener" target="_blank">MQTT protocol</a>&nbsp;(<a href="https://aws.amazon.com/iot-core" rel="noopener" target="_blank">AWS IoT Core</a>) with&nbsp;<a href="https://aws.amazon.com/step-functions/" rel="noopener" target="_blank">AWS Step Functions</a>&nbsp;to dispatch jobs to on-premises workers to access or retrieve data stored on-premises.</p> 
<p>You can use Step Functions to orchestrate many business processes. Many industries are required to provide audit trails for decision and transactional systems. Learn how to build a <a href="https://aws.amazon.com/blogs/compute/building-a-serverless-streaming-pipeline-to-deliver-reliable-messaging/" rel="noopener" target="_blank">serverless pipeline</a> to create a reliable, performant, traceable, and durable pipeline for audit processing.</p> 
<h2>Amazon EventBridge</h2> 
<p><a href="https://aws.amazon.com/blogs/compute/build-real-time-applications-with-amazon-eventbridge-and-aws-appsync/" rel="noopener" target="_blank">Amazon EventBridge&nbsp;now supports publishing events</a> to&nbsp;<a href="https://aws.amazon.com/appsync/" rel="noopener" target="_blank">AWS AppSync</a>&nbsp;GraphQL APIs as native targets. The new integration allows you to publish events easily to a wider variety of consumers and simplifies updating clients with near real-time data.</p> 
<div class="wp-caption aligncenter" id="attachment_22389" style="width: 466px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Amazon-EventBridge-publishing-events-to-AWS-AppSync.png"><img alt="Amazon EventBridge publishing events to AWS AppSync" class="size-full wp-image-22389" height="131" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Amazon-EventBridge-publishing-events-to-AWS-AppSync.png" width="456" /></a>
 <p class="wp-caption-text" id="caption-attachment-22389">Amazon EventBridge publishing events to AWS AppSync</p>
</div> 
<p><a href="https://aws.amazon.com/blogs/compute/sending-and-receiving-cloudevents-with-amazon-eventbridge/" rel="noopener" target="_blank">Discover how to send and receive CloudEvents</a> with EventBridge. <a href="https://cloudevents.io/" rel="noopener" target="_blank">CloudEvents&nbsp;</a>is an open-source specification for describing event data in a common way. You can publish CloudEvents directly to EventBridge, filter and route them, and use input transformers and&nbsp;<a href="https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-api-destinations.html" rel="noopener" target="_blank">API Destinations</a>&nbsp;to send CloudEvents to downstream AWS services and third-party APIs.</p> 
<h2>AWS Application Composer</h2> 
<p>AWS Application Composer lets you create infrastructure as code templates by dragging and dropping cards on a virtual canvas. These represent CloudFormation resources, which you can wire together to create permissions and references. Application Composer has now expanded to the VS Code IDE as part of the&nbsp;<a href="https://aws.amazon.com/visualstudiocode/" rel="noopener" target="_blank">AWS Toolkit</a>. This now includes a <a href="https://aws.amazon.com/blogs/compute/using-generative-infrastructure-as-code-with-application-composer/" rel="noopener" target="_blank">generative AI partner</a> that helps you write infrastructure as code (IaC) for all 1100+&nbsp;<a href="https://aws.amazon.com/cloudformation/" rel="noopener" target="_blank">AWS&nbsp;CloudFormation</a>&nbsp;resources that Application Composer now&nbsp;<a href="https://aws.amazon.com/about-aws/whats-new/2023/09/aws-application-composer-1000-cloudformation-resources/" rel="noopener" target="_blank">supports</a>.</p> 
<div class="wp-caption aligncenter" id="attachment_22388" style="width: 203px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/AWS-AppComposer-generate-suggestions.jpg"><img alt="AWS AppComposer generate suggestions" class="size-full wp-image-22388" height="200" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/AWS-AppComposer-generate-suggestions.jpg" width="193" /></a>
 <p class="wp-caption-text" id="caption-attachment-22388">AWS AppComposer generate suggestions</p>
</div> 
<h2>Amazon API Gateway</h2> 
<p>Learn how to <a href="https://aws.amazon.com/blogs/compute/consuming-private-amazon-api-gateway-apis-using-mutual-tls/" rel="noopener" target="_blank">consume private Amazon API Gateway APIs using mutual TLS (mTLS)</a>. mTLS helps prevent man-in-the-middle attacks and protects against threats such as impersonation attempts, data interception, and tampering.</p> 
<h2>Serverless at AWS re:Invent</h2> 
<div class="wp-caption aligncenter" id="attachment_22395" style="width: 634px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Serverless-at-AWS-reInvent.png"><img alt="Serverless at AWS reInvent" class="size-full wp-image-22395" height="125" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Serverless-at-AWS-reInvent.png" width="624" /></a>
 <p class="wp-caption-text" id="caption-attachment-22395">Serverless at AWS reInvent</p>
</div> 
<p>Visit the <a href="https://www.youtube.com/@ServerlessLand" rel="noopener" target="_blank">Serverless Land YouTube channel</a> to find a list of serverless and serverless container sessions from reinvent 2023. Hear from experts like Chris Munns and Julian Wood in their popular session, <em>Best practices for serverless developers</em>, or Nathan Peck and Jessica Deen in <em>Deploying multi-tenant SaaS applications on Amazon ECS and AWS Fargate.</em></p> 
<h2>Serverless blog posts</h2> 
<h3>January</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/using-generative-infrastructure-as-code-with-application-composer/" rel="noopener" target="_blank">Using generative infrastructure as code with Application Composer</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/consuming-private-amazon-api-gateway-apis-using-mutual-tls/" rel="noopener" target="_blank">Consuming private Amazon API Gateway APIs using mutual TLS</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/invoking-on-premises-resources-interactively-using-aws-step-functions-and-mqtt/" rel="noopener" target="_blank">Invoking on-premises resources interactively using AWS Step Functions and MQTT</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/build-real-time-applications-with-amazon-eventbridge-and-aws-appsync/" rel="noopener" target="_blank">Build real-time applications with Amazon EventBridge and AWS AppSync</a></li> 
</ul> 
<h3>February</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/re-platforming-java-applications-using-the-updated-aws-serverless-java-container/" rel="noopener" target="_blank">Re-platforming Java applications using the updated AWS Serverless Java Container</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/introducing-the-net-8-runtime-for-aws-lambda/" rel="noopener" target="_blank">Introducing the .NET 8 runtime for AWS Lambda</a></li> 
</ul> 
<h3>March</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/compute/comparing-design-approaches-for-building-serverless-microservices/" rel="noopener" target="_blank">Comparing design approaches for building serverless microservices</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/sending-and-receiving-cloudevents-with-amazon-eventbridge/" rel="noopener" target="_blank">Sending and receiving CloudEvents with Amazon EventBridge</a></li> 
 <li><a href="https://aws.amazon.com/blogs/compute/automating-chaos-experiments-with-aws-fault-injection-service-and-aws-lambda/" rel="noopener" target="_blank">Automating chaos experiments with AWS Fault Injection Service and AWS Lambda</a></li> 
</ul> 
<h2>Serverless container blog posts</h2> 
<h3>January</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/signing-and-validating-oci-artifacts-with-aws-signer/" rel="noopener" target="_blank">Signing and Validating OCI Artifacts with AWS Signer</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/amazon-ecs-enables-easier-ec2-capacity-management-with-managed-instance-draining/" rel="noopener" target="_blank">Amazon ECS enables easier EC2 capacity management, with managed instance draining</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/secure-amazon-elastic-container-service-workloads-with-amazon-ecs-service-connect/" rel="noopener" target="_blank">Secure Amazon Elastic Container Service workloads with Amazon ECS Service Connect</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/build-preview-environments-for-amazon-ecs-applications-with-aws-copilot/" rel="noopener" target="_blank">Build preview environments for Amazon ECS applications with AWS Copilot</a></li> 
</ul> 
<h3>February</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/how-perry-street-software-implemented-resilient-deployment-strategies-with-amazon-ecs/" rel="noopener" target="_blank">How Perry Street Software Implemented Resilient Deployment Strategies with Amazon ECS</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/distributed-machine-learning-with-amazon-ecs/" rel="noopener" target="_blank">Distributed machine learning with Amazon ECS</a></li> 
</ul> 
<h3>December</h3> 
<ul> 
 <li><a href="https://aws.amazon.com/blogs/containers/windows-authentication-with-gmsa-on-linux-containers-on-amazon-ecs-with-aws-fargate/" rel="noopener" target="_blank">Windows authentication with gMSA on Linux containers on Amazon ECS with AWS Fargate</a></li> 
 <li><a href="https://aws.amazon.com/blogs/containers/scale-your-amazon-ecs-using-different-aws-native-services/" rel="noopener" target="_blank">Scale your Amazon ECS using different AWS native services!</a></li> 
</ul> 
<h2>Serverless Office Hours</h2> 
<div class="wp-caption aligncenter" id="attachment_22398" style="width: 634px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Serverless-Office-Hours.png"><img alt="Serverless Office Hours" class="size-full wp-image-22398" height="399" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Serverless-Office-Hours.png" width="624" /></a>
 <p class="wp-caption-text" id="caption-attachment-22398">Serverless Office Hours</p>
</div> 
<p>January</p> 
<ul> 
 <li>Jan 9 – <a href="https://www.youtube.com/watch?v=D3qGzEZiB4I" rel="noopener" target="_blank">Introducing ServerlessVideo</a></li> 
 <li>Jan 16 – <a href="https://www.youtube.com/watch?v=ScKSQgzDpe0" rel="noopener" target="_blank">Serverless Containers</a></li> 
 <li>Jan 23 – <a href="https://www.youtube.com/watch?v=H4hCygngTrU" rel="noopener" target="_blank">API Gateway private integrations</a></li> 
 <li>Jan 30 – <a href="https://www.youtube.com/watch?v=QcPIok3X4Ag" rel="noopener" target="_blank">Connecting to Salesforce using EventBridge</a></li> 
</ul> 
<p>February</p> 
<ul> 
 <li>Feb 6 – <a href="https://www.youtube.com/watch?v=xeUd9YDBkxg" rel="noopener" target="_blank">Comparing Apache Airflow and Step Functions</a></li> 
 <li>Feb 13 – <a href="https://www.youtube.com/watch?v=cF1chd45Vhw" rel="noopener" target="_blank">Refactoring Java applications to serverless</a></li> 
 <li>Feb 20 – <a href="https://www.youtube.com/watch?v=owuv7_fCamo" rel="noopener" target="_blank">Lambda performance tuning</a></li> 
 <li>Feb 27 – <a href="https://www.youtube.com/watch?v=JDbkoICzQro" rel="noopener" target="_blank">Building well architected API Gateway APIs</a></li> 
</ul> 
<p>March</p> 
<ul> 
 <li>Mar 5 – <a href="https://www.youtube.com/watch?v=B9UGoKX2Fus" rel="noopener" target="_blank">Using the new .NET 8 runtime in Lambda</a></li> 
 <li>Mar 12 – <a href="https://www.youtube.com/watch?v=U1Q7dvDgmhU" rel="noopener" target="_blank">Combining Kafka and EventBridge</a></li> 
 <li>Mar 19 – <a href="https://www.youtube.com/watch?v=wy2QYgKAoEg" rel="noopener" target="_blank">Java AI/ML on Lambda with Human Graphics</a></li> 
 <li>Mar 26 – <a href="https://www.youtube.com/watch?v=RhnofoWc9y8" rel="noopener" target="_blank">Lambda low latency runtime</a></li> 
</ul> 
<h2>Containers from the Couch</h2> 
<div class="wp-caption aligncenter" id="attachment_22397" style="width: 478px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Containers-from-the-Couch.png"><img alt="Containers from the Couch" class="size-full wp-image-22397" height="276" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/Containers-from-the-Couch.png" width="468" /></a>
 <p class="wp-caption-text" id="caption-attachment-22397">Containers from the Couch</p>
</div> 
<p>January</p> 
<ul> 
 <li>Jan 4 – <a href="https://www.youtube.com/watch?v=2Qe_50eEbrc" rel="noopener" target="_blank">A deep dive into autoscaling on Amazon ECS</a></li> 
 <li>Jan 25 – <a href="https://www.youtube.com/watch?v=9jBcZ3ludHM" rel="noopener" target="_blank">Optimize workloads for speed and cost</a></li> 
</ul> 
<p>February</p> 
<ul> 
 <li>Feb 8 – <a href="https://www.youtube.com/watch?v=kmKnMb8P0_U" rel="noopener" target="_blank">Building your containers on Windows with Finch</a></li> 
 <li>Feb 15 – <a href="https://www.youtube.com/watch?v=w-rkxR_KeVY" rel="noopener" target="_blank">ECS Builder Series with Autodesk</a></li> 
 <li>Feb 29 – <a href="https://www.youtube.com/watch?v=TcpEUnDM-4I" rel="noopener" target="_blank">Amazon GuardDuty ECS Runtime Monitoring</a></li> 
</ul> 
<p>March</p> 
<ul> 
 <li>Mar 21 – <a href="https://www.youtube.com/watch?v=s0JwBkellik" rel="noopener" target="_blank">Accelerating modern application development with Amazon ECS</a></li> 
</ul> 
<h2>FooBar Serverless</h2> 
<div class="wp-caption aligncenter" id="attachment_22396" style="width: 478px;">
 <a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/FooBar-Serverless.png"><img alt="FooBar Serverless" class="size-full wp-image-22396" height="276" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/04/01/FooBar-Serverless.png" width="468" /></a>
 <p class="wp-caption-text" id="caption-attachment-22396">FooBar Serverless</p>
</div> 
<h2>January</h2> 
<ul> 
 <li>Jan 11 – <a href="https://www.youtube.com/watch?v=P9n8BE693go" rel="noopener" target="_blank">Bedrock Agents and Knowledge bases from a developer perspective with Demo!</a></li> 
 <li>Jan 18 – <a href="https://www.youtube.com/watch?v=bdA6yMXJW6Y" rel="noopener" target="_blank">What’s new in AppComposer? Integration with Visual Studio Code and Step Functions Workflow Studio!</a></li> 
 <li>Jan 24 – <a href="https://www.youtube.com/watch?v=hTdFq4kfWsE" rel="noopener" target="_blank">Step Functions optimized integration with Amazon Bedrock</a></li> 
</ul> 
<h3>February</h3> 
<ul> 
 <li>Feb 1 – <a href="https://www.youtube.com/watch?v=_OtKwMy4S5s" rel="noopener" target="_blank">Introduction to AWS Step Functions – what is this service for? Use cases? Benefits?</a></li> 
 <li>Feb 8 – <a href="https://www.youtube.com/watch?v=t2JeWUpiWFc" rel="noopener" target="_blank">Must know concepts to work with Step Functions | State types, data management, and workflow types</a></li> 
 <li>Feb 15 – <a href="https://www.youtube.com/watch?v=TYBYV0HWAnM" rel="noopener" target="_blank">Create your AWS Step Functions workflows with AWS SAM</a></li> 
 <li>Feb 22 – <a href="https://www.youtube.com/watch?v=BXdhXRNVvbQ" rel="noopener" target="_blank">Create your AWS Step Functions workflows with AWS CDK</a></li> 
 <li>Feb 29 – <a href="https://www.youtube.com/watch?v=vuFN4GC3rhg" rel="noopener" target="_blank">Step Functions Service Integration Patterns</a></li> 
</ul> 
<h3>March</h3> 
<ul> 
 <li>Mar 7 – <a href="https://www.youtube.com/watch?v=2nWzsBYRBEk" rel="noopener" target="_blank">Step Functions Error Handling Mechanisms</a></li> 
 <li>Mar 14 – <a href="https://www.youtube.com/watch?v=kCbfFsjArLQ" rel="noopener" target="_blank">Mastering AWS Step Functions: Cost Analysis and Optimization Techniques with Ben Smith</a></li> 
 <li>Mar 21 – <a href="https://www.youtube.com/watch?v=XN1Jow5bDJ0" rel="noopener" target="_blank">Advanced Step Functions Patterns with Ben Smith</a></li> 
 <li>Mar 28 – <a href="https://www.youtube.com/watch?v=L7Y--WJsxVY" rel="noopener" target="_blank">Run a long execution job with no hassle and for free with Step Functions</a></li> 
</ul> 
<h2>Still looking for more?</h2> 
<p>The&nbsp;<a href="http://aws.amazon.com/serverless" rel="noopener" target="_blank">Serverless landing page</a>&nbsp;has more information. The&nbsp;<a href="https://aws.amazon.com/lambda/resources/?aws-lambda-resources-blog.sort-by=item.additionalFields.createdDate&amp;aws-lambda-resources-blog.sort-order=desc" rel="noopener" target="_blank">Lambda resources page</a>&nbsp;contains case studies, webinars, whitepapers, customer stories, reference architectures, and even more Getting Started tutorials.</p> 
<p>You can also&nbsp;follow the Serverless Developer Advocacy team on Twitter&nbsp;to see the latest news, follow conversations, and interact with the team.</p> 
<table> 
 <tbody> 
  <tr> 
   <td> 
    <ul> 
     <li>James Beswick:&nbsp;<a href="https://twitter.com/jbesw" rel="noopener" target="_blank">@jbesw</a></li> 
     <li>Eric Johnson:&nbsp;<a href="https://twitter.com/edjgeek" rel="noopener" target="_blank">@edjgeek</a></li> 
     <li>Ben Smith:&nbsp;<a href="https://twitter.com/benjamin_l_s" rel="noopener" target="_blank">@benjamin_l_s</a></li> 
     <li>Julian Wood:&nbsp;<a href="https://twitter.com/julian_wood" rel="noopener" target="_blank">@julian_wood</a></li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>Marcia Villalba:&nbsp;<a href="https://twitter.com/mavi888uy/" rel="noopener" target="_blank">@mavi888uy</a></li> 
     <li>David Boyne:&nbsp;<a href="https://twitter.com/boyney123" rel="noopener" target="_blank">@boyney123</a></li> 
     <li>Maish Saidel-Keesing <a href="https://twitter.com/maishsk" rel="noopener" target="_blank">@maishsk</a></li> 
     <li>Olly Pomeroy <a href="https://www.linkedin.com/in/oliver-p/" rel="noopener" target="_blank">@oliver-p</a></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table> 
<p>And finally, visit the <a href="http://serverlessland.com/" rel="noopener" target="_blank">Serverless Land</a> and <a href="http://containersonaws.com/" rel="noopener" target="_blank">Containers on AWS</a> websites for all your serverless and serverless container needs.</p>
