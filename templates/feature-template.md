---
name: Feature Request (Strict DoR)
about: Propose a new feature with strict Definition of Ready requirements.
title: 'feat: '
state: refining, ready, in develop, done
persona: [Name, e.g., Haruki]
---

## Feature Story
**GitHub Issue**: #

**As a** [role]
**I want** [feature/capability]
**So that** [benefit/value]
**So that** [benefit/value]

## 🏗️ Domain Alignment (Bounded Contexts)
*Rule: A Feature should ideally live within ONE Subdomain.*
* **Primary Domain**: [e.g., Study, Battle, Profile]
* **Cross-Domain Dependencies**: [e.g., Emits event to Battle] (If any, explicitly list them).

## 🗣 Ubiquitous Language (DDD)
*Define key domain terms here to ensure shared understanding.*
- **Term 1**: Definition...
- **Term 2**: Definition...

## Acceptance Criteria
- [ ] ...

## Implementation Hints (Technical Strategy)
*Provide guidance for the developer/agent here.*
- **Suggested Libraries**: ...
- **Relevant Files**: ...
- **Pseudocode / SQL**: ...

## BDD Scenarios (Exhaustive - Min 20 Required)
*Requirement: define at least 20 scenarios covering Happy, Problem, Error, and Edge cases.*

### 1. Happy Path
**Given** [precondition]
**And** [additional precondition]
**When** [action]
**Then** [outcome]
**And** [additional outcome]

### 2. Problem Path
**Given** [precondition]
**When** [action]
**Then** [error message/outcome]
**And** [system state preservation]
**But** [negative consequence avoided]

### 3. Error Path
**Given** [precondition]
**When** [invalid action]
**Then** [graceful failure]

### 4. Edge Case
**Given** [rare precondition]
**When** [action]
**Then** [expected behavior]

### 5. Data Driven (Scenario Outline)
**Scenario Outline**: Validate inputs
**Given** the input is <input>
**When** the validator runs
**Then** the result should be <result>

**Examples**:
| input   | result  |
| "valid" | "true"  |
| "inv"   | "false" |
| ""      | "false" |

### 6. Shared Context (Background)
*Use 'Background' for steps common to all scenarios in a feature file*
**Background**:
**Given** the user is logged in
**And** the user has 'admin' permissions

**Scenario**: Admin specific action
**When** ...
**Then** ...


## End-to-End / Frontend Tests (Min 3 Required)
*Requirement: define at least 3 scenarios testing the whole feature from user perspective (UI flows).*

### Scenario 1: [Name]
- Step 1: ...
- Step 2: ...
- Expectation: ...

### Scenario 2: [Name]
- Step 1: ...
- Step 2: ...
- Expectation: ...

### Scenario 3: [Name]
- Step 1: ...
- Step 2: ...
- Expectation: ...

## Technical Details & NFRs
- **Performance**: ...
- **Security Check**: ...
- **Dependencies**: ...

## Implementation Plan
*Detailed breakdown of changes required to deliver this feature.*

### Proposed Changes
#### [Infrastructure] (Optional)
- [ ] [NEW/MODIFY] Description of cloud resources, database migrations, or environment variables needed.

#### [Component/Area]
- [ ] [NEW] `path/to/new/file` - Description
- [ ] [MODIFY] `path/to/existing/file` - Description of change

### Verification Plan
#### Automated Tests
- [ ] Unit Tests: `npm test path/to/test`
- [ ] Integration Tests: `npm run integration`

#### Manual Verification
- [ ] Step 1: ...
- [ ] Step 2: ...

## Quality Assurance (Lisa)
### Quality Scenarios (Attributes)
*Format: Source -> Stimulus -> Environment -> Response -> Measure*

**Scenario 1: [Title, e.g. Performance]**
- **Stimulus**: [e.g. 1000 concurrent updates]
- **Environment**: [e.g. Normal Operation / Peak Load]
- **Response**: [e.g. UI remains responsive]
- **Measure**: [e.g. Latency < 100ms]

### Exploratory Charters (Q3)
- **Charter**: Explore [Feature] with [Persona] to discover [Risk].

### Test Strategy (Isolation)
*Dependencies to mock for Domain Isolation.*
- **Mocks**: [e.g. `BattleService`, `ProfileContext`]
- **Data**: [e.g. `MockDeck`, `GuestUser`]
