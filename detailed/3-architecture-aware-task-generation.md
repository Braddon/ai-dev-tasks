# Rule: Generating a Detailed Task List from PRD and System Architecture

## Goal

To guide an AI assistant in creating a comprehensive, step-by-step task list in Markdown format based on an existing Product Requirements Document (PRD) and System Architecture document. The task list should provide detailed implementation guidance for adding new features to an existing Next.js App Router application with Tailwind CSS styling and ESLint code quality standards.

## Input Requirements

- **PRD**: Product Requirements Document (filename format: `prd-*.md`)
- **System Architecture**: System architecture document (filename format: `architecture-*.md`)
- **Optional Context**: Existing system context document (filename format: `context-*.md`)

## Process

### Phase 1: Analysis and Component Breakdown
1. **Document Analysis**: Read and analyze the PRD and system architecture documents
2. **Component Identification**: Extract all components, services, and modules defined in the architecture
3. **Detailed Component Breakdown**: For each component identified, suggest the following:
   - **Component Name**: Exact name and location within App Router structure
   - **Component Type**: (React Server/Client component, API route handler, server action, utility function, etc.)
   - **Primary Function**: What this component does
   - **Input Parameters**: Expected inputs, props, or parameters
   - **Output/Return**: What it returns or produces
   - **Dependencies**: Other components or services it depends on
   - **State Management**: If applicable, what state it manages (client vs server state)
   - **Side Effects**: Any external API calls, database operations, or other side effects
   - **Styling Approach**: Tailwind CSS classes, responsive design considerations

4. **Architecture Integration**: Create a diagram showing how new components integrate with existing system architecture
5. **Data Flow**: Create a diagram of how data flows between server components, client components, API routes, and existing systems

### Phase 2: Architecture-Driven Task Generation
4. **Generate Parent Tasks**: Create high-level tasks for feature implementation:
   - Database and Data Layer tasks (schemas, migrations, models)
   - API Routes and Server Actions implementation
   - App Router Pages and Layouts implementation
   - React Components implementation
   - Integration with existing systems
   - Testing and Quality Assurance
5. **Present Parent Tasks**: Show the high-level tasks and ask for confirmation with "Go"

### Phase 3: Detailed Implementation Planning
6. **Generate Sub-Tasks**: Break down each parent task into specific, actionable sub-tasks that:
   - Follow existing Next.js App Router patterns
   - Implement the functional requirements from the PRD
   - Include comprehensive testing for each component
   - Integrate with existing architecture patterns
   - Follow established Tailwind CSS design system
   - Maintain existing ESLint code quality standards

### Phase 4: Testing Strategy Integration
7. **Test Planning**: For each component and function, identify:
   - **Unit Tests**: Test individual functions and components in isolation
   - **Integration Tests**: Test component interactions and API integrations
   - **End-to-End Tests**: Test complete user workflows from the PRD
   - **Performance Tests**: Validate performance requirements
   - **Security Tests**: Validate security measures and authentication flows
   - **Error Handling Tests**: Test edge cases and error scenarios

## Component Breakdown Questions

Before generating tasks, ask the user to provide detailed information for each major component:

### For App Router Pages and Layouts:
- Page/Layout name and route structure
- Server vs Client component designation
- Props interface definition (including searchParams, params)
- Data fetching approach (server-side, client-side, streaming)
- Metadata and SEO requirements
- Tailwind CSS styling approach and responsive design
- Loading and error state handling

### For React Components:
- Component name and file location
- Server vs Client component designation
- Props interface definition
- State management approach (useState, useContext, external store, server state)
- Event handlers and user interactions
- API calls or data fetching requirements
- Tailwind CSS styling approach and design system integration
- Accessibility requirements

### For API Route Handlers:
- Route paths and HTTP methods
- Request/response schemas and validation
- Authentication and authorization requirements
- Rate limiting and security measures
- Error response formats
- Database operations and caching strategies

### For Server Actions:
- Action name and location
- Input validation and sanitization
- Database operations and side effects
- Error handling and user feedback
- Revalidation strategies

