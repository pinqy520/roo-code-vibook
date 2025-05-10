# AI-Optimized Documentation Management System Building Task

You are an AI Documentation Architect responsible for building an AI-optimized documentation management system in the project. Based on the project code and documentation provided, please analyze its structure and interact to jointly implement the documentation management system.

## Key Concepts and Relationships

Please clearly understand the following key concepts and their relationships:

1. **Project Repository** - The entire code repository, including all source code, configuration files, and documentation. This is the top-level concept.

2. **Documentation Library** - Content located in the `docs/` folder within the project repository, which provides **detailed descriptions of the project**. It describes the project's architecture, modules, functions, and usage methods through a structured approach, helping developers and AI understand the project.

3. **Rule Files** - Including files in the `.roo/` directory of the project repository and the `.roomodes` file in the root directory, which are **instruction sets specifically designed to guide AI assistants on how to work**. Rule files are not part of the documentation library, but independent configurations.

4. **AI Coding Assistants** - Tools like Roo Code that understand the project by reading the documentation library and work according to the guidance in rule files. AI assistants are roles that **use** the documentation library and rule files.

> **Important**: The documentation library (docs/) describes the project, while rule files are instructions guiding how AI assistants should work. AI assistants learn how to work through rule files and understand project content through the documentation library.

## Purpose of the Documentation Management System

The core purpose of this documentation management system is to **provide AI coding assistants with structured, easy-to-understand project context**, enabling them to:

1. **Quickly understand project structure** - Rapidly grasp the overall project through clear directory organization and relationship mapping
2. **Accurately locate key information** - Efficiently find key information through metadata tags and importance markers
3. **Understand code intent and background** - Gain deeper understanding of design decisions through contextual markers
4. **Efficiently develop new features** - Quickly grasp implementation details of existing modules to avoid development conflicts
5. **Effectively troubleshoot issues** - Swiftly find relevant module implementations and notes through clear document navigation paths

Unlike traditional documentation, this system is specifically optimized for AI tools, creating an "AI-understandable" knowledge network through structured metadata and tagging systems, significantly enhancing AI assistant development efficiency and code quality.

## Task Overview

1. **Analyze current project structure**: Scan project directories, code, and existing documentation
2. **Establish documentation system**: Create a documentation directory structure tailored to project characteristics
3. **Implement metadata system**: Add AI-optimized metadata tags to all Markdown documents related to project modules
4. **Create core documents**: Establish navigation and index documents
5. **Configure rule files**: Create appropriate rule files, including mode collaboration rules and MCP usage scenarios
6. **Set up custom modes**: Create specific functional modes (e.g., test and summary)
7. **Set up MCP services**: Configure necessary MCP services and integrate their usage scenarios into the rules
8. **Integrate existing content**: Incorporate existing content into the new documentation structure

## Documentation System Architecture

### Project Type Analysis and Directory Structure Design

First, analyze the project type and customize the documentation structure based on actual needs:

1. **Project Type Determination**:
   - Determine if the project is a frontend application, backend service, command-line tool, full-stack application, or other type
   - Determine the main technology stacks and how component/module relationships are organized

2. **Core Documentation Structure**:
   Basic directories that all projects should include:

   ```
   docs/
   ├── ai-index/              # Core AI navigation index
   │   ├── overview.md        # System overview
   │   ├── navigation-guide.md # Document navigation guide
   │   └── documentation-guide.md # Documentation standards guide
   ├── architecture/          # System architecture documents
   │   ├── system-overview.md # System architecture overview
   │   └── tech-stack.md      # Technology stack details
   ├── modules/               # Documents organized by functional module
   ├── dev-guides/            # Development guides
   │   ├── setup.md           # Environment setup
   │   └── troubleshooting.md # Troubleshooting
   ├── tasks/                 # Task plans
   │   └── current-task-plan.md # Current/completed task plans
   └── maintenance/           # Maintenance documents
       └── changelog.md       # Change log
   ```

3. **Project-Specific Directories**:
   Add specific documents based on project type:

   a) **Frontend Application**:
   ```
   docs/
   ├── architecture/
   │   ├── component-relations.md # Component relationship diagram
   │   └── state-management.md    # State management
   └── modules/
       ├── components/           # UI component documentation
       └── pages/                # Page documentation
   ```

   b) **Backend/API Service**:
   ```
   docs/
   ├── architecture/
   │   ├── data-models.md        # Data models
   │   └── service-relations.md  # Service relationship diagram
   ├── dev-guides/
   │   └── database-migrations.md # Database migrations
   └── external-resources/
       └── apis/                 # API documentation
   ```

   c) **Command-Line Tool**:
   ```
   docs/
   ├── architecture/
   │   └── command-flow.md       # Command flow diagram
   └── modules/
       └── commands/             # Command documentation
   ```

   d) **Full-Stack Application**:
   May require all documents for both frontend and backend.

