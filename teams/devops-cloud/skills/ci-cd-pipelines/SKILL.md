---
name: ci-cd-pipelines
description: GitHub Actions, GitLab CI/CD, Jenkins, Azure DevOps, build and test strategies, and deployment patterns
---

# CI/CD Pipelines

## GitHub Actions Workflows

### Core Concepts
- **Workflows**: YAML files defining automation processes
- **Events**: Triggers for workflow execution (push, pull_request, schedule)
- **Jobs**: Collections of steps that run on the same runner
- **Steps**: Individual tasks within a job
- **Actions**: Reusable components for common tasks

### Best Practices
- **Workflow Organization**
  - Use separate workflows for different concerns (CI, CD, release)
  - Use workflow templates for consistency
  - Use composite actions for reusable steps
  - Use reusable workflows for shared pipeline logic
  - Use matrix strategy for testing across multiple configurations

- **Job Optimization**
  - Use caching for dependencies and build artifacts
  - Use parallel jobs for faster execution
  - Use job dependencies for sequential execution
  - Use artifacts for passing data between jobs
  - Use self-hosted runners for custom environments

- **Security**
  - Use secrets for sensitive data
  - Use environments for deployment protection
  - Use required reviews for critical deployments
  - Use OIDC for cloud provider authentication
  - Use branch protection rules

### GitHub Actions Examples
```yaml
name: CI/CD Pipeline

on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  test:
    runs-on: ubuntu-latest
    strategy:
      matrix:
        node-version: [14.x, 16.x, 18.x]
    steps:
      - uses: actions/checkout@v3
      - name: Use Node.js ${{ matrix.node-version }}
        uses: actions/setup-node@v3
        with:
          node-version: ${{ matrix.node-version }}
          cache: 'npm'
      - run: npm ci
      - run: npm test
      - run: npm run build

  deploy:
    needs: test
    runs-on: ubuntu-latest
    if: github.ref == 'refs/heads/main'
    steps:
      - uses: actions/checkout@v3
      - name: Deploy to production
        run: |
          # Deployment commands
```

## GitLab CI/CD Pipelines

### Core Concepts
- **Pipelines**: Series of jobs executed in stages
- **Stages**: Logical grouping of jobs
- **Jobs**: Individual tasks that execute scripts
- **Runners**: Agents that execute jobs
- **Artifacts**: Files passed between jobs

### Best Practices
- **Pipeline Configuration**
  - Use `.gitlab-ci.yml` for pipeline definition
  - Use stages for logical job grouping
  - Use only/except rules for job execution control
  - Use rules for more complex conditions
  - Use needs for job dependencies

- **Job Optimization**
  - Use artifacts for passing data between jobs
  - Use cache for dependency caching
  - Use parallel jobs for faster execution
  - Use retry for transient failures
  - Use timeout for job duration limits

- **Security**
  - Use CI/CD variables for sensitive data
  - Use protected variables for protected branches
  - Use masked variables for hiding values
  - Use environments for deployment control
  - Use approval rules for critical deployments

### GitLab CI/CD Examples
```yaml
stages:
  - test
  - build
  - deploy

test:
  stage: test
  image: node:18
  script:
    - npm ci
    - npm test
  parallel:
    matrix:
      - NODE_VERSION: [14, 16, 18]
  cache:
    paths:
      - node_modules/

build:
  stage: build
  image: node:18
  script:
    - npm ci
    - npm run build
  artifacts:
    paths:
      - dist/

deploy:
  stage: deploy
  image: node:18
  script:
    - npm install -g serverless
    - serverless deploy
  only:
    - main
  when: manual
```

## Jenkins Pipelines

### Core Concepts
- **Pipelines**: Groovy scripts defining automation
- **Stages**: Logical grouping of steps
- **Steps**: Individual operations
- **Agents**: Nodes where pipeline runs
- **Credentials**: Secure storage for secrets

