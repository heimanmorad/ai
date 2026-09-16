# Runtime compatibility

This file describes host integration, not additional user intake fields. Keep the interview in the language of the parent skill.

## Shared contract

- Both variants use portable `SKILL.md` metadata (`name`, `description`) and relative references. No API key, SDK, provider CLI, or helper script is required by the skill.
- A normal model conversation can conduct intake. Actual worker/reviewer execution requires native subagent tools with sufficient model selection and verification. A skill cannot create missing capabilities.
- Stay in the main conversation as orchestrator. Do not configure this interviewing skill to run in a detached subagent. Explicit model selection applies to worker/reviewer calls, not an instruction pretending to switch the main conversation.
- Record the selected runtime model or alias and the basis for verification (tool configuration/runtime metadata). If an alias is all the runtime exposes, disclose that the exact backend version is unknown; do not claim a precise version. If strict exact-version selection is requested but unavailable, stop before execution.
- Keep the reviewer independent: supply only the approved definition, a versioned artifact, and evidence. Prefer a new reviewer context for each round. If the host cannot isolate context, disclose the limitation before approval; do not claim clean isolation.
- Run worker then reviewer sequentially, waiting for the actual output. If delegation tools require useful concurrent work, the orchestrator can independently verify the requirements, calculations, or artifact while the child works. Respect native tool scheduling restrictions; never invent parallel tasks just to obtain delegation.
- Reviewer access should be read-only to the artifact where supported. Do not let the reviewer modify the artifact being evaluated. Prevent concurrent workers from overwriting the same version.
- A tool configuration is evidence of the requested model, not proof of undisclosed server routing. Report only what the host exposes.

## Claude Code

Install each complete skill folder under `~/.claude/skills/` (personal) or `.claude/skills/` (project). Invoke `/loophe` or `/loopen`.
Use native agent tools with an explicit supported `model` argument or subagent configuration. Common aliases include `sonnet` and `opus`; resolve them in the actual environment. Fable is a user-requested option, not an assumed standard alias. Check effective configuration, including any `CLAUDE_CODE_SUBAGENT_MODEL` override, before promising a model.
Do not add `context: fork` to these skills: the initial interview must remain in the main conversation. Subagents need only their bounded task, not the whole interview skill.

## Codex / GPT

Install each complete skill folder under `~/.agents/skills/` (personal) or `.agents/skills/` (project). Invoke `$loophe` or `$loopen` or use the skill picker.
Use the host's native subagent tools. Resolve model identifiers from its available-model list. Astra (`gpt-6-astra`) and Sol (`gpt-5.6-sol`) are suggestions only when exposed by that runtime; never pass Claude aliases to a GPT-only host. When a tool disallows model overrides on a full-history fork, use a fresh/minimal context with explicit task instructions and the approved model.

## Hosted chat / ChatGPT Work / Claude web

Local installation does not automatically install a skill into a hosted chat account. Use that product's supported skill/plugin installation or supply the skill instructions as conversation context. Do not promise that slash commands or `$` invocation work everywhere.
Check the actual tools available to that conversation. Where native subagents/model selection are missing, finish intake and provide the approved definition for a supported environment; report execution blocked, and do not simulate separate agents. Do not introduce API keys as a workaround.

## Official references

- Claude skills: https://code.claude.com/docs/en/skills
- Claude subagents: https://code.claude.com/docs/en/subagents
- OpenAI skills: https://learn.chatgpt.com/docs/build-skills
- OpenAI subagents: https://learn.chatgpt.com/docs/agent-configuration/subagents

Runtime availability takes precedence over examples in this file. Consult current host documentation when installation or model controls differ.
