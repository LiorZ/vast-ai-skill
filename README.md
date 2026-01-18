# Vast.ai CLI Skills

This repository contains AI agent skill documentation for working with the Vast.ai CLI.

## What’s inside

- A comprehensive skill file at `.claude/vast-ai-skill.md`
- Usage guidance for searching offers, creating/destroying instances, volumes, data transfer, and auth
- Practical command examples and error-handling notes for agent workflows

## Quick start

Install the Vast.ai CLI:

```bash
pip install vastai
```

Set your API key:

```bash
vastai set api-key YOUR_API_KEY
```

## Example commands

```bash
# Search for GPU instances
vastai search offers 'gpu_ram>=24 reliability>0.95'

# Create an instance
vastai create instance OFFER_ID --image pytorch/pytorch:latest --jupyter --direct

# List your instances
vastai show instances

# Destroy an instance
vastai destroy instance INSTANCE_ID
```

## Repository layout

- `SKILLS.md`: catalog and overview
- `.claude/vast-ai-skill.md`: full skill documentation

## Contributing

1. Edit files under `.claude/`
2. Keep the format consistent
3. Add examples and error cases where useful
