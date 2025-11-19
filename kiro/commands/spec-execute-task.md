# Kiro Command: spec-execute-task

## Description
Executes a spec task, following execution rules using Kiro's advanced agent capabilities.

## Parameters
- spec-path: Path to spec directory (e.g., /spec/feature-name/)
- task-id: Task number (e.g., 1.1); if none provided, recommend next task

## Usage
Use this prompt template in Kiro IDE or CLI to execute specific implementation tasks.

## Prompt Template
```
Executing task in {spec-path}. Follow #enforce-spec.md rules, including reading all specs first.

1. Read requirements.md, design.md, tasks.md to understand context.

2. If no {task-id} provided, review tasks.md and recommend next: "Next suggested task: [id]. Description: [brief]. Proceed? [yes/no/other id]".

3. For specified task: If sub-tasks exist, start with them. Focus ONLY on this task. Generate code/test as needed, verify vs requirements.

4. Implement the task using Kiro's advanced agents. Stop after completion.

5. Prompt: "Task implementation complete. Review the changes and verify against requirements. Proceed to next task? [yes/no]". Do not auto-continue.

6. If questions about tasks (no execution needed), answer without implementing (e.g., "Next task is [id] with description [brief]").
```

## Kiro Specific Features
- Use autopilot mode for autonomous task execution
- Configure agent hooks to trigger on task completion (unit tests, documentation, etc.)
- Leverage multimodal capabilities for UI/UX implementation
- Use advanced context management for complex codebases
- Take advantage of native MCP support for external tool integration