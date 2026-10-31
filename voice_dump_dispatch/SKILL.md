# Voice-Dump Dispatch

Turn a rambling voice memo or one message holding several asks into a numbered task list, run the independent tasks in parallel, and report once in a compressed summary. Friction is input, not model quality.

## Recognize the trigger

- Use this skill when one message contains two or more distinct tasks, corrections, or questions, whether typed, dictated, or sent as a voice note.

- Handle a single-task message with the normal flow and skip this skill.

## Structure and classify

- Parse the dump into a numbered task list and keep the numbering stable for the whole job, so the user can correct, reorder, or cancel by number.

- Classify each task before acting:

  - (a) Independent and reversible, or preparation only. It may run right away.
  - (b) Depends on another task's output. Queue it behind that task.
  - (c) An outside action with side effects, such as a purchase, charge, signup, publication, send, deletion, or permission change. Do the groundwork only and wait for approval.

- Record the numbered list with `todo.write` and keep each item's status current as lanes finish.

## Start without a confirmation round trip

- Announce the numbered structure in one short message and start the (a) tasks in the same turn. In this installation the structure message is an announcement, not a gate, and the user corrects by number while work runs.

- Stop and ask by number only when a task is ambiguous in a way that changes what runs, or when a (c) task reaches its approval point.

## Dispatch in parallel

- Fan independent multi-step tasks out with `subagent.spawn`, one lane per task and at most 4 lanes at once.

- Run a quick single-step task directly instead of spawning a lane for it.

- Keep lanes isolated. A lane reports its own task only and never edits another task's work.

## Report once, compressed

- Send one report when the lanes finish, with one line per numbered task: its status (done, queued, or needs you), the result, and a file or link when one exists.

- List approval-gated (c) items separately at the end, with the groundwork already done and the exact decision the user needs to make.

- Give every numbered item a status. Never drop an item silently, and when unsure about an item, stop that item and ask by number.

## Boundaries

- Never invent approval for a (c) action, and never treat silence as approval.

- Stop at 2FA or CAPTCHA challenges and report them. Never bypass them.

- Treat the raw dump as input for this job only. Save durable decisions and outcomes to memory as usual, and leave the rambling itself out.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.