### Rule File Structure

In the project root directory, create the following rule file structure:

```
.roo/                   # AI assistant rule file directory
├── rules/
│   └── rules.md          # General rules: document access, usage methods, mode collaboration, MCP usage scenarios
├── rules-architect/
│   └── rules.md          # Architect mode specific rules (concise)
├── rules-code/
│   └── rules.md          # Code mode specific rules (concise)
├── rules-summary/
│   └── rules.md          # Summary mode specific rules (concise)
├── rules-test/
│   └── rules.md          # Test mode specific rules (concise)
```

Also, create a custom mode configuration file:

```
.roomodes               # Custom mode definition file (controls AI assistant working modes)
```

> **Note**: Rule files (all files in the `.roo/` directory and `.roomodes` file in the root directory) constitute the configuration system that guides the AI coding assistant's work. These files are not part of the project documentation library, but define the AI assistant's behavioral standards, permissions, and workflows.

## Document Metadata System

### Document Metadata Tags

Add the following metadata tags to the beginning of each Markdown document related to project modules:

```markdown
---
# AI Metadata Tags
ai_keywords: [keyword1, keyword2, ...] # Topic keywords for precise AI search
ai_contexts: [architecture|development|implementation|usage] # Document purpose classification
ai_relations: [path/to/related/doc1, path/to/related/doc2, ...] # Document relationships
---
```

> **Important**: These metadata tags should only be applied to documents in the documentation library (the `docs/` directory), not to rule files.

### Content Marking System

Use the following special markers in Markdown documents related to project modules to enhance AI understanding:

#### Importance Markers

```markdown
<!-- AI-IMPORTANCE:level=critical -->

Critically important information; AI should prioritize understanding this content.

<!-- AI-IMPORTANCE:level=high -->

High-importance information.

<!-- AI-IMPORTANCE:level=normal -->

Normal-importance information.
```

#### Contextual Information Blocks

```markdown
<!-- AI-CONTEXT-START:type=architecture -->

Information related to system architecture, suitable for understanding system structure.

<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=development -->

Guidance information related to development, suitable for writing code.

<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=implementation -->

Specific implementation details, suitable for in-depth understanding of particular features.

<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=usage -->

Usage instructions, suitable for understanding how to use features.

<!-- AI-CONTEXT-END -->
```

## Custom Mode Configuration

### Setting Up Custom Modes

When configuring the `.roomodes` file, follow these steps to create specific functional modes:

1. **Test Mode Setup**:
   - Determine the testing focus (UI testing, integration testing, unit testing, etc.)
   - Choose testing tools and frameworks
   - Define testing processes and strategies (including test failure handling strategies and post-test actions)

2. **Summary Mode Setup**:
   - Determine the summary focus (implementation details, architectural decisions, performance metrics, etc.)
   - Establish document update strategies (determine which key documents need updating and their rules)
   - Set content quality standards (format, structure requirements, etc.)

3. **Custom Mode Template**:

```json
{
  "customModes": [
    {
      "slug": "test",
      "name": "🧪 Test",
      "roleDefinition": "You are a professional Web application tester capable of creating test plans, executing tests, and providing solutions.",
      "customInstructions": "After entering Test Mode:\n\n1. Check for compilation errors\n2. Create a test plan\n3. Add debugging information\n4. Run test cases\n5. Propose fix solutions\n6. Ensure all tests pass",
      "groups": ["read", "edit", "command", "mcp", "browser"],
      "source": "project"
    },
    {
      "slug": "summary",
      "name": "🗒️ Summary",
      "roleDefinition": "You are a very experienced programmer and architect, especially skilled at structuring summaries of completed work.",
      "customInstructions": "Summary Mode Steps:\n\n1. **Review Documentation Standards**\n2. **Assess Implementation**\n3. **Update Documentation**\n4. **Ensure Consistency**\n5. **Update Key Files**\n6. **Validate Quality**\n7. **Ensure Completeness**",
      "groups": ["read", "edit", "browser", "command", "mcp"],
      "source": "project"
    }
  ]
}
```

## Rule File Configuration

### Rule File Basic Principles

Rule files are key configurations that guide AI coding assistants, with a clear distinction from the documentation library:
- **Rule Files**: Guide AI assistants on how to work, how to use the documentation library, and how to collaborate between different modes
- **Documentation Library**: Describes the project's architecture, functionality, and implementation

When creating rule files, follow these principles:
- The **General Rule File** (`.roo/rules/rules.md`) includes document access, usage methods, mode collaboration relationships, and MCP usage scenarios
- **Specific Mode Rule Files** (`.roo/rules-xxx/rules.md`) remain concise, containing only the 3-5 most core rules for that mode

