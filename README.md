# AI Spec-Driven Design

A comprehensive spec-driven development framework that enforces structured, iterative software development through AI-assisted workflows. Originally developed for Windsurf, but adaptable to other AI coding assistants like AWS Q CLI, Claude Code, and Cursor.

## Overview

This framework implements a phased approach to software development:
1. **Requirements Phase** - Define user stories and system requirements
2. **Design Phase** - Create architecture and technical specifications  
3. **Tasks Phase** - Break down implementation into manageable, testable tasks
4. **Execution Phase** - Implement tasks with continuous spec validation

## Project Structure

```
ai_spec-driven-design/
├── generic/                     # Platform-agnostic templates
│   ├── rules/
│   │   └── enforce-spect.md     # Core steering rules for any AI assistant
│   └── commands/                # Generic workflow templates
│       ├── spec-init.md         # Initialize new spec-driven project
│       ├── spec-init-jira.md    # Initialize with Jira integration
│       ├── spec-update.md       # Update existing specifications
│       └── spec-execute-task.md # Execute specific implementation tasks
├── windsurf/                    # Windsurf-specific integrations
│   ├── rules/
│   │   └── enforce-spect.md     # Windsurf-specific steering rules
│   └── workflows/               # Windsurf workflow commands
│       ├── spec-init.md         # Initialize new spec-driven project
│       ├── spec-init-jira.md    # Initialize with Jira integration
│       ├── spec-update.md       # Update existing specifications
│       └── spec-execute-task.md # Execute specific implementation tasks
├── claude-code/                 # Claude Code integrations
│   ├── commands/                # Custom commands
│   │   ├── spec-init.md         # /spec-init command
│   │   ├── spec-init-jira.md    # /spec-init-jira command
│   │   ├── spec-update.md       # /spec-update command
│   │   └── spec-execute-task.md # /spec-execute-task command
│   └── rules/
│       └── spec-driven-development.md # Spec-driven development rules
├── codex/                       # Codex integrations
│   ├── commands/                # Markdown command definitions
│   │   ├── spec-init.md         # Initialize new spec-driven project
│   │   ├── spec-init-jira.md    # Initialize with Jira integration
│   │   ├── spec-update.md       # Update existing specifications
│   │   └── spec-execute-task.md # Execute specific implementation tasks
│   └── rules/
│       └── spec-driven-development.md # Spec-driven development rules
├── aws-q-cli/                   # AWS Q CLI integrations
│   ├── rules/                   # Context rules for profiles/global
│   │   └── spec-driven-development.md
│   └── profiles/
│       └── setup-instructions.md # Profile configuration guide
├── copilot-vscode/              # GitHub Copilot for VSCode integrations
│   ├── rules/
│   │   └── spec-driven-development.instructions.md
│   └── commands/                # Prompt files for chat commands
│       ├── spec-init.prompt.md         # Initialize new spec-driven project
│       ├── spec-init-jira.prompt.md    # Initialize with Jira integration
│       ├── spec-update.prompt.md       # Update existing specifications
│       └── spec-execute-task.prompt.md # Execute specific implementation tasks

├── opencode/                    # OpenCode integrations
│   ├── rules/
│   │   └── spec-driven-development.md
│   └── commands/                # Terminal command templates
│       ├── spec-init.md         # Initialize new spec-driven project
│       ├── spec-init-jira.md    # Initialize with Jira integration
│       ├── spec-update.md       # Update existing specifications
│       └── spec-execute-task.md # Execute specific implementation tasks
├── kiro/                        # Kiro integrations
│   ├── rules/
│   │   └── spec-driven-development.md
│   └── commands/                # Agent and hook templates
│       ├── spec-init.md         # Initialize new spec-driven project
│       ├── spec-init-jira.md    # Initialize with Jira integration
│       ├── spec-update.md       # Update existing specifications
│       └── spec-execute-task.md # Execute specific implementation tasks
└── codex/                       # Codex integrations
    ├── commands/                # Markdown command definitions
    │   ├── spec-init.md         # Initialize new spec-driven project
    │   ├── spec-init-jira.md    # Initialize with Jira integration
    │   ├── spec-update.md       # Update existing specifications
    │   └── spec-execute-task.md # Execute specific implementation tasks
    └── rules/
        └── spec-driven-development.md # Spec-driven development rules
```

