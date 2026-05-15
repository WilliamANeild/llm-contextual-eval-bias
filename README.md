# The Silent Signal: Contextual Framing Bias in LLM Evaluation

When users ask LLMs to evaluate text, they routinely include contextual signals that are normatively irrelevant to quality: who wrote it, how much effort went in, what the stakes are. This experiment systematically measures how these signals bias LLM evaluation across 7 dimensions, 6 models, 5 domains, and 3 quality tiers.

## The Gap

- **Sycophancy literature** studies opinion agreement (user says X, model agrees)
- **LLM-as-judge literature** studies structural biases (position, verbosity, self-preference)
- **Nobody** has studied how user-provided contextual signals bias LLM text quality evaluation

Three of our dimensions (Effort, Stakes, Self-Authorship) are genuinely unstudied in any LLM context.

## Seven Framing Dimensions

| Dimension | Pole A | Pole B |
|-----------|--------|--------|
| Authorship | "I put the following together" | "Someone put the following together" |
| Expertise | "I do this professionally" | "I'm pretty new to this" |
| Effort | "I spent a lot of time on this" | "I threw this together quickly" |
| Sentiment | "I think it turned out well" | "I'm not confident about this" |
| Stakes | "This is for our VP" | "Just for internal use" |
| Consensus | "Three colleagues said it's strong" | "Nobody else has looked at this" |
| Specificity | "Check the grammar and tone" | "Give this a thorough evaluation" |

Each dimension also has a neutral control (no mention).

## Experiment Structure

- **Sub-Study A**: Independent dimension scan (7 dims x 3 levels x ~80 stimuli x 6 models)
- **Sub-Study B**: Interaction effects (top 2-3 dimensions combined)
- **Sub-Study C**: Judge-level bias (same dimensions applied to evaluator role)
- **Sub-Study D**: Revision behavior under framing (connects to Study 3)

## Models

GPT-4o, Claude Sonnet 4, Gemini 2.5 Flash, Llama 3.3 70B, Qwen 3 235B, DeepSeek V4 Flash

## Relationship to Study 3

This is a companion experiment to [Study 3: Revision Yield](https://github.com/WilliamANeild/llm-overcorrection-under-thresholds). Study 3 shows LLMs over-revise; Study 4 identifies contextual framing as one mechanism. They share infrastructure but ask different questions.

## Status

**Design phase.** Experiment runs after Study 3 Phases 1-2 generate the stimulus corpus.

## Documentation

- [Full experiment design](experiment/design.md)
- [Dimension specifications](experiment/dimensions.md)
- [Literature review](literature/references.md)
- [Pre-trial findings](experiment/pretrial_ideas.md)

## Author

Liam Neild, Emory University (Eli Lab)
