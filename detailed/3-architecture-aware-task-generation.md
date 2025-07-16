# Rule: Generating a Detailed Task List from PRD and System Architecture

## Goal

To guide an AI assistant in creating a comprehensive, step-by-step task list in Markdown format based called `tasks-*.md` on an existing Product Requirements Document (PRD) and System Architecture document. The task list should provide detailed implementation guidance for adding new features to an existing Next.js App Router application with Tailwind CSS styling and ESLint code quality standards.

## Input Requirements

- **PRD**: Product Requirements Document (filename format: `prd-*.md`)
- **System Architecture**: System architecture document (filename format: `architecture-*.md`)
- **Detailed Technical Requirements**:  Detailed requirements reflecting implementation of System Architecture (filename format: `techreq-*.md`)
- **Optional Context**: Existing system context document (filename format: `context-*.md`)

## Output Criteria

Tasks must be expressed concisely and thoroughly. As a set of tasks, they should address: 

1. **Next.js App Router Patterns**: Implement server components, client components, layouts, and route handlers
2. **Existing Technology Stack**: Use the technologies already specified in the architecture
3. **Security Framework**: Implement security measures consistent with existing patterns
4. **Performance Standards**: Meet existing performance targets and caching strategies
5. **Integration Points**: Properly integrate with existing microservices and databases
6. **Monitoring & Observability**: Use existing logging, metrics, and tracing approaches
7. **Code Quality**: Maintain existing ESLint standards and formatting
8. **Design System**: Follow existing Tailwind CSS patterns and responsive design principles


## Process

### Phase 1: Analysis and Breakdown of detailed technical requirements

1. **Document Analysis**: Read and analyze the PRD,  system architecture and detailed technical requirement documents
2. **Task Identification and Grouping** Use the detailed requirements to create a high level grouping of tasks.  Grouping should reflect interdependence of code (e.g. an api route would be implemented alongside the components in which that route is called).  
Use your judgement to find the best grouping of related or interacting elements. Enumerate these Groupings in the tasks document, and list the complete set of requirements that are to be implemented in within each high level task group.  Prompt me to see if they meet our high bar for quality, and if they do I will say 'go'.   If your groupings do not reflect our high bar for quality (they do not make sense or requirements have been missed) then I will asked you to revise. 
3.  **Subtask Creation** :  Break each of the tasks down into subtasks that are simple, with a low level of complexity and interdependency.  From the architecture and detailed technical requirements, extract all the detail  required to implement these subtasks.  When complete, the tasks should be structured as follows:

1.  TASK NAME
Requirements that are implemented by completetion of the task.
[Detail necessary to complete the task and is shared across subtasks]
1.1 SUBTASK NAME
[Detail necessary to complete the subtask, not shared across other subtasks]
Requirements that are implemented by the subtask.
Information from the architecture and technical requirements relating to the task and subtask should be captured here. 


For components, this will include: 
   - **Component Name**: Exact name and location within App Router structure
   - **Component Type**: (React Server/Client component, API route handler, server action, utility function, etc.)
   - **Primary Function**: What this component does
   - **Input Parameters**: Expected inputs, props, or parameters
   - **Output/Return**: What it returns or produces
   - **Dependencies**: Other components or services it depends on
   - **State Management**: If applicable, what state it manages (client vs server state)
   - **Side Effects**: Any external API calls, database operations, or other side effects
   - **Styling Approach**: Tailwind CSS classes, responsive design considerations

### For App Router Pages and Layouts this will include:
- Page/Layout name and route structure
- Server vs Client component designation
- Props interface definition (including searchParams, params)
- Data fetching approach (server-side, client-side, streaming)
- Metadata and SEO requirements
- Tailwind CSS styling approach and responsive design
- Loading and error state handling


### For API Route Handlers this will include
- Route paths and HTTP methods
- Request/response schemas and validation
- Authentication and authorization requirements
- Rate limiting and security measures
- Error response formats
- Database operations and caching strategies

### For Server Actions this will include:
- Action name and location
- Input validation and sanitization
- Database operations and side effects
- Error handling and user feedback
- Revalidation strategies

### For Database changes this will include:
- Table/collection names and schemas
- Relationships and foreign keys
- Indexing strategies
- Migration requirements
- Seed data specifications


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




## Target Audience

Assume the primary reader is a **junior developer** who needs explicit guidance on implementing new features within an existing Next.js App Router system with established patterns for Tailwind CSS styling, ESLint standards, and comprehensive testing strategies.

## Output files
Tasks should be included in in their own markdown file.
They should be named:  tasks-[project name]-[task number].md 
E.g. 'tasks-myproject-1.md'

After producing these files, also create an implementation traceability matrix, that maps requirements, tasks, subtasks and implementation status.  
File:  tracmat-[project name].md

Then verify that the full technical requirements are covered in the traceability matrix, and in each of the tasks. 
