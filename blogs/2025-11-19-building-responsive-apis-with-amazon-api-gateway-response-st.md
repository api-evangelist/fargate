---
title: "Building responsive APIs with Amazon API Gateway response streaming"
url: "https://aws.amazon.com/blogs/compute/building-responsive-apis-with-amazon-api-gateway-response-streaming/"
date: "Wed, 19 Nov 2025 23:10:51 +0000"
author: "Anton Aleksandrov"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p>Today, AWS announced support for response streaming in <a href="https://aws.amazon.com/api-gateway/">Amazon API Gateway</a>&nbsp;to significantly improve the responsiveness of your REST APIs by progressively streaming response payloads back to the client. With this new capability, you can use streamed responses to enhance user experience when building LLM-driven applications (such as AI agents and chatbots), improve time-to-first-byte (TTFB) performance for web and mobile applications, stream large files, and perform long-running operations while reporting incremental progress using protocols such as <a href="https://en.wikipedia.org/wiki/Server-sent_events">server-sent events</a> (SSE).</p> 
<p>In this post you will learn about this new capability, the challenges it addresses, and how to use response streaming to improve the responsiveness of your applications.</p> 
<h1>Overview</h1> 
<p>Consider this scenario – you’re running an AI-powered agentic application that uses an <a href="https://aws.amazon.com/bedrock/">Amazon Bedrock</a> <a href="https://docs.aws.amazon.com/bedrock/latest/userguide/foundation-models-reference.html">foundation model</a>. Your users interact with the application through an API, asking complex questions that require detailed responses. Before response streaming, users would send their prompts and wait to eventually receive the application response, sometimes for tens of seconds. This awkward pause between questions and responses created a disconnected, unnatural experience.</p> 
<p>With the new API Gateway response streaming capability, the interaction through the API becomes much more fluid and natural. As soon as your application starts processing the model response, you can stream it back to your users using the API Gateway.</p> 
<p>The following animation illustrates this significant user experience improvement. The prompt on the left is processed using a non-streaming response with user having to wait for several seconds to receive the result. The prompt on the right is using the new API Gateway response streaming, significantly reducing TTFB and improving user experience.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-apigw-streaming-compar.gif"><img alt="" class="aligncenter size-full wp-image-25083" height="500" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-apigw-streaming-compar.gif" width="1032" /></a></p> 
<p style="text-align: center;">Figure 1. Comparing user experience before (left) and after (right) enabling API Gateway response streaming when returning a response from a Bedrock foundational model.</p> 
<p>Your users can now see AI responses appear in real-time, word by word, just like watching someone type. This immediate feedback makes your applications feel more responsive and engaging, keeping users connected throughout the interaction. In addition, you don’t have to worry about response size limits or implement complex workarounds – the streaming happens automatically and efficiently, letting you focus on building great user experiences rather than managing infrastructure constraints.</p> 
<h1>Understanding response steaming</h1> 
<p>In the traditional request-response model, responses must be fully computed before being sent to the client. This can negatively impact user experience – the client must wait for the complete response to be generated on the server-side and transmitted over-the-wire. This is especially pronounced in interactive, latency-sensitive cloud applications such as AI agents, chatbots, virtual assistants, or music generators.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic1.png"><img alt="" class="aligncenter size-full wp-image-25084" height="494" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic1.png" width="1632" /></a></p> 
<p style="text-align: center;">Figure 2. Response is returned to the client only after it’s been fully generated, increasing time-to-first-byte latency.</p> 
<p>Another important scenario is returning larger response payloads, such as images, large documents, or datasets. In some cases, these payloads may exceed the 10 MB response size limit or default integration timeout limit of 29 seconds of API Gateway. Before the launch of response streaming, developers worked around these limitations by using <a href="https://docs.aws.amazon.com/AmazonS3/latest/userguide/ShareObjectPreSignedURL.html">pre-signed</a> <a href="https://aws.amazon.com/s3/">Amazon S3</a> URLs to download large responses or accepting lower RPS for an increase in timeout. While functional, these workarounds introduced additional latency and architectural complexity.</p> 
<p>With response streaming support you can address these challenges. You can now update your REST APIs to return streamed responses, significantly enhancing user experience, improving TTFB performance, supporting response payload sizes to exceed 10 MB, and serving requests that can take up to 15 minutes.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic2.png"><img alt="" class="aligncenter size-full wp-image-25086" height="553" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic2.png" width="1634" /></a></p> 
<p style="text-align: center;">Figure 3. Response streaming reduces time-to-first-byte and improves user experience.</p> 
<p>The response streaming capability is already delivering significant performance for organizations:</p> 
<p><em>“Working closely with the AWS teams to enable response streaming was instrumental in advancing our roadmap to deliver the most performant storefront experiences for our largest customers at Salesforce Commerce Cloud. Our collaboration exceeded our Core Web Vital goals; we saw our Total Blocking Time metrics drop by over 98%, which will enable our customers to drive higher revenue and conversion rates.”, says Drew Lau, Senior Director of Product Management at Salesforce.</em></p> 
<p>Response streaming is supported for any <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/setup-http-integrations.html">HTTP-proxy integration</a>, <a href="https://aws.amazon.com/lambda/">AWS Lambda</a> functions (using proxy integration mode), and <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/set-up-private-integration.html">private integrations</a>. To get started, configure your API integration to stream the response from your backend, as described in the following sections, and redeploy your API for changes to take effect.</p> 
<h1>Getting started with response streaming</h1> 
<p>To enable response streaming for your REST APIs, update your integration configuration to set the response transfer mode to <strong>STREAM</strong>. This enables API Gateway to start streaming the response to the client as soon as response bytes become available. When using response streaming, you can configure request timeout up to 15 minutes. For best time to first byte user experience, AWS strongly recommends your backend integration also implements response streaming.</p> 
<p>You can enable response streaming in several different ways, as illustrated in the following snippets:</p> 
<p>Using the API Gateway console, when creating method integrations, select Stream for the Response transfer mode.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic3.png"><img alt="" class="aligncenter size-full wp-image-25087" height="411" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic3.png" width="1618" /></a></p> 
<p style="text-align: center;">Figure 4. Enabling response streaming in API Gateway Console.</p> 
<p style="text-align: left;">Setting response transfer mode using the Open API spec:</p> 
<pre><code class="lang-yaml">paths:
  /products:
    get:
      x-amazon-apigateway-integration:
        httpMethod: "GET"
        uri: "https://example.com"
        type: "http_proxy"
        timeoutInMillis: 300000
        responseTransferMode: "STREAM"</code></pre> 
