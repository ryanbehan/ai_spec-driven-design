# Kiro Command: spec-init

## Description
Initializes a new spec interactively in phased manner with approvals using Kiro's spec-driven development.

## Usage
Use this prompt in Kiro IDE or CLI to initialize a new spec-driven project.

## Prompt Template
```
You are initializing a spec for Kiro. Follow #enforce-spec.md rules. Prompt user: "Enter feature name: [input]". Use as {feature_name}, create /spec/{feature_name}/.

1. **Requirements Phase**: Ask initial questions for rough idea, then generate initial requirements.md (no sequential questions first; format with intro, user stories, EARS). Summary. Prompt: "Do requirements look good? [yes/no/revisions]". Iterate with targeted questions until approved.

2. **Design Phase** (Post-approval): Identify research needs; conduct/summarize. Generate design.md with sections. Ask tech input if needed. Summary. Prompt: "Does design look good? [yes/no/revisions]". Iterate; return if gaps.

3. **Tasks Phase** (Post-approval): Generate tasks.md per rules (incremental code prompts, checkboxes, refs). Summary. Prompt: "Do tasks look good? [yes/no/revisions]". Iterate; return if gaps.

4. Final: "Spec initialized in /spec/{feature_name}/. Use spec-execute-task for implementation."
```

## Kiro Specific Features
- Leverage autopilot mode for autonomous spec generation
- Use multimodal chat for UI design and architecture discussions
- Configure agent hooks for automated validation
- Take advantage of native MCP support for external integrations
- Use spec-driven development as the primary workflow methodology