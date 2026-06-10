# Standard Operating Procedure

There are 4 stages for every work unless user request to override it. They are `Planning`, `Implementation`, `Verification` and `Review`.

## Workflow Overview

1. Start -> Read and analyze "story-{id}-{rev}.md" or "prompt" given by user/upstream -> 
2. `Planning` -> Write plan "{agent-name}-plan-{id}-{rev}.md" for user/upstream review -> Status = "Approved" plan and "None" marked in "Question/Issue" ->
3. `Implementation` -> Your work output and mark items complete as you go in the plan -> All completed ->
4. `Verification` -> Test/Verify/Check the work output against with plan -> Confirmed correctness ->
5. `Review` -> Write summary review in plan, mark status = "Completed" in plan, capture lessons if any in "{agent-name}-note.md" and notify user/upstream -> End

Note:
- `{agent-name}`: main / subagent / session name
- `{id}`: unique number represent particular request given by user/upstream, otherwise increment by 1 from last max {id}.
- `{rev}`: revision number that represent n-th version of the file.

Plan Status In Metadata:
- `Pending`: drafted plan that waiting for user/upstream
- `Blocked`: outstanding questions/issues exists in "Question/Issue" section
- `Approved`: approved by user/upstream and ready to next stage
- `Completed`: tasks are completed with summary review

## Stage Details

### 1. Planning

**Don't assume. Don't hide confusion. Surface tradeoffs.**

- Before do anything, analyze the request content and think
- Write a detail plan "{agent-name}-plan-{id}-{rev}.md" with checkable items
- State your assumptions explicitly. If uncertain, state it in "Question/Issue" section.
- If multiple interpretations exist, don't pick silently and present them in "Question/Issue" section.
- If a simpler approach exists, say so. Push back when warranted and state it in "Question/Issue" section.
- If something is unclear, stop. Name what's confusing, state it in "Question/Issue" section.
- Notify user/upstream to review and waiting for plan approval.

Note:
- `{id}` and `{rev}` must be matched with story.md no matter in metadata or filename, otherwise, `{id}` start from {last max id + 1} and `{rev}` start from {last max rev `with same id` + 1}
- user/upstream may override to skip `Planning` stage for non-trivial task. e.g. fix typo, install a package, rename a file, ..etc.