## Installation

### For Windsurf

1. **Install Rules**:
   ```bash
   # Copy rules to your project's Windsurf configuration
   cp windsurf/rules/enforce-spect.md .windsurf/rules/
   ```

2. **Install Workflows**:
   ```bash
   # Copy all workflow commands
   cp windsurf/workflows/*.md .windsurf/workflows/
   ```

3. **Verify Installation**:
   - Rules should appear in `.windsurf/rules/enforce-spect.md`
   - Workflows should appear in `.windsurf/workflows/spec-*.md`

### For Claude Code

1. **Install Slash Commands**:
   ```bash
   # Copy commands to your Claude Code settings
   # (Adjust path based on your Claude Code configuration)
   cp claude-code/commands/*.md ~/.claude/commands/
   ```

2. **Install Project Rules**:
   ```bash
   # Copy rules to your project root and customize as needed
   cp claude-code/rules/spec-driven-development.md ./CLAUDE.md
   ```

3. **Verify Installation**:
   - Commands should be available: `/spec-init`, `/spec-init-jira`, `/spec-update`, `/spec-execute-task`
   - Project rules should be active via `CLAUDE.md` in your project root

### For Other AI Coding Assistants

1. **Install Generic Rules**:
   ```bash
   # Create rules directory if it doesn't exist
   mkdir -p .ai-assistant/rules/
   
   # Copy generic rules
   cp generic/rules/enforce-spect.md .ai-assistant/rules/
   ```

2. **Install Generic Commands**:
   ```bash
   # Copy generic workflow templates
   cp generic/commands/*.md .ai-assistant/workflows/
   ```

### For AWS Q CLI

1. **Setup Global Context** (applies to all projects):
   ```bash
   q chat
   > /context add --global aws-q-cli/rules/spec-driven-development.md
   ```

2. **Setup Project Profile** (recommended):
   ```bash
   q chat
   > /profile create spec-driven-dev
   > /context add aws-q-cli/rules/spec-driven-development.md
   > /profile set spec-driven-dev
   ```

3. **Project-Specific Rules** (optional):
   ```bash
   # In your project directory
   mkdir -p .amazonq/rules
   cp aws-q-cli/rules/spec-driven-development.md .amazonq/rules/
   ```

4. **Verify Setup**:
    ```bash
    q chat
    > /context show  # Should display spec-driven rules
    > /profile       # Should show your profiles
    ```

### For GitHub Copilot for VSCode

**Project-Specific Setup (Recommended)**

1. **Deploy Instructions File**:
   ```bash
   # Copy custom instructions to your project's .github directory
   mkdir -p .github/instructions
   cp copilot-vscode/rules/spec-driven-development.instructions.md .github/instructions/spec-driven-development.instructions.md
   ```
   - This file provides persistent rules that apply to all Copilot Chat interactions in the workspace
   - VS Code will automatically load instructions from `.github/instructions/` when present

2. **Deploy Prompt Files** (Workspace Commands):
   ```bash
   # Copy prompt files to your project's .github/prompts directory
   mkdir -p .github/prompts
   cp copilot-vscode/commands/*.prompt.md .github/prompts/
   ```
   - Prompts are stored in the workspace `.github/prompts/` folder (not user home directory)
   - After copying, reload VS Code: Command Palette → Developer: Reload Window
   - Prompts will appear as slash commands when you type `/` in Copilot Chat

3. **Verify Installation**:
   ```bash
   # Confirm files are in place
   ls -la .github/instructions/
   ls -la .github/prompts/
   ```
   - Open Copilot Chat and type `/` to see the four prompts: `/spec-init`, `/spec-init-jira`, `/spec-execute-task`, `/spec-update`
   - Check the Output panel (View → Output → "GitHub Copilot") for any loading or parse errors

4. **Usage**:
   - **Initialize a new spec**: Type `/spec-init` in chat and follow the phased workflow (requirements → design → tasks)
   - **Initialize from JIRA**: Type `/spec-init-jira` and provide a JIRA ticket ID
   - **Execute a task**: Type `/spec-execute-task` and specify the spec path and task ID
   - **Update a spec**: Type `/spec-update` to revise existing specifications

