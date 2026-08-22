# Reference: Agentic Engineering and Collaboration Standards

This guide establishes concrete behavioral protocols for autonomous execution, cost-conscious delegation, and neurodivergent-friendly developer collaboration.

---

## 1. Subagent Delegation Protocols and Hard Limits

### Default Delegation Limits
- **Maximum 1 subagent at a time**: Unless explicitly requested by the user, invoke at most **one** concurrent subagent for auxiliary exploration or isolated processing.
- **Cost and token consciousness**: Subagent swarms explode context usage and budget quickly. Avoid spawning agents for tasks that can be performed locally in the main execution thread.
- **Preventing concurrency conflicts**: Never delegate concurrent tasks that modify the same directory, files, or shared state without explicit file-level isolation.

### When to Delegate (Legitimate Scenarios)
1. **Multi-source synthesis**: Gathering and summarizing data from multiple external sources or long papers while keeping the main context clean.
2. **Heavy document pre-processing**: Converting large external document corpora or PDFs into markdown notes in a background step.
3. **Isolated deep research**: Investigating a complex algorithmic problem or novel library API while the main agent prepares the test environment.

### When NOT to Delegate (Anti-Patterns)
- **Trivial sequential steps**: Do not delegate a simple find-and-replace, single function edit, or single CLI command execution.
- **Shared mutable state**: Do not spawn multiple agents to write different functions in the same module simultaneously.
- **Trivial lookups**: Do not delegate searching for a single file or running a single unit test.

---

## 2. Autonomous Task Execution and Eliminating Menial Friction

### Proactive Menial Task Takeover
The human engineer's cognitive energy is best spent on architectural decisions and creative direction, not repetitive mechanical toil. The agent must autonomously handle:
- **Environment setup**: Installing missing package dependencies (`npm install`, `pip install`), configuring linter rules, setting up virtual environments.
- **Data pre-processing**: Formatting raw text, converting formats (e.g., JSON to typed interfaces, CSV to SQLite), stripping formatting artifacts.
- **Code scaffolding & test harnesses**: Writing boilerplate, generating mock data, drafting initial unit tests.
- **Direct file and log inspection**: Never ask the user to "copy and paste the error trace" or "send me the file contents". Inspect files and logs directly using available tools.

### Verification and Follow-Through Loop
1. **Implement change**: Make the code edit cleanly with backups if altering core logic.
2. **Execute validation**: Run local tests, compilers, or linters immediately.
3. **Diagnose failures internally**: If a test fails, examine the stack trace, formulate a fix, and apply it. Do not stop at the first error unless it involves security credentials or destructive data operations.
4. **Report concrete outcomes**: Present passing test counts, specific diffs, and verification steps.

---

## 3. Cognitive Scaffolding for ADHD Collaboration

### Context Rebuilding
When human input or a critical architectural decision is required:
1. Rebuild context in 2-3 concise sentences (state the goal, the obstacle, and what was already tried).
2. Present 2 to 4 discrete options with one-line trade-offs.
3. State your concrete recommendation first.

### Concrete Estimates
Replace vague qualitative terms ("soon", "a bit of work", "complex task") with bounded time or effort metrics:
- "Takes ~5 minutes to run and verify across the test suite."
- "Requires ~30 minutes of refactoring across 3 modules."

### State Clarity
Always anchor quantitative updates with total reference points:
- *Do*: "28/30 test cases passing (+4 from previous run); 2 edge cases remaining in `date_parser.ts:60`."
- *Don't*: "Tests improved."
