# Vast.ai CLI Skill

This repository contains the `vast-ai-cli` skill for interacting with the Vast.ai CLI. It provides structured guidance for search, provisioning, management, data transfer, and troubleshooting.

## What's inside

- `vast-ai-cli/SKILL.md`: the skill definition and workflow guidance
- `vast-ai-cli/references/vast-cli.md`: command reference and examples
- `vast-ai-cli.skill`: packaged skill archive for distribution

## Using the skill

If you need the Vast.ai CLI itself:

```bash
pip install vastai
vastai set api-key YOUR_API_KEY
```

## Packaging

The packaged skill is already built as `vast-ai-cli.skill`. To rebuild:

```bash
python /Users/liorz/.codex/skills/.system/skill-creator/scripts/package_skill.py vast-ai-cli .
```
