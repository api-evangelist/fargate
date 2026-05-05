---
title: "Securing Amazon ECS workloads on AWS Fargate with customer managed keys"
url: "https://aws.amazon.com/blogs/compute/securing-amazon-ecs-workloads-on-aws-fargate-with-customer-managed-keys/"
date: "Mon, 10 Jun 2024 21:16:19 +0000"
author: "Maish Saidel-Keesing"
feed_url: "https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/feed/"
---
<p>As <a href="https://www.youtube.com/watch?v=vWfkbGF6fiA&amp;t=4335s" rel="noopener" target="_blank">Amazon CTO Werner Vogels said</a>, “Encryption is the tool we have to make sure that nobody else has access to your data. Amazon Web Services (AWS) built encryption into nearly all of its 165 cloud services. Make use of it. Dance like nobody is watching. Encrypt like everyone is.”</p> 
<p>Security is the top priority at AWS, underpinning everything we do. With AWS Fargate, every <a href="https://aws.amazon.com/ecs/" rel="noopener" target="_blank">Amazon Elastic Container Service</a> (Amazon ECS) task is launched on to a new single use, single tenant unit of compute. The ephemeral storage for this compute is always encrypted, and the&nbsp;<a href="https://aws.amazon.com/kms/" rel="noopener" target="_blank">AWS Key Management Service</a> (AWS KMS) encryption key used for this encryption is&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/fargate-task-storage.html" rel="noopener" target="_blank">managed by AWS Fargate</a>.</p> 
<p>Today, AWS is announcing that you can bring your own customer managed keys (CMKs). Once added to AWS KMS, you can use these to encrypt the underlying ephemeral storage of an Amazon ECS task on <a href="https://aws.amazon.com/fargate/" rel="noopener" target="_blank">AWS Fargate</a>. With this new capability, customers operating in heavily regulated environments can now have more control and visibility into their task’s ephemeral storage encryption.</p> 
<p>This post dives into AWS Fargate task ephemeral storage and shows how the new customer managed key (CMK) feature can be enabled and audited.</p> 
<h2>Overview</h2> 
<p>AWS Fargate is a serverless compute engine for containerized workloads running on Amazon ECS and <a href="https://aws.amazon.com/eks/" rel="noopener" target="_blank">Amazon Elastic Kubernetes Service</a> (Amazon EKS). Each time a new piece of work is scheduled on to AWS Fargate, as an Amazon ECS task or an <a href="https://docs.aws.amazon.com/eks/latest/userguide/fargate-pod-configuration.html" rel="noopener" target="_blank">Amazon EKS Pod</a>, this workload is placed on a single use, single-tenant instance of compute.</p> 
<p>For Amazon ECS tasks, that unit of compute has 20GiBs of <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/fargate-task-storage.html" rel="noopener" target="_blank">ephemeral storage attached</a>. This can be increased up to 200GiB by specifying the&nbsp;<code>ephemeralStorage</code>&nbsp;parameter in your task definition.&nbsp;This ephemeral storage is bound to the lifecycle of the Amazon ECS task, and once the Amazon ECS task has stopped, along with the underlying compute, this ephemeral storage is deleted.</p> 
<p>If you are using AWS Fargate <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform-linux-fargate.html" rel="noopener" target="_blank">platform version 1.4.0 </a>or higher, this ephemeral storage volume is encrypted by default. It is encrypted using an AWS Key Management Service (KMS) key with the&nbsp;AES-256 encryption algorithm. The key, and its lifecycle, is owned by the AWS Fargate service. You can learn more about Fargate-managed ephemeral storage encryption in the <a href="https://d1.awsstatic.com/whitepapers/AWS_Fargate_Security_Overview_Whitepaper.pdf" rel="noopener" target="_blank">AWS Fargate Security Whitepaper</a>.</p> 
<p>With today’s launch, as an alternative to the Fargate-managed encryption, you can choose to encrypt the ephemeral storage with customer managed keys (CMKs).&nbsp;This helps regulation-sensitive customers meet their&nbsp;internal security policies and regulatory requirements.</p> 
<p>Customers can import their own existing keys into AWS KMS or create a new CMK to encrypt the ephemeral storage. CMKs used by AWS Fargate can be managed through the normal AWS KMS lifecycle actions such as being rotated, disabled, and deleted. See the&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/fargate-managing-kms-key.html" rel="noopener" target="_blank">Amazon ECS documentation</a> for more details on managing the KMS key. Additionally, all access from AWS Fargate to the KMS key can be audited in <a href="https://docs.aws.amazon.com/awscloudtrail/latest/userguide/cloudtrail-working-with-log-files.html" rel="noopener" target="_blank">AWS CloudTrail Logs</a>.</p> 
<p>In January 2024, <a href="https://aws.amazon.com/about-aws/whats-new/2024/01/amazon-ecs-fargate-integrate-ebs/" rel="noopener" target="_blank">AWS announced</a> that additional <a href="https://aws.amazon.com/ebs/" rel="noopener" target="_blank">Amazon Elastic Block Store</a> (Amazon EBS) volumes can now be attached to Amazon ECS tasks running on AWS Fargate. These EBS volumes unlock additional use cases for AWS Fargate customers, using higher capacity and high-performance volumes for use in their tasks alongside the ephemeral storage. These additional EBS volumes are managed differently to the ephemeral storage, and these volumes can already be&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ebs-kms-encryption.html" rel="noopener" target="_blank">encrypted with customer managed KMS keys (CMKs)</a>.</p> 
<p>AWS Fargate falls under the scope of the <a href="https://aws.amazon.com/compliance/services-in-scope/" rel="noopener" target="_blank">following compliance programs</a> regarding AWS’s side of the shared responsibility model. The compliance programs covered by AWS Fargate&nbsp;include:</p> 
<ul> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/C5/" rel="noopener" target="_blank">C5</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/CCCS/" rel="noopener" target="_blank">CCCS</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/CISPE/" rel="noopener" target="_blank">CISPE</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/desc-csp/" rel="noopener" target="_blank">DESC CSP</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/DoD_CC_SRG/" rel="noopener" target="_blank">DOD CC SRG</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/FedRAMP/" rel="noopener" target="_blank">FedRAMP</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/FINMA/" rel="noopener" target="_blank">FINMA</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/HITRUST-CSF/" rel="noopener" target="_blank">HITRUST CSF</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/ISMAP/" rel="noopener" target="_blank">ISMAP</a></li> 
 <li><a href="https://aws.amazon.com/compliance/iso-certified/" rel="noopener" target="_blank">ISO and CSA STAR certificates</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/K-ISMS/" rel="noopener" target="_blank">K-ISMS</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/MTCS/" rel="noopener" target="_blank">MTCS</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/PCI/" rel="noopener" target="_blank">PCI</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/PiTuKri/https://aws.amazon.com/compliance/services-in-scope/PiTuKri/" rel="noopener" target="_blank">PiTuKri</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/SOC/" rel="noopener" target="_blank">SOC</a></li> 
 <li><a href="https://aws.amazon.com/compliance/services-in-scope/SNI27001/" rel="noopener" target="_blank">SNI 27001</a></li> 