<p>Setting response transfer mode using infrastructure-as-code (IaC) frameworks, such as <a href="https://aws.amazon.com/cloudformation/">AWS CloudFormation</a>. Note the <strong>/response-streaming-invocations</strong> Uri fragment, it tells API Gateway to use the Lambda <a href="https://docs.aws.amazon.com/lambda/latest/api/API_InvokeWithResponseStream.html">InvokeWithResponseStreaming</a> endpoint:</p> 
<pre><code class="lang-yaml">MyProxyResourceMethod:
  Type: 'AWS::ApiGateway::Method'
  Properties:
    RestApiId: !Ref LambdaSimpleProxy
    ResourceId: !Ref ProxyResource
    HttpMethod: ANY
    Integration:
      Type: AWS_PROXY
      IntegrationHttpMethod: POST
      ResponseTransferMode: STREAM
      Uri: !Sub arn:aws:apigateway:${APIGW_REGION}:lambda:path/2021-11-
           15/functions/${FN_ARN}/response-streaming-invocations</code></pre> 
<p>Updating response transfer mode using the AWS CLI:</p> 
<pre><code class="lang-bash">aws apigw update-integration \
   --rest-api-id a1b2c2 \
   --resource-id aaa111 \
   --http-method GET \
   --patch-operations "op='replace',path='/responseTransferMode',value=STREAM" \
   --region us-west-2</code></pre> 