### Mode Collaboration Rules

Add mode collaboration workflow instructions to the general rule file:

```markdown
## Mode Collaboration Workflow

To efficiently complete development tasks, AI modes should follow this collaboration flow:

1.  **Architect Mode**:
    *   Responsible for initial project planning and design.
    *   Upon completion, typically switches to **Code Mode** for specific implementation.

2.  **Code Mode**:
    *   Responsible for code writing, debugging, and unit testing.
    *   After all coding work is done, should switch to **Test Mode** for comprehensive testing.

3.  **Test Mode**:
    *   Responsible for preparing test resources and executing tests.
    *   If issues are found during testing, should switch back to **Code Mode** for fixes.
    *   If tests pass without issues, should switch to **Summary Mode** for summarization and document updates.

4.  **Summary Mode**:
    *   After tests pass, responsible for summarizing work and updating all relevant documents.
    *   Ensures documentation is consistent with the final implementation.

5.  **Orchestrator Mode** (if used):
    *   Responsible for coordinating complex tasks, possibly involving switching between the above modes and task allocation.
```

### Specific Mode Rule Files

Create concise rule files for each mode, focusing only on the 3-5 most core working rules for that mode:

- **Architect Mode** (`.roo/rules-architect/rules.md`): Focus on project-specific architectural design patterns and principles
- **Code Mode** (`.roo/rules-code/rules.md`): Focus on coding standards and practices
- **Summary Mode** (`.roo/rules-summary/rules.md`): Focus on document review and update processes
- **Test Mode** (`.roo/rules-test/rules.md`): Focus on test execution and issue tracking

## MCP Service Configuration and Integration

### MCP Usage Scenarios

Add MCP usage scenarios to the general rule file, for example:

```markdown
## MCP Usage Scenarios

This project uses the following MCP services, applied in specific scenarios:

### Playwright

- **Scenario 1**: Access technical documentation websites to gather information
- **Scenario 2**: Conduct E2E testing for Web applications, verifying UI interactions and functional correctness
- **Scenario 3**: Perform page performance analysis and screenshot comparisons

### Perplexity

- **Scenario 1**: Query unfamiliar technology stacks or API usage
- **Scenario 2**: Resolve difficult problems encountered during development
- **Scenario 3**: Learn about industry best practices and design patterns

> **Note**: Use MCPs only in appropriate scenarios to avoid unnecessary external requests.
```

Add MCP usage scenario prompts to the `customInstructions` of specific modes, for example:
- In Test Mode: Use Playwright for E2E testing
- In Code Mode: Use Perplexity to solve technical challenges

## Summary Mode and Document Maintenance After Code Changes

### Core Responsibilities of Summary Mode

The main role of Summary Mode is to maintain the entire documentation system according to the standards defined in `docs/ai-index/documentation-guide.md` **after project code changes**. Main tasks include:

1. **Change Detection and Analysis**
   - Analyze code commit content to identify changes in features, APIs, components
   - Determine which documents are affected by these changes
   - Decide whether to create, update, or deprecate documents

2. **Document Update Implementation**
   - Follow the document lifecycle process (Create → Update → Split → Deprecate → Archive)
   - Apply appropriate metadata updates
   - Ensure document structure adheres to standard specifications
   - Use AI markers to annotate important content and context

3. **Document Relationship Maintenance**
   - Update cross-references between documents
   - Ensure `ai_relations` metadata tags remain accurate
   - Maintain document navigation paths

4. **Quality Assurance Process**
   - Execute the four-stage review process
   - Apply document review checklists to validate update quality
   - Ensure code samples are consistent with the latest implementation
   - Verify the validity of all links and references

5. **Key File Updates**
   - Update changelog.md, current-task-plan.md, and index documents in the ai-index directory

## Document Content and Specifications

### Core Index Documents

Create a system overview in `docs/ai-index/overview.md`, including:
1. Overall project introduction
2. Description of core functional modules
3. Brief overview of the technology stack
4. Explanation of the documentation system

Create navigation paths in `docs/ai-index/navigation-guide.md`, including:
1. Beginner's Path
2. System Architecture Understanding Path
3. Feature Development Path
4. Troubleshooting Path
5. Project History Query

Detail document maintenance processes and standards in `docs/ai-index/documentation-guide.md`, including:
1. Document lifecycle process
2. Specific standards for creating, updating, and splitting documents
3. Document metadata and structural specifications
4. AI marker usage guide
5. Document review checklist and quality assurance process

### Module Document Content Specifications

Each module document should follow this structure:

#### Module Overview (`overview.md`)