### Best Practices
- **Pipeline Design**
  - Use Declarative Pipeline syntax
  - Use shared libraries for reusable code
  - Use pipeline stages for logical organization
  - Use when conditions for conditional execution
  - Use post sections for cleanup and notifications

- **Agent Management**
  - Use labels for agent selection
  - Use Docker agents for consistent environments
  - Use Kubernetes agents for dynamic scaling
  - Use agent none for lightweight pipelines
  - Use stash/unstash for passing data

- **Security**
  - Use credentials binding for secrets
  - Use credential scopes for access control
  - Use approval steps for manual gates
  - Use input steps for user interaction
  - Use role-based strategy for permissions

### Jenkins Pipeline Examples
```groovy
pipeline {
    agent any
    
    stages {
        stage('Test') {
            parallel {
                stage('Node 14') {
                    agent { docker { image 'node:14' } }
                    steps {
                        sh 'npm ci'
                        sh 'npm test'
                    }
                }
                stage('Node 16') {
                    agent { docker { image 'node:16' } }
                    steps {
                        sh 'npm ci'
                        sh 'npm test'
                    }
                }
            }
        }
        
        stage('Build') {
            agent { docker { image 'node:18' } }
            steps {
                sh 'npm ci'
                sh 'npm run build'
                archiveArtifacts artifacts: 'dist/**'
            }
        }
        
        stage('Deploy') {
            when {
                branch 'main'
            }
            steps {
                input message: 'Deploy to production?', ok: 'Deploy'
                sh 'npm install -g serverless'
                sh 'serverless deploy'
            }
        }
    }
    
    post {
        always {
            cleanWs()
        }
        success {
            emailext subject: 'Build Success',
                body: 'The build completed successfully.',
                to: 'team@example.com'
        }
        failure {
            emailext subject: 'Build Failed',
                body: 'The build failed.',
                to: 'team@example.com'
        }
    }
}
```

## Azure DevOps Pipelines

### Core Concepts
- **Pipelines**: YAML or GUI-defined automation
- **Stages**: Major divisions in a pipeline
- **Jobs**: Units of work within a stage
- **Tasks**: Pre-built units of work
- **Agents**: Machines that run jobs

### Best Practices
- **Pipeline Configuration**
  - Use YAML pipelines for version control
  - Use templates for reusable pipeline logic
  - Use parameters for pipeline customization
  - Use variables for configuration values
  - Use stages for environment separation

- **Job Optimization**
  - Use parallel jobs for faster execution
  - Use artifacts for passing data between jobs
  - Use caching for dependency caching
  - Use matrix strategy for multiple configurations
  - Use demands for agent selection

- **Security**
  - Use secret variables for sensitive data
  - Use variable groups for organization
   - Use key vault for secret management
  - Use environment checks for deployment control
  - Use approval gates for manual intervention

### Azure DevOps Pipeline Examples
```yaml
trigger:
- main
- develop

pool:
  vmImage: 'ubuntu-latest'

stages:
- stage: Test
  jobs:
  - job: Test
    strategy:
      matrix:
        Node_14:
          node_version: 14.x
        Node_16:
          node_version: 16.x
        Node_18:
          node_version: 18.x
    steps:
    - task: UseNode@1
      inputs:
        versionSpec: $(node_version)
    - script: |
        npm ci
        npm test
      displayName: 'Install dependencies and run tests'

- stage: Build
  dependsOn: Test
  jobs:
  - job: Build
    steps:
    - task: UseNode@1
      inputs:
        versionSpec: '18.x'
    - script: |
        npm ci
        npm run build
      displayName: 'Build application'
    - publish: dist
      artifact: dist

- stage: Deploy
  dependsOn: Build
  condition: and(succeeded(), eq(variables['Build.SourceBranch'], 'refs/heads/main'))
  jobs:
  - deployment: Deploy
    environment: 'production'
    strategy:
      runOnce:
        deploy:
          steps:
          - script: |
              npm install -g serverless
              serverless deploy
            displayName: 'Deploy to production'
```

## Build and Test Strategies

