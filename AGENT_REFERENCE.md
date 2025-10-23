# MCP Agent Reference Guide

**FutureTranz AI-Assisted Development - Agent Delegation Handbook**

## Overview

This guide provides comprehensive information about when and how to use specialized MCP (Model Context Protocol) agents during feature development. Following an agent-first workflow ensures expert-level quality across all aspects of your implementation.

## Core Principle: Agent-First Workflow

**BEFORE starting ANY significant task, ask yourself:**
1. Which agents can help with this task?
2. Should I delegate this to a specialized agent?
3. Am I the best tool for this job, or is there an expert agent?

## Available Agents

### 1. Project Manager Agent

**Primary Use Cases:**
- Sprint planning and task breakdown
- Time and effort estimation
- Resource allocation
- Progress tracking and reporting
- Risk assessment

**Available Functions:**
- `plan_sprint` - Create comprehensive sprint plans with task assignments
- `estimate_tasks` - Break down features with time/effort estimates
- `assess_risks` - Identify and assess project risks
- `track_progress` - Generate progress reports with KPIs
- `allocate_resources` - Optimize resource allocation
- `generate_standup` - Create daily standup agendas

**When to Use:**
- Starting a new feature or sprint
- Need detailed task estimates
- Managing complex project dependencies
- Tracking multi-task features

**Example:**
```
Use project-manager agent to plan_sprint for the user authentication feature with team capacity of 40 story points
```

---

### 2. CFO Agent

**Primary Use Cases:**
- Financial projections and ROI analysis
- Budget management
- Business plan development
- Cash flow tracking

**Available Functions:**
- `create_business_plan` - Generate comprehensive business plans
- `generate_financial_projections` - Create P&L, balance sheet forecasts
- `analyze_financials` - Perform financial analysis and benchmarking
- `calculate_roi` - Calculate ROI with NPV and IRR
- `track_cash_flow` - Monitor and analyze cash flow

**When to Use:**
- Building business cases for features
- Cost-benefit analysis
- Resource budget planning

---

### 3. Spec Writer Agent

**Primary Use Cases:**
- Technical specification generation
- User story creation
- API documentation
- Test plan development

**Available Functions:**
- `generate_spec` - Generate comprehensive technical specifications
- `create_user_story` - Create detailed user stories with acceptance criteria
- `generate_api_spec` - Generate OpenAPI/Swagger specifications

**When to Use:**
- Complex features needing formal specs
- API design and documentation
- Converting requirements to user stories

**Example:**
```
Use spec-writer agent to create_user_story for admin user managing user permissions
```

---

### 4. Code Reviewer Agent

**Primary Use Cases:**
- Code quality assessment
- Security scanning
- Performance analysis
- Architecture review

**Available Functions:**
- `review_code` - Comprehensive code review with quality assessment
- `security_scan` - Security-focused code analysis
- `performance_analysis` - Performance optimization recommendations
- `architecture_review` - Architecture and design pattern analysis

**When to Use:**
- After writing significant code blocks
- Before committing major features
- Performance-critical sections
- Security-sensitive code

**Example:**
```
Use code-reviewer agent to review_code for the payment processing module with focus on security and performance
```

---

### 5. Security Reviewer Agent

**Primary Use Cases:**
- Comprehensive security audits
- OWASP vulnerability analysis
- Authentication/authorization review
- Cryptography assessment
- Compliance auditing

**Available Functions:**
- `security_audit` - Full security audit of code and architecture
- `owasp_analysis` - OWASP Top 10 vulnerability checks
- `auth_security_review` - Review auth/authz implementation
- `crypto_analysis` - Analyze cryptographic implementations
- `data_privacy_audit` - Audit data handling for privacy compliance
- `infrastructure_security` - Assess infrastructure and deployment security
- `threat_modeling` - Create threat models and risk assessments

**When to Use:**
- Authentication/authorization features
- Payment processing
- Personal data handling
- Before production deployment
- Compliance requirements (GDPR, HIPAA, PCI-DSS)

**Example:**
```
Use security-reviewer agent to security_audit the user authentication system for OWASP compliance
```

---

### 6. Debugger Agent

**Primary Use Cases:**
- Error analysis and resolution
- Performance debugging
- Memory leak detection
- Test failure analysis
- Log analysis

**Available Functions:**
- `analyze_error` - Analyze error messages and stack traces
- `debug_performance` - Debug performance issues
- `memory_analysis` - Detect and analyze memory leaks
- `test_failure_analysis` - Analyze failing tests
- `log_analysis` - Analyze application logs for patterns
- `debugging_strategy` - Generate debugging strategy and troubleshooting plan

**When to Use:**
- Encountering errors or exceptions
- Performance degradation
- Test failures
- Memory issues
- Production incidents

**Example:**
```
Use debugger agent to analyze_error for the database connection timeout with full stack trace
```

---

### 7. UI/UX Designer Agent

**Primary Use Cases:**
- UI component design
- UX flow analysis
- Accessibility audits
- Responsive design
- Design system creation

**Available Functions:**
- `design_component` - Create/improve UI components
- `analyze_ux_flow` - Analyze user experience flows
- `accessibility_audit` - Perform WCAG accessibility audits
- `responsive_design` - Create responsive design solutions
- `design_system` - Create/enhance design system components
- `optimize_performance` - Optimize UI performance

**When to Use:**
- Building new UI components
- Accessibility requirements
- Multi-device support needed
- Performance optimization for frontend

