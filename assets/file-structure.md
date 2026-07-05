# Project File Structure

```
# Main files

Project Folder
├── CLAUDE.md
├── .claude/rules/                 ← claude code project rules
│   ├── xxxx1
│   └── xxxx2
├── tasks/
│   ├── story-1-r1-template.md        ← request template
│   ├── story-{id}-r{rev}.md          ← request with `unique ID` and `revision` from user
│   ├── xxxx-plan-{id}-r{rev}.md      ← work plan correspond to `unique ID + revision` request
│   ├── xxxx-report-{id}-r{rev}.html  ← work report correspond to `unique ID + revision` request
│   ├── ...
│   └── archived/                     ← archive folder for tasks related files
├── assets/                           ← static project files
│   ├── file-structure.md             ← project file structure
│   ├── sop.md                        ← project sop
│   └── ...
├── index.html                        ← landing page
├── src/
│   ├── xxxx1                         ← codebase files
│   └── xxxx2
├── tests/
│   ├── xxxx1                         ← test files
│   └── xxxx2
├── xxxxx
└── xxxxx                             ← other project file


# Project knowledge base files

Project Folder
└── project-kb/                             ← project knowledge base (kb) folder
    ├── src/
    │   ├── main-kb-1-r1-template.md        ← lesson captured template
    │   ├── {agent-name}-kb-{id}-r{rev}.md  ← lesson captured by agent (source of truth)
    │   ├── ...
    │   └── archived/                       ← archived lesson source folder
    ├── kb/
    │   └── ...                             ← compiled kb files
    └── kb-index.md                         ← kb entry page (kb index)

```
