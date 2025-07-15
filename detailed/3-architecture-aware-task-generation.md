# Rule: Generating a Detailed Task List from PRD and System Architecture

## Goal

To guide an AI assistant in creating a comprehensive, step-by-step task list in Markdown format based on an existing Product Requirements Document (PRD) and System Architecture document. The task list should provide detailed implementation guidance that explicitly addresses the architectural design decisions and ensures comprehensive testing coverage.

## Input Requirements

- **PRD**: Product Requirements Document (filename format: `prd-*.md`)
- **System Architecture**: System architecture document (filename format: `architecture-*.md`)
- **Detailed technical requirements**:  Technical requirements for task generation (filename format: `techreq-*.md`)
- **Optional Context**: Existing system context document (filename format: `context-*.md`)

## Process


### Phase 1: Architecture-Driven Task Generation
4. **Generate Parent Tasks**: Create high-level tasks that directly correspond to the architecture layers:
   - Frontend Architecture tasks (Next.js App Router components, pages, layouts, Server/Client components)
   - Backend Architecture tasks (API route handlers, Server Actions, service layers, middleware)
   - Data Access Layer tasks (database schemas, ORM setup, caching)
   - Integration tasks (external APIs, microservices, authentication)
   - Infrastructure tasks (deployment, monitoring, security)
5. **Present Parent Tasks**: Show the high-level tasks and ask for confirmation with "Go"

### Phase 2: Detailed Implementation Planning
6. **Generate Sub-Tasks**: Break down each parent task into specific, actionable sub-tasks that:
   - Follow the architectural patterns specified in the system design
   - Implement the functional requirements from the PRD
   - Include comprehensive testing for each component
   - Address security, performance, and scalability considerations from the architecture
   - Implement monitoring and observability as specified

### Phase 3: Testing Strategy Integration
7. **Test Planning**: For each component and function, identify:
   - **Unit Tests**: Test individual functions and components in isolation
   - **Integration Tests**: Test component interactions and API integrations
   - **End-to-End Tests**: Test complete user workflows from the PRD
   - **Performance Tests**: Validate performance requirements from architecture
   - **Security Tests**: Validate security measures and authentication flows
   - **Error Handling Tests**: Test edge cases and error scenarios

### Phase 4: File Structure and Documentation
8. **File Identification**: Based on the architecture and tasks, identify all files that need to be created or modified
9. **Generate Final Output**: Create the comprehensive task list with proper structure

## Component Breakdown Questions

Before generating tasks, ensure the following detailed information is available for each major component:

### For Frontend Components:
- Component name and file location (app/[route]/page.tsx, app/[route]/layout.tsx, or components/)
- Component type (Server Component or Client Component with "use client")
- Props interface definition and TypeScript types
- State management approach (useState for client components, server state for server components)
- Data fetching strategy (server-side in Server Components, client-side in Client Components)
- Event handlers and user interactions (client-side only)
- Server Actions integration for mutations
- Styling approach and design system integration
- Loading and error states (loading.tsx, error.tsx, not-found.tsx)

### For Backend Services and Server Actions:
- Service class name and location
- Server Action definitions for form handling and mutations
- Method signatures and return types
- Database entities and relationships
- External API integrations
- Authentication and authorization requirements
- Error handling and logging specifications
- Integration with Server Components and route handlers

### For Database Components:
- Table/collection names and schemas
- Relationships and foreign keys
- Indexing strategies
- Migration requirements
- Seed data specifications

### For API Endpoints and Server Actions:
- Route handler paths (app/api/[route]/route.ts) and HTTP methods (GET, POST, PUT, DELETE)
- Server Actions for form submissions and mutations
- Request/response schemas and TypeScript interfaces
- Validation rules and input sanitization
- Authentication and authorization middleware
- Rate limiting and security measures
- Error response formats and status codes
- Integration with Server Components for data fetching

## Architecture Integration Requirements

Tasks must explicitly address:

1. **Next.js App Router Patterns**: Implement Server Components by default, use Client Components ("use client") only when necessary for interactivity
2. **Architectural Patterns**: Implement the specific patterns chosen in the system architecture (microservices, modular monolith, etc.)
3. **Technology Stack**: Use the exact technologies specified in the architecture
4. **Data Fetching Strategy**: Use Server Components for initial data loading, Client Components for interactive features
5. **Server Actions**: Implement Server Actions for form submissions and mutations instead of API routes where appropriate
6. **Security Framework**: Implement the security measures and authentication patterns specified
7. **Performance Standards**: Meet the performance targets and caching strategies defined, leveraging Server Components for performance
8. **Integration Points**: Properly integrate with existing microservices and databases as specified
9. **Monitoring & Observability**: Implement the logging, metrics, and tracing approaches defined

## Testing Strategy

Each task category must include comprehensive testing:

### Unit Testing
- Test individual functions and methods
- Mock external dependencies
- Test edge cases and error conditions
- Validate input/output contracts

