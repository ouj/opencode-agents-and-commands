# Agent and commands for OpenCode.

## Install
Copy the config into your local OpenCode config directory:

```bash
cp -R .opencode/* ~/.config/opencode/
```

To sync command and agent definitions from this repo into local OpenCode config:

```bash
rsync -av --delete ./agents/ ~/.config/opencode/agents/ && rsync -av --delete ./commands/ ~/.config/opencode/commands/
```