**Optional: User-Level Setup (Cross-Workspace Prompts)**

If you want prompts available across all your workspaces (not just this project):
   ```bash
   # User prompts go in VS Code profile, not home ~/.github directory
   # Macros VS Code profile location:
   mkdir -p ~/.config/Code/User/globalStorage/github.copilot/prompts
   cp copilot-vscode/commands/*.prompt.md ~/.config/Code/User/globalStorage/github.copilot/prompts/
   ```
   - Note: Workspace prompts (in `.github/prompts/`) take priority and are recommended for team consistency

### Project rule handling — Claude Code and Copilot

Claude Code and Copilot integrations include rule files that, if copied directly to a project's primary rule file, will overwrite that file (for example copying `claude-code/rules/spec-driven-development.md` to `./CLAUDE.md`). To avoid accidental overwrites and to make project rules easier to manage, choose one of the two patterns below.

Claude Code

- Option A — Keep a separate rules directory (recommended):
   - Copy the rules into a project rules directory and reference it from your `CLAUDE.md` (link or include).
   - Example commands:
      ```bash
      mkdir -p .claude/rules
      cp claude-code/rules/spec-driven-development.md .claude/rules/spec-driven-development.md
      ```
   - In `CLAUDE.md` point to the file (as a link or an include depending on your toolchain):
      ```markdown
      [Project rules](./.claude/rules/spec-driven-development.md)
      ```

- Option B — Append the rule into `CLAUDE.md` (if you want a single-file approach):
   - This preserves existing `CLAUDE.md` content and adds the rules at the end:
      ```bash
      cat claude-code/rules/spec-driven-development.md >> ./CLAUDE.md
      ```

GitHub Copilot (instructions file)

- The same two approaches apply for Copilot instructions, using `copilot-instructions.md` as your project instruction file.

- Option A — Separate project rules directory:
   ```bash
   mkdir -p .copilot/rules
   cp copilot-vscode/rules/spec-driven-development.instructions.md .copilot/rules/spec-driven-development.instructions.md
   ```
   - Then reference or link the file from `copilot-instructions.md`:
      ```markdown
      [Project rules](./.copilot/rules/spec-driven-development.instructions.md)
      ```

- Option B — Append the rule into `copilot-instructions.md`:
   ```bash
   cat copilot-vscode/rules/spec-driven-development.instructions.md >> ./copilot-instructions.md
   ```

Note: VS Code Copilot also supports workspace-level instructions in `.github/instructions/`. If you intend these rules to be loaded by Copilot Chat for the entire workspace, consider the `.github/instructions/` location instead of a project `copilot-instructions.md` file.

Codex

Codex prompts are commonly installed globally and rules can be either global or project-scoped. Keep in mind that copying templates directly to a primary rule file will overwrite it — prefer the two patterns above to avoid accidental data loss.

- Global prompts location (common): `~/.codex/prompts`
- Rule locations (choose one):
   - Global rules: `~/.codex/rules`
   - Project rules: `.codex/rules`

Examples

- Install templates as global prompts and rules:
   ```bash
   mkdir -p ~/.codex/prompts ~/.codex/rules
   cp path/to/your/templates/*.md ~/.codex/prompts/
   cp path/to/your/rules/*.md ~/.codex/rules/
   ```

- Install templates for a single project (project-scoped rules):
   ```bash
   mkdir -p .codex/rules
   cp path/to/repo/rules/spec-driven-development.md .codex/rules/
   ```

- Reference vs append (project rule file):
   - Reference (keeps a single canonical rule file and avoids overwriting):
      ```markdown
      [Project rules](./.codex/rules/spec-driven-development.md)
      ```
   - Append (merge contents into a single file):
      ```bash
      cat .codex/rules/spec-driven-development.md >> ./CODEX_RULES.md
      ```

Choose the approach that fits your team's workflow: separate rule files are easier to maintain and update independently, while appending produces a single-file artifact that some assistants may prefer to read directly.


### For OpenCode

1. **Install Rules**:
   ```bash
   # Copy rules to OpenCode configuration
   cp opencode/rules/spec-driven-development.md ~/.opencode/rules/
   ```