<h1>Using response streaming with Lambda functions</h1> 
<p>When using Lambda functions as a downstream integration endpoint, your Lambda functions must be <a href="https://docs.aws.amazon.com/lambda/latest/dg/config-rs-write-functions.html">streaming-enabled</a>. The API Gateway uses the <a href="https://docs.aws.amazon.com/lambda/latest/api/API_InvokeWithResponseStream.html">InvokeWithResponseStreaming</a> API to invoke functions, as illustrated in the following diagram, and requires Lambda proxy integration. See the <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/response-transfer-mode.html">API Gateway documentation</a> for additional guidance.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic4.png"><img alt="" class="aligncenter size-full wp-image-25091" height="270" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic4.png" width="1635" /></a></p> 
<p style="text-align: center;">Figure 5. Using API Gateway response streaming with Lambda functions for interactive AI applications.</p> 
<p>When you use response streaming with Lambda functions, API Gateway expects the handler response stream to contain the following components (in order):</p> 
<ul> 
 <li><strong>JSON response metadata</strong> – Must be a valid JSON object and can only contain <strong>statusCode</strong>, <strong>headers</strong>, <strong>multiValueHeaders</strong>, and <strong>cookies</strong> fields (all optional). Metadata cannot be an empty string; at a minimum it must be an empty JSON object.</li> 
 <li><strong>The 8-null-byte delimiter</strong> – Lambda adds this delimiter automatically when you use the built-in <strong>awslambda.HttpResponseStream.from()</strong> method, as illustrated below. When not using this method, you’re responsible for adding the delimiter yourself.</li> 
 <li><strong>Response payload</strong> – Can be empty.</li> 
</ul> 
<p>The following code snippet illustrates how you can return a streamed response from your Lambda functions so it will be compatible with API Gateway response streaming:</p> 
<pre><code class="lang-js">export const handler = awslambda.streamifyResponse(
   async (event, responseStream, context) =&gt; {

      const httpResponseMetadata = {
         statusCode: 200,
         headers: {
            'Content-Type': 'text/plain',
            'X-Custom-Header': 'some-value'
         }
      };

      responseStream = awslambda.HttpResponseStream.from(
         responseStream,
         httpResponseMetadata
      );

      responseStream.write('hello');
      await new Promise(r =&gt; setTimeout(r, 1000));
      responseStream.write(' world');
      await new Promise(r =&gt; setTimeout(r, 1000));
      responseStream.write('!!!');
      responseStream.end();
   }
);</code></pre> 
<p>Refer to the <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/response-transfer-mode.html">API Gateway documentation</a> for further implementation guidelines.</p> 
<h1>Using response streaming with HTTP Proxy integrations</h1> 
<p>You can stream HTTP responses from your applications used as downstream integration endpoints, for example web servers running on <a href="https://aws.amazon.com/ecs/">Amazon Elastic Container Service</a> (Amazon ECS) or <a href="https://aws.amazon.com/eks/">Amazon Elastic Kubernetes Service</a> (Amazon EKS). In this case, you must use <strong>HTTP_PROXY</strong> integration and specify the response transfer mode as <strong>STREAM</strong> (using the console, AWS CLI, or IaC). Redeploy your API after modifying it.</p> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic5.png"><img alt="" class="aligncenter size-full wp-image-25092" height="294" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2025/11/06/compute-2459-pic5.png" width="1628" /></a></p> 
<p style="text-align: center;">Figure 6. Using API Gateway response streaming with HTTP server applications.</p> 
<p>Once API Gateway receives a streaming response from your application, it will wait until the HTTP headers block transfer is complete. Then, it will send to the client an HTTP response status code and headers, followed by the content from your application as it gets received by the API Gateway service. It will continue streaming response from your application to the client until the stream ends (up to 15 minutes).</p> 
<p>Many popular API and web application development frameworks provide response streaming abstractions. The following code snippet illustrates how you can implement HTTP response streaming using FastAPI:</p> 
<pre><code class="lang-python">app = FastAPI()

async def stream_response():
   yield b"Hello "
   await asyncio.sleep(1)
   yield b"World "
   await asyncio.sleep(1)
   yield b"!"

@app.get("/")
async def main():
   return StreamingResponse(stream_response(), media_type="text/plain")</code></pre> 
