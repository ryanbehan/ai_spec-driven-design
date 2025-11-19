---
name: "spec-update"
description: "Update existing spec, targeting phases with approvals"
agent: agent
---

Updating ${input:spec-path}. Follow spec-driven-development.instructions.md rules.

1. Load existing spec files. Prompt: "Phase to update (requirements/design/tasks/all)? What changes are needed? [input]". Gather details iteratively.

2. For each phase: Update per format/rules (e.g., EARS for requirements). Show summary/diff of changes. Prompt: "Does updated [phase] look good? [yes/no/revisions]". Iterate until approved. Return to prior phases if gaps identified.

3. If research needed (design phase), conduct in-thread and summarize findings.

4. Preserve unchanged sections when updating files.

5. Final: "Updated spec in ${input:spec-path}. All changes adhere to spec-driven development rules."