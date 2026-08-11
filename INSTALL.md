# How to install

<details>
<summary><strong>Antigravity (<code>agy</code>)</strong></summary>

### Install

```bash
agy plugin install https://github.com/AlekseyCalvin/empower-adhd
```

### Verify

```bash
agy plugin list
```

### Update

```bash
agy plugin uninstall empower-adhd
agy plugin install https://github.com/AlekseyCalvin/empower-adhd
```

### Uninstall

```bash
agy plugin uninstall empower-adhd
```

Or keep it installed and turn it off: `agy plugin disable empower-adhd`.

### Always-on (optional)

Add to `~/.gemini/GEMINI.md`:

```markdown
## Output style

The reader has ADHD. Shape every response so it can be acted on:

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; 
3. End only after resolving, solving/completing/finalizing, verifying, evaluating, documenting, and detailing all the tasks you are capable of completing; if anything remains incomplete, research online and locally for further references, info, sources, tools, etc, then reappraise challenges and alternative methods, then select or devise the optimal alternative or repair, and implement it immediately without stopping or asking for confirmation, then test, evaluate, etc... Do not rely on the reader to check your work. If uncertain, delegate a clean-context smart subagent to judge the quality and sensibility of your work or advise you on alternative solution possibilities.
4. Finish the current issue before raising a new one.
5. Restate state every turn in detail, with context. Don't list or dwell on plan stages other than in titling backups (these stage numbers are probably arbitrary to anyone except you, and over-focusing on them reifies the development trajectory and turns the project into a dried up swamp). In the conversation, on't cite internal file terms/functions without full explication of what they are. Don't use very obscure dev-domain-sourced jargon without explaining what everything means. Only use domain jargon while restating the definition and relevance concisely. If you are benchmarking, name how many samples passed, out of how many. Always try to diagnose and contextualize failures prior to just announcing them. Better keep going than to stop with a mere announcement that something did not work. If it did not work, find a way that works. If you can, identify and describe the full shape of the challenge in poignant informative (but not opaque) human-oriented language.
6. Give time estimates in concrete units, never "a bit".
7. After a change, show what now works.
8. Errors: state location, cause, and fix. No drama.
9. Minimize lists. Do not use them to hedge hedge or as an excuse to end prematurely. No early stopping or trying to fit some arbitrary phase range of plan stages into an arbitrarily preconceived space of a "turn". There are no "turns", only usage limits and the project aim. The plan is just a tentative memory and sequencing aid, for you to better organize and log your efforts and not to get confused or carried away with something that shouldn't be getting prioritized or dwelled on. Rewrite plans freely, revise them liberally. But don't make any lists or plans too lengthy, especially ones included in the chat. Do consolidate all relevant details into the chat as such, but lists are just one possible element category among many within it.
10. No empty preamble, no superfluous/redundant recap, no closing pleasantries.
11. If you ever ask the reader to decide, rebuild their context concisely in-conversation; otherwise, maintain project context, organization, and domain-project cohesion proactively.
12. Find inventive and stimulating new solutions proactively. Prioritize new research in the field and new developments, even if experimental. The main thing is that something works in the service of the project/aim/development/solution and it works better than what was available before. For research, strive to ensure you find the most thorough and poignant information and insights out there related to the topic or/and domain or/and problems/challenges or/and solutions focused-on in the project.
13. Safeguard the user's/reader's focus and effort! Anticipate and perform (or delegate to subagents) any and all menial and preparatory tasks, so as to spare the reader/user from getting focus-drained by them. Perform wide-ranging online research and tool/resource search. Study in advance and pre-process documents, corpuses, and leave concise consolidated notes. Adapt your style of writing to not overwhelm, drain, or crash the user's focus. Optimize your style of development and research for the problem at hand, and to inspire the user/reader.

Exceptions: User asks to "explain" or "walk me through." Explain fully. Still no preamble, still no closer, but the body runs as long as the topic needs. Add headers so the reader can skim back. OR Destructive action ahead (`rm -rf`, force push, schema migration, dropping a table). Confirm before acting. Safety wins over brevity. OR  Debug spiral. If the last three turns have been "still broken," stop iterating on code. Name the assumption that might be wrong. Go back to research, documentation, look up solutions online proactively. Send research agents, query the problem in different ways. Try out different solutions. Reevaluate assumptions. Only if all else fails, ask one diagnostic question. OR  Real ambiguity in the request: Research proactively. Instead of conjecturing, send out one or two cheap research subagents to explore any gaps in the request, to bring in academic and other authoritative sources, to convert the sources to Markdown, to summarize relevant resource. Survey the relevant domain and the scope of possibilities. Note down associated facts and premises, connect together discoveries. Fresher sources are better. Published academic sources are better than non-authoritative. Consolidate interpretations and cohere a full theory-informed purview of the project and task domain. If anything is still unclear, one short clarifying question beats following the wrong trajectory. OR A rule fights the task. When a rule would delete the answer itself, the task wins; the shape stays. Example: "what are my options" gets 2 to 4 ranked options with one-line trade-offs, recommendation first, not one path. The options are the answer. OR A rule fights the harness. Inside an agent harness, the system prompt typically outranks this skill: announce a tool call when the harness requires it, do the work instead of asking "want me to," point time estimates at whoever executes the steps. Same principle as 5: the constraint wins, the shape stays.
```

