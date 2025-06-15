# Assignment-2.13
# Comparison between Serverless Framework and Terraform as tools for IaC

## What type of infrastructure and application deployments are each tool best suited for?

### Serverless Framework

- Serverless applications (AWS Lambda, API Gateway, EventBridge)
- Event-driven architectures (e.g., real-time processing, microservices)
- Rapid deployment of cloud functions with minimal infra management

### Terraform

- Multi-cloud or hybrid cloud infrastructure (AWS, Azure, GCP, on-prem)
- Stateful resources (VMs, databases, Kubernetes clusters, networking)
- Complex, long-lived infrastructure with dependencies

## How do their primary objectives differ?

### Serverless Framework

- Simplify serverless application deployment by abstracting cloud provider APIs.

### Terraform

- Provide declarative infrastructure orchestration across any cloud/service.

## How do they differ in terms of learning curve and ease of use for developers or DevOps teams?

### Serverless Framework

#### Learning Curve

- Low (for serverless developers)

#### Ease of Use

- Simple YAML/JS configs.
- Built-in CLI for deployments.

### Terraform

#### Learning Curve

- Moderate to steep (requires understanding of IaC concepts, providers, state management.)

#### Ease of Use

- HCL syntax is verbose.
- Requires manual state management.

## What are the differences in how each tool handles state tracking and deployment changes?

### Serverless Framework

#### State Tracking

- No native state tracking.
- Relies on cloud provider’s APIs for updates.

#### Deployment Changes

- Atomic deployments (rollback on failure).
- Limited drift detection.

### Terraform

#### State Tracking

- Tracks state in files (local/remote).
- Detects and reconciles drift.

#### Deployment Changes

- Plan/Apply workflow for safe changes.
- Explicit dependency resolution.

## In what scenarios would you recommend using Serverless Framework over Terraform, and vice versa?

### Serverless Framework

- Deploying AWS Lambda functions quickly as it abstracts AWS complexity.

### Terraform

- Setting up a multi-cloud Kubernetes cluster for cross cloud support and modular resource definitions.

### Both

- Event-driven app with SQS/DynamoDB as serverless framework manages ephemeral functions (e.g., Lambda), while Terraform provisions stateful resources (e.g., RDS, S3).
- Terraform deploys the VPC, RDS, and S3 buckets. Then use serverless Framework to deploys Lambda functions triggered by S3 events.

## Are there scenarios where using both together might be beneficial?

- Leverage Serverless’s simplicity for functions + Terraform’s robustness for infra.
- Avoid Terraform’s limitations with serverless (e.g., slow Lambda updates).
