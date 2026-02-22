# Component Spec: [Component Name]

> **TYPE:** [Atom / Molecule / Organism]
> **STATUS:** [Draft / Ready for Dev]
> **FIGMA LINK:** [Insert URL]

---

## 1. Anatomy & Layout
* **Container:** [e.g., Flexbox, Row, Centered]
* **Padding:** [e.g., Token: `p-4` (1rem)]
* **Background:** [e.g., Token: `bg-surface-primary`]
* **Border/Radius:** [e.g., `rounded-md`]

---

## 2. States & Props (The Contract)
*Define the API for this component.*

| Prop Name | Type | Default | Description |
| :--- | :--- | :--- | :--- |
| `variant` | String | 'primary' | Options: 'primary', 'secondary', 'ghost' |
| `isDisabled` | Boolean | false | Visual opacity 50%, pointer-events-none |
| `icon` | SVG | null | Optional leading icon |

---

## 3. Accessibility (A11y)
* **Role:** [e.g., `button`]
* **Tab Index:** [e.g., 0]
* **Keyboard:** Enter/Space triggers action.
* **Aria-Label:** Required if icon-only.

---

## 4. Responsive Behavior
* **Mobile (<768px):** [e.g., Full width, Stack vertical]
* **Desktop:** [e.g., Fixed width, Horizontal]