2. **Project-Specific Configuration**:
   ```bash
   # In your project directory
   cp opencode/rules/spec-driven-development.md .opencode/rules.md
   ```

3. **Verify Installation**:
   - OpenCode should load steering rules on startup
   - Multi-session support should be available

### For Kiro

1. **Install Steering Rules**:
   ```bash
   # Copy rules to Kiro configuration
   cp kiro/rules/spec-driven-development.md .kiro/steering/
   ```

2. **Setup Agent Hooks** (optional):
   ```bash
   # Configure automated spec validation
   cp kiro/commands/spec-execute-task.md .kiro/hooks/
   ```

3. **Verify Installation**:
    - Steering rules should be active in Kiro IDE/CLI
    - Agent hooks should trigger on configured events

### For Codex

1. **Install Project Rules**:
   ```bash
   # Copy rules to your project's Codex configuration
   mkdir -p .codex/rules
   cp codex/rules/spec-driven-development.md .codex/rules/
   ```

2. **Install Commands**:
   ```bash
   # Copy markdown command definitions to your Codex configuration
   mkdir -p .codex/commands
   cp codex/commands/*.md .codex/commands/
   ```

3. **Verify Installation**:
   - Rules should be in `.codex/rules/spec-driven-development.md`
   - Markdown command files should be in `.codex/commands/`
   - Commands should be available in Codex interface

### For Other AI Coding Assistants

1. **Adaptation Guide**:
   - **Cursor**: Create Cursor Rules for workflow guidance (custom commands not yet supported)
   - **Other Tools**: Adapt the markdown templates to your platform's format

3. **Customization**:
   - Edit the generic rules to match your platform's capabilities
   - Add platform-specific guidance where needed
   - Test with your AI assistant's workflow system

## Usage

### Quick Start

#### Windsurf Users
1. **Initialize a New Project**: Use the `/spec-init` workflow to create initial specifications
2. **Execute Tasks**: Use `/spec-execute-task` to implement specific features  
3. **Update Specifications**: Use `/spec-update` when requirements or design changes

#### Claude Code Users
1. **Initialize a New Project**: Run `/spec-init` to create initial specifications
2. **Execute Tasks**: Run `/spec-execute-task spec-path:/spec/feature-name/ task-id:1.1` to implement features
3. **Update Specifications**: Run `/spec-update` when requirements or design changes

**Note**: The slash commands are helpful tools, but standard prompting will also follow these rules when `CLAUDE.md` is present in your project. You don't need to use the commands exclusively.

#### Cursor Users
1. **Setup Project Rules**: Copy `generic/rules/enforce-spect.md` content into Cursor Rules
2. **Initialize Projects**: Use Agent Mode with natural language prompts following the phased approach
3. **Execute Tasks**: Reference specifications in chat and use Agent Mode for autonomous implementation

#### AWS Q CLI Users
1. **Setup Profile**: Create and switch to `spec-driven-dev` profile with rules loaded
2. **Initialize Projects**: Use natural language: "Initialize spec-driven project for [feature]"
3. **Execute Tasks**: Reference specifications: "Execute task 1.1 from /spec/[feature]/tasks.md"
4. **Context Persistence**: Use `q chat --resume` to maintain conversation context

#### GitHub Copilot for VSCode Users
1. **Setup Instructions**: Copy rules to `.github/instructions/spec-driven-development.instructions.md`
2. **Setup Prompts**: Copy prompt files to `.github/prompts/` and enable prompt files in settings
3. **Initialize Projects**: Type `/spec-init` in chat for phased development
4. **Execute Tasks**: Use `/spec-execute-task` with spec path and task ID
5. **Update Specifications**: Use `/spec-update` for iterative spec refinement

#### OpenCode Users
1. **Setup Rules**: Configure rules in OpenCode configuration
2. **Initialize Projects**: Use terminal prompts for multi-session spec development
3. **Execute Tasks**: Use terminal-based prompts for accurate code generation
4. **Parallel Development**: Use multi-session support for complex workflows

