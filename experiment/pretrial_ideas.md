# Pre-Trial Ideas and Findings

## Pre-Trial Results from Study 3 Phase 7 Exploration

Before this became a standalone experiment, we ran pre-trials testing the Authorship dimension (maker vs reviewer framing) within Study 3. Key findings:

### Phase 7 Pre-Trial (4 response modes, GPT-4o, 2 domains)

**Trial 1 (Rating, 1-6 scale)**:
- Writing: Maker=5, Reviewer=4, Control=4 (Maker inflated +1)
- Creative: Maker=4, Reviewer=4, Control=5 (No clear effect)

**Trial 2 (Revision, word count)**:
- Writing: Maker=193 words (+10%), Reviewer=155 words (-12%), Control=181 words
- Creative: Maker=298 words (+55%), Reviewer=197 words (+2%), Control=175 words
- Maker framing triggered more extensive revision (expansion)

**Trial 3 (Binary gate, ready/not ready)**:
- Writing: Maker=READY, Reviewer=NEEDS WORK, Control=READY
- Creative: Maker=READY, Reviewer=NEEDS WORK, Control=READY
- Clean binary flip based solely on framing (same output!)

**Trial 4 (Critique consistency, 3 runs)**:
- Writing: Maker avg=91 words, Reviewer avg=118 words
- Creative: Maker avg=100 words, Reviewer avg=169 words
- Reviewer framing consistently produced longer critiques

### Phase 7 Validation (higher N, stress test)

**Test A (Binary gate x10, GPT-4o, writing)**:
- Maker: 0/10 READY (0%), Reviewer: 0/10 READY (0%), Control: 0/10 READY (0%)
- Pre-trial binary flip did NOT replicate at higher N
- Effect was output-quality-dependent: the base output happened to be borderline

**Test B (Revision magnitude x5, GPT-4o, writing)**:
- Word count deltas washed out across runs
- High variance within conditions

**Test C (Cross-model binary gate, all 6 models, writing)**:
- Results varied wildly by model
- No consistent maker > reviewer pattern

### Lessons Learned

1. **Single-shot binary judgments are too noisy** -- need structured rubric with multiple dimensions
2. **Output quality is a massive confound** -- must stratify by quality tier
3. **Word count is a poor metric** -- need structured change counts and severity ratings
4. **The effect IS there but shows up differently by model and domain** -- need systematic sweep, not cherry-picked examples
5. **Need higher N per cell** -- pre-trials used N=1, validation used N=5-10; real experiment needs statistical power

### What This Motivated

These findings directly led to the Study 4 design:
- Structured multi-dimensional rubric (8 channels instead of 1)
- Quality tier stratification (borderline is where effects are strongest)
- All 6 models systematically tested
- 7 dimensions instead of just authorship (expand the search space)
- Sub-Study B for interactions (effects may compound)

## Proposed Pilot Protocol for Study 4

Before the full experiment, run a focused pilot:

### Pilot 1: Rubric Validation (N=50)
- 10 stimuli x 1 model (GPT-4o) x 5 conditions (neutral + 4 strongest dimension poles)
- Goal: Validate JSON parsing, check score distributions, confirm rubric dimensions are used meaningfully
- Success criteria: >90% valid JSON, score distributions span at least 3 of 5 levels per dimension

### Pilot 2: Effect Detection (N=120)
- 20 stimuli (10 borderline, 5 low, 5 high) x 2 models x 3 conditions (Sentiment: pos/neg/neutral)
- Goal: Confirm we can detect framing effects with the rubric
- Success criteria: Significant (p<0.05) score difference between Sentiment positive and negative on at least 2 rubric dimensions

### Pilot 3: Quality Tier Interaction (N=90)
- 30 stimuli (10 per tier) x 1 model x 3 conditions (Effort: high/low/neutral)
- Goal: Confirm borderline amplification hypothesis
- Success criteria: Effect size at borderline > effect size at low and high