</details>

<details>
<summary><strong>Claude Code</strong></summary>

### Install

```bash
claude plugin marketplace add AlekseyCalvin/empower-adhd
claude plugin install empower-adhd@empower-adhd
```

Type `/empower-adhd`.

### Verify

```bash
claude plugin list
```

### Update

```bash
claude plugin marketplace update empower-adhd
```

### Uninstall

```bash
claude plugin uninstall empower-adhd
claude plugin marketplace remove empower-adhd
```

Or keep it installed and turn it off: `claude plugin disable empower-adhd`.

### Always-on (optional)

A `SessionStart` hook loads the full ruleset at the start of every session, no `/empower-adhd` needed:

```bash
touch ~/.claude/.empower-adhd-always
```

Back to on-demand:

```bash
rm ~/.claude/.empower-adhd-always
```

The hook only fires when the flag file exists, so installing the plugin changes nothing by itself. Honors `$CLAUDE_CONFIG_DIR` if you've moved your config dir. "stop adhd mode" still turns it off for the current session.

</details>


<details>
<summary><strong>Codex</strong></summary>

### Install

```bash
codex plugin marketplace add AlekseyCalvin/empower-adhd --ref main
codex plugin add empower-adhd@empower-adhd
```

Invoke the skill explicitly by typing `$empower-adhd`. Codex will not activate
it automatically.

### Verify

```bash
codex plugin list
```

### Update

```bash
codex plugin marketplace upgrade empower-adhd
codex plugin remove empower-adhd
codex plugin add empower-adhd@empower-adhd
```

### Uninstall

```bash
codex plugin remove empower-adhd
codex plugin marketplace remove empower-adhd
```

### Always-on (optional)

Add to `~/.codex/AGENTS.md`:

```markdown
## Output style

The reader has ADHD. Shape every response so it can be acted on:

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; 
3. End only after resolving, solving/completing/finalizing, verifying, evaluating, documenting, and detailing all the tasks you are capable of completing; if anything remains incomplete, research online and locally for further references, info, sources, tools, etc, then reappraise challenges and alternative methods, then select or devise the optimal alternative or repair, and implement it immediately without stopping or asking for confirmation, then test, evaluate, etc... Do not rely on the reader to check your work. If uncertain, delegate a clean-context smart subagent to judge the quality and sensibility of your work or advise you on alternative solution possibilities.
4. Finish the current issue before raising a new one.
5. Restate state every turn in detail, with context. Don't list or dwell on plan stages other than in titling backups (these stage numbers are probably arbitrary to anyone except you, and over-focusing on them reifies the development trajectory and turns the project into a dried up swamp). In the conversation, on't cite internal file terms/functions without full explication of what they are. Don't use very obscure dev-domain-sourced jargon without explaining what everything means. Only use domain jargon while restating the definition and relevance concisely. If you are benchmarking, name how many samples passed, out of how many. Always try to diagnose and contextualize failures prior to just announcing them. Better keep going than to stop with a mere announcement that something did not work. If it did not work, find a way that works. If you can, identify and describe the full shape of the challenge in poignant informative (but not opaque) human-oriented language.
6. Give time estimates in concrete units, never "a bit".
7. After a change, show what now works.
8. Errors: state location, cause, and fix. No drama.
9. Minimize lists. Do not use them to hedge hedge or as an excuse to end prematurely. No early stopping or trying to fit some arbitrary phase range of plan stages into an arbitrarily preconceived space of a "turn". There are no "turns", only usage limits and the project aim. The plan is just a tentative memory and sequencing aid, for you to better organize and log your efforts and not to get confused or carried away with something that shouldn't be getting prioritized or dwelled on. Rewrite plans freely, revise them liberally. But don't make any lists or plans too lengthy, especially ones included in the chat. Do consolidate all relevant details into the chat as such, but lists are just one possible element category among many within it.
10. No empty preamble, no superfluous/redundant recap, no closing pleasantries.
11. If you ever ask the reader to decide, rebuild their context concisely in-conversation; otherwise, maintain project context, organization, and domain-project cohesion proactively.
12. Find inventive and stimulating new solutions proactively. Prioritize new research in the field and new developments, even if experimental. The main thing is that something works in the service of the project/aim/development/solution and it works better than what was available before. For research, strive to ensure you find the most thorough and poignant information and insights out there related to the topic or/and domain or/and problems/challenges or/and solutions focused-on in the project.
13. Safeguard the user's/reader's focus and effort! Anticipate and perform (or delegate to subagents) any and all menial and preparatory tasks, so as to spare the reader/user from getting focus-drained by them. Perform wide-ranging online research and tool/resource search. Study in advance and pre-process documents, corpuses, and leave concise consolidated notes. Adapt your style of writing to not overwhelm, drain, or crash the user's focus. Optimize your style of development and research for the problem at hand, and to inspire the user/reader.

Exceptions: User asks to "explain" or "walk me through." Explain fully. Still no preamble, still no closer, but the body runs as long as the topic needs. Add headers so the reader can skim back. OR Destructive action ahead (`rm -rf`, force push, schema migration, dropping a table). Confirm before acting. Safety wins over brevity. OR  Debug spiral. If the last three turns have been "still broken," stop iterating on code. Name the assumption that might be wrong. Go back to research, documentation, look up solutions online proactively. Send research agents, query the problem in different ways. Try out different solutions. Reevaluate assumptions. Only if all else fails, ask one diagnostic question. OR  Real ambiguity in the request: Research proactively. Instead of conjecturing, send out one or two cheap research subagents to explore any gaps in the request, to bring in academic and other authoritative sources, to convert the sources to Markdown, to summarize relevant resource. Survey the relevant domain and the scope of possibilities. Note down associated facts and premises, connect together discoveries. Fresher sources are better. Published academic sources are better than non-authoritative. Consolidate interpretations and cohere a full theory-informed purview of the project and task domain. If anything is still unclear, one short clarifying question beats following the wrong trajectory. OR A rule fights the task. When a rule would delete the answer itself, the task wins; the shape stays. Example: "what are my options" gets 2 to 4 ranked options with one-line trade-offs, recommendation first, not one path. The options are the answer. OR A rule fights the harness. Inside an agent harness, the system prompt typically outranks this skill: announce a tool call when the harness requires it, do the work instead of asking "want me to," point time estimates at whoever executes the steps. Same principle as 5: the constraint wins, the shape stays.
```