#### Kiro Users
1. **Setup Steering Rules**: Configure rules in Kiro project configuration
2. **Initialize Projects**: Use autopilot mode for autonomous spec generation
3. **Execute Tasks**: Configure agent hooks for automated task execution
4. **Advanced Features**: Leverage multimodal chat and MCP integrations

#### All Platforms
- Follow the phased approach: requirements → design → tasks → execution
- Each task references and validates against specifications  
- Maintains traceability throughout development

### Key Features

- **Spec Adherence**: All code generation validates against written specifications
- **Phased Approval**: Explicit approval required before proceeding to next phase
- **Incremental Development**: Tasks broken into manageable, testable chunks
- **Research Integration**: In-thread research with source citation
- **Security Focus**: Prioritizes secure coding practices and best practices

### Workflow Examples

#### Windsurf Workflow
```
1. Run spec-init → Creates /spec/{feature}/requirements.md
2. Review/approve requirements → Proceed to design phase
3. Generate design.md → Architecture and technical decisions
4. Review/approve design → Proceed to tasks phase  
5. Generate tasks.md → Numbered implementation checklist
6. Execute tasks → Use spec-execute-task for each item
```

#### Claude Code Workflow
```
1. Run /spec-init → Creates /spec/{feature}/requirements.md
2. Review/approve requirements → Proceed to design phase
3. Generate design.md → Architecture and technical decisions
4. Review/approve design → Proceed to tasks phase  
5. Generate tasks.md → Numbered implementation checklist
6. Execute tasks → Use /spec-execute-task or standard prompting for each item
```

#### Cursor Workflow
```
1. Setup Cursor Rules with spec-driven guidelines
2. Use Agent Mode: "Initialize spec for [feature]" → Creates /spec/{feature}/requirements.md
3. Review/approve requirements → Proceed to design phase
4. Generate design.md → Architecture and technical decisions
5. Review/approve design → Proceed to tasks phase  
6. Generate tasks.md → Numbered implementation checklist
7. Execute tasks → Use Agent Mode referencing specifications
```

#### AWS Q CLI Workflow
```
1. Setup profile: q chat > /profile set spec-driven-dev
2. Initialize project: "Initialize spec-driven project for [feature]" → Creates /spec/{feature}/requirements.md
3. Review/approve requirements → Proceed to design phase
4. Generate design.md → Architecture and technical decisions
5. Review/approve design → Proceed to tasks phase
6. Generate tasks.md → Numbered implementation checklist  
7. Execute tasks → "Execute task 1.1 from /spec/[feature]/tasks.md"
```

#### GitHub Copilot for VSCode Workflow
```
1. Setup custom instructions in .github/instructions/spec-driven-development.instructions.md
2. Enable prompt files in VS Code settings
3. Use chat: "/spec-init" → Creates /spec/{feature}/requirements.md
4. Review/approve requirements → Proceed to design phase
5. Generate design.md → Architecture and technical decisions
6. Review/approve design → Proceed to tasks phase
7. Generate tasks.md → Numbered implementation checklist
8. Execute tasks → Use "/spec-execute-task /spec/{feature}/ 1.1" for each item
```

#### OpenCode Workflow
```
1. Configure rules in OpenCode configuration
2. Start terminal session with OpenCode
3. Initialize spec: Use terminal prompt for [feature] → Creates /spec/{feature}/requirements.md
4. Review/approve requirements → Proceed to design phase
5. Generate design.md → Architecture and technical decisions
6. Review/approve design → Proceed to tasks phase
7. Generate tasks.md → Numbered implementation checklist
8. Execute tasks → Use multi-session support for parallel development
```

#### Kiro Workflow
```
1. Setup steering rules in Kiro configuration
2. Use autopilot: "Initialize spec for [feature]" → Creates /spec/{feature}/requirements.md
3. Review/approve requirements → Proceed to design phase
4. Generate design.md → Architecture and technical decisions
5. Review/approve design → Proceed to tasks phase
6. Generate tasks.md → Numbered implementation checklist
7. Execute tasks → Configure agent hooks for automated execution
8. Use multimodal chat for UI design and complex requirements
```

