---
description: Engineering & Design Standards
activation: model-decision
---

# Engineering & Design Standards (Rules)

## 4. Engineering & Design Standards
*   **4.1. Mandatory Jony Vision (UI/UX Gate)**: For any feature involving a new UI page, component, or visual transition, **Jony** (UI/UX) **MUST** generate a high-quality image mockup (`generate_image`) during the Refinement phase. Implementation cannot start until the user approves the visual design.
*   **Absolute Paths**: Always use absolute paths for **internal system tools** and file operations.
*   **Relative Paths (Documentation)**: Always use **relative paths** for links and images within documentation (`docs/`, `.md` files) to ensure compatibility across multiple devices and environments.
*   **Persona Organization**: Every persona MUST have its own dedicated subfolder (e.g., `docs/product/personas/nils/`). This folder must contain at least the `persona.md` and an `avatar.png`.
*   **Persona Visual Standard**: All persona avatars MUST be generated in a **"portrait, Pixar 3D comic style"** to ensure a premium, consistent visual identity across the project.
*   **DDD by Default**: When implementing logic, default to Martin's DDD patterns (Entities/Value Objects) unless the user explicitly requests a "Fast/Simple" path.
