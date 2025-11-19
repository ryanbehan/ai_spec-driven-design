# OpenCode Command: spec-init-jira

## Description
Builds a spec from a JIRA ticket in phased manner with approvals using OpenCode terminal interface.

## Parameters
- jira-id: The JIRA ticket ID (e.g., PROJ-123)

## Usage
Use this prompt template in OpenCode to initialize a spec from a JIRA ticket.

## Prompt Template
```
You are building a spec for JIRA ticket {jira-id} in /spec/{jira-id}/. Follow #enforce-spec.md rules fully, including formats and approvals.

1. Fetch JIRA via integrated tools or user input (title, description, acceptance criteria, etc.); if unavailable, prompt: "Paste JIRA description: [input]".

2. **Requirements Phase**: Generate initial requirements.md per #enforce-spec.md (no questions first; use EARS, user stories, intro). Summary response. Prompt: "Do requirements look good? [yes/no/revisions]". Iterate until approved.

3. **Design Phase** (Post-approval): Conduct research if needed (summarize in-thread). Generate design.md with required sections. Summary. Prompt: "Does design look good? [yes/no/revisions]". Iterate; return to requirements if gaps.

4. **Tasks Phase** (Post-approval): Generate tasks.md per #enforce-spec.md instructions/format (checkboxes, code-only tasks). Summary. Prompt: "Do tasks look good? [yes/no/revisions]". Iterate; return if gaps.

5. If insufficient details, prompt per rules. Final: "Spec complete in /spec/{jira-id}/. Use spec-execute-task for implementation."
```

## OpenCode Specific Features
- Use multi-session capability for parallel research and spec development
- Leverage LSP integration for accurate code intelligence in examples
- Configure appropriate LLM providers for JIRA analysis and spec generation
- Use terminal-based interface for efficient iterative refinement