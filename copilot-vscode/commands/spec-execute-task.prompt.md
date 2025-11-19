---
name: "spec-execute-task"
description: "Execute a spec task, following execution rules"
agent: agent
---

Executing task in ${input:spec-path}. Follow spec-driven-development.instructions.md rules, including reading all specs first.

1. Read requirements.md, design.md, tasks.md to understand context.

2. If no ${input:task-id} provided, review tasks.md and recommend next: "Next suggested task: [id]. Description: [brief]. Proceed? [yes/no/other id]".

3. For specified task: If sub-tasks exist, start with them. Focus ONLY on this task. Generate code/test as needed, verify vs requirements.

4. Implement the task using inline suggestions or chat responses. Stop after completion.

5. Prompt: "Task implementation complete. Review the changes and verify against requirements. Proceed to next task? [yes/no]". Do not auto-continue.

6. If questions about tasks (no execution needed), answer without implementing (e.g., "Next task is [id] with description [brief]").