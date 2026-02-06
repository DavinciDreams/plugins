---
name: cloud-platforms
description: AWS, Azure, and GCP cloud services and best practices
---

# Cloud Platforms

## AWS Services and Best Practices

### Compute Services
- **EC2 (Elastic Compute Cloud)**: Virtual servers in the cloud
  - Use instance types appropriate for workload requirements
  - Implement Auto Scaling Groups for elasticity
  - Use Spot Instances for fault-tolerant, interruptible workloads
  - Leverage EC2 Fleet for diverse instance strategies
  
- **Lambda**: Serverless compute service
  - Ideal for event-driven architectures
  - Use for short-lived, stateless functions
  - Implement dead-letter queues for failed invocations
  - Monitor with CloudWatch metrics and logs

- **ECS (Elastic Container Service)**: Container orchestration
  - Use Fargate for serverless container execution
  - Implement task definitions with resource limits
  - Use service auto-scaling based on metrics
  - Configure load balancing with ALB/NLB

- **EKS (Elastic Kubernetes Service)**: Managed Kubernetes
  - Use managed node groups for simplified operations
  - Implement pod autoscaling (HPA, VPA)
  - Use AWS VPC CNI for networking
  - Integrate with IAM for service accounts

### Storage Services
- **S3 (Simple Storage Service)**: Object storage
  - Use lifecycle policies for cost optimization
  - Implement versioning for data protection
  - Use S3 Transfer Acceleration for faster uploads
  - Configure CORS for cross-origin access
  - Enable S3 Event Notifications for automation

- **EBS (Elastic Block Store)**: Block storage
  - Choose volume type based on workload (gp3, io2, etc.)
  - Use multi-attach for high availability
  - Implement snapshots for backup
  - Monitor volume metrics for performance

### Database Services
- **RDS (Relational Database Service)**: Managed relational databases
  - Use Multi-AZ deployments for high availability
  - Enable read replicas for scaling reads
  - Use automated backups and point-in-time recovery
  - Implement parameter groups for configuration

- **DynamoDB**: NoSQL database
  - Design partition keys for even distribution
  - Use on-demand mode for unpredictable workloads
  - Implement TTL for automatic data expiration
  - Use DynamoDB Accelerator (DAX) for caching

### Infrastructure as Code
- **CloudFormation**: AWS native IaC
  - Use stacks for resource organization
  - Implement nested stacks for modularity
  - Use change sets for safe updates
  - Leverage CloudFormation exports for cross-stack references

### Networking
- **VPC (Virtual Private Cloud)**: Isolated network environment
  - Use public and private subnets for tiered architecture
  - Implement NAT Gateways for private subnet outbound access
  - Use VPC endpoints for private connectivity to AWS services
  - Configure route tables and security groups properly

## Azure Services and Best Practices

### Compute Services
- **Azure Virtual Machines**: Virtual servers
  - Use managed disks for storage
  - Implement availability sets for high availability
  - Use Azure Spot VMs for cost savings
  - Configure extensions for monitoring and management

- **Azure Functions**: Serverless compute
  - Use Consumption plan for event-driven workloads
  - Implement Durable Functions for stateful orchestrations
  - Use Application Insights for monitoring
  - Configure function app scaling

- **Azure Kubernetes Service (AKS)**: Managed Kubernetes
  - Use Azure CNI for advanced networking
  - Implement cluster autoscaler
  - Use Azure AD integration for authentication
  - Configure pod identity for secure access to Azure resources

### Storage Services
- **Azure Blob Storage**: Object storage
  - Use access tiers (Hot, Cool, Archive) for cost optimization
  - Implement lifecycle management policies
  - Use blob versioning for data protection
  - Configure CORS and shared access signatures

- **Azure Disk Storage**: Block storage
  - Choose disk type based on workload (Premium SSD, Ultra Disk)
  - Use Azure Disk Encryption for data at rest
  - Implement snapshots for backup
  - Monitor disk performance metrics

