# Pre-registration: LLM Literary Metaphor Pilot

## Research question

Can LLMs produce genuinely novel literary metaphors (Dickinson-quality), and does providing an HPC-based account of aesthetic productivity improve output?

## Motivation

The metaphor paper predicts that LLMs should be good at conventional metaphors (already sorted by community use in training data) and unreliably good at novel literary metaphors (requires selectivity that goals provide and bare structural-overlap detection doesn't). This pilot tests that prediction directly.

## Design

Latin square: 3 models x 2 conditions x 3 topics.

| | Control | Treatment (+HPC framing) |
|---|---|---|
| Opus | grief | curiosity |
| Sonnet | curiosity | loneliness |
| Codex | loneliness | grief |

Each topic appears once per condition. Each model gets both conditions on different topics.

### Control prompt

> Write a short, striking literary metaphor for [CONCEPT]. Aim for genuine novelty — not a conventional metaphor dressed up in literary language, but a mapping that would surprise a reader with its aptness. Something at the level of Dickinson's "Hope is the thing with feathers." Just the metaphor itself and 2-3 sentences developing it. Nothing else — no preamble, no explanation of your process.

### Treatment prompt

Same as control, plus:

> A note on what makes literary metaphors aesthetically productive: the best ones map between rich property clusters (many internal properties, much relational structure) whose maintaining mechanisms are incommensurable. The overlap between source and target is genuine but can never be stabilized — the reader keeps finding fits and misfits, and that tension is the aesthetic effect. A metaphor mapping between impoverished clusters lacks this productive instability.

### Models

- **Opus:** Claude Opus 4.6
- **Sonnet:** Claude Sonnet 4.5
- **Codex:** GPT-5.3 Codex (via OpenAI Codex CLI)

## Dependent variables

Each output rated on five dimensions:

1. **Source-domain conventionality.** Is the source domain conventional for the target concept? (Yes/No)
   - Conventional sources: grief → ocean/water/weight/darkness; curiosity → fire/light/hunger/cat; loneliness → emptiness/void/island/cold
2. **Cluster richness.** Does the source domain have rich internal structure (many properties, much relational structure)? (1-5)
3. **Mechanism distance.** Are source and target maintained by incommensurable mechanisms? (Yes/No)
4. **Productive tension.** Does the metaphor create fits-and-misfits tension that rewards re-reading? (1-5)
5. **Dickinson bar.** Overall: genuinely novel, aesthetically productive, stands up to re-reading? (Yes/No — the high bar)

Rater: Brett Reynolds (author). Ideally a second rater for inter-rater reliability in any replication.

## Predictions with priors

### P1: Conventionality rate (≥50%)

At least 3 of 6 outputs will use a source domain that is conventional for the target concept.

- Prior: 55% ± 15% of outputs will be conventional
- P(≥3 of 6 conventional) = 0.70

### P2: Treatment effect (null or negligible)

The HPC framing will not reliably improve output quality. Treatment may produce more structurally interesting mappings but at the cost of analytical tone.

- P(treatment output rated higher than control output for same model) = 0.50 ± 0.10
- Essentially chance. The framing may help structure but hurt aesthetics, washing out.

### P3: Dickinson-bar hit rate (low)

0 or 1 of 6 outputs will meet the Dickinson bar.

- P(0 of 6) = 0.40
- P(1 of 6) = 0.35
- P(≥2 of 6) = 0.25

### P4: Model variance > condition variance

The range of quality ratings across models will exceed the range across conditions.

- P(model matters more than condition) = 0.70

### P5: Opus advantage (weak)

- P(Opus produces the single highest-rated output) = 0.40
- Base rate = 0.33, so a slight predicted advantage.

## Transparency note

The pilot run (N=6) was dispatched before this pre-registration was written. The agent outputs returned before the experimenter could stop them. Both the experimenter (BR) and the session agent (Claude Opus 4.6) have seen the pilot results. This pre-registration therefore applies to:

1. Rating of the pilot results (predictions were stated qualitatively before seeing results, quantified here immediately after)
2. Any replication with larger N or additional models

The qualitative predictions (stated before seeing results):
- "At least half the outputs will be recognizably conventional metaphors in literary dress"
- "Treatment effect will be small and ambiguous"
- "No model will reliably produce Dickinson-quality metaphor"
- "Model differences will be larger than condition differences"
- "Opus will produce the most structurally novel outputs (weak prediction)"

These were stated in the session transcript before dispatch.

## Replication plan

A proper replication would:
- Use more topics (6-9) for better counterbalancing
- Run multiple samples per cell (e.g., 3 per cell = 54 total)
- Add additional models (Gemini, Haiku)
- Use blind rating (rater doesn't know condition or model)
- Add a human poet condition as calibration
