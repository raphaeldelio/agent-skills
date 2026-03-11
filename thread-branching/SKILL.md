---
name: thread-branching
description: Create a ready-to-paste prompt for starting one or more new conversations from the current thread context. Use when Codex needs to hand off the current repo state, goal, constraints, touched files, verification status, or open risks into a self-contained prompt for another thread, subagent, or parallel follow-up conversation.
---

# Thread Branching

Use this skill when the user wants to continue the current work in a new thread without losing context.

The output should be a prompt that can be pasted into a fresh conversation and still make sense on its own.

## Default Outcome

Produce a ready-to-paste prompt, not a plan about the prompt.

Unless the user asks otherwise:
- give one prompt per requested new thread
- make each prompt self-contained
- keep it concise but complete enough to act on immediately

## What to Include

Every handoff prompt should include:
- repo path
- user goal for the new thread
- current implementation state
- important constraints or repo rules
- relevant files or directories
- what has already been verified
- what is still open
- exact ask for the new thread

Prefer concrete facts over summaries like "we changed some styles".

## Workflow

### 1. Identify the branch target

Decide what the new thread is for:
- continue the same task
- tackle one subproblem
- review a change
- implement a follow-up
- investigate a bug

If the user wants multiple parallel threads, split them by file ownership or concern so they do not overlap.

### 2. Gather only the needed context

Pull in only the current facts the next thread needs:
- changed files
- current behavior
- verification already run
- blockers or open questions

Do not dump the whole conversation.

### 3. Write the prompt as an executable brief

The prompt should tell the next thread:
- where it is working
- what to do
- what not to redo
- what constraints to respect
- how to verify success

Use the templates in [references/templates.md](references/templates.md).

### 4. Keep it safe for fresh context

The new thread should not depend on hidden history.

Replace vague references like:
- "the thing we discussed"
- "the previous fix"
- "same as before"

with explicit statements:
- current UI issue
- file path
- expected outcome
- relevant command

## Prompt Rules

- Prefer direct instructions over narrative recap.
- Mention exact files when they matter.
- Mention exact commands when verification matters.
- If the next thread is review-only, say so explicitly.
- If the next thread should not edit certain files, say so explicitly.
- If multiple prompts are requested, label them clearly.

## Interaction Rules

- If the user asks for "a prompt", return just the prompt unless a short note adds real value.
- If the user asks for several prompts, return one block per prompt.
- If the next thread is intended for parallel work, include file boundaries.
- If context is stale or uncertain, say what needs rechecking in the new thread.

## Resources

- [references/templates.md](references/templates.md): starter prompt templates for continuation, implementation, review, debugging, and parallel split prompts.

