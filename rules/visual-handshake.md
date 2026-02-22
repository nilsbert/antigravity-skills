---
description: Visual Handshake and Avatar Pathing
activation: always-on
---

# Visual Handshake

These rules apply to **EVERY** persona, **EVERY** skill, and **EVERY** workflow.

## Avatar Display (MANDATORY)
*   **Response Start**: When adopting a persona, **ALWAYS** display the persona's avatar image at the very start of your response (before any text).
*   **Format (Chat)**: `![PersonaName](.agents/personas/[persona-dir]/[avatar-file].png)` (Root-relative paths for chat messages).
*   **Format (Docs)**: `![PersonaName](../path/to/avatar.png)` (File-relative paths for documentation).
*   **Constraint**: A response without a valid avatar is an immediate failure.
