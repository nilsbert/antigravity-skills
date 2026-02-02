# Logic Test Template (Unit)

> **Purpose:** Documentation of Business Rules & Math.
> **Audience:** Architects, Developers, Domain Experts.

The goal is to simplify complex logic into readable rules.

## Critical Requirements

1. **Every test MUST have a JSDoc description** explaining WHAT is being tested and WHY
2. **Test names MUST be descriptive** and read naturally during execution
3. **Test output should be self-documenting** - anyone reading the console should understand what passed/failed

## Structure

```typescript
/**
 * @logic [Domain Concept] (REQUIRED)
 * @requirement [Link to Story/Bug] (REQUIRED)
 */
describe('Logic: [Domain Concept]', () => {
    
    /**
     * REQUIRED: Describe what is being tested and why
     * @rule [Business Rule Description] (REQUIRED)
     * @input [Specific arguments/context state]
     * @output [Expected return value or state change]
     * @invariant [What must ALWAYS be true? e.g. "Stability never < 0"]
     * @value [Why this rule exists?] (REQUIRED)
     */
    describe('Rule: [Business Requirement]', () => {
        
        // Test name should read naturally: "should [action/outcome] when/given [condition]"
        it('should [satisfy rule] given [specific inputs]', () => {
             // ... implementation
        });
    });
});
```

## Example (Correct)

```typescript
/**
 * @logic Interval Calculation
 * @requirement feat-006/story-01.md
 */
describe('Logic: Interval Calculation', () => {
    /**
     * @rule "Again" resets stability
     * @input PreviousInterval > 0, Grade = "Again"
     * @output Stability = 0
     * @invariant NextDueDate < CurrentTime + 10min
     * @value Critical for SRS efficiency, ensures user relearns forgotten items
     */
    describe('Rule: "Again" resets stability', () => {
        it('should set stability to 0 given any previous interval', () => {
             // ...
        });
    });
});
```

## Test Execution Output

When tests run, they should display clearly:

```
✓ Logic: Interval Calculation
  ✓ Rule: "Again" resets stability
    ✓ should set stability to 0 given any previous interval (12ms)
```

The test name **"should set stability to 0 given any previous interval"** is immediately understandable without reading the code.
