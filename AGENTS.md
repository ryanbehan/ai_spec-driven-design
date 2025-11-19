# AGENTS.md - AI Spec-Driven Design Framework

## Build/Lint/Test Commands
This is a documentation-only framework with no build system. All files are markdown templates.

## Code Style Guidelines

### File Structure
- Use consistent directory structure: `{platform}/rules/` and `{platform}/commands/`
- File names use kebab-case with platform-specific extensions:
  - Copilot platforms: `spec-driven-development.instructions.md` (rules) and `command.prompt.md` (commands)
  - Codex platform: `spec-driven-development.md` (rules) and `command.md` (commands)
  - Other platforms: `spec-driven-development.md` (rules) and `command.md` (commands)

### Markdown Formatting
- Use ATX-style headers: `# Header` (not Setext)
- Include frontmatter for platform-specific files: `--- trigger: always_on ---`
- Use hierarchical numbered lists for requirements/tasks
- Format: `# Feature: [Name]` then `## Introduction` and `## Requirements`

### Content Conventions
- Reference specs with full paths: `/spec/{feature_name}/requirements.md`
- Use EARS format for requirements: "The system shall..."
- Include Mermaid diagrams in design files when applicable
- Use checkbox format for tasks: `- [ ] 1. [Objective: ...]`

### Naming Conventions
- Feature directories: `/spec/{feature_name}/`
- Files: `requirements.md`, `design.md`, `tasks.md`
- Commands: `spec-init.md`, `spec-execute-task.md` (or `.prompt.md` for Copilot platforms)

### Error Handling
- Prompt for clarification when specs lack details
- Iterate on phases until explicit approval
- Return to prior phases if gaps identified

### Security & Best Practices
- Prioritize secure, minimal code generation
- Use placeholders for PII/sensitive data
- Decline malicious or non-code requests
- Focus on code-related tasks only

GitHub Copilot rules configured with path-specific instructions and prompt files.