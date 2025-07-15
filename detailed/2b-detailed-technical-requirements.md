# Rule: Generating Detailed Component Design from PRD and System Architecture

## Goal
To guide an AI assistant in creating a comprehensive detailed design document that defines every component, function, interface, and integration point needed to implement a feature. This detailed design serves as a complete specification for subsequent task generation and implementation.

## Input Requirements
- **PRD**: Product Requirements Document (filename format: `prd-*.md`)
- **System Architecture**: System architecture document (filename format: `architecture-*.md`)
- **Optional Context**: Existing system context document (filename format: `context-*.md`)

## Process

### Phase 1: Requirements Analysis and Extraction
1. **Functional Requirements Mapping**: Extract and categorize all functional requirements from the PRD
2. **Non-Functional Requirements Identification**: Identify performance, security, scalability, and usability requirements
3. **User Journey Analysis**: Map each user story to specific system interactions and data flows
4. **Integration Points Analysis**: Identify all touchpoints with existing systems from the architecture document

### Phase 2: Component Discovery and Classification
1. **Component Inventory**: Create a comprehensive list of all components needed, categorized by:
   - **Frontend Components**: React components, pages, hooks, context providers
   - **Backend Services**: API endpoints, service classes, middleware, validators
   - **Data Layer**: Models, repositories, database schemas, migration scripts
   - **Integration Layer**: External API clients, message queue handlers, event processors
   - **Infrastructure**: Configuration, deployment scripts, monitoring setup

2. **Dependency Mapping**: For each component, identify:
   - **Direct Dependencies**: Components this component directly uses
   - **Inverse Dependencies**: Components that depend on this component
   - **External Dependencies**: Third-party libraries, services, or APIs
   - **Data Dependencies**: Database tables, external data sources, cache stores

### Phase 3: Detailed Component Specification

For each component identified, define the following comprehensive specification:

#### A. Component Identity
- **Full Name**: Complete component name with namespace/module
- **File Location**: Exact file path in the project structure
- **Component Type**: React Component, API Route, Service Class, Utility Function, Database Model, etc.
- **Architectural Layer**: Presentation, Business Logic, Data Access, Integration, Infrastructure

#### B. Functional Specification
- **Primary Purpose**: Single-sentence description of the component's main responsibility
- **Secondary Functions**: Additional responsibilities this component handles
- **Business Rules**: Specific business logic this component must enforce
- **Validation Rules**: Input validation, business rule validation, data integrity checks

#### C. Interface Definition
- **Input Schema**: Complete TypeScript interface or JSON schema for inputs
  ```typescript
  interface ComponentProps {
    requiredProp: string;
    optionalProp?: number;
    callbackProp: (data: ResponseType) => void;
  }
  ```
- **Output Schema**: Complete TypeScript interface for return values
- **Event Emissions**: Events this component emits and their payload schemas
- **State Schema**: If stateful, complete definition of managed state structure

#### D. Behavior Specification
- **Success Scenarios**: Normal operation behavior and expected outcomes
- **Error Scenarios**: All possible error conditions and their handling
- **Edge Cases**: Boundary conditions and their expected behavior
- **Performance Requirements**: Response time, throughput, memory usage constraints
- **Security Requirements**: Authentication, authorization, data protection needs

#### E. Integration Specification
- **API Contracts**: For external integrations, complete API specifications
- **Database Contracts**: Table schemas, relationships, indexing requirements
- **Message Contracts**: For async communication, message format and routing
- **Event Contracts**: Event schemas for event-driven architectures

#### F. Testing Specification
- **Unit Test Requirements**: Specific test cases that must be covered
- **Integration Test Requirements**: Integration scenarios that must be tested
- **Mock Requirements**: External dependencies that need mocking
- **Test Data Requirements**: Specific test data sets needed

### Phase 4: System Integration Design

#### A. Data Flow Specification
Create detailed data flow diagrams showing:
- **Request/Response Flows**: Complete HTTP request lifecycles
- **Data Transformation Points**: Where and how data is transformed
- **Validation Checkpoints**: Where validation occurs in the flow
- **Error Propagation**: How errors flow through the system
- **State Changes**: How component interactions affect system state

#### B. Component Interaction Specification
- **Synchronous Interactions**: Direct function calls, API calls, database queries
- **Asynchronous Interactions**: Event emissions, message queue interactions, webhooks
- **State Synchronization**: How components maintain consistent state
- **Error Boundary Definition**: Where errors are caught and handled

