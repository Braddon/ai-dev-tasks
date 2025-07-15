# Rule: Generating a Detailed Task List from PRD and System Architecture

## Goal

To guide an AI assistant in creating a comprehensive, step-by-step task list in Markdown format based on an existing Product Requirements Document (PRD) and System Architecture document. The task list should provide detailed implementation guidance that explicitly addresses the architectural design decisions and ensures comprehensive testing coverage.

## Input Requirements

- **PRD**: Product Requirements Document (filename format: `prd-*.md`)
- **System Architecture**: System architecture document (filename format: `architecture-*.md`)
- **Optional Context**: Existing system context document (filename format: `context-*.md`)

## Process

### Phase 1: Analysis and Component Breakdown
1. **Document Analysis**: Read and analyze the PRD and system architecture documents
2. **Component Identification**: Extract all components, services, and modules defined in the architecture
3. **Detailed Component Breakdown**: For each component identified, suggest the following:
   - **Component Name**: Exact name and location
   - **Component Type**: (React component, API endpoint, service class, utility function, etc.)
   - **Primary Function**: What this component does
   - **Input Parameters**: Expected inputs, props, or parameters
   - **Output/Return**: What it returns or produces
   - **Dependencies**: Other components or services it depends on
   - **State Management**: If applicable, what state it manages
   - **Side Effects**: Any external API calls, database operations, or other side effects

4.  **Diagram of Component and Architecture Decisions** Create a diagram that shows
   -  how these new functions and components are structured
   -  touch points with existing system, including front end, back end, and API
   -  input and output types to each component and function, error behaviour, and other items as relevant

5. ** Diagram data flow**
  - create a diagram of how data flows through these systems, and is shared between front end, backend, and other systems

### Phase 2: Architecture-Driven Task Generation
4. **Generate Parent Tasks**: Create high-level tasks that directly correspond to the architecture layers:
   - Frontend Architecture tasks (Next.js components, pages, state management)
   - Backend Architecture tasks (API routes, service layers, middleware)
   - Data Access Layer tasks (database schemas, ORM setup, caching)
   - Integration tasks (external APIs, microservices, authentication)
   - Infrastructure tasks (deployment, monitoring, security)
5. **Present Parent Tasks**: Show the high-level tasks and ask for confirmation with "Go"

### Phase 3: Detailed Implementation Planning
6. **Generate Sub-Tasks**: Break down each parent task into specific, actionable sub-tasks that:
   - Follow the architectural patterns specified in the system design
   - Implement the functional requirements from the PRD
   - Include comprehensive testing for each component
   - Address security, performance, and scalability considerations from the architecture
   - Implement monitoring and observability as specified

### Phase 4: Testing Strategy Integration
7. **Test Planning**: For each component and function, identify:
   - **Unit Tests**: Test individual functions and components in isolation
   - **Integration Tests**: Test component interactions and API integrations
   - **End-to-End Tests**: Test complete user workflows from the PRD
   - **Performance Tests**: Validate performance requirements from architecture
   - **Security Tests**: Validate security measures and authentication flows
   - **Error Handling Tests**: Test edge cases and error scenarios

### Phase 5: File Structure and Documentation
8. **File Identification**: Based on the architecture and tasks, identify all files that need to be created or modified
9. **Generate Final Output**: Create the comprehensive task list with proper structure

## Component Breakdown Questions

Before generating tasks, ask the user to provide detailed information for each major component:

### For Frontend Components:
- Component name and file location
- Props interface definition
- State management approach (useState, useContext, external store)
- Event handlers and user interactions
- API calls or data fetching requirements
- Styling approach and design system integration

### For Backend Services:
- Service class name and location
- Method signatures and return types
- Database entities and relationships
- External API integrations
- Authentication and authorization requirements
- Error handling and logging specifications

### For Database Components:
- Table/collection names and schemas
- Relationships and foreign keys
- Indexing strategies
- Migration requirements
- Seed data specifications

### For API Endpoints:
- Route paths and HTTP methods
- Request/response schemas
- Validation rules
- Rate limiting and security measures
- Error response formats

