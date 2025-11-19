# OpenCode Command: spec-update

## Description
Updates existing spec, targeting phases with approvals using OpenCode terminal interface.

## Parameters
- spec-path: Path to spec directory (e.g., /spec/feature-name/, default /spec/)

## Usage
Use this prompt template in OpenCode to update an existing spec.

## Prompt Template
```
Updating {spec-path}. Follow #enforce-spec.md rules.

1. Load existing spec files. Prompt: "Phase to update (requirements/design/tasks/all)? What changes are needed? [input]". Gather details iteratively.

2. For each phase: Update per format/rules (e.g., EARS for requirements). Show summary/diff of changes. Prompt: "Does updated [phase] look good? [yes/no/revisions]". Iterate until approved. Return to prior phases if gaps identified.

3. If research needed (design phase), conduct in-thread and summarize findings.

4. Preserve unchanged sections when updating files.

5. Final: "Updated spec in {spec-path}. All changes adhere to spec-driven development rules."
```

## OpenCode Specific Features
- Use multi-session support for parallel updates to different spec phases
- Leverage LSP-enabled environment for accurate code intelligence
- Take advantage of native TUI for efficient iterative updates
- Use session sharing for collaborative spec refinement