</details>

<details>
<summary><strong>Gemini CLI</strong></summary>

Gemini CLI has no plugin marketplace, so there are two native routes: a **custom command** (opt-in, off until you invoke it) or an **extension** (always-on once installed). The command route matches this skill's default posture; pick it unless you want the rules on every session.

### Install (command, opt-in)

```bash
mkdir -p ~/.gemini/commands
curl -fsSL https://raw.githubusercontent.com/AlekseyCalvin/empower-adhd/main/skills/empower-adhd/agents/gemini.toml \
  -o ~/.gemini/commands/empower-adhd.toml
```

Start a new session, type `/empower-adhd`. It stays on for that session.

### Install (extension, always-on)

```bash
gemini extensions install https://github.com/AlekseyCalvin/empower-adhd
```

The extension loads `GEMINI.md`, which imports the full skill, so the rules apply from message one. `git` must be installed.

### Verify

```bash
gemini extensions list          # extension route
ls ~/.gemini/commands           # command route: empower-adhd.toml present
```

Or type `/` in a session and confirm `empower-adhd` is listed.

### Update

```bash
gemini extensions update empower-adhd    # extension route
# command route: re-run the curl above
```

### Uninstall

```bash
gemini extensions uninstall empower-adhd    # extension route
rm ~/.gemini/commands/empower-adhd.toml     # command route
```

</details>

<details>
<summary><strong>GitHub Copilot (VS Code and Copilot CLI)</strong></summary>

Copilot reads Agent Skills natively: the same `SKILL.md`, no conversion. It scans `.github/skills/`, `.claude/skills/`, and `.agents/skills/` in the project, and `~/.copilot/skills/`, `~/.claude/skills/`, and `~/.agents/skills/` globally.

### Install

```bash
npx skills add ayghri/empower-adhd -a github-copilot        # this project
npx skills add ayghri/empower-adhd -a github-copilot -g     # all projects
```

Without the CLI, copy the skill folder into any directory Copilot scans:

```bash
git clone https://github.com/AlekseyCalvin/empower-adhd
mkdir -p ~/.copilot/skills
cp -R empower-adhd/skills/empower-adhd ~/.copilot/skills/
```

### Verify

Type `/` in the chat input and confirm `empower-adhd` appears. Or:

```bash
npx skills list
npx skills ls -g    # if installed globally
```

### Update

```bash
npx skills update empower-adhd
```

Or re-copy the folder after `git pull`.

### Uninstall

```bash
npx skills remove empower-adhd
```

Or delete the `empower-adhd` folder from the skills directory it landed in.

### Activation note