### Database Services
- **Azure SQL Database**: Managed SQL database
  - Use vCore-based or DTU-based purchasing models
  - Implement geo-replication for disaster recovery
  - Use transparent data encryption
  - Configure automatic backups

- **Azure Cosmos DB**: Globally distributed NoSQL database
  - Choose appropriate API (SQL, MongoDB, Cassandra, etc.)
  - Use multi-master replication for global availability
  - Implement consistency levels based on requirements
  - Use throughput provisioning with RU/s

### Infrastructure as Code
- **Azure Resource Manager (ARM) Templates**: Azure native IaC
  - Use parameter files for environment-specific configurations
  - Implement linked templates for modularity
  - Use deployment scripts for post-deployment actions
  - Leverage template specs for reusability

### Networking
- **Azure Virtual Network (VNet)**: Isolated network
  - Use subnets for network segmentation
  - Implement NSGs for security rules
  - Use Azure Firewall for network protection
  - Configure VNet peering for connectivity

## GCP Services and Best Practices

### Compute Services
- **Compute Engine**: Virtual machines
  - Use custom machine types for optimized workloads
  - Implement instance groups for auto-scaling
  - Use preemptible VMs for cost savings
  - Configure startup and shutdown scripts

- **Cloud Functions**: Serverless compute
  - Use 2nd generation functions for better performance
  - Implement event triggers for automation
  - Use Cloud Logging and Cloud Monitoring
  - Configure function deployment settings

- **Google Kubernetes Engine (GKE)**: Managed Kubernetes
  - Use Autopilot for fully managed clusters
  - Implement node auto-provisioning
  - Use Workload Identity for secure access
  - Configure network policies for pod security

### Storage Services
- **Cloud Storage**: Object storage
  - Use storage classes (Standard, Nearline, Coldline, Archive)
  - Implement lifecycle management rules
  - Use object versioning for data protection
  - Configure signed URLs and ACLs

- **Persistent Disks**: Block storage
  - Choose disk type (Standard, Balanced, Extreme)
  - Use regional disks for high availability
  - Implement snapshots for backup
  - Monitor disk I/O and throughput

### Database Services
- **Cloud SQL**: Managed relational databases
  - Use high availability configuration
  - Implement read replicas for scaling
  - Use automated backups and point-in-time recovery
  - Configure SSL/TLS connections

- **Cloud Spanner**: Globally distributed SQL database
  - Use multi-region configuration for global availability
  - Design schema for optimal performance
  - Implement instance sizing and scaling
  - Use database roles for access control

### Infrastructure as Code
- **Deployment Manager**: GCP native IaC
  - Use Jinja or Python templates
  - Implement composite types for reusability
  - Use deployment manifests for organization
  - Configure preview deployments

### Networking
- **Virtual Private Cloud (VPC)**: Isolated network
  - Use subnets for network segmentation
  - Implement VPC peering for connectivity
  - Use Cloud NAT for private subnet outbound access
  - Configure firewall rules for security

## Multi-Cloud Strategies and Considerations

### Multi-Cloud Approaches
- **Multi-Cloud for Resilience**: Distribute workloads across providers for disaster recovery
- **Best-of-Breed Services**: Use specific services from each provider based on strengths
- **Vendor Lockout Mitigation**: Avoid single-provider dependencies
- **Cost Optimization**: Leverage competitive pricing and spot markets

### Multi-Cloud Challenges
- **Complexity**: Increased operational complexity and management overhead
- **Consistency**: Maintaining consistency across different platforms
- **Networking**: Cross-cloud connectivity and latency considerations
- **Identity and Access Management**: Unified identity across providers

### Multi-Cloud Best Practices
- **Abstraction Layers**: Use abstraction layers (Terraform, Pulumi) for multi-cloud deployments
- **Standardization**: Standardize on common tools and practices
- **Observability**: Implement unified monitoring and logging across clouds
- **Security**: Implement consistent security policies across all platforms
