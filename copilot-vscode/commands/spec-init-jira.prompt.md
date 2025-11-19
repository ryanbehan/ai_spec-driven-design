---
name: "spec-init-jira"
description: "Build a spec from a JIRA ticket in phased manner with approvals"
agent: agent
---

You are building a spec for JIRA ticket ${input:jira-id}. Follow spec-driven-development.instructions.md rules fully, including formats and approvals.

1. Fetch JIRA via MCP integration or GitHub integration (title, description, acceptance criteria, etc.); if unavailable, prompt: "Paste JIRA description: [input]".

2. **Requirements Phase**: Generate initial requirements.md per spec-driven-development.instructions.md (no questions first; use EARS, user stories, intro). Summary response. Prompt: "Do requirements look good? [yes/no/revisions]". Iterate until approved.

3. **Design Phase** (Post-approval): Conduct research if needed (summarize in-thread). Generate design.md with required sections. Summary. Prompt: "Does design look good? [yes/no/revisions]". Iterate; return to requirements if gaps.

4. **Tasks Phase** (Post-approval): Generate tasks.md per spec-driven-development.instructions.md instructions/format (checkboxes, code-only tasks). Summary. Prompt: "Do tasks look good? [yes/no/revisions]". Iterate; return if gaps.

5. If insufficient details, prompt per rules. Final: "Spec complete in /spec/${input:jira-id}/. Use spec-execute-task for implementation."