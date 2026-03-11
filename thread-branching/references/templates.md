# Templates

Use these as output shapes. Fill in only the sections that matter.

## 1. Continuation Prompt

```text
You are continuing work in the repository at <REPO_PATH>.

Goal:
- <WHAT THIS NEW THREAD SHOULD ACCOMPLISH>

Current state:
- <IMPORTANT FACT 1>
- <IMPORTANT FACT 2>
- <IMPORTANT FACT 3>

Relevant files:
- <PATH>
- <PATH>

Constraints:
- <CONSTRAINT 1>
- <CONSTRAINT 2>

Already verified:
- <COMMAND OR CHECK>
- <COMMAND OR CHECK>

Open issue:
- <WHAT STILL NEEDS TO BE CHANGED OR VERIFIED>

Do this next:
- <CONCRETE NEXT ACTION>
- <CONCRETE NEXT ACTION>

In your final response, summarize:
- what changed
- what you verified
- any remaining risks
```

## 2. Implementation Prompt

```text
You are working in <REPO_PATH>.

Implement this change:
- <REQUEST>

Context:
- <CURRENT BEHAVIOR>
- <WHY IT IS WRONG OR INCOMPLETE>
- <EXPECTED BEHAVIOR>

Touch these files if needed:
- <PATH>
- <PATH>

Avoid touching:
- <PATH OR AREA>

Verification:
- <COMMAND>
- <MANUAL CHECK>
```

## 3. Debug Prompt

```text
You are debugging an issue in <REPO_PATH>.

Problem:
- <OBSERVED FAILURE>

Known facts:
- <FACT 1>
- <FACT 2>
- <FACT 3>

Likely hotspots:
- <PATH>
- <PATH>

What has already been tried:
- <ATTEMPT 1>
- <ATTEMPT 2>

Your task:
- identify the cause
- implement the fix if safe
- verify the fix

Verification:
- <COMMAND>
- <MANUAL CHECK>
```

## 4. Review Prompt

```text
Review the implementation in <REPO_PATH>.

Focus on:
- bugs
- regressions
- missing verification
- styling or behavioral mismatches relevant to this task

Scope:
- <PATH>
- <PATH>

Context:
- <WHAT THIS CHANGE WAS SUPPOSED TO DO>

Return findings first, ordered by severity, with file references.
If there are no findings, say so and mention residual risks.
```

## 5. Parallel Prompt

```text
You are assigned one isolated slice of work in <REPO_PATH>.

Goal:
- <SLICE GOAL>

Allowed files:
- <PATH>
- <PATH>

Do not touch:
- <PATH>
- <PATH>

Current context:
- <FACT 1>
- <FACT 2>

Verification:
- <COMMAND>
- <MANUAL CHECK>

Final response format:
Status: done | blocked
Files changed:
- <path>
Verification run:
- <command or check>
Blockers/follow-ups:
- <item or "none">
```