### Integration Testing
- Test Server Component and Client Component interactions
- Test API route handler functionality and Server Action execution
- Test database operations and data persistence
- Test third-party service integrations
- Test Server Component data fetching and Client Component state management
- Test form submissions with Server Actions

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
- `app/[feature]/page.tsx` - Main page component implementing [architectural pattern] (Server Component by default)
- `app/[feature]/layout.tsx` - Layout component for feature section
- `app/[feature]/loading.tsx` - Loading UI component
- `app/[feature]/error.tsx` - Error UI component
- `components/[feature]/[Component].tsx` - Feature-specific component (Client Component with "use client" if needed)
- `components/[feature]/[Component].test.tsx` - Unit tests for component
- `hooks/use[Feature].ts` - Custom hook for client-side state management
- `hooks/use[Feature].test.ts` - Unit tests for custom hook

### Backend Files
- `app/api/[feature]/[endpoint]/route.ts` - API route handler following [API pattern]
- `app/api/[feature]/[endpoint]/route.test.ts` - API route handler tests
- `app/actions/[feature].ts` - Server Actions for mutations and server-side logic
- `app/actions/[feature].test.ts` - Server Actions tests
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
- `__tests__/integration/[feature].test.ts` - Integration tests for API routes and Server Actions
- `__tests__/e2e/[feature].spec.ts` - End-to-end tests for complete user workflows
- `__tests__/performance/[feature].test.ts` - Performance tests for Server Components and route handlers
- `__tests__/server-actions/[feature].test.ts` - Server Action specific tests

### Infrastructure & Configuration
- `app/globals.css` - Global styles and CSS variables
- `app/layout.tsx` - Root layout component with metadata and providers
- `app/not-found.tsx` - Global 404 page
- `lib/config/[feature].ts` - Feature configuration
- `lib/middleware/[feature].ts` - Custom middleware for App Router
- `lib/utils/[feature].ts` - Utility functions
- `lib/utils/[feature].test.ts` - Utility function tests
- `middleware.ts` - Next.js middleware (root level)

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
- [ ] 3.2 Create API route handlers (app/api/[route]/route.ts) adhering to App Router conventions
- [ ] 3.3 Implement Server Actions for form submissions and mutations
- [ ] 3.4 Implement authentication and authorization middleware
- [ ] 3.5 Set up request validation and error handling for route handlers
- [ ] 3.6 Implement rate limiting and security measures
- [ ] 3.7 Write unit tests for service layer methods
- [ ] 3.8 Write integration tests for API route handlers and Server Actions
- [ ] 3.9 Implement logging and monitoring as specified

### 4.0 Frontend Component Implementation
- [ ] 4.1 Create page components (app/[route]/page.tsx) as Server Components following Next.js App Router patterns
- [ ] 4.2 Create layout components (app/[route]/layout.tsx) for shared UI and metadata
- [ ] 4.3 Implement loading states (app/[route]/loading.tsx) and error boundaries (app/[route]/error.tsx)
- [ ] 4.4 Create feature-specific React components (Client Components with "use client" when needed)
- [ ] 4.5 Set up client-side state management following architectural decisions
- [ ] 4.6 Implement server-side data fetching in Server Components
- [ ] 4.7 Create custom hooks for client-side reusable logic
- [ ] 4.8 Implement form handling with Server Actions
- [ ] 4.9 Write unit tests for React components (both Server and Client Components)
- [ ] 4.10 Write integration tests for user interactions and Server Actions
- [ ] 4.11 Implement responsive design and accessibility features

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

- `npm test` - Run all unit tests (Server Components, Client Components, Server Actions)
- `npm run test:integration` - Run integration tests for API routes and Server Actions
- `npm run test:e2e` - Run end-to-end tests for complete user workflows
- `npm run test:server-actions` - Run Server Action specific tests
- `npm run test:performance` - Run performance tests for Server Components and route handlers
- `npm run test:security` - Run security tests for authentication and authorization
- `npm run test:coverage` - Generate test coverage report

## Architecture Compliance Checklist

- [ ] Follows Next.js App Router conventions with proper app/ directory structure
- [ ] Correctly implements Server Components vs Client Components ("use client" directive)
- [ ] Uses layout.tsx, loading.tsx, error.tsx, and not-found.tsx appropriately
- [ ] Implements Server Actions for form handling and mutations
- [ ] Uses API route handlers (app/api/[route]/route.ts) for external API consumption
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
- Tasks follow Next.js App Router conventions with proper Server/Client Component distinctions
- Server Actions are used for form handling and mutations, while API routes handle external integrations
- Each component must have comprehensive test coverage including unit, integration, and E2E tests
- Performance and security testing are integral parts of the implementation process
- Tasks are organized to follow the architecture layers: data, service, API/Server Actions, and presentation
- Integration points with existing systems are clearly identified and tested
- Monitoring and observability are built into each layer of the implementation
- Special attention is given to Server Component data fetching vs Client Component state management
```

## Interaction Model

1. **Phase 1**: Create a document with detailed component breakdown questions suggest detailed component specifications that will implement the components in line with our constraints and requirements;
2. **Phase 2**: Generate high-level tasks based on architecture and PRD, then ask for "Go" confirmation
3. **Phase 3**: Generate detailed sub-tasks with comprehensive testing requirements
4. **Phase 4**: Finalize and save the task list with proper file structure

## Target Audience

Assume the primary reader is a **junior developer** who needs explicit guidance on implementing the architectural patterns and comprehensive testing strategies defined in the system design.
