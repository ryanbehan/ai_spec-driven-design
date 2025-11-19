# Kiro Command: spec-init-jira

## Description
Builds a spec from a JIRA ticket in phased manner with approvals using Kiro's advanced capabilities.

## Parameters
- jira-id: The JIRA ticket ID (e.g., PROJ-123)

## Usage
Use this prompt template in Kiro IDE or CLI to initialize a spec from a JIRA ticket.

## Prompt Template
```
You are building a spec for JIRA ticket {jira-id} in /spec/{jira-id}/. Follow #enforce-spec.md rules fully, including formats and approvals.

1. Fetch JIRA via MCP integration or native connectors (title, description, acceptance criteria, etc.); if unavailable, prompt: "Paste JIRA description: [input]".

2. **Requirements Phase**: Generate initial requirements.md per #enforce-spec.md (no questions first; use EARS, user stories, intro). Summary response. Prompt: "Do requirements look good? [yes/no/revisions]". Iterate until approved.

3. **Design Phase** (Post-approval): Conduct research if needed (summarize in-thread). Generate design.md with required sections. Summary. Prompt: "Does design look good? [yes/no/revisions]". Iterate; return to requirements if gaps.

4. **Tasks Phase** (Post-approval): Generate tasks.md per #enforce-spec.md instructions/format (checkboxes, code-only tasks). Summary. Prompt: "Do tasks look good? [yes/no/revisions]". Iterate; return if gaps.

5. If insufficient details, prompt per rules. Final: "Spec complete in /spec/{jira-id}/. Use spec-execute-task for implementation."
```

## Kiro Specific Features
- Use autopilot mode for autonomous spec generation from JIRA tickets
- Leverage multimodal capabilities for analyzing ticket attachments
- Configure agent hooks for automated JIRA updates
- Use native MCP support for JIRA API integration
- Take advantage of advanced context management for complex tickets