# Runtime guidance

Read once per environment before proposing the run. Keep user-facing conversation in the parent skill's language.

- Stay in the main conversation as orchestrator. The skill cannot switch its model. Use available runtime metadata/configuration to identify models; an agent's self-description is not evidence.
- Pick supported worker/reviewer models and show the choices briefly in the approval summary. Prefer a capable efficient worker for routine work, and stronger reasoning for difficult design, synthesis, or review. Honor explicit user preferences. Use native selection controls; verify effective settings rather than assuming an alias guarantees a version.
- Exact model/version control is required only when the user requires it. If only an alias or inherited model is exposed, describe that limitation honestly before approval. Never substitute silently for an explicitly selected model.
- Require real subagent tools and a separate reviewer context. If unavailable, finish useful intake and offer a portable definition marked **EXECUTION BLOCKED**. Approval of that definition does not authorize or simulate a run. Do not replace independent review with self-review or ask for API keys.
- Supply only the approved definition, current artifact, and evidence to a fresh reviewer. Keep it read-only where supported. Use sequential worker/reviewer execution; respect host scheduling rules and avoid concurrent writes to the same artifact.
- Check the host's actual tools and settings. If an agreed capability fails later, preserve progress and report the blocker.

## Claude Code

Install complete folders under `~/.claude/skills/` or project `.claude/skills/`; invoke `/loophe` or `/loopen`. Do not set `context: fork` on this interviewing skill. Use supported native agent model controls, considering environment or organization overrides.

[Skills](https://code.claude.com/docs/en/skills) · [Subagents and model selection](https://code.claude.com/docs/en/sub-agents)

## Codex / ChatGPT

Install local skills under `~/.agents/skills/` or project `.agents/skills/`; invoke `$loophe` or `$loopen` in Codex. Use models exposed by that host. If full-history forks prohibit model overrides, use fresh/minimal context when selecting a model explicitly.

Hosted ChatGPT or Claude sessions use their own installation mechanisms and capabilities; local installation does not establish hosted availability.

[OpenAI skills](https://learn.chatgpt.com/docs/build-skills)
