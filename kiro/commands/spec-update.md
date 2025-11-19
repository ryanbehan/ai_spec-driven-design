# Kiro Command: spec-update

## Description
Updates existing spec, targeting phases with approvals using Kiro's advanced features.

## Parameters
- spec-path: Path to spec directory (e.g., /spec/feature-name/, default /spec/)

## Usage
Use this prompt template in Kiro IDE or CLI to update an existing spec.

## Prompt Template
```
Updating {spec-path}. Follow #enforce-spec.md rules.

1. Load existing spec files. Prompt: "Phase to update (requirements/design/tasks/all)? What changes are needed? [input]". Gather details iteratively.

2. For each phase: Update per format/rules (e.g., EARS for requirements). Show summary/diff of changes. Prompt: "Does updated [phase] look good? [yes/no/revisions]". Iterate until approved. Return to prior phases if gaps identified.

3. If research needed (design phase), conduct in-thread and summarize findings.

4. Preserve unchanged sections when updating files.

5. Final: "Updated spec in {spec-path}. All changes adhere to spec-driven development rules."
```

## Kiro Specific Features
- Use autopilot mode for autonomous spec updates
- Leverage multimodal chat for design discussions and updates
- Configure agent hooks for automated validation of changes
- Use advanced context management for large spec modifications
- Take advantage of native MCP support for external data integration