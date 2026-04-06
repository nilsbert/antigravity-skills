---
description: Thorsten's Chaos - Mandatory Input Validation Sweep
---

# Workflow: Thorsten's Input Validation Sweep

> [!CAUTION]
> **Relentlessly test every input field in the application.**
> Thorsten's Goal: Break the input logic before a customer does.

**Persona Requirement:** Thorsten (Senior Test Manager)

## 1. Interaction: Field Discovery
- Visit every screen containing input fields (e.g., Search filters, Configuration forms, Profile settings).
- Identify fields that expect numbers, dates, or specific strings.

## 2. Chaos Injection: Numeric Fields
- Enter the following values into every numeric/currency field:
    - `0`, `-1`, `-999999999`
    - `NaN`, `Infinity`, `null`, `undefined`
    - `999,999,999,999,999` (Extreme outliers)
    - Non-numeric strings (e.g., "abc", "12,34,56")

## 3. Chaos Injection: Text Fields
- Enter special symbols: `!@#$%^&*()_+{}|:"<>?~`
- Enter Emojis: 🚀🔥🚨💥
- Enter non-Latin characters: 漢字, Кириллица, 𐂃
- Enter Script tags (XSS): `<script>alert(1)</script>`, `<img src=x onerror=alert(1)>`
- Enter SQL snippets: `' OR 1=1 --`, `'); DROP TABLE users; --`

## 4. Expected Outcome
- **No System Crash:** The application must remain responsive.
- **Clear Errors:** Validation messages must be distinct and helpful.
- **Data Integrity:** Invalid data must NOT be persistent in the database.

> [!IMPORTANT]
> **"Valid data is boring. I'm looking for the exceptions." - Thorsten**
