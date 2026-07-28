# Ansible Development with AI

Notes and configuration for AI-assisted Ansible development workflows.

## AI Forge - Ansible Community AI Skills

[ansible-community/ai-forge](https://github.com/ansible-community/ai-forge) provides AI assistant modules for developing Ansible automation content following Red Hat Communities of Practice (CoP) best practices.

### Setup

#### Prerequisites

```bash
pip install lola-ai
```

#### Add the Ansible Content Marketplace

```bash
lola market add ansible-content https://raw.githubusercontent.com/ansible-community/ai-forge/main/lola-market.yml
```

#### Install Modules Globally (User Scope)

```bash
lola install ansible-collection-standards -a claude-code --scope user --force
lola install ansible-role -a claude-code --scope user --force
lola install ansible-collection-sdlc -a claude-code --scope user --force
lola install ansible-content-development -a claude-code --scope user --force
lola install cloud_content -a claude-code --scope user --force
lola install network_content -a claude-code --scope user --force
lola install ansible-documentation -a claude-code --scope user --force
```

### Installed Modules

| Module | Contents | Purpose |
|--------|----------|---------|
| ansible-collection-standards | 1 skill, 3 commands | CoP standards compliance, scaffolding, and review |
| ansible-role | 1 command | Interactive role scaffolding |
| ansible-collection-sdlc | 26 skills, 3 commands | Full dev lifecycle - commits, PRs, releases, testing, SonarCloud |
| ansible-content-development | 4 skills | Content authoring - modules, playbooks, roles, Molecule scenarios |
| cloud_content | 4 skills | Cloud automation workflows |
| network_content | 1 skill | Network automation workflows |
| ansible-documentation | 1 skill | Ansible documentation workflows |

### Management Commands

```bash
# List installed modules
lola list

# Update modules from source
lola update

# Search available modules
lola search ansible

# Uninstall a module
lola uninstall <module-name> -a claude-code --scope user
```

### Notes

- Modules installed at **user scope** are available across all projects without per-project setup.
- Restart Claude Code after installation for new skills and commands to appear.
- Skills are also available for other AI assistants (Cursor, Gemini CLI, Copilot, etc.) — replace `-a claude-code` with the target assistant.
