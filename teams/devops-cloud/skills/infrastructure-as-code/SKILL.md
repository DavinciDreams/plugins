---
name: infrastructure-as-code
description: Terraform, CloudFormation, ARM templates, Kubernetes manifests, and state management best practices
---

# Infrastructure as Code

## Terraform Best Practices and Patterns

### Core Concepts
- **Declarative Syntax**: Describe desired state, not execution steps
- **State Management**: Terraform state tracks infrastructure resources
- **Providers**: Plugins for interacting with cloud providers and services
- **Modules**: Reusable components for infrastructure

### Best Practices
- **State Management**
  - Use remote state (S3, Azure Storage, GCS) for collaboration
  - Enable state locking with DynamoDB, Azure Blob lease, or GCS lock
  - Separate state files by environment (dev, staging, prod)
  - Use state workspaces for environment isolation
  - Implement state versioning and backups

- **Module Structure**
  - Use modules for reusable infrastructure components
  - Follow standard module structure: `main.tf`, `variables.tf`, `outputs.tf`
  - Document modules with README.md
  - Version control modules in separate repositories
  - Use module registries for sharing

- **Resource Naming**
  - Use consistent naming conventions
  - Include environment and region in resource names
  - Use `name_prefix` or `name_suffix` for dynamic naming
  - Avoid hard-coded names where possible

- **Variables and Outputs**
  - Use variables for configurable values
  - Provide sensible defaults for non-critical variables
  - Use variable validation for type checking
  - Output important resource attributes for other modules to consume

- **Provider Configuration**
  - Use provider blocks for cloud provider authentication
  - Configure provider regions and endpoints
  - Use provider aliases for multi-region or multi-cloud deployments
  - Store provider credentials securely (environment variables, vault)

### Terraform Patterns
- **Multi-Environment Pattern**: Use workspaces or separate state files
- **Multi-Region Pattern**: Use provider aliases and module replication
- **Multi-Cloud Pattern**: Use multiple providers and provider aliases
- **GitOps Pattern**: Use Terraform with GitOps tools (Atlantis, TF-Controller)
- **Zero-Downtime Pattern**: Use `create_before_destroy` and lifecycle rules

### Terraform Commands
- `terraform init`: Initialize working directory and download providers
- `terraform plan`: Preview changes before applying
- `terraform apply`: Apply configuration changes
- `terraform destroy`: Destroy infrastructure
- `terraform import`: Import existing resources into state
- `terraform state mv`: Move resources in state
- `terraform refresh`: Update state file with real resources

## AWS CloudFormation Templates

### Core Concepts
- **Templates**: JSON or YAML files describing AWS resources
- **Stacks**: Collections of resources managed as a single unit
- **Change Sets**: Preview changes before executing
- **Parameters**: Input values for template customization
- **Outputs**: Values returned after stack creation

### Best Practices
- **Template Organization**
  - Use YAML for better readability
  - Use nested stacks for modularity
  - Use CloudFormation exports for cross-stack references
  - Use intrinsic functions for dynamic values
  - Use mappings for environment-specific values

- **Resource Management**
  - Use DeletionPolicy for resource protection
  - Use UpdateReplacePolicy for resource replacement behavior
  - Use DependsOn for explicit resource dependencies
  - Use CreationPolicy and UpdatePolicy for resource lifecycle management

- **Parameter and Output Design**
  - Use parameters for configurable values
  - Use parameter constraints for validation
  - Use default values for non-critical parameters
  - Output important resource attributes

- **Change Set Management**
  - Always create change sets before updating stacks
  - Review change sets carefully before execution
  - Use change sets for zero-downtime deployments
  - Cancel change sets if changes are unexpected

### CloudFormation Intrinsic Functions
- `!Ref`: Reference parameters or resources
- `!GetAtt`: Get resource attributes
- `!Sub`: String substitution
- `!Join`: Join strings with a delimiter
- `!Select`: Select from a list
- `!Split`: Split a string into a list
- `!If`: Conditional logic
- `!Equals`: Compare values
- `!And`, `!Or`, `!Not`: Boolean logic
- `!FindInMap`: Look up values in a mapping
- `!ImportValue`: Import exported values from other stacks

## Azure ARM Templates

### Core Concepts
- **Templates**: JSON files describing Azure resources
- **Resource Groups**: Logical containers for Azure resources
- **Deployments**: Operations to create or update resources
- **Parameters**: Input values for template customization
- **Variables**: Internal values for template logic

### Best Practices
- **Template Structure**
  - Use parameter files for environment-specific values
  - Use linked templates for modularity
  - Use deployment scripts for post-deployment actions
  - Use template specs for reusability
  - Use Azure Blueprints for governance

- **Resource Management**
  - Use dependsOn for explicit dependencies
  - Use copy loops for multiple resource instances
  - Use deployment mode (incremental vs complete)
  - Use resource identity for managed identities

