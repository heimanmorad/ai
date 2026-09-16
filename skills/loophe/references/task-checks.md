# Task-specific acceptance

Use only the section relevant to the requested deliverable. These are prompts for selecting criteria, not a mandatory expanded checklist. Decide acceptance before execution; do not add work just to fill a template.

## Management plans and decisions

Build a plan someone can act on at the requested level of detail. Connect recommendations to the goal and available constraints.

Possible criteria:
- **Decision fit:** addresses the actual problem, priorities, and relevant alternatives; makes consequential tradeoffs visible.
- **Feasibility:** timing, capacity, dependencies, and material risks are consistent with supplied facts. Mark unconfirmed assumptions and proposed owners as proposals.
- **Actionability:** clear next actions and observable success measures; include sequencing and responsibility when they help execution.

Verify decisive arithmetic and trace important claims to their inputs. A polished table is not evidence that resources or dates are feasible. Do not create external tasks, assign people, or send a plan unless authorized.

## Research and comparisons

Start with the decision or question the research must inform. Set boundaries so gathering does not expand without purpose.

Possible criteria:
- **Evidence:** important claims have identifiable sources, dates, and relevant scope. Prefer primary evidence; independent sources matter for contested conclusions. Do not invent citations or universal source quotas.
- **Synthesis:** separate observed facts, interpretation, forecasts, and uncertainty; address meaningful conflicting evidence and comparable definitions.
- **Decision usefulness:** recommendations follow from the evidence; expose assumptions that would change the recommendation.

Verify changing facts against current sources when access is available. Disclose access and freshness gaps; an unverified mandatory claim blocks approval. A research plan or a plausible narrative is not completed research.

## Product and web development

Match the requested stage. A vision needs a clear outcome and scope; a PRD needs user behavior and testable acceptance; a technical design needs implementable decisions and relevant dependencies. Do not manufacture all stages for every request.

For implementation, read applicable repository instructions and existing architecture. Prefer a small coherent change that satisfies user-visible acceptance:
- **Behavior:** demonstrate the requested flow, including relevant error/empty states; reproduce a reported bug before and check after the fix when possible.
- **Integration:** use relevant existing tests/build/type checks and verify interfaces affected by the change. Add tests when they materially prevent regression, not merely to mirror code.
- **Usability and operability:** for changed UI inspect the running flow and responsive behavior when tools allow; check accessibility, security, or performance where the change creates a concrete risk.

State exactly which checks ran and which remain unverified. Compilation does not demonstrate a working user flow. Do not deploy, merge, or alter live data beyond the approved scope.

## Artifact presentation

Honor the requested language and format. Use real RTL layout for Hebrew reader-facing documents and inspect rendered output when layout matters. Keep code, identifiers, and technical paths intact. Avoid producing extra formats or lengthy supporting documents without a use.
