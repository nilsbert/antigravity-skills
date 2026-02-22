# Feature Test Template (BDD)

> **Purpose:** Verification of the User Journey.
> **Audience:** Product Owners, Designers, Non-Technical Stakeholders.

The goal is to write tests that read like a story.

## Critical Requirements

1. **Every scenario MUST have a JSDoc description** with Given/When/Then
2. **Test names MUST be user-friendly** - non-technical stakeholders should understand them
3. **Test output should tell a story** - the test runner should display readable scenarios

## Structure

```typescript
/**
 * @feature [Name of Feature] (REQUIRED)
 * @requirement [Link to Feature/Story File] (REQUIRED)
 * @persona [Persona Name] (REQUIRED)
 */
describe('Feature: [Name of Feature]', () => {
    
    /**
     * REQUIRED: Describe the user scenario in Given/When/Then format
     * @scenario [User Goal / Situation] (REQUIRED)
     * @given [The starting state] (REQUIRED)
     * @when [The user interaction] (REQUIRED)
     * @then [The observable result] (REQUIRED)
     * @value [Why is this important?] (REQUIRED)
     */
    describe('Scenario: [User Goal]', () => {
        
        // Test name should describe the OUTCOME from the user's perspective
        it('should [Visual Result] when [User Action]', () => {
            // ... implementation
        });
    });
});
```

## Example (Correct)

```typescript
/**
 * @feature Grading
 * @requirement feat-001/story-02.md
 * @persona Haruki
 */
describe('Feature: Grading', () => {
    /**
     * @scenario User knows the answer (Happy Path)
     * @given User is viewing the back of a card
     * @when User clicks the "Good" button
     * @then The card slides out to the left and next card appears
     * @value Verifies the core SRS loop and positive feedback animation
     */
    describe('Scenario: User knows the answer', () => {
        it('should slide the card away when "Good" is clicked', () => {
            // ...
        });
    });
});
```

## Example (Incorrect - Too Technical)

```typescript
describe('GradeComponent', () => {
    it('onclick handler calls dispatch with payload', () => {
        // ...
    });
});
```

## Test Execution Output

When tests run, they should be readable as user stories:

```
✓ Feature: Grading
  ✓ Scenario: User knows the answer
    ✓ should slide the card away when "Good" is clicked (24ms)
```

Even a non-technical Product Owner can understand: **"When the user clicks Good, the card slides away."**
