# Last Alibi — Initial GDD
Status: Initial / G1 proposal. No playable implementation or verified behavior is claimed.
Owner: Nikhil Chagam, Executive Producer and Creative Director. Individual project with a directed agent team.

## The X
Investigate a murder, connect clues, and question three suspects to feel the tension of outsmarting someone hiding the truth.

## Player, genre, platform
Single-player deduction mystery for mystery fans motivated by discovery and mastery. Proposed platform: desktop, using Godot 4 and GDScript. Mouse/keyboard; typed interviews, clickable searches, and an evidence board. Accessibility target: readable text, keyboard navigation, and labeled progress indicators.

## Valid session and core loop
Start a fixed case with three suspects and a limited turn budget. Act: search a location or ask a question. Respond: receive a fixed clue or validated testimony. Interpret: compare claims and connect evidence on a timeline. Next action: pursue a lead or accuse. Each search/interview consumes one turn; rejected technical responses and board review consume none. Exact initial turn budget is OPEN; budget planning assumes at most 12 model calls.

## Mechanics and dynamics
- Immutable culprit, timeline, clue facts, and suspect knowledge.
- Original questions can challenge a remembered earlier claim.
- Rapport, pressure, and revealing another suspect's claim affect cooperation, never the truth.
- Evidence board records source statements and player connections.
- Verified connections increase case strength; duplicate links give no additional credit.
- Escape countdown displays remaining turns. Exact thresholds and scoring are OPEN.
- Proposed accusation: choose culprit and supporting evidence; a deterministic solution rubric evaluates it.
- Success requires the correct culprit and sufficient supporting evidence before escape; confession is optional.
- Proposed failure: unsupported/wrong accusation or expiry without a successful accusation. Final-turn ordering is OPEN; ensure a final accusation opportunity.
- Nervousness never proves guilt. A refusal must not make the case impossible.

Intended dynamics: prioritize leads, test competing theories, balance rapport and pressure. Intended aesthetics: tension, discovery, and earned certainty. Progression is within one case, with no campaign.

## Pillars and concept comparison
Earn the conclusion; remember the lie; spend each turn well.
Proposed alternatives: fixed branching-dialogue mystery (reliable but limits novel follow-up); open detective chat (flexible but risks inconsistent facts). Last Alibi combines flexible questioning with a fixed solvable case.
OPEN: confirm these alternatives reflect the owner's actual earlier exploration.

## Agent hypothesis and baseline
Adaptive testimony bounded by facts, knowledge, rapport, and remembered statements should increase the feeling of outsmarting a suspect. Baseline: branching scripted interviews, same case, clues, turn budget, and UI. Scripts lose flexible follow-up on a player-invented questioning strategy.
Proposed exploratory study: 4–6 external players, alternate version order; account for familiarity/learning. Ask: “Could you pursue your own theory and make a suspect address an earlier claim?” Observe theory revisions, evidence-supported accusations, contradictions, fallback rate, completion, and response latency. No results yet.

## Scope and cuts
Include one crime scene, three suspects, a fixed clue set, board, case strength, countdown, scripted and adaptive modes. Exclude voice, multiplayer, procedural crimes, multiple cases, and custom art production.
Cut relationship complexity, then exploration polish. Preserve fixed truth, evidence validation, remembered claims, and baseline.
Balance requires clue-path walkthroughs and external tests before tuning exact turns.

## References and terms
Return of the Obra Dinn: deduction record connecting identities/events. L.A. Noire: confronting testimony with evidence. Borrow mechanical ideas; change to adaptive interviews with remembered claims. These are proposed references, not claims of personal play history.
Use original case writing, characters, text, and visual assets; no third-party game assets/code are licensed by reference. Godot uses MIT terms; retain required notices and check dependencies. Provider terms/prices remain to be checked at selection.

## Open questions
Official G2/G3/G4 dates; final case script and solution rubric; exact clue count/turn limit; model; build target; rapport/pressure rules; supported interview input; cost and latency evidence.
See [Configuration](initial-configuration.md) and [Project Plan](initial-project-plan.md).