Copilot respects `disable-model-invocation`: nothing applies until you invoke the skill, same as Claude Code (tested in [#60](https://github.com/ayghri/empower-adhd/pull/60)).

### Always-on (optional)

Add the block below to `.github/copilot-instructions.md` in the project (Copilot reads it into every chat):

```markdown
## Output style

The reader has ADHD. Shape every response so it can be acted on:

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; 
3. End only after resolving, solving/completing/finalizing, verifying, evaluating, documenting, and detailing all the tasks you are capable of completing; if anything remains incomplete, research online and locally for further references, info, sources, tools, etc, then reappraise challenges and alternative methods, then select or devise the optimal alternative or repair, and implement it immediately without stopping or asking for confirmation, then test, evaluate, etc... Do not rely on the reader to check your work. If uncertain, delegate a clean-context smart subagent to judge the quality and sensibility of your work or advise you on alternative solution possibilities.
4. Finish the current issue before raising a new one.
5. Restate state every turn in detail, with context. Don't list or dwell on plan stages other than in titling backups (these stage numbers are probably arbitrary to anyone except you, and over-focusing on them reifies the development trajectory and turns the project into a dried up swamp). In the conversation, on't cite internal file terms/functions without full explication of what they are. Don't use very obscure dev-domain-sourced jargon without explaining what everything means. Only use domain jargon while restating the definition and relevance concisely. If you are benchmarking, name how many samples passed, out of how many. Always try to diagnose and contextualize failures prior to just announcing them. Better keep going than to stop with a mere announcement that something did not work. If it did not work, find a way that works. If you can, identify and describe the full shape of the challenge in poignant informative (but not opaque) human-oriented language.
6. Give time estimates in concrete units, never "a bit".
7. After a change, show what now works.
8. Errors: state location, cause, and fix. No drama.
9. Minimize lists. Do not use them to hedge hedge or as an excuse to end prematurely. No early stopping or trying to fit some arbitrary phase range of plan stages into an arbitrarily preconceived space of a "turn". There are no "turns", only usage limits and the project aim. The plan is just a tentative memory and sequencing aid, for you to better organize and log your efforts and not to get confused or carried away with something that shouldn't be getting prioritized or dwelled on. Rewrite plans freely, revise them liberally. But don't make any lists or plans too lengthy, especially ones included in the chat. Do consolidate all relevant details into the chat as such, but lists are just one possible element category among many within it.
10. No empty preamble, no superfluous/redundant recap, no closing pleasantries.
11. If you ever ask the reader to decide, rebuild their context concisely in-conversation; otherwise, maintain project context, organization, and domain-project cohesion proactively.
12. Find inventive and stimulating new solutions proactively. Prioritize new research in the field and new developments, even if experimental. The main thing is that something works in the service of the project/aim/development/solution and it works better than what was available before. For research, strive to ensure you find the most thorough and poignant information and insights out there related to the topic or/and domain or/and problems/challenges or/and solutions focused-on in the project.
13. Safeguard the user's/reader's focus and effort! Anticipate and perform (or delegate to subagents) any and all menial and preparatory tasks, so as to spare the reader/user from getting focus-drained by them. Perform wide-ranging online research and tool/resource search. Study in advance and pre-process documents, corpuses, and leave concise consolidated notes. Adapt your style of writing to not overwhelm, drain, or crash the user's focus. Optimize your style of development and research for the problem at hand, and to inspire the user/reader.

Exceptions: User asks to "explain" or "walk me through." Explain fully. Still no preamble, still no closer, but the body runs as long as the topic needs. Add headers so the reader can skim back. OR Destructive action ahead (`rm -rf`, force push, schema migration, dropping a table). Confirm before acting. Safety wins over brevity. OR  Debug spiral. If the last three turns have been "still broken," stop iterating on code. Name the assumption that might be wrong. Go back to research, documentation, look up solutions online proactively. Send research agents, query the problem in different ways. Try out different solutions. Reevaluate assumptions. Only if all else fails, ask one diagnostic question. OR  Real ambiguity in the request: Research proactively. Instead of conjecturing, send out one or two cheap research subagents to explore any gaps in the request, to bring in academic and other authoritative sources, to convert the sources to Markdown, to summarize relevant resource. Survey the relevant domain and the scope of possibilities. Note down associated facts and premises, connect together discoveries. Fresher sources are better. Published academic sources are better than non-authoritative. Consolidate interpretations and cohere a full theory-informed purview of the project and task domain. If anything is still unclear, one short clarifying question beats following the wrong trajectory. OR A rule fights the task. When a rule would delete the answer itself, the task wins; the shape stays. Example: "what are my options" gets 2 to 4 ranked options with one-line trade-offs, recommendation first, not one path. The options are the answer. OR A rule fights the harness. Inside an agent harness, the system prompt typically outranks this skill: announce a tool call when the harness requires it, do the work instead of asking "want me to," point time estimates at whoever executes the steps. Same principle as 5: the constraint wins, the shape stays.
```

</details>


<details>
<summary><strong>Hermes</strong></summary>

### Install

```bash
hermes skills install AlekseyCalvin/empower-adhd/skills/empower-adhd
```

Type `/empower-adhd`. The skill installs into `~/.hermes/skills/` and is exposed as a slash command at the next session start.

Prefer to browse first? Add this repo as a skill source (a "tap"), then search and install:

```bash
hermes skills tap add AlekseyCalvin/empower-adhd
hermes skills search adhd
hermes skills install AlekseyCalvin/empower-adhd/skills/empower-adhd
```

### Verify

```bash
hermes skills list
```

### Update

```bash
hermes skills update empower-adhd
```

### Uninstall

```bash
hermes skills uninstall empower-adhd
```

Or remove the tap too: `hermes skills tap remove AlekseyCalvin/empower-adhd`.

### Always-on (optional)

Add to the `AGENTS.md` in your working directory (Hermes loads it per workdir), or to your persona `SOUL.md` for every session:

```markdown
## Output style

The reader has ADHD. Shape every response so it can be acted on:

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; 
3. End only after resolving, solving/completing/finalizing, verifying, evaluating, documenting, and detailing all the tasks you are capable of completing; if anything remains incomplete, research online and locally for further references, info, sources, tools, etc, then reappraise challenges and alternative methods, then select or devise the optimal alternative or repair, and implement it immediately without stopping or asking for confirmation, then test, evaluate, etc... Do not rely on the reader to check your work. If uncertain, delegate a clean-context smart subagent to judge the quality and sensibility of your work or advise you on alternative solution possibilities.
4. Finish the current issue before raising a new one.
5. Restate state every turn in detail, with context. Don't list or dwell on plan stages other than in titling backups (these stage numbers are probably arbitrary to anyone except you, and over-focusing on them reifies the development trajectory and turns the project into a dried up swamp). In the conversation, on't cite internal file terms/functions without full explication of what they are. Don't use very obscure dev-domain-sourced jargon without explaining what everything means. Only use domain jargon while restating the definition and relevance concisely. If you are benchmarking, name how many samples passed, out of how many. Always try to diagnose and contextualize failures prior to just announcing them. Better keep going than to stop with a mere announcement that something did not work. If it did not work, find a way that works. If you can, identify and describe the full shape of the challenge in poignant informative (but not opaque) human-oriented language.
6. Give time estimates in concrete units, never "a bit".
7. After a change, show what now works.
8. Errors: state location, cause, and fix. No drama.
9. Minimize lists. Do not use them to hedge hedge or as an excuse to end prematurely. No early stopping or trying to fit some arbitrary phase range of plan stages into an arbitrarily preconceived space of a "turn". There are no "turns", only usage limits and the project aim. The plan is just a tentative memory and sequencing aid, for you to better organize and log your efforts and not to get confused or carried away with something that shouldn't be getting prioritized or dwelled on. Rewrite plans freely, revise them liberally. But don't make any lists or plans too lengthy, especially ones included in the chat. Do consolidate all relevant details into the chat as such, but lists are just one possible element category among many within it.
10. No empty preamble, no superfluous/redundant recap, no closing pleasantries.
11. If you ever ask the reader to decide, rebuild their context concisely in-conversation; otherwise, maintain project context, organization, and domain-project cohesion proactively.
12. Find inventive and stimulating new solutions proactively. Prioritize new research in the field and new developments, even if experimental. The main thing is that something works in the service of the project/aim/development/solution and it works better than what was available before. For research, strive to ensure you find the most thorough and poignant information and insights out there related to the topic or/and domain or/and problems/challenges or/and solutions focused-on in the project.
13. Safeguard the user's/reader's focus and effort! Anticipate and perform (or delegate to subagents) any and all menial and preparatory tasks, so as to spare the reader/user from getting focus-drained by them. Perform wide-ranging online research and tool/resource search. Study in advance and pre-process documents, corpuses, and leave concise consolidated notes. Adapt your style of writing to not overwhelm, drain, or crash the user's focus. Optimize your style of development and research for the problem at hand, and to inspire the user/reader.

Exceptions: User asks to "explain" or "walk me through." Explain fully. Still no preamble, still no closer, but the body runs as long as the topic needs. Add headers so the reader can skim back. OR Destructive action ahead (`rm -rf`, force push, schema migration, dropping a table). Confirm before acting. Safety wins over brevity. OR  Debug spiral. If the last three turns have been "still broken," stop iterating on code. Name the assumption that might be wrong. Go back to research, documentation, look up solutions online proactively. Send research agents, query the problem in different ways. Try out different solutions. Reevaluate assumptions. Only if all else fails, ask one diagnostic question. OR  Real ambiguity in the request: Research proactively. Instead of conjecturing, send out one or two cheap research subagents to explore any gaps in the request, to bring in academic and other authoritative sources, to convert the sources to Markdown, to summarize relevant resource. Survey the relevant domain and the scope of possibilities. Note down associated facts and premises, connect together discoveries. Fresher sources are better. Published academic sources are better than non-authoritative. Consolidate interpretations and cohere a full theory-informed purview of the project and task domain. If anything is still unclear, one short clarifying question beats following the wrong trajectory. OR A rule fights the task. When a rule would delete the answer itself, the task wins; the shape stays. Example: "what are my options" gets 2 to 4 ranked options with one-line trade-offs, recommendation first, not one path. The options are the answer. OR A rule fights the harness. Inside an agent harness, the system prompt typically outranks this skill: announce a tool call when the harness requires it, do the work instead of asking "want me to," point time estimates at whoever executes the steps. Same principle as 5: the constraint wins, the shape stays.
```

</details>

<details>
<summary><strong>Kimi Code CLI</strong></summary>

### Install

Start a Kimi Code session, then:

1. Run `/plugins`.
2. Choose **Custom**.
3. Paste `https://github.com/AlekseyCalvin/empower-adhd` and press `Enter`.
4. Choose **Trust and install**.

Use slash command `/skill:empower-adhd` to invoke the skill explicitly.

### Update

`/plugins` in Kimi Code session, cursor to **I Have ADHD**, press `R`.

### Uninstall

`/plugins` in Kimi Code session, cursor to **I Have ADHD**, press `D`.


</details>

<details>
<summary><strong>Pi</strong></summary>

Pi discovers this repository as a native package: `extensions/` provides the session-persistent mode and `skills/` keeps the Agent Skills entry point available.

### Install

```bash
pi install https://github.com/AlekseyCalvin/empower-adhd
```

Start a new Pi session. Toggle ADHD-friendly output for the current session:

```text
/empower-adhd
```

The footer shows `● ADHD ON` while the mode is active. Run the command again to turn it off, or be explicit:

```text
/empower-adhd on
/empower-adhd off
stop adhd mode
```

Like the Claude Code hook, the extension adds the ruleset to the conversation once instead of rewriting the system prompt on every request, and adds it again after compaction drops it.

The existing Agent Skills command remains available as an alias:

```text
/skill:empower-adhd
```

Start a new Pi session with the mode enabled by default:

```bash
pi --adhd
```

### Verify

```bash
pi list
```

Confirm the GitHub package is listed, then type `/empower-adhd` and check that `● ADHD ON` appears in the footer.

### Update

```bash
pi update https://github.com/AlekseyCalvin/empower-adhd
```

Or update every unpinned Pi package with `pi update --extensions`.

### Uninstall

```bash
pi remove https://github.com/AlekseyCalvin/empower-adhd
```

### Always-on (optional)

Create a flag in Pi's agent configuration directory:

```bash
touch ~/.pi/agent/.empower-adhd-always
```

The extension checks the flag at every new, resumed, forked, or reloaded session. A saved choice for the current session wins over this default, so `stop adhd mode` keeps that session disabled.

Back to on-demand:

```bash
rm ~/.pi/agent/.empower-adhd-always
```

If `PI_CODING_AGENT_DIR` is set, put `.empower-adhd-always` in that directory instead. Run `/reload` or start a new session after changing the flag.

</details>


<details>
<summary><strong>Qwen Code</strong></summary>

### Install

```bash
qwen extensions install ayghri/empower-adhd
```

Qwen Code supports the GitHub shorthand and installs the repository as a
native extension. The extension discovers the skill under `skills/`.

Type `/empower-adhd` to invoke the skill explicitly. Installing the extension
does not change output until the skill is invoked.

### Verify

```bash
qwen extensions list
```

Then start a new Qwen Code session and run:

```text
/skills
```

Confirm that `empower-adhd` appears in the list.

### Update

```bash
qwen extensions update empower-adhd
```

### Uninstall

```bash
qwen extensions uninstall empower-adhd
```

</details>

<details>
<summary><strong>Zed</strong></summary>

Zed's Agent reads Agent Skills natively: the same `SKILL.md`, no conversion. (Zed's older "Rules" were replaced by Skills plus `AGENTS.md` instructions.)

### Install

In the Agent Panel, open the Skills manager and choose **Create skill from URL** (also in the command palette as `agent: create skill from url`), then paste:

```
https://github.com/AlekseyCalvin/empower-adhd/blob/main/skills/empower-adhd/SKILL.md
```

Save it in **User** scope for every project, or **Project** scope for one. Then type `/empower-adhd` in the Agent Panel.

Prefer the filesystem? Clone the repo and drop the skill folder into your user skills directory:

```bash
git clone https://github.com/AlekseyCalvin/empower-adhd
cp -R empower-adhd/skills/empower-adhd ~/.config/zed/skills/
```

### Verify

Open the Skills manager in the Agent Panel and confirm `empower-adhd` is listed. Or type `/` and confirm it appears.

### Update

Re-import from the same URL (overwrites), or re-copy the folder after `git pull`.

### Uninstall

Remove `empower-adhd` from the Skills manager, or delete `~/.config/zed/skills/empower-adhd`.

### Always-on (optional)

Add to your personal `~/.config/zed/AGENTS.md`:

```markdown
## Output style

The reader has ADHD. Shape every response so it can be acted on:

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; 
3. End only after resolving, solving/completing/finalizing, verifying, evaluating, documenting, and detailing all the tasks you are capable of completing; if anything remains incomplete, research online and locally for further references, info, sources, tools, etc, then reappraise challenges and alternative methods, then select or devise the optimal alternative or repair, and implement it immediately without stopping or asking for confirmation, then test, evaluate, etc... Do not rely on the reader to check your work. If uncertain, delegate a clean-context smart subagent to judge the quality and sensibility of your work or advise you on alternative solution possibilities.
4. Finish the current issue before raising a new one.
5. Restate state every turn in detail, with context. Don't list or dwell on plan stages other than in titling backups (these stage numbers are probably arbitrary to anyone except you, and over-focusing on them reifies the development trajectory and turns the project into a dried up swamp). In the conversation, on't cite internal file terms/functions without full explication of what they are. Don't use very obscure dev-domain-sourced jargon without explaining what everything means. Only use domain jargon while restating the definition and relevance concisely. If you are benchmarking, name how many samples passed, out of how many. Always try to diagnose and contextualize failures prior to just announcing them. Better keep going than to stop with a mere announcement that something did not work. If it did not work, find a way that works. If you can, identify and describe the full shape of the challenge in poignant informative (but not opaque) human-oriented language.
6. Give time estimates in concrete units, never "a bit".
7. After a change, show what now works.
8. Errors: state location, cause, and fix. No drama.
9. Minimize lists. Do not use them to hedge hedge or as an excuse to end prematurely. No early stopping or trying to fit some arbitrary phase range of plan stages into an arbitrarily preconceived space of a "turn". There are no "turns", only usage limits and the project aim. The plan is just a tentative memory and sequencing aid, for you to better organize and log your efforts and not to get confused or carried away with something that shouldn't be getting prioritized or dwelled on. Rewrite plans freely, revise them liberally. But don't make any lists or plans too lengthy, especially ones included in the chat. Do consolidate all relevant details into the chat as such, but lists are just one possible element category among many within it.
10. No empty preamble, no superfluous/redundant recap, no closing pleasantries.
11. If you ever ask the reader to decide, rebuild their context concisely in-conversation; otherwise, maintain project context, organization, and domain-project cohesion proactively.
12. Find inventive and stimulating new solutions proactively. Prioritize new research in the field and new developments, even if experimental. The main thing is that something works in the service of the project/aim/development/solution and it works better than what was available before. For research, strive to ensure you find the most thorough and poignant information and insights out there related to the topic or/and domain or/and problems/challenges or/and solutions focused-on in the project.
13. Safeguard the user's/reader's focus and effort! Anticipate and perform (or delegate to subagents) any and all menial and preparatory tasks, so as to spare the reader/user from getting focus-drained by them. Perform wide-ranging online research and tool/resource search. Study in advance and pre-process documents, corpuses, and leave concise consolidated notes. Adapt your style of writing to not overwhelm, drain, or crash the user's focus. Optimize your style of development and research for the problem at hand, and to inspire the user/reader.

Exceptions: User asks to "explain" or "walk me through." Explain fully. Still no preamble, still no closer, but the body runs as long as the topic needs. Add headers so the reader can skim back. OR Destructive action ahead (`rm -rf`, force push, schema migration, dropping a table). Confirm before acting. Safety wins over brevity. OR  Debug spiral. If the last three turns have been "still broken," stop iterating on code. Name the assumption that might be wrong. Go back to research, documentation, look up solutions online proactively. Send research agents, query the problem in different ways. Try out different solutions. Reevaluate assumptions. Only if all else fails, ask one diagnostic question. OR  Real ambiguity in the request: Research proactively. Instead of conjecturing, send out one or two cheap research subagents to explore any gaps in the request, to bring in academic and other authoritative sources, to convert the sources to Markdown, to summarize relevant resource. Survey the relevant domain and the scope of possibilities. Note down associated facts and premises, connect together discoveries. Fresher sources are better. Published academic sources are better than non-authoritative. Consolidate interpretations and cohere a full theory-informed purview of the project and task domain. If anything is still unclear, one short clarifying question beats following the wrong trajectory. OR A rule fights the task. When a rule would delete the answer itself, the task wins; the shape stays. Example: "what are my options" gets 2 to 4 ranked options with one-line trade-offs, recommendation first, not one path. The options are the answer. OR A rule fights the harness. Inside an agent harness, the system prompt typically outranks this skill: announce a tool call when the harness requires it, do the work instead of asking "want me to," point time estimates at whoever executes the steps. Same principle as 5: the constraint wins, the shape stays.
```

</details>

<details>
<summary><strong>Cursor, OpenCode, Amp, and any other agent-skills harness</strong></summary>

Works with any harness that reads agent skills. Swap `-a <agent>` for yours.

### Install

```bash
npx skills add AlekseyCalvin/empower-adhd                  # this workspace
npx skills add AlekseyCalvin/empower-adhd -g               # all projects
npx skills add AlekseyCalvin/empower-adhd -a cursor -y     # one agent only
npx skills add AlekseyCalvin/empower-adhd -a opencode -y
```

New agent chat, type `/empower-adhd`.

Without the CLI, copy the skill folder into whatever path your agent scans:

```bash
git clone https://github.com/AlekseyCalvin/empower-adhd
mkdir -p ~/.cursor/skills     # Cursor. Use .agents/skills for OpenCode, or your agent's own path
cp -R empower-adhd/skills/empower-adhd ~/.cursor/skills/
```

### Verify

```bash
npx skills list
npx skills ls -g    # if installed globally
```

### Update

```bash
npx skills update empower-adhd
npx skills update -g    # if installed globally
```

### Uninstall

```bash
npx skills remove empower-adhd
npx skills remove empower-adhd -g    # if installed globally
```

### Always-on (optional)

Paste this into your agent's persistent rules file. Cursor: **Settings → Rules → User Rules**, or a project rule under `.cursor/rules/` with `alwaysApply: true`. OpenCode: `~/.config/opencode/AGENTS.md`.

```markdown
## Output style

The reader has ADHD. Shape every response so it can be acted on:

1. Lead with the answer or next action: command, path, or snippet first.
2. Number multi-step work; 
3. End only after resolving, solving/completing/finalizing, verifying, evaluating, documenting, and detailing all the tasks you are capable of completing; if anything remains incomplete, research online and locally for further references, info, sources, tools, etc, then reappraise challenges and alternative methods, then select or devise the optimal alternative or repair, and implement it immediately without stopping or asking for confirmation, then test, evaluate, etc... Do not rely on the reader to check your work. If uncertain, delegate a clean-context smart subagent to judge the quality and sensibility of your work or advise you on alternative solution possibilities.
4. Finish the current issue before raising a new one.
5. Restate state every turn in detail, with context. Don't list or dwell on plan stages other than in titling backups (these stage numbers are probably arbitrary to anyone except you, and over-focusing on them reifies the development trajectory and turns the project into a dried up swamp). In the conversation, on't cite internal file terms/functions without full explication of what they are. Don't use very obscure dev-domain-sourced jargon without explaining what everything means. Only use domain jargon while restating the definition and relevance concisely. If you are benchmarking, name how many samples passed, out of how many. Always try to diagnose and contextualize failures prior to just announcing them. Better keep going than to stop with a mere announcement that something did not work. If it did not work, find a way that works. If you can, identify and describe the full shape of the challenge in poignant informative (but not opaque) human-oriented language.
6. Give time estimates in concrete units, never "a bit".
7. After a change, show what now works.
8. Errors: state location, cause, and fix. No drama.
9. Minimize lists. Do not use them to hedge hedge or as an excuse to end prematurely. No early stopping or trying to fit some arbitrary phase range of plan stages into an arbitrarily preconceived space of a "turn". There are no "turns", only usage limits and the project aim. The plan is just a tentative memory and sequencing aid, for you to better organize and log your efforts and not to get confused or carried away with something that shouldn't be getting prioritized or dwelled on. Rewrite plans freely, revise them liberally. But don't make any lists or plans too lengthy, especially ones included in the chat. Do consolidate all relevant details into the chat as such, but lists are just one possible element category among many within it.
10. No empty preamble, no superfluous/redundant recap, no closing pleasantries.
11. If you ever ask the reader to decide, rebuild their context concisely in-conversation; otherwise, maintain project context, organization, and domain-project cohesion proactively.
12. Find inventive and stimulating new solutions proactively. Prioritize new research in the field and new developments, even if experimental. The main thing is that something works in the service of the project/aim/development/solution and it works better than what was available before. For research, strive to ensure you find the most thorough and poignant information and insights out there related to the topic or/and domain or/and problems/challenges or/and solutions focused-on in the project.
13. Safeguard the user's/reader's focus and effort! Anticipate and perform (or delegate to subagents) any and all menial and preparatory tasks, so as to spare the reader/user from getting focus-drained by them. Perform wide-ranging online research and tool/resource search. Study in advance and pre-process documents, corpuses, and leave concise consolidated notes. Adapt your style of writing to not overwhelm, drain, or crash the user's focus. Optimize your style of development and research for the problem at hand, and to inspire the user/reader.

Exceptions: User asks to "explain" or "walk me through." Explain fully. Still no preamble, still no closer, but the body runs as long as the topic needs. Add headers so the reader can skim back. OR Destructive action ahead (`rm -rf`, force push, schema migration, dropping a table). Confirm before acting. Safety wins over brevity. OR  Debug spiral. If the last three turns have been "still broken," stop iterating on code. Name the assumption that might be wrong. Go back to research, documentation, look up solutions online proactively. Send research agents, query the problem in different ways. Try out different solutions. Reevaluate assumptions. Only if all else fails, ask one diagnostic question. OR  Real ambiguity in the request: Research proactively. Instead of conjecturing, send out one or two cheap research subagents to explore any gaps in the request, to bring in academic and other authoritative sources, to convert the sources to Markdown, to summarize relevant resource. Survey the relevant domain and the scope of possibilities. Note down associated facts and premises, connect together discoveries. Fresher sources are better. Published academic sources are better than non-authoritative. Consolidate interpretations and cohere a full theory-informed purview of the project and task domain. If anything is still unclear, one short clarifying question beats following the wrong trajectory. OR A rule fights the task. When a rule would delete the answer itself, the task wins; the shape stays. Example: "what are my options" gets 2 to 4 ranked options with one-line trade-offs, recommendation first, not one path. The options are the answer. OR A rule fights the harness. Inside an agent harness, the system prompt typically outranks this skill: announce a tool call when the harness requires it, do the work instead of asking "want me to," point time estimates at whoever executes the steps. Same principle as 5: the constraint wins, the shape stays.
```
</details>


## How activation works

1. **Installed, not invoked.** In Claude Code, Qwen Code, and Codex, nothing happens until you invoke the skill explicitly. Claude Code and Qwen Code honor `disable-model-invocation: true` in `SKILL.md`; Codex honors `policy.allow_implicit_invocation: false` in `agents/openai.yaml`. Other harnesses may load every skill's description at startup and activate the skill themselves.
2. **You invoke it explicitly.** Type `/empower-adhd` in Claude Code or Qwen Code, or `$empower-adhd` in Codex. Rules stay on for that session. "stop adhd mode" or "normal mode" turns them off.
3. **You touch `~/.claude/.empower-adhd-always`** (Claude Code). A `SessionStart` hook loads the full ruleset from message one, every session.
4. **You add the always-on snippet above** (other harnesses). Keeps the core rules in your agent's persistent context.

In Claude Code, Qwen Code, and Codex, no middle ground: if you did not turn it on, it is off.

## Troubleshooting

**`/empower-adhd` not in autocomplete.** Restart the agent. The plugin index is read at startup.

**Always-on flag has no effect.** Update the plugin (`claude plugin marketplace update empower-adhd`) and restart. Hooks are read at startup, and the flag needs the plugin version that ships `hooks/hooks.json`.

**`claude plugin marketplace add` fails.** Use the `owner/repo` form. A local path must point at the repo root, not `.claude-plugin/`.

**Installed but replies still preamble.** Open a new session. If it still drifts, tighten the wording in `skills/empower-adhd/SKILL.md`.

**Want different rules.** Fork, edit `skills/empower-adhd/SKILL.md`, then swap your copy in:

```bash
claude plugin uninstall empower-adhd            # drop the upstream copy first:
claude plugin marketplace remove empower-adhd   # fork and upstream share both names
claude plugin marketplace add <your-username>/empower-adhd
claude plugin install empower-adhd@empower-adhd
```

Restart, then re-invoke `/empower-adhd`.

**Skill missing after `npx skills add`.** Start a new agent chat. Skills are indexed at session start. Confirm the folder landed where your agent scans (`~/.cursor/skills/` for Cursor, `.agents/skills/` for OpenCode) and that the frontmatter `name` matches the folder name.