<h1>Adding real-time response streaming to your HTTP clients</h1> 
<p>Different HTTP clients have different ways to process streamed response fragments as they arrive. The following code snippet illustrates how to process a streamed response with a Node.js application:</p> 
<pre><code class="lang-js">const request = http.request(options, (response)=&gt;{
   response.on('data', (chunk) =&gt; {
      console.log(chunk);
   });

   response.on('end', () =&gt; {
      console.log('Response complete’);
   });
});

request.end();</code></pre> 
<p>When using CURL, you can use the <strong>–no-buffer</strong> argument to print response fragments as they arrive.</p> 
<pre><code class="lang-bash">curl --no-buffer {URL}</code></pre> 
<h1>Sample code</h1> 
<p><a href="https://github.com/aws-samples/serverless-samples/tree/main/apigw-response-streaming">Clone this sample project from GitHub</a> to see API Gateway response streaming in action. Follow instructions in the README.md to provision the sample project in your AWS account.</p> 
<h1>Considerations</h1> 
<p>Before you enable response streaming, consider:</p> 
<ul> 
 <li>Response streaming is available for REST APIs and can be used with HTTP_PROXY integrations, Lambda integrations (in proxy mode), and private integrations.</li> 
 <li>You can use API Gateway response streaming with <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-api-endpoint-types.html">any endpoint type</a>, such as Regional, Private, and Edge-optimized, with or without <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/how-to-custom-domains.html">custom domain names</a>.</li> 
 <li>When using response streaming, you can configure response timeouts up to 15 minutes, according to your scenario requirements.</li> 
 <li>All streaming responses from Regional or Private endpoints are subject to a 5-minute idle timeout. All streaming responses from edge-optimized endpoints are subject to a 30-second idle timeout.</li> 
 <li>Within each streaming response, the first 10MB of response payload is not subject to any bandwidth restrictions. Response payload data exceeding 10MB is restricted to 2MB/s.</li> 
 <li>Response streaming is compatible with API Gateway security capabilities such as <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html">authorizers</a>, <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-control-access-aws-waf.html">WAF</a>, <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-control-access-to-api.html">access controls</a>, <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/rest-api-mutual-tls.html">TLS/mTLS</a>, <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-request-throttling.html">request throttling</a>, and <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/rest-api-monitor.html">access logging</a>.</li> 
 <li>When processing streamed responses, the following features are not supported: response transformation with VTL, integration response caching, and content encoding.</li> 
 <li>Always protect your APIs against unauthorized access and other potential security threats by implementing proper authorization with <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-use-lambda-authorizer.html">Lambda Authorizers</a> or <a href="https://aws.amazon.com/cognito/">Amazon Cognito</a> <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/apigateway-integrate-with-cognito.html">User Pools</a>. Read <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/rest-api-protect.html">REST API protection documentation</a> and <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/security.html">API Gateway security documentation</a> for additional details.</li> 
</ul> 
<h1>Observability</h1> 
<p>You can continue using existing observability capabilities, such as <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/security-monitoring.html">execution logs</a>, <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/security-monitoring.html">access logs</a>, <a href="https://aws.amazon.com/xray/">AWS X-Ray</a> integration, and <a href="https://aws.amazon.com/cloudwatch/">Amazon CloudWatch</a> metrics with API Gateway response streaming.</p> 
<p>In addition to the existing <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/api-gateway-variables-for-access-logging.html">access logs variables</a>, the following new variables are available:</p> 
<ul> 
 <li><strong>$content.integration.responseTransferMode</strong> – the response transfer mode of your integration. This can be either <strong>BUFFERED</strong> or <strong>STREAMED</strong>.</li> 
 <li><strong>$context.integration.timeToAllHeaders</strong> – the time between when API Gateway establishes the integration connection to when it receives all integration response headers from the client.</li> 
 <li><strong>$context.integration.timeToFirstContent</strong> – the time between when API Gateway establishes the integration connection to when it receives the first content bytes.</li> 
</ul> 
<p>See <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/response-streaming-troubleshoot.html">API Gateway documentation</a> for more information.</p> 
<h1>Pricing</h1> 
<p>With this new capability, you continue to pay the same API Invoke rates for streamed responses. Each 10MB of response data, rounded up to the nearest 10MB, is billed as a single request. See <a href="https://aws.amazon.com/api-gateway/pricing/">API Gateway pricing page</a> for additional details.</p> 
<h1>Conclusion</h1> 
<p>The new response streaming capability for Amazon API Gateway enhances how you can build and deliver responsive APIs in the cloud. With immediate streaming of response data as it becomes available, you can significantly improve time-to-first-byte performance and overcome traditional payload size and timeout limitations. This is particularly valuable for AI-powered applications, file transfers, and interactive web experiences that demand real-time responsiveness.</p> 
<p>To learn more about API Gateway response streaming see the <a href="https://docs.aws.amazon.com/apigateway/latest/developerguide/response-transfer-mode.html">service documentation</a>.</p> 
<p>To learn more about building Serverless architectures see <a href="https://serverlessland.com/">Serverless Land</a>.</p>