</ul> 
<p>You can download third-party audit reports using <a href="https://aws.amazon.com/artifact/" rel="noopener" target="_blank">AWS Artifact</a>. For more information, see <a href="https://docs.aws.amazon.com/artifact/latest/ug/downloading-documents.html" rel="noopener" target="_blank">Downloading Reports in AWS Artifact</a>.&nbsp;Many of these compliance programs require customers to&nbsp;encrypt their data at rest within their Amazon ECS on AWS Fargate resources.</p> 
<p>Customers also have additional internal risk management policies for key handling, where they must generate their own keys, have backups for these keys off-cloud, and manage the lifecycle of these keys. Until today, these customers could not use AWS Fargate’s default encryption solution for the workloads subject to their internal security policies.</p> 
<h2>Enabling CMK for ephemeral storage on an Amazon ECS Cluster</h2> 
<p>Following today’s launch a single KMS key can now be attached to a new or existing Amazon ECS Cluster. Once a key has been attached, all new tasks launched on to AWS Fargate use this KMS key. If you have existing tasks running in the Amazon ECS cluster, they must be redeployed to use the new encryption key. If these tasks are part of an Amazon ECS service, passing the –force-new-deployment flag to an amazon ecs update-service <a href="https://docs.aws.amazon.com/cli/latest/reference/ecs/update-service.html" rel="noopener" target="_blank">command</a> forces all tasks to be redeployed with the new KMS key (while respecting the&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DeploymentConfiguration.html&quot; \l &quot;ECS-Type-DeploymentConfiguration-minimumHealthyPercent" rel="noopener" target="_blank"><code>minimumHealthyPercent</code></a> of the service).</p> 
<p>To attach a KMS key to a new or existing cluster, specify the <code>KeyId</code> to the new&nbsp;<code>managedStorageConfiguration</code> field:</p> 
<pre><code class="lang-bash">aws ecs create-cluster \
  --cluster clusterName&nbsp;\
  --configuration '{"managedStorageConfiguration":{"fargateEphemeralStorageKmsKeyId":"arn:aws:kms:us-west-2:012345678901:key/a1b2c3d4-5678-90ab-cdef-EXAMPLE11111"}}'</code></pre> 
<p>Here is an example of the output of a DescribeClusters&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeClusters.html" rel="noopener" target="_blank">API request</a> to an Amazon ECS cluster with a customer managed key:</p> 
<pre><code class="lang-bash">aws ecs describe-clusters --clusters ecs-fargate-self-managed-key-cluster&nbsp;--region us-west-2&nbsp;--include&nbsp;CONFIGURATIONS</code></pre> 
<p><a href="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/05/08/Screenshot_2024-05-08-16.01.34_S1V3tt.png"><img alt="Result of describe-clusters query" class="alignleft size-full wp-image-22449" height="285" src="https://d2908q01vomqb2.cloudfront.net/1b6453892473a467d07372d45eb05abc2031647a/2024/05/08/Screenshot_2024-05-08-16.01.34_S1V3tt.png" width="1252" /></a></p> 
<p>Aside from auditing CloudTrail Logs for encryption events, you can also verify that an ECS task is using the KMS key by using the <code><a href="https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_DescribeTasks.html" rel="noopener" target="_blank">DescribeTask</a></code>&nbsp;API on an existing task:</p> 
<pre><code class="lang-json">{
    "tasks": [
        {
            ....
            "clusterArn": "arn:aws:ecs:us-west-2:1234567890:cluster/mycluster",
            "taskArn": "arn:aws:ecs:us-west-2:1234567890:task/11223342-1111-4fde-b6ca-273c5cfc00a1]",
            "fargateEphemeralStorage": {
                "sizeInGiB": 20,
                "<strong>kmsKeyId</strong>": "<strong>arn:aws:kms:us-west-2:1234567890:key/082222a1-1111-4fde-b6ca-273c5cfc00a1</strong>"
            }
        }
    ]
}</code></pre> 
<h2>Enforcing encryption with customer managed keys</h2> 
<p>The new&nbsp;<a href="https://aws.amazon.com/iam/" rel="noopener" target="_blank">AWS Identity and Access Management</a> (IAM) <a href="https://docs.aws.amazon.com/service-authorization/latest/reference/list_amazonelasticcontainerservice.html" rel="noopener" target="_blank">condition key</a> ensures that your Amazon ECS clusters are created with a customer managed key. This can be applied as <a href="https://docs.aws.amazon.com/organizations/latest/userguide/orgs_manage_policies_scps.html" rel="noopener" target="_blank">Service Control Policy in your AWS Organization</a>&nbsp;or as part of your <a href="https://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies.html" rel="noopener" target="_blank">IAM permissions</a>.</p> 
<p>Here is an IAM policy example snippet that ensures a cluster can only be created when a specific AWS KMS key is used:</p> 
<pre><code class="lang-json">{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Action": [
        "ecs:CreateCluster"
      ],
      "Resource": "*",
      "Condition": {
        "StringEquals": {
          "<strong>ecs:fargate-ephemeral-storage-kms-key": "arn:aws:kms:us-east-1:123456789012:key/1234abcd-12ab-34cd-56ef-1234567890ab</strong>"
        }
      }
    }
  ]
}</code></pre> 
<h2>Audit encryption events</h2> 
<p>Encryption events are logged in AWS CloudTrail. The following is an example of a CloudTrail event that includes the volume ID, cluster name, and AWS Account ID of the operation. You can find more details about the type of events that are logged in&nbsp;<a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/fargate-managing-kms-key.html" rel="noopener" target="_blank">Managing AWS KMS keys for Fargate ephemeral storage.</a></p> 
<pre><code class="lang-json">{
    "eventVersion": "1.08",
    "userIdentity": {
        "type": "AWSService",
        "invokedBy": "ec2-frontend-api.amazonaws.com"
    },
    "eventTime": "2024-04-23T18:08:13Z",
    "eventSource": "kms.amazonaws.com",
    "eventName": "CreateGrant",
    "awsRegion": "us-west-2",
    "sourceIPAddress": "ec2-frontend-api.amazonaws.com",
    "userAgent": "ec2-frontend-api.amazonaws.com",
    "requestParameters": {
        "keyId": "arn:aws:kms:us-west-2:123456789012:key/9b52b885-3f4d-40af-9843-d6b24b735559",
        "granteePrincipal": "fargate.us-west-2.amazonaws.com",
        "operations": [
            "Decrypt"
        ],
        "constraints": {
            "encryptionContextSubset": {
                "<strong>aws:ecs:clusterAccount": "123456789012"</strong>,
                <strong>"aws:ebs:id": "vol-01234567890abcdef"</strong>,
                <strong>"aws:ecs:clusterName": "ecs-fargate-self-managed-key-cluster"</strong>
            }
        },
        "retiringPrincipal": "ec2.us-west-2.amazonaws.com"
    },
    "responseElements": {
        "grantId": "e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855",
        "keyId": "arn:aws:kms:us-west-2:123456789012:key/9b52b885-3f4d-40af-9843-d6b24b735559"
    },
    "requestID": "be4d1a4e4730e0dceca51f87ee7454d5db76400d80e22bfbf3c4ca01e893b60c",
    "eventID": "bf36027c-86bd-40f2-a561-960cbe148c4c",
    "readOnly": false,
    "resources": [
        {
            "accountId": "AWS Internal",
            "type": "AWS::KMS::Key",
            "ARN": "arn:aws:kms:us-west-2:123456789012:key/9b52b885-3f4d-40af-9843-d6b24b735559"
        }
    ],
    "eventType": "AwsApiCall",
    "managementEvent": true,
    "recipientAccountId": "123456789012",
    "sharedEventID": "bf36027c-86bd-40f2-a561-960cbe148c4c",
    "eventCategory": "Management"
}</code></pre> 
<h2>Conclusion</h2> 
<p>With the use of AWS KMS customer managed keys, you can now meet your security requirements for your data inside your Amazon ECS workloads running on AWS Fargate.</p> 
<p>To learn more about compliance on your Amazon ECS workloads you can reference the&nbsp;<a href="https://aws.amazon.com/blogs/industries/fsi-service-spotlight-amazon-elastic-container-service-ecs-with-aws-fargate/" rel="noopener" target="_blank">FSI Services Spotlight: Amazon Elastic Container Service (ECS) with AWS Fargate blog post</a>&nbsp;or the <a href="https://d1.awsstatic.com/whitepapers/AWS_Fargate_Security_Overview_Whitepaper.pdf" rel="noopener" target="_blank">security overview of AWS Fargate whitepaper</a>. To learn more about the use of customer managed keys in AWS Fargate, refer to the <a href="https://docs.aws.amazon.com/AmazonECS/latest/developerguide/fargate-task-storage.html" rel="noopener" target="_blank">AWS documentation</a>.&nbsp;This feature was <a href="https://github.com/aws/containers-roadmap/issues/915" rel="noopener" target="_blank">requested</a> by our customers on the <a href="https://github.com/aws/containers-roadmap/" rel="noopener" target="_blank">AWS Containers roadmap</a>.</p>
