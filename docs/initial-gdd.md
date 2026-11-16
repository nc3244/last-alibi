# Last Alibi — Initial GDD
Status: Initial / G1, revised concept v0.2. Proposal only; no implemented or verified gameplay.
Owner: Nikhil Chagam, Executive Producer and Creative Director. Individual project with a directed agent team.

## Revision and The X
Owner-directed revision: replace the room-exploration mystery with camera-based night-shift survival horror featuring human workers. Preserve evidence-based deduction and remembered lies.
The X: Monitor cameras, question three workers, and ration security power to survive a night shift while uncovering a murderer hiding among your coworkers.

## Premise, player and platform
You are the overnight security guard at a closed warehouse. A murder has triggered a lockdown, and police assistance arrives at dawn. Three human workers remain inside: a shift supervisor, a maintenance technician, and a cleaner. One is the murderer and wants to reach the security office to silence you; the others move for work or to hide unrelated secrets. These are original characters, not robotic performers.
Single-player surveillance/survival mystery for players who enjoy tense resource decisions and evidence-based deduction. Hypothesis: players compare camera observations with testimony, revise theories, and explain why they spent power on protection rather than investigation.
Proposed platform: desktop, Godot 4 / GDScript. Stationary office interface with four camera views, text intercom, one powered door, and an evidence board. Mouse and keyboard; provide labeled controls and readable threat indicators. No free-roaming environment.

## Time rules and valid session
One compressed night, midnight to 6 a.m. Proposed initial tuning: 24 decision ticks of 15 simulated minutes each. This is turn-based surveillance tension, not continuous real-time survival.
Reviewing the board, inspecting already captured evidence, switching UI panels and composing a question are free. A fresh camera sweep, an accepted intercom interview, or a wait/door-control action consumes one tick. Set the door state for the next tick through the action panel; no unlimited free door toggling.
Each committed action resolves in this order: capture observation or accepted testimony → charge resource use → advance deterministic worker routes → resolve any telegraphed office breach → advance clock. A successful defense prevents the breach. At tick 24, resolve survival before the final accusation screen.
Pause simulation during model generation, validation, fallback, menus and final accusation. An invalid/late model response falls back to a script for the same action; it does not add a tick.
At dawn, a surviving player gets one untimed accusation with selected supporting evidence. Final win requires survival AND correct culprit AND valid evidence support. Survival with a weak/wrong accusation is a partial outcome, not a full win. An undefended culprit breach before dawn loses the session.

## Core loop
Act: check a camera, question a worker, or spend an action preparing the door/waiting.
Respond: receive timestamped observations or validated testimony; show power drain, worker movement, threat cues and clock change.
Interpret: compare worker claims with captured footage and incident records on the board; decide whether a threat cue merits spending power.
Next action: investigate another lead, confront a remembered claim, or defend the office.
Example: a technician denies entering the loading bay; a saved frame places them there. Confronting them may clarify their timeline but lets the hidden culprit advance another tick. Suspicion does not prove guilt.

## Mechanics, scoring and feedback
- World truth, culprit, timeline, camera observations, worker knowledge and route rules are fixed.
- Four cameras show timestamped observations; captures persist on the board so the player need not memorize transient frames.
- Camera sweeps, intercom use and a closed door consume power under deterministic rules. Proposed start: 100 units; exact action/door costs are OPEN pending solvability testing.
- The powered door blocks a breach while closed with sufficient power. At zero power it unlocks; zero power is not an automatic loss, but subsequent undefended breach is.
- Threats have observable warning cues at least one action before a possible breach. No unavoidable attack from an unseen random roll.
- Only the culprit is deliberately attacking. Innocent movement and other secrets create ambiguity; location or nervousness alone never establishes guilt.
- Case strength increases for unique verified evidence connections, not dialogue volume or emotional behavior. Exact rubric/threshold: OPEN.
- Rapport and pressure may affect disclosure/cooperation, never crime facts or movement legality. Refusals must not make the case insoluble.
- Feedback: night clock, remaining power, labeled door state, warning cue, claim log and case-strength indicator. These replace the former escape countdown.
- Earlier request for clearer winning markers is addressed by power/survival indicators plus case strength.

## Pillars and explored directions
Watch before you commit; every watt is a choice; prove the alibi false.
Actual direction history in this conversation: (1) the original room-search/interview mystery, rejected as too simple and lacking survival pressure; (2) a robotic-performer surveillance concept, replaced at the owner's request with human workers. The chosen version combines camera/resource tension with believable coworker lies.
These are documented design revisions; do not describe them as concepts explored before the original November 9 pitch.

## Agent hypothesis and scripted comparison
Bounded agents adapt each worker's wording and defense to shown evidence, rapport, questions and remembered statements. The model never controls routes, threats, attacks, door, power, clock, culprit or score.
Hypothesis: adaptive interviews make pursuing one's own theory feel more consequential while preserving fair survival choices.
Baseline: branching scripted worker interviews using the same fixed case, camera observations, survival schedule, resources and UI. Scripts lose flexible follow-up that makes a worker address a player-invented challenge to a prior claim.
Propose 4–6 exploratory external-player sessions; alternate mode order and account for case familiarity. Ask: “Could you challenge a worker's earlier claim while deciding whether to investigate or protect yourself?”
Observe theory revisions, supported accusations, survival, power choices, consistency, fallback rate and latency. Separate survival difficulty from dialogue benefit; no results yet.

## Scope and cuts
Include one short night, one office, four static camera views, three human workers, one powered door, fixed route/threat schedule, evidence board, clock/power/case indicators, scripted and adaptive interview modes.
Exclude continuous real-time simulation, 3D/free roam, voice, multiplayer, multiple nights, generated crimes, combat, custom animation and elaborate relationship simulation.
Cut relationship depth, then camera/art polish and secondary event variety. Keep one readable threat route, the fair clue path, door/power choices, fixed truth, validation and scripted baseline.
Required pre-test: verify at least one feasible survive-and-solve strategy; ensure fallback/refusal never deletes essential evidence.

## References and attribution
Five Nights at Freddy's: camera monitoring, powered protection and limited-power tradeoffs from a fixed security station. Change to three human coworkers, a fixed murder investigation, evidence board and adaptive intercom interviews. This is an original game inspired by mechanics, not an official or branded franchise installment.
L.A. Noire: confronting claims with evidence; change to original intercom questions and persistent claim memory.
Return of the Obra Dinn: evidence-linked deduction record; change to a live survival investigation.
Use original warehouse, characters, dialogue, UI and audiovisual assets. Do not copy franchise characters, names, maps, imagery, sounds, code or distinctive branding. No reference grants an asset license. Godot uses MIT terms; retain notices and record dependency licenses. Exact provider/model terms and rates: OPEN.

## Open questions
Official G2/G3/G4 dates; final case/culprit/evidence rubric; final tick count, resource costs and routes; warning clarity; model/provider rates; final build target; measured latency/cost and survival balance.
See [Configuration](initial-configuration.md) and [Project Plan](initial-project-plan.md).