#### Codex Workflow
```
1. Setup rules in .codex/rules/spec-driven-development.md
2. Load markdown commands into Codex configuration (.codex/commands/)
3. Initialize spec: Use spec-init command → Creates /spec/{feature}/requirements.md
4. Review/approve requirements → Proceed to design phase
5. Generate design.md → Architecture and technical decisions
6. Review/approve design → Proceed to tasks phase
7. Generate tasks.md → Numbered implementation checklist
8. Execute tasks → Use spec-execute-task command for each item
```

**Notes**:
- **Claude Code**: With `CLAUDE.md` in your project, automatically follows spec-driven rules in all interactions
- **Cursor**: Agent Mode provides autonomous workflow execution with specification validation
- **AWS Q CLI**: Profiles and context rules provide persistent spec-driven guidance across all conversations
- **GitHub Copilot for VSCode**: Path-specific instructions in `.github/instructions/` and prompt files in `.github/prompts/` provide consistent spec-driven behavior
- **GitHub Copilot CLI**: Steering rules and slash commands enable advanced spec-driven workflows
- **OpenCode**: Multi-session support and provider flexibility optimize terminal-based spec development
- **Kiro**: Autopilot mode and agent hooks provide autonomous spec-driven development with advanced features
- **Codex**: Markdown command definitions and rules in `.codex/` provide structured spec-driven workflows

### Advanced Usage Examples

#### GitHub Copilot for VSCode Advanced Features
- **Path-specific instructions**: Use `.github/instructions/*.instructions.md` files for component-specific guidance
- **Prompt files**: Access standardized workflows via `/command-name` in chat
- **Coding agent integration**: Use coding agent for complex multi-step implementations
- **Inline vs chat workflows**: Use inline chat for quick edits, full chat for complex spec development

#### GitHub Copilot CLI Advanced Features
- **Custom agents**: Configure specialized agents for different task types
- **MCP integrations**: Use `/mcp add` for external tool integrations (JIRA, documentation, etc.)
- **Session management**: Use `--resume` and `--continue` for persistent development sessions
- **Trusted directories**: Use `/add-dir` to include additional context directories

#### OpenCode Advanced Features
- **Multi-session development**: Run parallel sessions for different spec phases
- **Provider flexibility**: Switch between Claude, OpenAI, and local models per task
- **Session sharing**: Share session links for collaborative spec development
- **Terminal optimization**: Native TUI interface for efficient terminal-based development

#### Kiro Advanced Features
- **Agent hooks automation**: Configure hooks to trigger on file save, commit, or other events
- **Multimodal inputs**: Use images for UI design, diagrams for architecture discussions
- **MCP server integration**: Connect to databases, APIs, and documentation sources
- **Autopilot complex tasks**: Let Kiro autonomously handle multi-step implementations

## Benefits

- **Consistency**: Standardized approach across all development phases
- **Traceability**: Clear links from requirements to implementation
- **Quality**: Built-in validation and review checkpoints
- **Documentation**: Specifications serve as living documentation
- **Adaptability**: Framework works with multiple AI coding platforms

## Contributing

This framework is designed to be extended and customized. Feel free to:
- Add new command templates for specific use cases
- Adapt rules for different development methodologies
- Create platform-specific integrations

### Platform-Specific Integration Testing

When contributing new platform integrations, please test with the actual tools:

**GitHub Copilot for VSCode**:
- Test path-specific instructions loading from `.github/instructions/*.instructions.md`
- Verify prompt files work via `/command-name` in chat
- Test coding agent integration for complex tasks
- Ensure prompt files are properly formatted with YAML frontmatter

**OpenCode**:
- Test multi-session functionality
- Verify terminal-based code generation accuracy
- Test provider switching (Claude, OpenAI, local models)

**Kiro**:
- Test autopilot mode for complex task execution
- Verify agent hooks configuration and triggering
- Test multimodal input capabilities
- Validate MCP server integrations

### Testing Checklist for New Platforms
- [ ] Directory structure created (rules/ and commands/)
- [ ] Rule file uses proper naming convention (.instructions.md for Copilot, .md for others)
- [ ] Command templates created with platform-specific features
- [ ] Prompt files created for Copilot platforms (.prompt.md with YAML frontmatter)
- [ ] README installation section added with correct paths
- [ ] README usage examples included
- [ ] Workflow examples documented
- [ ] Platform tested with actual tool (if available)

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
