# Report format

Lead with the scoped score, one-sentence diagnosis, and confidence (high/medium/low with reason). Keep the default report concise; expand only when requested.

1. **Scope:** product assumption, screens/routes, viewports, states, evidence source, untested areas, rubric v1.0.
2. **Score table:** dimension | weight | rating /5 or U | contribution | evidence and primary deduction. Follow with the sum, observed denominator, coverage, and rounded score. Include grade band. Explain provisional status when applicable.
3. **Keep:** 1–3 evidence-backed strengths.
4. **Fix first:** issue table with priority | location/evidence | problem and impact | exact change | acceptance check | effort. Include at most five key issues.
5. **Design direction and handoff:** a short cohesive direction, followed by an ordered implementation prompt grounded in the observed problems. Make it directly usable by a coding agent; specify preservation constraints and verification steps. Do not instruct it to overwrite product goals or existing brand intent.

Example issue:
P1 · E2 / mobile checkout · Three equally prominent buttons obscure the next step · Keep “Continue” as the single primary button; style “Back” as secondary and “Help” as a text action using existing tokens · At the reviewed mobile width, primary action is visible without overlap and keyboard focus reaches actions in logical order · M (estimate).

Separate observed failures from risks and preference suggestions. If only evidence for two issues exists, report two; do not fabricate the other three.
