# Project File Structure

```

Project Folder
├── CLAUDE.md
├── .claude/rules/                ← claude code project rules
│   ├── xxxx1
│   └── xxxx2
├── tasks/
│   ├── story-1-r1-template.md    ← request template
│   ├── story-{id}-r{rev}.md      ← request with `unique ID` and `revision` from user
│   ├── xxxx-plan-{id}-r{rev}.md  ← work plan correspond to `unique ID + revision` request
│   ├── xxxx-note.md              ← lessons capture by agent
│   └── ...
├── assets/                       ← static project files
│   ├── file-structure.md         ← project file structure
│   ├── sop.md                    ← project sop
│   └── ...
├── index.html                    ← landing page
├── src/
│   ├── xxxx1                     ← codebase files
│   └── xxxx2
├── xxxxx
└── xxxxx                         ← other project file

```
