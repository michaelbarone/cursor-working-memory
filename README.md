# Cursor Working Memory

This repo contains resources to help add project documentation, planning materials, and working memory for development tasks in existing or new projects, leveraging the Cursor IDE (or other AI).

View the readme in the /docs/ directory for more info on use cases and prompt exapmles.

## Cursor setup

Copy the quoted section of `cursor_setting.md` into your cursor settings User Rules section and customize as needed.

NOTE: to prevent cursor IDE from changing or possibly disabling triggers of rules, update your user settings .json file with this to disable the built in mdc editor:
JSON Configuration:

```json
    "workbench.editorAssociations": {
        "*.mdc": "default"
    }
```

After disabling the editer, ensure the the following rule files are in your .cursor/rules directory:

- 010-docs-memory-knowledge-management.mdc
- 011-docs-plan-management.mdc

If copying the .cursor/rules folder from this repo into your project review these:

- the 002-rule-file-naming.mdc file to see the naming schemes, and remove any rule files that arent needed for your environment and tech stack.
- the 004-ai-auto-create-rule.mdc allows you to ask the agent to create new rules for your framework, languages and other best practices you want to add.

## Project Setup

update the `docs/project-context.md` with specifics for this project for things like directory structure, key frameworks and depenedencies, and best practices.

you can do this more as the project evolves to ensure this file is always up to date.

Shell Command:

```shell
Can you ensure the @/docs/project-context.md file matches the project structure, and highlights key frameworks, dependencies and best practices for this project

@package.json
@/docs/
```

## Project Feature Documentation

Leverage the `docs/features` structure to document features in an existing project, or after you have built features in a new project.  By documenting it can help to identify issues in logic, and also provides reference for future AI interactions which give it better context about project decisions, architechure and specifics for critical functionality.

ask the ai to help document the features:

```shell
Can you help document the features in our application in the @/docs/features structure.  Ask any clarifying questions as needed.
```

After creating the documentation, you may want to open a new chat (fresh context) and ask it to review the project documentation, scan the application to make any improvements or add any missing info to help ensure completeness.

```shell
Can you review our feature documentation in @/docs/features structure.  Then review our project code and see if any updates to the feature documentation is needed.  Ask any clarifying questions as needed.
```

## Repo Directory Structure

```plaintext
/.cursor
   └── rules/           # Cursor rules files
/docs/
   ├── working-memory/           # Active context
   │   ├── open/                 # Active tasks
   │   │   └── {task-id}/        # Task-specific directory
   │   │       └── .plan         # Task plan
   │   ├── done/                 # Completed tasks
   |   └── plan.md               # tracks all open and completed plans
   ├── templates/                # Project templates
   │   └── features/              # Feature documentation templates
   │       ├── README.md
   │       ├── api.md
   │       ├── architecture.md
   │       ├── components.md
   │       └── testing.md
   ├── features/                 # Project features
   └── project-context.md        # Project Context, project folder structure, key dependencies and 
/cursor_settings.md        # Cursor IDE settings
/README.md                 # This file
```