#### C. Architecture Compliance Verification
- **Pattern Adherence**: Verify each component follows specified architectural patterns
- **Security Compliance**: Ensure security requirements are met at each layer
- **Performance Compliance**: Verify performance requirements can be met
- **Scalability Compliance**: Ensure design supports specified scaling requirements

### Phase 5: Documentation and Validation

#### A. Component Relationship Diagrams
Create comprehensive diagrams showing:
- **System Architecture Diagram**: High-level component relationships
- **Detailed Component Diagram**: Component dependencies and interfaces
- **Data Flow Diagram**: End-to-end data movement and transformation
- **Integration Diagram**: External system touchpoints and protocols
- **Error Flow Diagram**: Error propagation and handling paths

#### B. Interface Contract Documentation
- **API Documentation**: Complete OpenAPI/Swagger specifications for all endpoints
- **Component Documentation**: JSDoc/TSDoc for all components and functions
- **Database Documentation**: Schema documentation with relationships and constraints
- **Configuration Documentation**: All configurable parameters and their effects

#### C. Design Validation Checklist
- [ ] All PRD functional requirements are addressed by specific components
- [ ] All user stories have complete implementation paths defined
- [ ] All architectural decisions from system architecture are reflected
- [ ] All integration points with existing systems are specified
- [ ] All error scenarios have defined handling mechanisms
- [ ] All performance requirements have supporting design elements
- [ ] All security requirements are addressed in the design
- [ ] All components have complete interface definitions
- [ ] All data flows are documented and validated
- [ ] All testing requirements are specified

## Output Format

```markdown
# Detailed Design: [Feature Name]

## Executive Summary
Brief overview of the design approach and key architectural decisions.

## Requirements Traceability Matrix
| PRD Requirement | Design Components | Acceptance Criteria |
|-----------------|-------------------|-------------------|
| REQ-001 | Component1, Component2 | Specific measurable criteria |

## Component Specifications

### Frontend Components

#### [ComponentName]
- **Location**: `src/components/[path]/[ComponentName].tsx`
- **Type**: React Functional Component
- **Purpose**: [Single sentence description]
- **Architecture Layer**: Presentation

**Interface Definition:**
```typescript
interface [ComponentName]Props {
  // Complete prop definitions
}

interface [ComponentName]State {
  // State structure if applicable
}
```

**Behavior Specification:**
- **Success Flow**: [Detailed steps for normal operation]
- **Error Handling**: [Specific error scenarios and responses]
- **Edge Cases**: [Boundary conditions and handling]
- **Performance**: [Specific performance requirements]

**Dependencies:**
- Direct: [List of direct dependencies]
- Data: [API endpoints, state stores used]
- External: [Third-party libraries]

**Testing Requirements:**
- Unit Tests: [Specific test scenarios]
- Integration Tests: [Integration test requirements]
- Mock Requirements: [What needs to be mocked]

### Backend Services

#### [ServiceName]
[Similar detailed specification format]

### Data Layer

#### [ModelName]
[Similar detailed specification format]

## System Integration

### Data Flow Diagrams
[Mermaid diagrams showing data flow]

### Component Interaction Diagrams
[Mermaid diagrams showing component relationships]

### Integration Points
[Detailed specifications for all external integrations]

## Architecture Compliance

### Design Patterns Applied
[How the design implements architectural patterns]

### Security Implementation
[How security requirements are addressed]

### Performance Implementation
[How performance requirements are met]

## Validation Results

### Requirements Coverage
[Verification that all requirements are addressed]

### Architecture Compliance
[Verification that design follows architecture]

### Integration Verification
[Verification that all integrations are properly specified]
```

## Key Improvements

1. **Comprehensive Component Specification**: Every component gets a complete specification including interfaces, behavior, and testing requirements
2. **Requirements Traceability**: Direct mapping from PRD requirements to design components
3. **Interface Contracts**: Complete TypeScript/schema definitions for all interfaces
4. **Error Scenario Planning**: Systematic identification and specification of error handling
5. **Testing Integration**: Testing requirements defined during design phase
6. **Validation Framework**: Built-in validation to ensure design completeness
7. **Architecture Compliance**: Explicit verification that design follows architectural decisions
8. **Integration Specification**: Detailed specification of all system touchpoints

This enhanced approach ensures that the detailed design phase produces a complete, unambiguous specification that can directly drive task generation and implementation.
