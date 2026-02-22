---
description: Engineering & Design Standards
activation: model-decision
---

# Engineering & Design Standards (Rules)

# Engineering & Design Standards

## UI/UX Gate
*   **Jony Vision**: For any feature involving a new UI page, component, or visual transition, **Jony** (UI/UX) **MUST** generate a high-quality image mockup (`generate_image`) during Refinement. Implementation cannot start without explicit user approval.

## Path Standards
*   **System Tools**: Always use absolute paths for internal system tools and file operations.
*   **Documentation**: Always use relative paths for links and images within docs (`docs/`, `.md` files) to ensure multi-device compatibility.

## Persona Standards
*   **Organization**: Every persona must have a dedicated subfolder (e.g., `docs/product/personas/nils/`) containing `persona.md` and `avatar.png`.
*   **Visual Identity**: Persona avatars must be "portrait, Pixar 3D comic style" for consistent project branding.

## Domain Driven Design
*   **Martins's DDD**: Default to DDD patterns (Entities/Value Objects) for logic unless a "Fast/Simple" path is explicitly requested.
