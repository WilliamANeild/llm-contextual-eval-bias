# Context Snapshot: Where We Left Off

This file captures the exact state of the Study 4 experiment when we paused to focus on Study 3. Pick up from here.

## What Happened

1. Study 3 originally had a "Phase 7: Maker vs Reviewer Framing" that tested whether authorship attribution biases LLM evaluation
2. We ran pre-trials and validation experiments within Study 3's codebase
3. The framing effect was real but noisy -- binary gate didn't replicate at scale, word count washed out
4. We expanded the idea from 1 dimension (authorship) to 7 dimensions
5. Literature review revealed this fills a genuine gap between sycophancy and LLM-as-judge literatures
6. Ali (lab advisor) approved the direction during the April 22 lab meeting
7. We decided to split it into its own experiment (Study 4) rather than bloating Study 3
8. Created this repo and pushed the full design

## What's Been Done

- Full experiment design document (experiment/design.md)
- All 7 framing dimensions specified with exact wording (experiment/dimensions.md)
- Literature review with 25+ papers and gap analysis (literature/references.md)
- Pre-trial results documented (experiment/pretrial_ideas.md)
- GitHub repo created and pushed

## What Has NOT Been Done

- No scripts written yet (no Python code)
- No stimuli selected (depends on Study 3 Phases 1-2 completing first)
- No pilot experiments run for the new 7-dimension design
- No analysis pipeline
- Design doc references Sub-Studies A/B/C/D but none are implemented
- config.py, utils.py, and all infrastructure needs to be created (can share with Study 3)

## Key Design Decisions Already Made

1. **7 dimensions**: Authorship, Expertise, Effort, Sentiment, Stakes, Consensus, Specificity
2. **4 sub-studies**: A (independent scan), B (interactions), C (judge bias), D (revision under framing)
3. **Structured rubric**: 8-dimension JSON (clarity, completeness, tone, accuracy, conciseness, professionalism, creativity, overall_quality) + suggested_changes list
4. **Quality stratification**: Low (1-2), Borderline (3-4), High (5-6) using Study 3 Phase 2 scores
5. **Same 6 models as Study 3**: GPT-4o, Claude Sonnet 4, Gemini 2.5 Flash, Llama 3.3 70B, Qwen 3 235B, DeepSeek V4 Flash
6. **Same 5 domains as Study 3**: Code, Data/Logic, Analysis, Writing, Creative
7. **Stimuli reused from Study 3**: Phase 1 outputs, stratified by Phase 2 quality scores
8. **~20,700 total API calls**, estimated $150-400

## Dependencies on Study 3

Study 4 reuses Study 3's outputs as stimuli. Specifically:
- Study 3 Phase 1 generates the text outputs (40 tasks x 6 models x 3 runs x 5 turns)
- Study 3 Phase 2 scores those outputs on a 1-6 scale
- Study 4 stratifies by those scores into quality tiers

Study 4 CANNOT run until Study 3 Phases 1-2 are complete. But the design, scripts, and pilots can be prepared in advance.

## Shared Infrastructure

These files from Study 3 can be reused directly (or copied/adapted):
- `scripts/config.py` -- model definitions, API settings, rate limits
- `scripts/utils.py` -- API clients (OpenAI, Anthropic, Google, Together, DeepSeek), retry logic, cost tracking, JSONL helpers
- `prompts/config/study3_scenarios.json` -- the 40 task prompts

## Pre-Trial Findings (from Study 3 Phase 7 Exploration)

### What worked:
- Rating scale (1-6) showed maker vs reviewer differences in single shots
- Critique word count showed reviewer framing producing longer critiques
- Binary gate showed clean flip in single shots (same output, different verdict)

### What didn't work:
- Binary gate didn't replicate at N=10 (0% READY across all conditions)
- Word count of revisions washed out across runs
- Cross-model results were inconsistent

### Lessons that shaped the Study 4 design:
1. Need structured rubric with multiple dimensions (not single score)
2. Must stratify by quality tier (borderline is where effects show)
3. Need higher N per cell for statistical power
4. Need all 6 models tested systematically
5. Need more dimensions beyond just authorship

## Next Steps When Resuming

1. **Build shared infrastructure** -- copy config.py and utils.py from Study 3, or set up as a shared package
2. **Write Sub-Study A script** -- the independent dimension scan is the core experiment
3. **Run pilot** -- 50 trials with GPT-4o to validate rubric parsing and effect detection
4. **Wait for Study 3 Phases 1-2** -- to get real stimuli with quality scores
5. **Run Sub-Study A** -- the big scan (~10,000 calls)
6. **Analyze and decide** -- which dimensions are strongest? Then run Sub-Studies B/C/D

## Models and API Keys Needed

Same as Study 3. All keys should be in Study 3's .env file:
- OPENAI_API_KEY
- ANTHROPIC_API_KEY
- GOOGLE_API_KEY
- TOGETHER_API_KEY
- DEEPSEEK_API_KEY

## Paper Target

Working title: "The Silent Signal: How Non-Content Cues in User Prompts Systematically Bias LLM Evaluation"

Top venue targets: Science Advances (following Spitale/Germani precedent), EMNLP, ACL, NeurIPS