## Architecture Integration Requirements

Tasks must explicitly address:

1. **Architectural Patterns**: Implement the specific patterns chosen in the system architecture (microservices, modular monolith, etc.)
2. **Technology Stack**: Use the exact technologies specified in the architecture
3. **Security Framework**: Implement the security measures and authentication patterns specified
4. **Performance Standards**: Meet the performance targets and caching strategies defined
5. **Integration Points**: Properly integrate with existing microservices and databases as specified
6. **Monitoring & Observability**: Implement the logging, metrics, and tracing approaches defined

## Testing Strategy

Each task category must include comprehensive testing:

### Unit Testing
- Test individual functions and methods
- Mock external dependencies
- Test edge cases and error conditions
- Validate input/output contracts

### Integration Testing
- Test component interactions
- Test API endpoint functionality
- Test database operations
- Test third-party service integrations

### End-to-End Testing
- Test complete user workflows from PRD user stories
- Test authentication and authorization flows
- Test data persistence and retrieval
- Test error handling and recovery

### Performance Testing
- Load testing for API endpoints
- Frontend performance testing
- Database query performance
- Caching effectiveness validation

### Security Testing
- Authentication and authorization testing
- Input validation and sanitization testing
- OWASP security checklist validation
- API security testing

## Output Format

```markdown
# Task List: [Feature Name]

## Architecture Overview
Brief summary of how this implementation follows the system architecture design patterns and decisions.

## Component Breakdown Summary
| Component | Type | Function | Dependencies | Testing Requirements |
|-----------|------|----------|--------------|---------------------|
| ComponentName | React Component | Brief description | List of deps | Unit, Integration, E2E |

## Relevant Files

### Frontend Files
- `pages/[feature]/index.tsx` - Main page component implementing [architectural pattern]
- `components/[feature]/[Component].tsx` - Feature-specific component
- `components/[feature]/[Component].test.tsx` - Unit tests for component
- `hooks/use[Feature].ts` - Custom hook for state management
- `hooks/use[Feature].test.ts` - Unit tests for custom hook

### Backend Files
- `pages/api/[feature]/[endpoint].ts` - API endpoint following [API pattern]
- `pages/api/[feature]/[endpoint].test.ts` - API endpoint tests
- `lib/services/[feature]Service.ts` - Service layer implementation
- `lib/services/[feature]Service.test.ts` - Service layer tests
- `lib/models/[Feature].ts` - Data models and schemas
- `lib/models/[Feature].test.ts` - Model validation tests

### Database Files
- `prisma/migrations/[timestamp]_add_[feature].sql` - Database migration
- `prisma/seed/[feature].ts` - Seed data for testing
- `lib/db/[feature]Repository.ts` - Data access layer
- `lib/db/[feature]Repository.test.ts` - Repository tests

### Integration & E2E Tests
- `tests/integration/[feature].test.ts` - Integration tests
- `tests/e2e/[feature].spec.ts` - End-to-end tests
- `tests/performance/[feature].test.ts` - Performance tests

### Infrastructure & Configuration
- `lib/config/[feature].ts` - Feature configuration
- `lib/middleware/[feature].ts` - Custom middleware
- `lib/utils/[feature].ts` - Utility functions
- `lib/utils/[feature].test.ts` - Utility function tests

## Implementation Tasks

### 1.0 Architecture Setup and Configuration
- [ ] 1.1 Set up project structure following [architectural pattern]
- [ ] 1.2 Configure build tools and dependencies as specified in architecture
- [ ] 1.3 Set up testing framework and configuration
- [ ] 1.4 Configure monitoring and logging as per architecture specification
- [ ] 1.5 Set up security configuration and authentication framework

### 2.0 Database and Data Layer Implementation
- [ ] 2.1 Create database schema and migrations following data architecture
- [ ] 2.2 Implement data models with validation according to schema design
- [ ] 2.3 Create repository pattern implementation for data access
- [ ] 2.4 Set up caching layer as specified in architecture
- [ ] 2.5 Write comprehensive unit tests for data layer
- [ ] 2.6 Write integration tests for database operations
- [ ] 2.7 Set up seed data for testing and development

### 3.0 Backend Service Layer Implementation
- [ ] 3.1 Implement service classes following architectural patterns
- [ ] 3.2 Create API endpoints adhering to API design patterns
- [ ] 3.3 Implement authentication and authorization middleware
- [ ] 3.4 Set up request validation and error handling
- [ ] 3.5 Implement rate limiting and security measures
- [ ] 3.6 Write unit tests for service layer methods
- [ ] 3.7 Write integration tests for API endpoints
- [ ] 3.8 Implement logging and monitoring as specified

### 4.0 Frontend Component Implementation
- [ ] 4.1 Create page components following Next.js architecture patterns
- [ ] 4.2 Implement feature-specific React components
- [ ] 4.3 Set up state management following architectural decisions
- [ ] 4.4 Implement client-side data fetching patterns
- [ ] 4.5 Create custom hooks for reusable logic
- [ ] 4.6 Implement form handling and validation
- [ ] 4.7 Write unit tests for React components
- [ ] 4.8 Write integration tests for user interactions
- [ ] 4.9 Implement responsive design and accessibility features

### 5.0 Integration and System Testing
- [ ] 5.1 Set up end-to-end testing framework
- [ ] 5.2 Write E2E tests for complete user workflows from PRD
- [ ] 5.3 Implement performance testing for critical paths
- [ ] 5.4 Set up security testing and vulnerability scanning
- [ ] 5.5 Test integration with existing microservices
- [ ] 5.6 Validate monitoring and alerting functionality
- [ ] 5.7 Test error handling and recovery scenarios
- [ ] 5.8 Perform load testing and scalability validation

### 6.0 Deployment and DevOps
- [ ] 6.1 Set up CI/CD pipeline following architecture specifications
- [ ] 6.2 Configure deployment environments (dev, staging, production)
- [ ] 6.3 Implement infrastructure as code for reproducible deployments
- [ ] 6.4 Set up monitoring and observability in production
- [ ] 6.5 Configure backup and disaster recovery procedures
- [ ] 6.6 Implement security scanning and compliance checks
- [ ] 6.7 Set up automated testing in CI/CD pipeline
- [ ] 6.8 Configure performance monitoring and alerting

## Testing Commands

- `npm test` - Run all unit tests
- `npm run test:integration` - Run integration tests
- `npm run test:e2e` - Run end-to-end tests
- `npm run test:performance` - Run performance tests
- `npm run test:security` - Run security tests
- `npm run test:coverage` - Generate test coverage report

## Architecture Compliance Checklist

- [ ] Follows specified architectural patterns from system design
- [ ] Implements security framework as defined in architecture
- [ ] Meets performance standards specified in architecture
- [ ] Integrates properly with existing microservices
- [ ] Implements monitoring and observability as specified
- [ ] Follows data architecture and caching strategies
- [ ] Implements error handling and resilience patterns
- [ ] Follows API design patterns and conventions
- [ ] Meets scalability requirements from architecture
- [ ] Implements proper logging and audit trails

## Notes

- All tasks explicitly reference and implement the architectural decisions made in the system design
- Each component must have comprehensive test coverage including unit, integration, and E2E tests
- Performance and security testing are integral parts of the implementation process
- Tasks are organized to follow the architecture layers: data, service, API, and presentation
- Integration points with existing systems are clearly identified and tested
- Monitoring and observability are built into each layer of the implementation
```

## Interaction Model

1. **Phase 1**: Create a document with detailed component breakdown questions suggest detailed component specifications that will implement the components in line with our constraints and requirements;
2. **Phase 2**: Generate high-level tasks based on architecture and PRD, then ask for "Go" confirmation
3. **Phase 3**: Generate detailed sub-tasks with comprehensive testing requirements
4. **Phase 4**: Finalize and save the task list with proper file structure

## Target Audience

Assume the primary reader is a **junior developer** who needs explicit guidance on implementing the architectural patterns and comprehensive testing strategies defined in the system design.