- **Parameter and Variable Design**
  - Use parameters for external configuration
  - Use variables for internal calculations
  - Use parameter decorators for validation
  - Use secure strings for sensitive values

### ARM Template Functions
- `parameters()`: Reference parameters
- `variables()`: Reference variables
- `reference()`: Get resource properties
- `concat()`: Concatenate strings
- `substring()`: Extract substring
- `replace()`: Replace string
- `toUpper()`, `toLower()`: Case conversion
- `uniqueString()`: Generate unique strings
- `resourceId()`: Get resource ID
- `subscription()`, `resourceGroup()`: Get deployment scope

## Kubernetes Manifests and Helm Charts

### Kubernetes Manifests
- **Core Concepts**
  - YAML files describing Kubernetes resources
  - Declarative configuration for pods, services, deployments, etc.
  - Use kubectl for applying manifests

- **Best Practices**
  - Use labels and selectors for resource organization
  - Use namespaces for resource isolation
  - Use resource requests and limits for resource management
  - Use liveness and readiness probes for health checks
  - Use ConfigMaps and Secrets for configuration
  - Use persistent volumes for data persistence
  - Use services for service discovery
  - Use ingress for external access

- **Common Resources**
  - Pod: Smallest deployable unit
  - Deployment: Manages replica sets and pods
  - Service: Exposes pods as network services
  - ConfigMap: Stores configuration data
  - Secret: Stores sensitive data
  - PersistentVolumeClaim: Claims storage
  - Ingress: Manages external access to services
  - Namespace: Logical partition for resources

### Helm Charts
- **Core Concepts**
  - Helm is a package manager for Kubernetes
  - Charts are packages of Kubernetes manifests
  - Values files for chart customization
  - Templates for dynamic manifest generation

- **Best Practices**
  - Use semantic versioning for chart versions
  - Use Chart.yaml for chart metadata
  - Use values.yaml for default values
  - Use values files for environment-specific configuration
  - Use templates for dynamic manifest generation
  - Use Helm hooks for lifecycle events
  - Use chart dependencies for modularity
  - Document charts with README.md

- **Helm Commands**
  - `helm create`: Create a new chart
  - `helm install`: Install a chart
  - `helm upgrade`: Upgrade a release
  - `helm uninstall`: Uninstall a release
  - `helm template`: Render templates
  - `helm lint`: Validate charts
  - `helm repo add`: Add chart repository

## Ansible Playbooks

### Core Concepts
- **Playbooks**: YAML files describing automation tasks
- **Modules**: Reusable units of work
- **Inventory**: List of managed hosts
- **Roles**: Organized collections of playbooks, tasks, and files

### Best Practices
- **Playbook Structure**
  - Use descriptive playbook names
  - Use roles for modularity
  - Use handlers for service restarts
  - Use tags for selective execution
  - Use variables for configuration

- **Task Design**
  - Use idempotent modules
  - Use become for privilege escalation
  - Use when for conditional execution
  - Use loop for iteration
  - Use register for capturing output

- **Inventory Management**
  - Use dynamic inventory for cloud resources
  - Use inventory groups for host organization
  - Use host variables for host-specific configuration
  - Use group variables for group-specific configuration

## State Management and Drift Detection

### State Management
- **Terraform State**
  - Use remote state for collaboration
  - Enable state locking
  - Implement state backups
  - Use state workspaces for isolation
  - Implement state versioning

- **CloudFormation Stack State**
  - Use stack sets for multi-account deployments
  - Use stack policies for resource protection
  - Use drift detection for configuration changes
  - Use stack notifications for events

- **Kubernetes State**
  - Use GitOps for desired state management
  - Use controllers for reconciliation
  - Use operators for complex applications
  - Use admission controllers for validation

### Drift Detection
- **Terraform Drift**
  - Use `terraform plan` to detect drift
  - Use `terraform refresh` to update state
  - Implement automated drift detection
  - Use drift detection tools (tfsec, checkov)

- **CloudFormation Drift Detection**
  - Enable drift detection for stacks
  - Use AWS Config for compliance monitoring
  - Implement automated drift remediation
  - Use AWS CloudTrail for audit logging

- **Kubernetes Drift**
  - Use tools like OPA Gatekeeper for policy enforcement
  - Use tools like Kyverno for validation
  - Use tools like Argo CD for GitOps and drift detection
  - Implement admission webhooks for validation

## Security Considerations

- **Secrets Management**
  - Use secret stores (Vault, AWS Secrets Manager, Azure Key Vault)
  - Never commit secrets to version control
  - Use environment variables or secret injection
  - Rotate secrets regularly

- **Access Control**
  - Use IAM roles and policies for access control
  - Implement least privilege access
  - Use service accounts for application access
  - Use temporary credentials where possible

- **Compliance**
  - Use security scanning tools (tfsec, checkov, kube-bench)
  - Implement policy as code (OPA, Sentinel)
  - Use audit logging for compliance
  - Regular security reviews
