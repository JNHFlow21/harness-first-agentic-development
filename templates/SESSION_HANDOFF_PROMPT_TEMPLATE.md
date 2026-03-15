# Session Handoff Prompt Template

```text
We are continuing work on [PROJECT NAME].

Important constraint:
All files, docs, implementation code, PRDs, designs, and scripts must stay in:
[PROJECT_ROOT]

Repository:
[REPO_URL]

Product positioning:
[ONE_SENTENCE_PRODUCT_DEFINITION]

Before continuing, read and understand the existing documents:

1. [PATH_1]
2. [PATH_2]
3. [PATH_3]

Current consensus:
- Main path:
- MVP scope:
- Non-goals:
- Key constraints:

Development method:
- This project uses Harness-First Agentic Development
- Human owns goals, priorities, and experience acceptance
- Agent owns convergence, implementation, testing, deployment, and repair
- Ralph-style loop is only for narrow bugfix / refactor tasks

Additional constraints:
- [Constraint 1]
- [Constraint 2]

Please continue by doing this:
[NEXT EXECUTION TASK]

Requirements:
- Do not repeat generic background
- Continue directly from the existing docs
- Keep output execution-oriented
- If new documents are needed, create them inside [PROJECT_ROOT]
```
