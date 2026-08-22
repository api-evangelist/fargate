# AWS Fargate (fargate)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

AWS Fargate is a serverless, pay-as-you-go compute engine for containers that works with Amazon Elastic Container Service (ECS) and Amazon Elastic Kubernetes Service (EKS). It removes the need to provision and manage servers, letting you focus on building and running applications without managing infrastructure.

**APIs.json:** [https://aws.amazon.com/fargate/](https://aws.amazon.com/fargate/)

## Tags

- Compute
- Containers
- Docker
- Kubernetes
- Serverless

## Timestamps

- **Created:** 2024-01-01
- **Modified:** 2026-05-19

## APIs

### Amazon ECS API (Fargate)

The Amazon ECS API provides programmatic access to manage Fargate tasks and services through Amazon Elastic Container Service. It supports creating and managing clusters, task definitions, services, and container instances using the Fargate launch type for serverless container execution.

- **Human URL:** [https://docs.aws.amazon.com/AmazonECS/latest/APIReference/](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/)
- **Base URL:** `https://ecs.{region}.amazonaws.com`

#### Tags

- Containers
- ECS
- Fargate
- Orchestration
- Serverless

#### Properties

- [Documentation](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/AWS_Fargate.html)
- [OpenAPI](https://api.apis.guru/v2/specs/amazonaws.com/ecs/2014-11-13/openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](https://raw.githubusercontent.com/api-evangelist/fargate/refs/heads/main/openapi/fargate-ecs-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/Welcome.html)
- [A P I  Operations](https://docs.aws.amazon.com/AmazonECS/latest/APIReference/API_Operations.html)
- [Getting Started](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/getting-started-fargate.html)
- [Pricing](https://aws.amazon.com/fargate/pricing/)
- [Developer  Guide](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/Welcome.html)
- [C L I  Reference](https://docs.aws.amazon.com/cli/latest/reference/ecs/)
- [S D Ks](https://aws.amazon.com/tools/)
- [Platform  Versions](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform-fargate.html)
- [Changelog](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform-versions-changelog.html)
- [Service  Quotas](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-quotas.html)
- [Security](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/security-fargate.html)
- [Monitoring](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/monitoring-fargate-usage.html)
- [Container  Insights](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/cloudwatch-container-insights.html)
- [Troubleshooting](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/troubleshooting.html)
- [Best  Practices](https://docs.aws.amazon.com/AmazonECS/latest/bestpracticesguide/intro.html)
- [Windows  Containers](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/windows-considerations.html)
- [E C S  Exec](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/ecs-exec.html)
- [Postman Collection](collections/fargate-ecs.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fargate-ecs.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Amazon EKS API (Fargate)

The Amazon EKS API provides programmatic access to manage Fargate pods through Amazon Elastic Kubernetes Service. It supports creating Fargate profiles that define which Kubernetes pods run on Fargate infrastructure, enabling serverless Kubernetes workloads without managing nodes.

- **Human URL:** [https://docs.aws.amazon.com/eks/latest/APIReference/](https://docs.aws.amazon.com/eks/latest/APIReference/)
- **Base URL:** `https://eks.{region}.amazonaws.com`

#### Tags

- Containers
- EKS
- Fargate
- Kubernetes
- Serverless

#### Properties

- [Documentation](https://docs.aws.amazon.com/eks/latest/userguide/fargate.html)
- [OpenAPI](https://api.apis.guru/v2/specs/amazonaws.com/eks/2017-11-01/openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [API Reference](https://docs.aws.amazon.com/eks/latest/APIReference/Welcome.html)
- [Getting Started](https://docs.aws.amazon.com/eks/latest/userguide/fargate-getting-started.html)
- [Pricing](https://aws.amazon.com/fargate/pricing/)
- [Fargate  Profiles](https://docs.aws.amazon.com/eks/latest/userguide/fargate-profile.html)
- [Pod  Configuration](https://docs.aws.amazon.com/eks/latest/userguide/fargate-pod-configuration.html)
- [Pod  Execution  Role](https://docs.aws.amazon.com/eks/latest/userguide/pod-execution-role.html)
- [C L I  Reference](https://docs.aws.amazon.com/cli/latest/reference/eks/create-fargate-profile.html)
- [S D Ks](https://aws.amazon.com/tools/)
- [Postman Collection](collections/fargate-ecs.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/fargate-ecs.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://aws.amazon.com/fargate/)
- [Documentation](https://aws.amazon.com/documentation-overview/fargate/)
- [Features](https://aws.amazon.com/fargate/features/)
- [Pricing](https://aws.amazon.com/fargate/pricing/)
- [Getting Started](https://aws.amazon.com/fargate/getting-started/)
- [F A Q](https://aws.amazon.com/fargate/faqs/)
- [Customers](https://aws.amazon.com/fargate/customers/)
- [Partners](https://aws.amazon.com/fargate/partners/)
- [Console](https://console.aws.amazon.com/ecs/)
- [Authentication](https://docs.aws.amazon.com/general/latest/gr/signature-version-4.html)
- [S D Ks](https://aws.amazon.com/tools/)
- [C L I](https://aws.amazon.com/cli/)
- [Status Page](https://status.aws.amazon.com/)
- [Blog](https://aws.amazon.com/blogs/compute/category/compute/aws-fargate/)
- [Terms of Service](https://aws.amazon.com/service-terms/)
- [Privacy Policy](https://aws.amazon.com/privacy/)
- [S L A](https://aws.amazon.com/ecs/sla/)
- [Support](https://aws.amazon.com/premiumsupport/)
- [Knowledge  Center](https://repost.aws/tags/TAd-wgX2x3QgSxyelEN6raFg/amazon-elastic-container-service)
- [Security](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/security-fargate.html)
- [Security  Whitepaper](https://d1.awsstatic.com/whitepapers/AWS_Fargate_Security_Overview_Whitepaper.pdf)
- [GitHub Organization](https://github.com/aws-containers)
- [GitHub Repository](https://github.com/aws/containers-roadmap)
- [Changelog](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/platform-versions-changelog.html)
- [Service  Quotas](https://docs.aws.amazon.com/AmazonECS/latest/developerguide/service-quotas.html)
- [Integrations](https://aws.amazon.com/marketplace)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