### Build Strategies
- **Incremental Builds**: Build only changed components
- **Parallel Builds**: Build multiple components simultaneously
- **Matrix Builds**: Build across multiple configurations
- **Cached Builds**: Use cache for faster builds
- **Docker Builds**: Use Docker for consistent build environments

### Test Strategies
- **Unit Tests**: Test individual components in isolation
- **Integration Tests**: Test component interactions
- **End-to-End Tests**: Test complete user flows
- **Performance Tests**: Test system performance
- **Security Tests**: Test for security vulnerabilities

### Quality Gates
- **Code Coverage**: Minimum code coverage threshold
- **Linting**: Code style and quality checks
- **Static Analysis**: Security and vulnerability scanning
- **Dependency Scanning**: Check for vulnerable dependencies
- **License Compliance**: Check for license compliance

## Deployment Patterns

### Blue-Green Deployment
- **Concept**: Maintain two identical production environments
- **Benefits**: Zero downtime, instant rollback
- **Implementation**: Switch traffic between blue and green environments
- **Best Practices**: Use load balancers for traffic switching, test green environment before switching

### Canary Deployment
- **Concept**: Gradually roll out changes to a subset of users
- **Benefits**: Reduced risk, gradual feedback
- **Implementation**: Route small percentage of traffic to new version
- **Best Practices**: Monitor metrics closely, have rollback plan ready

### Rolling Deployment
- **Concept**: Replace instances one at a time
- **Benefits**: Gradual rollout, minimal downtime
- **Implementation**: Update instances in batches
- **Best Practices**: Use health checks, monitor for failures

### Feature Flags
- **Concept**: Enable/disable features without deployment
- **Benefits**: Gradual rollout, instant rollback
- **Implementation**: Use feature flag management system
- **Best Practices**: Keep flags temporary, clean up old flags

### Immutable Infrastructure
- **Concept**: Replace rather than modify infrastructure
- **Benefits**: Consistency, easier rollback, no configuration drift
- **Implementation**: Use infrastructure as code, replace instances on updates
- **Best Practices**: Version all infrastructure, use golden images

## Pipeline Orchestration

### Pipeline Dependencies
- **Sequential Execution**: Jobs run in sequence
- **Parallel Execution**: Jobs run simultaneously
- **Conditional Execution**: Jobs run based on conditions
- **Artifact Passing**: Pass data between jobs
- **Environment Promotion**: Promote through environments

### Pipeline Triggers
- **Push Triggers**: Run on code push
- **Pull Request Triggers**: Run on pull requests
- **Schedule Triggers**: Run on schedule
- **Manual Triggers**: Run on demand
- **Webhook Triggers**: Run on webhook events

### Pipeline Notifications
- **Email Notifications**: Send email on pipeline events
- **Slack Notifications**: Send Slack messages on pipeline events
- **Microsoft Teams Notifications**: Send Teams messages on pipeline events
- **Custom Webhooks**: Send custom webhook notifications
- **Status Badges**: Display pipeline status as badges

## Pipeline Security

### Secrets Management
- **Secret Variables**: Store secrets as pipeline variables
- **Secret Stores**: Use secret stores (Vault, AWS Secrets Manager)
- **OIDC Authentication**: Use OIDC for cloud provider authentication
- **Key Vault**: Use key vault for secret management
- **Secret Rotation**: Rotate secrets regularly

### Access Control
- **Branch Protection**: Protect branches from direct pushes
- **Pull Request Reviews**: Require reviews for merges
- **Environment Approvals**: Require approvals for deployments
- **Role-Based Access**: Use RBAC for pipeline access
- **Audit Logging**: Enable audit logging for compliance

### Supply Chain Security
- **Dependency Scanning**: Scan for vulnerable dependencies
- **Container Scanning**: Scan container images for vulnerabilities
- **SBOM Generation**: Generate software bill of materials
- **Code Signing**: Sign artifacts for integrity
- **Policy Enforcement**: Enforce policies with tools like OPA
