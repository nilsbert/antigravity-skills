# Antigravity Skills

This repository contains a collection of shared skills for Google Antigravity.

## Installation

To load these skills into your existing project (replacing any current `.agent` folder), you can use the following one-liner in your terminal. This will backup your existing configuration to `.agent.old` before installing.

### Terminal Command

```bash
# Backup existing .agent folder and clone new skills
if [ -d ".agent" ]; then mv .agent .agent.old.$(date +%s); fi && git clone https://github.com/nilsbert/antigravity-skills .agent && rm -rf .agent/.git
```

### Agent Prompt

You can also ask your Antigravity agent to do this for you with the following prompt:

> Please install the shared skills from `https://github.com/nilsbert/antigravity-skills` into my `.agent` folder. Please back up my current `.agent` folder to `.agent.old` first, then clone the repository, and remove the `.git` directory from the new `.agent` folder so it doesn't conflict with my project's git.
