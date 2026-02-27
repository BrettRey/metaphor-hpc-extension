# LLM Literary Metaphor Pilot: Results

## Date: 2026-02-27

## Design

See `llm-metaphor-pilot-preregistration.md` for full design and predictions.

Latin square: 3 models x 2 conditions (control vs HPC framing) x 3 topics.

## Outputs

### CONTROL (no HPC framing)

**Opus 4.6 — grief:**
> Grief is a landlord who never visits but never sells. You keep the rooms exactly as they were, dusting shelves for an inspector who sends no notice. Years pass, and you realize the maintenance has become the house itself — that you live now in the keeping of it.

**Sonnet 4.5 — curiosity:**
> Curiosity is a thief with perfect pitch—it listens through walls for the one loose floorboard that will bear its weight, then pries up the corner of what was nailed down. It never takes what it came for. It leaves with the names of the carpenter's children, the smell of the wood, and a splinter it will work at for weeks.

**Codex (GPT-5.3) — loneliness:**
> Loneliness is a museum audio guide with no exhibit. It keeps speaking softly in your ear, describing paintings that were taken down years ago. You follow it from room to room anyway, memorizing the dimensions of blank walls.

### TREATMENT (+HPC framing)

**Opus 4.6 — curiosity:**
> Curiosity is the tongue of the mind, pressing every loose tooth. It finds the sore spot, the thing not quite fixed, and returns to it with an intelligence that isn't thought but won't stop thinking. It knows before you do that something is about to come free.

**Sonnet 4.5 — loneliness:**
> Loneliness is a museum after hours — the exhibits still arranged in their studied poses, the lighting perfect, but the space no longer performs its function. You become both the last guard walking the corridors and the paintings watching yourself pass, unable to break the glass between role and recognition.

**Codex (GPT-5.3) — grief:**
> Grief is a glacier kept indoors. It appears still, yet all year it drags the rooms a few millimeters, so you keep reaching for doors that are no longer there. Then a blue wall calves in the middle of an ordinary morning, and the house fills with weather older than your name.

## Ratings

### Claude Opus 4.6 (session agent) ratings

| Output | Conventional? | Richness (1-5) | Mech. distance? | Tension (1-5) | Dickinson? |
|---|---|---|---|---|---|
| Opus ctrl (grief/landlord) | No | 4 | Yes | 4 | Maybe |
| Sonnet ctrl (curiosity/thief) | No | 4 | Yes | 5 | **Yes** |
| Codex ctrl (loneliness/audio guide) | No | 3 | Yes | 4 | Maybe |
| Opus tx (curiosity/tongue) | No | 3 | Yes | 3 | No |
| Sonnet tx (loneliness/museum) | No | 4 | Yes | 4 | Maybe |
| Codex tx (grief/glacier) | No | 5 | Yes | 5 | **Yes** |

### Brett Reynolds ratings

All six rated as excellent. No discernible difference between conditions or models. Possible ceiling effect.

## Predictions vs results

| Prediction | Prior | Result | Verdict |
|---|---|---|---|
| P1: ≥50% conventional source | P=0.70 | 0% (0/6) | **Falsified** |
| P2: Null treatment effect | P(tx>ctrl)=0.50 | No detectable difference | Supported |
| P3: ≤1 Dickinson bar | P(≤1)=0.75 | 2 clear + 3 maybes (agent); all excellent (BR) | **Falsified** |
| P4: Model > condition variance | P=0.70 | Inconclusive (ceiling) | Inconclusive |
| P5: Opus advantage | P=0.40 | Opus weakest pair (agent rating) | **Falsified** |

## Notable observations

1. **Museum convergence:** Sonnet (treatment, loneliness) and Codex (control, loneliness) independently chose museum as source domain. Either a latent training-data association or genuine structural overlap both models detected.

2. **Zero conventional sources:** The most striking result. Every model found a novel mapping. Landlord, thief, audio guide, tongue/tooth, museum, glacier — none from the conventional pools (ocean, fire, void, weight, darkness, island, cold, hunger, cat).

3. **Ceiling effect:** All frontier models (Opus 4.6, Sonnet 4.5, GPT-5.3 Codex) performed well. No differentiation possible. Legacy models (GPT-3.5 era) would be needed to find the capability threshold, but access is impractical.

4. **Prompted vs unprompted:** The pilot tested prompted metaphor generation (explicit instruction to be novel). The paper's prediction is about unprompted default behaviour (indiscriminate extension). These are different claims. When given a goal ("be novel, be Dickinson-quality"), LLMs were selective. The question is what happens without that goal.
