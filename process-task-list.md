# Task List Management

Guidelines for managing task lists in markdown files to track progress on completing a PRD

## Agent-First Workflow (CRITICAL)

**During task execution, leverage specialized MCP agents for quality and expertise:**

### Available Agents and When to Use Them

1. **code-reviewer agent** - After writing significant code
   - Use `review_code` for comprehensive code quality assessment
   - Use `security_scan` for security-focused analysis
   - Use `performance_analysis` for optimization recommendations

2. **security-reviewer agent** - For security-critical features
   - Use `security_audit` for comprehensive security analysis
   - Use `owasp_analysis` for OWASP Top 10 vulnerability checks
   - Use `auth_security_review` for authentication/authorization code

3. **debugger agent** - When encountering issues
   - Use `analyze_error` for error message and stack trace analysis
   - Use `debug_performance` for performance problems
   - Use `test_failure_analysis` for failing tests

4. **ui-ux-designer agent** - For frontend components
   - Use `design_component` for UI component creation
   - Use `accessibility_audit` for WCAG compliance
   - Use `responsive_design` for multi-device support

5. **cto-agent** - For architectural decisions
   - Use `design_architecture` for system design choices
   - Use `assess_technology` for evaluating new technologies

**Agent Usage Protocol:**
- Consider agent delegation BEFORE starting each task
- Use agents proactively, not just when stuck
- Document agent recommendations in task notes

## Task Logging (FutureTranz Required)

**For each discrete task, log execution details in TASK_LOG.md:**

```
START LOG:
[START]: YYYYMMDDHHMMSS
[TASK]: Brief description of what will be done

END LOG:
[END]: YYYYMMDDHHMMSS | [Duration: HH:MM:SS] | [Tokens: <actual count or 'N/A - multi-turn'>] | [Summary]: Max 2 sentences describing what was accomplished

Example:
START LOG:
[START]: 20250122143000
[TASK]: Implement user authentication API endpoint

END LOG:
[END]: 20250122150500 | [Duration: 00:35:00] | [Tokens: N/A - multi-turn] | [Summary]: All authentication deliverables completed with enterprise-grade quality. JWT-based auth system implemented with comprehensive test coverage.
```

**Important Notes:**
- Token count should reflect ACTUAL usage for single-interaction tasks only
- For multi-turn conversations, mark as 'N/A - multi-turn'
- Duration should be estimated based on task complexity
- Summary must be concrete and specific about what was delivered
- TASK_LOG.md file should be maintained in the project root

## Task Implementation
- **One sub-task at a time:** Do **NOT** start the next sub‑task until you ask the user for permission and they say "yes" or "y"
- **Completion protocol:**
  1. When you finish a **sub‑task**, immediately mark it as completed by changing `[ ]` to `[x]`.
  2. **Create task log entry** in TASK_LOG.md with START and END logs
  3. If **all** subtasks underneath a parent task are now `[x]`, follow this sequence:
    - **First**: Run the full test suite (`pytest`, `npm test`, `bin/rails test`, etc.)
    - **Only if all tests pass**: Stage changes (`git add .`)
    - **Clean up**: Remove any temporary files and temporary code before committing
    - **Commit**: Use a descriptive commit message that:
      - Uses conventional commit format (`feat:`, `fix:`, `refactor:`, etc.)
      - Summarizes what was accomplished in the parent task
      - Lists key changes and additions
      - References the task number and PRD context
      - **Formats the message as a single-line command using `-m` flags**, e.g.:

        ```
        git commit -m "feat: add payment validation logic" -m "- Validates card type and expiry" -m "- Adds unit tests for edge cases" -m "Related to T123 in PRD"
        ```
  4. Once all the subtasks are marked completed and changes have been committed, mark the **parent task** as completed.
- Stop after each sub‑task and wait for the user's go‑ahead.

## Task List Maintenance

1. **Update the task list as you work:**
   - Mark tasks and subtasks as completed (`[x]`) per the protocol above.
   - Add new tasks as they emerge.

2. **Maintain the "Relevant Files" section:**
   - List every file created or modified.
   - Give each file a one‑line description of its purpose.

## AI Instructions

When working with task lists, the AI must:

1. Regularly update the task list file after finishing any significant work.
2. Follow the completion protocol:
   - Mark each finished **sub‑task** `[x]`.
   - Mark the **parent task** `[x]` once **all** its subtasks are `[x]`.
3. Add newly discovered tasks.
4. Keep "Relevant Files" accurate and up to date.
5. Before starting work, check which sub‑task is next.
6. After implementing a sub‑task, update the file and then pause for user approval.