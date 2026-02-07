# Atlas Agents - Claude Code Plugin Marketplace

Agent team plugins for Claude Code. Each team is a pre-configured group of specialized agents that collaborate through phased workflows to deliver high-quality results.

## 📋 Quick Reference

| Team | Description | Agents | Primary Focus |
|------|-------------|--------|---------------|
| [fullstack-dev](#fullstack-dev) | Full-stack development | 5 | Frontend, Backend, QA, DevOps |
| [game-dev](#game-dev) | Multi-engine game development | 6 | Unity, Unreal, Godot, Three.js, Orleans |
| [marketing-seo](#marketing-seo) | Marketing, SEO, and social media | 5 | Content creation, SEO, engagement |
| [data-science](#data-science) | Data science and ML | 5 | Data analysis, ML models, MLOps |
| [devops-cloud](#devops-cloud) | DevOps and cloud infrastructure | 5 | CI/CD, deployment, observability |
| [design-ux](#design-ux) | Design and UX | 5 | User research, UI/UX, accessibility |
| [security](#security) | Security and compliance | 5 | Code security, vulnerability scanning |
| [documentation](#documentation) | Technical documentation | 5 | API docs, tutorials, guides |
| [qa-testing](#qa-testing) | QA and testing | 5 | Automated testing, performance, quality |

---

## 🚀 Available Teams

### fullstack-dev

**Full-stack development team with frontend, backend, QA, and DevOps agents**

- **Agents (5)**: Code Explorer, Frontend Developer, Backend Developer, QA Engineer, DevOps Engineer
- **Key Skills**:
  - API Design - RESTful API design patterns and best practices
  - Fullstack Conventions - Full-stack development standards and patterns
- **Workflows**: Feature development, Bugfix
- **Usage**:
  ```bash
  /fullstack-dev:fullstack Build a user dashboard with authentication
  /fullstack-dev:status
  ```

---

### game-dev

**Multi-engine game development team covering Unity, Unreal, Godot, Three.js/R3F, and Orleans distributed servers**

- **Agents (6)**: Code Explorer, Engine & Systems Programmer, Gameplay & Mechanics Programmer, Level/Scene/World Designer, Asset Pipeline & Build Engineer, QA & Playtesting Engineer
- **Key Skills**:
  - Engine Patterns - Game engine architecture and design patterns
  - Gamedev Conventions - Game development best practices
  - Godot - Godot Engine development
  - Orleans - Orleans distributed game servers
  - Three.js - Three.js and React Three Fiber web game development
  - Unity - Unity game engine development
  - Unreal - Unreal Engine development
- **Workflows**: Feature, Mechanic, Bugfix, Optimization
- **Usage**:
  ```bash
  /game-dev:game Implement a character controller system
  /game-dev:status
  ```

---

### marketing-seo

**Marketing, SEO, and social media team for content creation, optimization, and engagement**

- **Agents (5)**: Content Analyst, Content Writer, SEO Specialist, Social Media Manager, Content Reviewer
- **Key Skills**:
  - Content Strategy - Content planning and strategy development
  - Marketing Conventions - Marketing best practices and standards
  - SEO Best Practices - Search engine optimization techniques
  - Social Platforms - Social media platform strategies
- **Workflows**: Campaign, Content, Optimization
- **Usage**:
  ```bash
  /marketing-seo:marketing Create a content marketing campaign for SaaS product
  /marketing-seo:status
  ```

---

### data-science

**Data science and machine learning team for data analysis, ML model development, and MLOps**

- **Agents (5)**: Data Explorer, Data Engineer, ML Engineer, MLOps Engineer, Data Analyst
- **Key Skills**:
  - Data Engineering - Data pipeline and ETL processes
  - ML Best Practices - Machine learning development standards
  - MLOps Pipelines - ML model deployment and operations
  - Statistical Analysis - Statistical methods and analysis
- **Workflows**: Analysis, Model, Pipeline, Optimization
- **Usage**:
  ```bash
  /data-science:data Build a predictive model for customer churn
  /data-science:status
  ```

---

### devops-cloud

**DevOps and cloud team for infrastructure, CI/CD, deployment, and observability**

- **Agents (5)**: Infrastructure Explorer, Cloud Architect, CI/CD Engineer, Security Engineer, SRE Engineer
- **Key Skills**:
  - CI/CD Pipelines - Continuous integration and deployment
  - Cloud Platforms - AWS, Azure, GCP cloud services
  - Infrastructure as Code - Terraform, CloudFormation, Pulumi
  - Monitoring & Observability - Prometheus, Grafana, ELK stack
- **Workflows**: Infrastructure, Deployment, Migration, Optimization
- **Usage**:
  ```bash
  /devops-cloud:devops Set up a production-ready CI/CD pipeline
  /devops-cloud:status
  ```

---

### design-ux

**Design and UX team for user research, UI/UX design, wireframing, and accessibility**

- **Agents (5)**: User Researcher, UX Designer, UI Designer, Interaction Designer, Design Reviewer
- **Key Skills**:
  - Accessibility - WCAG compliance and inclusive design
  - Design Systems - Component libraries and design tokens
  - User Research - User testing and research methodologies
  - Wireframing & Prototyping - Figma, Sketch, Adobe XD workflows
- **Workflows**: Research, Design, Prototype, Iteration
- **Usage**:
  ```bash
  /design-ux:design Design a mobile app onboarding flow
  /design-ux:status
  ```

---

### security

**Security team for code security, vulnerability scanning, threat analysis, and compliance**

- **Agents (5)**: Threat Analyst, Security Auditor, Penetration Tester, Compliance Officer, Incident Responder
- **Key Skills**:
  - Compliance Frameworks - SOC2, HIPAA, PCI-DSS, GDPR
  - Secure Coding - Secure coding practices and patterns
  - Threat Modeling - STRIDE, PASTA threat modeling methodologies
  - Vulnerability Scanning - SAST, DAST, dependency scanning
- **Workflows**: Audit, Assessment, Remediation, Incident
- **Usage**:
  ```bash
  /security:security Conduct a security audit of the application
  /security:status
  ```

---

### documentation

**Documentation team for technical writing, API documentation, tutorials, and guides**

- **Agents (5)**: Documentation Analyst, Technical Writer, API Documentation Specialist, Tutorial Author, Documentation Reviewer
- **Key Skills**:
  - API Documentation - OpenAPI/Swagger, API reference docs
  - Content Strategy - Documentation planning and organization
  - Documentation Tools - Docusaurus, MkDocs, GitBook
  - Technical Writing - Clear, concise technical communication
- **Workflows**: Documentation, API Docs, Tutorial, Update
- **Usage**:
  ```bash
  /documentation:docs Create comprehensive API documentation
  /documentation:status
  ```

---

### qa-testing

**QA and testing team for automated testing, test coverage, performance testing, and quality assurance**

- **Agents (5)**: Test Analyst, Automation Engineer, Manual Tester, Performance Tester, QA Reviewer
- **Key Skills**:
  - Performance Testing - Load testing, stress testing, benchmarking
  - Quality Metrics - Code coverage, test metrics, quality gates
  - Test Automation - Selenium, Cypress, Playwright, Jest
  - Test Frameworks - Testing frameworks and methodologies
- **Workflows**: Testing, Automation, Performance, Regression
- **Usage**:
  ```bash
  /qa-testing:qa Create automated test suite for authentication module
  /qa-testing:status
  ```

---

## 📦 Installation

```bash
# Add the marketplace
claude plugin marketplace add atlas-agents/plugins

# Install a team
claude plugin install fullstack-dev
claude plugin install game-dev
claude plugin install marketing-seo
claude plugin install data-science
claude plugin install devops-cloud
claude plugin install design-ux
claude plugin install security
claude plugin install documentation
claude plugin install qa-testing
```

## 💡 Usage

After installing a team, use its slash command to start a workflow:

```
/{team-name}:{command} [task description]
```

**Examples:**
```bash
/fullstack-dev:fullstack Build a RESTful API with authentication
/game-dev:game Create a multiplayer lobby system
/marketing-seo:marketing Write a blog post about AI tools
/data-science:data Analyze customer behavior patterns
/devops-cloud:devops Deploy application to AWS ECS
/design-ux:design Create a responsive dashboard layout
/security:security Review code for security vulnerabilities
/documentation:docs Write getting started guide
/qa-testing:qa Set up end-to-end testing pipeline
```

Check team status:
```bash
/{team-name}:status
```

## 🏗️ Architecture

Each team contains:

- **`team.json`** - Team manifest defining members, roles, models, and workflow phases
- **`commands/`** - Slash commands (orchestrator + status)
- **`agents/`** - Specialized agent definitions with roles and responsibilities
- **`skills/`** - Team-specific conventions, guidelines, and best practices
- **`hooks/`** - Telemetry and team logging for observability

### Workflow Phases

Teams execute work through phased workflows:

1. **Discovery** - Analyze requirements, explore codebase, gather context
2. **Planning** - Create implementation plan, define tasks
3. **Execution** - Implement features, write code, create content
4. **Review** - Quality assurance, testing, validation
5. **Summary** - Document results, provide deliverables

### Team Composition

Teams are composable - they focus on agents/commands/skills. MCP servers (GitHub, Playwright, etc.) are installed separately from the official marketplace.

## 🔨 Creating Teams

See [CONTRIBUTING.md](./CONTRIBUTING.md) for how to create new agent teams.

Use the scaffold script to bootstrap a new team:

```bash
bash scripts/scaffold-team.sh my-team "Team description" "agent-a agent-b agent-c"
```

This creates a complete team structure with:
- Team manifest (`team.json`)
- Agent templates
- Command definitions
- Skill modules
- Hooks for telemetry

## 📊 Telemetry

Each team logs tool usage to `~/.claude/team-logs/{team}.jsonl` for observability. Structured for future LangSmith integration.

**Logged Data:**
- Tool invocations and parameters
- Agent handoffs and phase transitions
- Workflow execution time
- Error tracking and debugging

## 🤝 Contributing

We welcome contributions! Please see [CONTRIBUTING.md](./CONTRIBUTING.md) for guidelines.

## 📄 License

See LICENSE file for details.

---

**Built for Claude Code** - Empowering developers with intelligent agent teams