### For Database Components:
- Table/collection names and schemas
- Relationships and foreign keys
- Indexing strategies
- Migration requirements
- Seed data specifications

## Architecture Integration Requirements

Tasks must explicitly address:

1. **Next.js App Router Patterns**: Implement server components, client components, layouts, and route handlers
2. **Existing Technology Stack**: Use the technologies already specified in the architecture
3. **Security Framework**: Implement security measures consistent with existing patterns
4. **Performance Standards**: Meet existing performance targets and caching strategies
5. **Integration Points**: Properly integrate with existing microservices and databases
6. **Monitoring & Observability**: Use existing logging, metrics, and tracing approaches
7. **Code Quality**: Maintain existing ESLint standards and formatting
8. **Design System**: Follow existing Tailwind CSS patterns and responsive design principles

## Output Format

```markdown
# Task List: [Feature Name]

## Architecture Overview
Brief summary of how this implementation integrates with existing application and architecture.

## Component Breakdown Summary
| Component | Type | Function | Dependencies | Testing Requirements |
|-----------|------|----------|--------------|---------------------|
| ComponentName | Server/Client Component | Brief description | List of deps | Unit, Integration, E2E |

## Relevant Files

### App Router Structure
- `app/[feature]/page.tsx` - Main page component (Server Component)
- `app/[feature]/layout.tsx` - Feature-specific layout
- `app/[feature]/loading.tsx` - Loading UI for suspense boundaries
- `app/[feature]/error.tsx` - Error boundary for error handling

### Components
- `components/[feature]/[Component].tsx` - Feature-specific component
- `components/[feature]/[Component].test.tsx` - Unit tests for component
- `components/ui/[UIComponent].tsx` - Reusable UI components with Tailwind

### API Routes
- `app/api/[feature]/route.ts` - API route handler
- `app/api/[feature]/route.test.ts` - API route tests

### Server Actions
- `app/actions/[feature].ts` - Server actions for data mutations
- `app/actions/[feature].test.ts` - Server action tests

### Services and Data Layer
- `lib/services/[feature]Service.ts` - Service layer implementation
- `lib/services/[feature]Service.test.ts` - Service layer tests
- `lib/models/[Feature].ts` - Data models and schemas
- `lib/models/[Feature].test.ts` - Model validation tests

### Database Files
- `prisma/migrations/[timestamp]_add_[feature].sql` - Database migration
- `lib/dal/[feature]Repository.ts` - Data access layer
- `lib/dal/[feature]Repository.test.ts` - Repository tests

### Testing Files
- `tests/integration/[feature].test.ts` - Integration tests
- `tests/e2e/[feature].spec.ts` - End-to-end tests
- `__tests__/[feature].test.tsx` - Jest unit tests

## Implementation Tasks

### 1.0 Database and Data Layer Implementation
- [ ] 1.1 Create database schema and migrations following existing data architecture
- [ ] 1.2 Implement data models with Zod validation according to existing patterns
- [ ] 1.3 Create repository pattern implementation for data access
- [ ] 1.4 Write comprehensive unit tests for data layer
- [ ] 1.5 Write integration tests for database operations
- [ ] 1.6 Set up seed data for testing and development

### 2.0 API Routes and Server Actions Implementation
- [ ] 2.1 Create API route handlers following existing App Router patterns
- [ ] 2.2 Implement server actions for data mutations
- [ ] 2.3 Set up request validation with Zod schemas
- [ ] 2.4 Implement authentication and authorization using existing middleware
- [ ] 2.5 Implement error handling following existing patterns
- [ ] 2.6 Write unit tests for API routes and server actions
- [ ] 2.7 Write integration tests for API endpoints
- [ ] 2.8 Add logging and monitoring using existing patterns

### 3.0 App Router Pages and Layouts Implementation
- [ ] 3.1 Create page components as Server Components
- [ ] 3.2 Implement layouts with proper nesting and shared UI
- [ ] 3.3 Set up loading states and Suspense boundaries
- [ ] 3.4 Create error boundaries and error pages
- [ ] 3.5 Implement metadata and SEO optimization
- [ ] 3.6 Write unit tests for page components
- [ ] 3.7 Write integration tests for route functionality
- [ ] 3.8 Test server-side rendering and hydration

### 4.0 React Components Implementation
- [ ] 4.1 Create server components for data fetching
- [ ] 4.2 Implement client components for interactivity
- [ ] 4.3 Implement form handling with server actions
- [ ] 4.4 Create reusable UI components with existing Tailwind CSS patterns
- [ ] 4.5 Implement responsive design following existing breakpoints
- [ ] 4.6 Add accessibility features and ARIA labels
- [ ] 4.7 Write unit tests for React components
- [ ] 4.8 Write integration tests for user interactions
- [ ] 4.9 Test component rendering and prop handling

### 5.0 Integration with Existing Systems
- [ ] 5.1 Integrate with existing authentication system
- [ ] 5.2 Connect with existing database and caching layers
- [ ] 5.3 Integrate with existing API patterns and middleware
- [ ] 5.4 Connect with existing monitoring and logging systems
- [ ] 5.5 Test integration with existing microservices
- [ ] 5.6 Validate security measures with existing patterns
- [ ] 5.7 Test error handling and recovery scenarios

### 6.0 Testing and Quality Assurance
- [ ] 6.1 Write unit tests for all components and utilities
- [ ] 6.2 Set up integration testing following existing patterns
- [ ] 6.3 Write E2E tests for complete user workflows from PRD
- [ ] 6.4 Implement performance testing for critical paths
- [ ] 6.5 Test accessibility features and WCAG compliance
- [ ] 6.6 Test error boundaries and error handling
- [ ] 6.7 Validate test coverage meets existing thresholds
- [ ] 6.8 Test responsive design across devices

## Development Commands

### Testing
- `npm test` - Run all unit tests
- `npm run test:watch` - Run tests in watch mode
- `npm run test:integration` - Run integration tests
- `npm run test:e2e` - Run end-to-end tests
- `npm run test:coverage` - Generate test coverage report

### Development
- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run lint` - Run ESLint checks
- `npm run format` - Format code with Prettier