**Example:**
```
Use ui-ux-designer agent to design_component for a modern, accessible navigation menu with WCAG AA compliance
```

---

### 8. CTO Agent

**Primary Use Cases:**
- System architecture design
- Technology stack decisions
- Technical roadmap planning
- Technology assessment
- Innovation strategy

**Available Functions:**
- `design_architecture` - Design system architecture
- `create_tech_roadmap` - Create technology roadmaps
- `assess_technology` - Evaluate new technologies
- `manage_innovation` - Develop innovation strategies
- `review_performance` - Analyze system performance
- `plan_capacity` - Plan infrastructure capacity

**When to Use:**
- Architectural decisions
- Choosing technologies/frameworks
- Scalability planning
- Technical debt assessment

**Example:**
```
Use cto-agent to design_architecture for a microservices-based e-commerce platform with high scalability
```

---

### 9. Business Analyst Agent

**Primary Use Cases:**
- Requirements gathering
- Business process mapping
- Gap analysis
- Stakeholder analysis
- User story creation
- Change impact assessment

**Available Functions:**
- `gather_requirements` - Systematically gather business requirements
- `map_process` - Create business process maps
- `analyze_gaps` - Perform gap analysis
- `create_user_stories` - Convert requirements to user stories
- `analyze_stakeholders` - Stakeholder analysis and communication planning
- `assess_change_impact` - Analyze impact of proposed changes

**When to Use:**
- Starting new projects
- Complex business requirements
- Process improvement initiatives
- Stakeholder management

**Example:**
```
Use business-analyst agent to gather_requirements for the invoice management system with stakeholder input
```

---

### 10. Claudia (Orchestrator Agent)

**Primary Use Cases:**
- Multi-agent workflow coordination
- Agent health monitoring
- Task delegation
- Performance optimization

**Available Functions:**
- `check_agent_health` - Health check of all agents
- `orchestrate_workflow` - Coordinate multi-agent workflows
- `delegate_task` - Delegate tasks to specific agents
- `generate_performance_report` - Generate platform performance reports
- `optimize_agent_performance` - Optimize agent performance

**When to Use:**
- Complex workflows requiring multiple agents
- Monitoring agent ecosystem
- Performance issues with agents

---

## Agent Selection Decision Tree

```
START: What type of task are you performing?

├─ Planning/Estimation
│  ├─ Business requirements → business-analyst
│  ├─ Technical specs → spec-writer
│  └─ Sprint/tasks → project-manager
│
├─ Implementation
│  ├─ Architecture design → cto-agent
│  ├─ UI components → ui-ux-designer
│  └─ Code implementation → (direct implementation, then review)
│
├─ Quality Assurance
│  ├─ Code review → code-reviewer
│  ├─ Security review → security-reviewer
│  └─ Performance review → code-reviewer OR debugger
│
├─ Troubleshooting
│  ├─ Errors/bugs → debugger
│  ├─ Performance issues → debugger
│  └─ Test failures → debugger
│
└─ Analysis
   ├─ Financial/ROI → cfo-agent
   ├─ Business process → business-analyst
   └─ Technology assessment → cto-agent
```

## Best Practices

### 1. Use Agents Proactively
- Do not wait until you are stuck
- Consult agents during planning phases
- Use agents for validation and verification

### 2. Combine Multiple Agents
- Use business-analyst + spec-writer for requirements
- Use code-reviewer + security-reviewer for critical code
- Use project-manager + cto-agent for architecture planning

### 3. Document Agent Recommendations
- Add agent feedback to task notes
- Reference agent analysis in commit messages
- Maintain audit trail of agent consultations

### 4. Follow the 95% Certainty Rule
- If less than 95% certain, consult an agent
- Do not guess when expert knowledge is available
- Ask clarifying questions before proceeding

## Integration with Development Workflow

### During PRD Creation
1. Consider **business-analyst** for requirements gathering
2. Consider **spec-writer** for technical specifications
3. Consider **cto-agent** for architecture guidance

### During Task Generation
1. Use **project-manager** for task breakdown and estimation
2. Use **cto-agent** for technical feasibility
3. Use **security-reviewer** for security requirement identification

### During Implementation
1. Use **ui-ux-designer** for frontend components
2. Use **code-reviewer** after significant code blocks
3. Use **security-reviewer** for auth/sensitive code
4. Use **debugger** when encountering issues

### During Review/Completion
1. Use **code-reviewer** for final code review
2. Use **security-reviewer** for security audit
3. Use **project-manager** for progress tracking

---

## Quick Reference Table

| Task Type | Primary Agent | Secondary Agent |
|-----------|---------------|-----------------|
| Requirements gathering | business-analyst | spec-writer |
| Sprint planning | project-manager | - |
| Architecture design | cto-agent | - |
| API design | spec-writer | code-reviewer |
| UI component | ui-ux-designer | code-reviewer |
| Code review | code-reviewer | security-reviewer |
| Security audit | security-reviewer | code-reviewer |
| Performance issues | debugger | code-reviewer |
| Error debugging | debugger | - |
| Financial analysis | cfo-agent | - |
| Test failures | debugger | code-reviewer |
| Accessibility | ui-ux-designer | - |
| Technology evaluation | cto-agent | - |

---

**Document last updated: 2025-10-22**
**Verified against FutureTranz development standards and MCP agent capabilities**
