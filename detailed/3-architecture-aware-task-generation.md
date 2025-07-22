# Task Generation Rules for Next.js App Router Implementation

## Purpose
Generate comprehensive, step-by-step task lists (`tasks-*.md`) for implementing PRD features in existing Next.js App Router applications, targeting junior developers who need explicit implementation guidance.

## Input Requirements
- **PRD**: Product Requirements Document (`prd-*.md`)
- **Architecture**: System architecture document (`architecture-*.md`)  
- **Technical Requirements**: Implementation details (`techreq-*.md`)
- **Context** (Optional): Existing system context (`context-*.md`)

## Core Technology Standards
- **Framework**: Next.js App Router with app/ directory structure
- **Components**: Server Components (default), Client Components ("use client" when needed)
- **Styling**: Tailwind CSS with responsive design principles
- **Quality**: ESLint standards, comprehensive testing
- **Actions**: Server Actions for mutations, API routes for external integrations

## Task Structure Requirements

### Component Detail Standards
Each task/subtask must specify:

**For All Components:**
- Exact name and file location within app/ structure
- Component type (Server/Client Component, API route, Server Action)
- Input parameters, props, TypeScript interfaces
- Dependencies and integration points
- Testing requirements (unit, integration, E2E)

**For Frontend Components:**
- Server vs Client Component designation with rationale
- Data fetching strategy (server-side in Server Components, client-side in Client Components)
- State management approach (useState for Client, server state for Server)
- Event handlers and user interactions (Client Components only)
- Server Actions integration for form handling
- Tailwind CSS styling and responsive design
- Loading states (loading.tsx, error.tsx, not-found.tsx)

**For Backend Services:**
- API route handlers (app/api/[route]/route.ts) with HTTP methods
- Server Actions for form submissions and mutations
- Request/response schemas and validation
- Authentication/authorization middleware
- Error handling and logging specifications
- Integration with Server Components

**For Database Changes:**
- Schema definitions, relationships, indexes
- Migration requirements and seed data
- Repository patterns and data access layers

## Implementation Process

### Phase 1: Architecture Analysis
1. **Generate Parent Tasks**: Create high-level tasks corresponding to architecture layers:
   - Frontend (Next.js components, pages, layouts)
   - Backend (API routes, Server Actions, services)
   - Data Layer (schemas, repositories, caching)
   - Integration (external APIs, authentication)
   - Infrastructure (deployment, monitoring)

2. **Present for Confirmation**: Show parent tasks, await "Go" confirmation

### Phase 2: Detailed Task Breakdown
3. **Generate Sub-Tasks**: Break down each parent into specific, actionable sub-tasks that:
   - Follow architectural patterns from system design
   - Implement functional requirements from PRD
   - Include comprehensive testing for each component
   - Address security, performance, scalability from architecture
   - Implement specified monitoring and observability

### Phase 3: Testing Integration
4. **Test Planning**: For each component, specify:
   - **Unit Tests**: Individual functions/components in isolation
   - **Integration Tests**: Component interactions, API integrations
   - **End-to-End Tests**: Complete user workflows from PRD
   - **Performance Tests**: Validate architectural performance requirements
   - **Security Tests**: Authentication flows, input validation
   - **Error Handling Tests**: Edge cases and error scenarios

## Task Content Standards

### Information Density Rules
- **Parent Task Description**: Include only details shared across 2+ subtasks
- **Subtask Description**: Include specific implementation details unique to that subtask
- **Architectural Context**: Reference specific patterns and decisions from system design
- **Requirement Traceability**: Map each task/subtask to specific requirements

### Detail Requirements
Tasks must address all architectural concerns:
- Next.js App Router patterns and conventions
- Existing technology stack integration
- Security framework implementation
- Performance targets and caching strategies
- Microservice integration points
- Monitoring and observability approaches
- Code quality standards (ESLint, formatting)
- Design system consistency (Tailwind CSS)

## Output Structure

### File Organization
- **Task Files**: `tasks-[project-name]-[number].md`
- **Traceability Matrix**: `tracmat-[project-name].md`

### Task File Template
```markdown
# Task List: [Feature Name]

## Architecture Integration
How this implementation follows system design patterns and decisions.

## Component Breakdown
| Component | Type | Function | Dependencies | Tests |
|-----------|------|----------|--------------|-------|
| Name | Server/Client/API | Purpose | List | Unit/Int/E2E |

## Implementation Tasks

### 1.0 [Architecture Layer Name]
Requirements implemented by this task group.

- [ ] 1.1 [Specific Subtask]
  - Implementation details unique to this subtask
  - Architectural patterns and technical requirements
  - Testing specifications

### 2.0 [Next Architecture Layer]
[Continue pattern...]
```

## Quality Assurance

### Task Completeness Verification
- All technical requirements covered in traceability matrix
- Each architectural layer properly addressed
- Server/Client Component boundaries correctly defined
- Server Actions used appropriately for mutations
- API routes used correctly for external integrations
- Comprehensive testing strategy for each component
- Performance and security requirements integrated
- Monitoring and observability properly implemented

### File Deliverables
1. **Task files** with complete implementation guidance
2. **Traceability matrix** mapping requirements to tasks/subtasks
3. **Verification report** confirming complete coverage
4. **File summary** describing purpose and structure of deliverables

## Post-Generation Analysis Requirements

After creating all task files and traceability matrix, provide:

### 1. File Summary
- **Purpose**: Explain each generated file and its role in the implementation process
- **Structure**: Describe the organization and relationship between files
- **Usage**: How developers should use these files during implementation

### 2. Risk Assessment
Identify potential risks not addressed in the design:
- **Technical Risks**: Performance bottlenecks, scalability limits, integration failures
- **Implementation Risks**: Complex dependencies, resource constraints, timeline challenges
- **Operational Risks**: Monitoring gaps, security vulnerabilities, maintenance overhead
- **Business Risks**: Feature scope creep, requirement changes, stakeholder alignment

### 3. Complexity Analysis
Identify requirements that may need further breakdown:
- **High-Complexity Subtasks**: Tasks that may overwhelm junior developers
- **Multi-System Integration**: Requirements spanning multiple architectural boundaries
- **Performance-Critical Paths**: Components requiring specialized optimization
- **Security-Sensitive Areas**: Authentication, authorization, data protection implementations

### 4. Requirements Clarification
Highlight areas needing stakeholder input before implementation:
- **Ambiguous Requirements**: Unclear functional or non-functional specifications
- **Missing Dependencies**: External systems, third-party services, or data sources
- **Undefined Interfaces**: API contracts, data formats, or integration protocols
- **Assumption Validation**: Technical assumptions that require business confirmation
- **Scope Boundaries**: Feature limits, user permissions, or system constraints