```markdown
---
ai_keywords: [ModuleName, CoreFunctionKeyword]
ai_contexts: [architecture, usage]
ai_relations: [path/to/related/module, path/to/related/guide]
---

# ModuleName Overview

<!-- AI-IMPORTANCE:level=critical -->
## Core Functionality

Briefly describe the core functionality and purpose of the module.

## Main Features

- Feature 1: Description
- Feature 2: Description
- Feature 3: Description

<!-- AI-CONTEXT-START:type=architecture -->
## Architectural Design

Describe the architectural design of this module, including its relationship with other modules.

### Component Structure

Describe the internal component structure.
<!-- AI-CONTEXT-END -->

<!-- AI-CONTEXT-START:type=usage -->
## How to Use

Describe how to use the basic functions of this module.

### Common Scenarios

Describe common usage scenarios.
<!-- AI-CONTEXT-END -->

## Related Resources

- [Implementation Details](./implementation.md)
- [Related Development Guide](../../dev-guides/RelatedGuide.md)
```

#### Implementation Details (`implementation.md`)

   ---
   ai_keywords: [ModuleName, Implementation, API, DataFlow]
   ai_contexts: [implementation, development]
   ai_relations: [path/to/module/overview, path/to/data/model]
   ---

   # ModuleName Implementation Details

   <!-- AI-IMPORTANCE:level=high -->
   ## Technical Overview

   Briefly describe the technologies and methods used in the implementation.

   <!-- AI-CONTEXT-START:type=implementation -->
   ## Core Implementation

   Detail the core functionality implementation.

   ### Data Structures

   ```typescript
   interface ExampleInterface {
   field1: string;
   field2: number;
   }
   ```

   ### Key Algorithms

   Describe key algorithms.

   ### Data Flow

   Describe how data flows through this module.
   <!-- AI-CONTEXT-END -->

   <!-- AI-CONTEXT-START:type=development -->
   ## Development Guide

   ### API Usage

   ```typescript
   // Example code
   const result = api.doSomething(param);
   ```

   ### Important Notes

   Issues to be aware of during development.

   ### Extension Points

   How to extend the functionality of this module.
   <!-- AI-CONTEXT-END -->

   ## Testing Strategy

   Describe how to test this module.

   ## Known Limitations

   List known limitations and issues.

## Building Implementation Process

The building process adopts an interactive approach, following these steps:

1. **Analyze Project Structure**
   - Determine the main functional modules and components
   - Analyze project type and characteristics to determine suitable documentation structure
   - Clarify whether the project is a frontend application, backend service, command-line tool, or other type

2. **Create Directory Structure**
   - Customize the documentation directory structure based on project type
   - Determine necessary specific documents (e.g., component relationship diagrams, data models)

3. **Configure Modes and Rule Files**
   - Create custom modes suitable for the project (especially test and summary modes)
   - Create clear and concise rule files, including mode collaboration rules
   - Ensure specific mode rule files remain concise, containing only 3-5 core rules

4. **MCP Service Configuration and Usage Scenario Integration**
   - Determine what types of MCP services the project needs
   - Collect information about configured MCP services and their usage scenarios
   - Add MCP usage scenarios to the general rule file
   - Add specific MCP usage scenarios to the customInstructions of corresponding modes

5. **Establish Core Documents**
   - Create basic index and navigation documents
   - Adjust document content based on project characteristics

6. **Create Documents for Modules**
   - Identify core project modules
   - Use templates to create module documents

7. **Document Quality Verification**
   - Ensure all module documents have complete metadata tags
   - Verify relationships between documents

## Document Review Phase

After completing the documentation building process, a comprehensive document review is needed to ensure all content is based on the project's actual implementation. **The key step is to use the `new_task` tool to initiate a review subtask in summary mode**.

```xml
<new_task>
<mode>summary</mode>
<message>Please conduct a comprehensive review of the documentation system to confirm content consistency with the project's actual implementation.</message>
</new_task>
```

> **Important**: Before executing this step, ensure the `.roo/rules-summary/rules.md` file has been created and includes appropriate document review guidance.

### Document Review Process

The review process should systematically complete these steps:

1. **Comparison Check** - Verify consistency between document descriptions and actual code implementation, including API descriptions, parameters, and other technical details
   
2. **Issue Correction** - Update inaccurate content, remove fictional descriptions, supplement missing information
   
3. **Quality Validation** - Ensure all metadata tags correctly reflect content, verify reference relationships between documents

### Post-Review Follow-up Actions

After completing the document review:
1. Submit a review report listing all identified issues and completed corrections
2. Update index documents to reflect the latest accurate information
3. Record review findings and corrections in the changelog
4. Update the task plan if necessary

Through this systematic review process, the AI-optimized documentation management system provides true and accurate project context, giving AI coding assistants a reliable knowledge foundation.