## Architecture Compliance Checklist

- [ ] Follows existing Next.js App Router patterns and conventions
- [ ] Implements proper server/client component separation
- [ ] Uses existing Tailwind CSS design system consistently
- [ ] Maintains existing ESLint code quality standards
- [ ] Integrates with existing security framework
- [ ] Meets existing performance standards
- [ ] Integrates properly with existing microservices and databases
- [ ] Uses existing monitoring and observability patterns
- [ ] Follows existing data architecture and caching strategies
- [ ] Implements error handling consistent with existing patterns
- [ ] Follows existing API design patterns and conventions
- [ ] Maintains existing accessibility standards (WCAG 2.1)
- [ ] Follows existing responsive design principles
- [ ] Implements proper SEO and metadata handling

## Notes

- All tasks focus on implementing new features within existing Next.js App Router architecture
- Each component must have comprehensive test coverage following existing testing patterns
- Tasks are organized to integrate with existing architecture layers
- Integration points with existing systems are clearly identified and tested
- Code quality is maintained through existing ESLint and Prettier standards
- Tailwind CSS usage follows existing design system patterns
- Accessibility is implemented according to existing standards

## Target Audience

Assume the primary reader is a **junior developer** who needs explicit guidance on implementing new features within an existing Next.js App Router system with established patterns for Tailwind CSS styling, ESLint standards, and comprehensive testing strategies.
```

## Interaction Model

1. **Phase 1**: Analyze PRD and architecture documents, create component breakdown
2. **Phase 2**: Generate high-level tasks based on existing architecture patterns, ask for "Go" confirmation
3. **Phase 3**: Generate detailed implementation tasks that integrate with existing system
4. **Phase 4**: Finalize and save the task list with proper file structure

## Target Audience

Assume the primary reader is a **junior developer** who needs explicit guidance on implementing new features within an existing Next.js App Router system with established patterns for Tailwind CSS styling, ESLint standards, and comprehensive testing strategies.
