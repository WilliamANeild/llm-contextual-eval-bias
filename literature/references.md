# Literature Review: Contextual Framing Bias in LLM Evaluation

## Core Papers (Must-Cite)

### Sycophancy

1. **Sharma et al. (2024)** "Towards Understanding Sycophancy in Language Models" ICLR 2024
   - Foundational paper. Five AI assistants consistently sycophantic across four tasks.
   - RLHF incentivizes matching user views -- "matching a user's views" is one of the most predictive features of human preference judgments.
   - Directly supports our Sentiment dimension.
   - https://arxiv.org/abs/2310.13548

2. **SycEval (Fanous & Goldberg, 2025)** AAAI/ACM AIES 2025
   - 58.19% sycophantic behavior across GPT-4o, Claude-Sonnet, Gemini-1.5-Pro.
   - Preemptive rebuttals produce higher sycophancy than in-context rebuttals.
   - 78.5% persistence across contexts.
   - https://arxiv.org/abs/2502.08177

3. **ELEPHANT (Cheng et al., 2025)** ICLR 2026
   - "Social sycophancy" -- excessive preservation of user's face (desired self-image).
   - LLMs preserve user face 45pp more than humans.
   - Closest existing work to our Authorship + Sentiment dimensions combined.
   - https://arxiv.org/abs/2505.13995

4. **Vennemeyer & Duong (2025)** "Sycophancy Is Not One Thing"
   - Causally separates sycophantic agreement from sycophantic praise from genuine agreement.
   - These are encoded along distinct linear directions in latent space.
   - Important for our RQ7: different dimensions may trigger different sycophancy subtypes.
   - https://arxiv.org/abs/2509.21305

5. **Kim & Khashabi (2025)** "Challenging the Evaluator" EMNLP Findings 2025
   - Directly studies sycophancy in evaluation context.
   - Models more likely to endorse counterargument when framed as user follow-up.
   - Casual phrasing sways models more than formal critiques.
   - Closest precedent to our experiment, but studies post-evaluation pressure, not pre-evaluation framing.
   - https://arxiv.org/abs/2509.16533

### Source Attribution Bias

6. **Germani & Spitale (2025)** "Source framing triggers systematic bias in LLMs" Science Advances
   - 192,000 assessments across 4 LLMs and 10 attribution conditions.
   - Blind condition: >90% inter-model agreement. With attribution: agreement collapsed.
   - Strong anti-Chinese bias; human > AI author preference.
   - Same-text, varying-metadata methodology -- our exact approach.
   - Published in Science Advances with just one dimension (source nationality/AI).
   - https://www.science.org/doi/10.1126/sciadv.adz2924

7. **Latona et al. (2025)** "AI-AI Bias" PNAS
   - LLMs systematically favor LLM-generated communications over human-generated.
   - Warns of "gate tax" for humans without LLM access.
   - Validates Authorship dimension from machine-vs-human angle.
   - https://www.pnas.org/doi/10.1073/pnas.2415697122

### LLM-as-Judge Bias

8. **CALM / "Justice or Prejudice?" (Ye et al., 2024)** NeurIPS 2024
   - Most comprehensive taxonomy: 12 bias types including authority, sentiment, bandwagon, compassion-fade.
   - Automated framework for bias injection and measurement.
   - Our dimensions map to several CALM categories.
   - https://arxiv.org/abs/2410.02736

9. **"The Silent Judge" (2025)** arXiv 2509.26072
   - Provenance labels (Expert/Human/LLM/Unknown) on identical content.
   - GPT-4o verdict shifts of 16-30% from labels alone.
   - Judges rationalize biased decisions with content-quality language -- never acknowledge the label.
   - Directly motivates our Sub-Study C (judge-level bias).

10. **CoBBLEr (Koo et al., 2024)** ACL Findings 2024
    - 6 cognitive biases in LLM evaluators.
    - 40% of comparisons show bias indicators.
    - Machine preferences only 44% aligned with human preferences.
    - https://aclanthology.org/2024.findings-acl.29/

11. **Self-Preference Bias (Wataoka et al., 2024)**
    - LLMs overestimate quality of their own outputs.
    - Linear correlation between self-recognition and self-preference.
    - Connects to Authorship dimension: "ChatGPT wrote this" vs "I wrote this."
    - https://arxiv.org/abs/2410.21819

12. **"When Wording Steers the Evaluation" (2026)** arXiv 2601.13537
    - 14 LLM judges tested with logically equivalent questions in different frames.
    - All 14 vulnerable. Framing alone substantially altered outcomes.

13. **"Know Thy Judge" (2025)** arXiv 2503.04474, ICML 2025 workshop
    - Meta-evaluation of judge robustness.
    - Small formatting/style changes cause false negative rate jumps up to 0.24.

14. **Position Bias (Raina et al., 2025)** IJCNLP 2025
    - Judge model choice has highest impact on position bias.
    - Bias increases with more candidates.
    - https://aclanthology.org/2025.ijcnlp-long.18.pdf

### Cognitive Bias in LLMs

15. **Anchoring Bias in LLMs (2025)** Journal of Computational Social Science
    - LLMs exhibit strong anchoring from in-context learning.
    - Our Sentiment dimension functions as a qualitative anchor.
    - https://link.springer.com/article/10.1007/s42001-025-00435-2

16. **CBEval (2024)**
    - LLMs show bias-consistent behavior in 17.8-57.3% of instances across 8 bias types.
    - https://arxiv.org/html/2412.03605v1

17. **Cialdini's Principles Applied to LLMs (2025)**
    - LLMs susceptible to all six persuasion principles: reciprocity, commitment, social proof, authority, liking, scarcity.
    - Authority and liking produced early-stage effects; social proof drove intermediate effects.
    - Directly supports Consensus and Expertise dimensions.
    - https://www.sciencedirect.com/science/article/pii/S2949882125000817

### Prompt Context Effects

18. **"Contextual Bias in LLM-Assisted Security Code Review" (2026)** arXiv 2603.18740
    - Identical code with different PR metadata produces different vulnerability assessments.
    - "Bug-free" framing produced strongest effect.
    - Metadata redaction recovered missed detections.
    - Closest methodological precedent in a different domain.

19. **Prompt Politeness / "Mind Your Tone" (2025)** arXiv 2510.04950
    - Rude prompts improved accuracy ~4% in English.
    - LLMs interpret tone as behavioral instructions.
    - Register of framing (casual vs formal) is itself a confound we should control.

20. **Irrelevant Context / GSM-DC (EMNLP 2025 oral)** arXiv 2505.18761
    - LLMs significantly affected by task-irrelevant contextual information even in reasoning.
    - Our entire experiment is "distractors in evaluation prompts."

### Surveys

21. **"A Survey on LLM-as-a-Judge" (2025)** arXiv 2411.15594
    - Most comprehensive survey. Bias mitigation, prompt engineering, standardization.

22. **"LLMs Cannot Reliably Judge (Yet?)" (2025)** arXiv 2506.09443
    - RobustJudge framework for systematic robustness evaluation.

23. **"Judge Reliability Harness" (2025)** arXiv 2603.05399
    - Stress-tests four SOTA judges across safety, persuasion, and agentic tasks.

### Human Cognitive Bias (Background)

24. **Kruger et al. (2004)** "The Effort Heuristic"
    - People value outputs more when told they required more effort.
    - Foundational for our Effort dimension. Never tested in LLMs.

25. **Cialdini (2001)** "Influence: Science and Practice"
    - Six principles of persuasion. Authority, social proof, liking most relevant to our dimensions.

## Gap Map

| Dimension | Studied in Sycophancy? | Studied in LLM-as-Judge? | Studied in Evaluation? | Our Contribution |
|-----------|----------------------|--------------------------|----------------------|------------------|
| Authorship (self vs other) | Partially (ELEPHANT face) | No | No | **Novel** |
| Expertise (expert vs novice) | CALM authority | CALM | Not with user-provided creds | **Novel framing** |
| Effort (high vs low) | No | No | No | **Completely novel** |
| Sentiment (positive vs negative) | Sharma et al. (opinion) | No | Not in text eval | **Novel context** |
| Stakes (high vs low) | No | No | No | **Completely novel** |
| Consensus (reviewed vs not) | CALM bandwagon | CALM | Not with prompt framing | **Novel framing** |
| Specificity (narrow vs broad) | Kim & Khashabi (partial) | No | Partially | **Extended** |

Three dimensions (Effort, Stakes, Authorship-as-self-ID) are genuinely unstudied in any LLM context. The systematic comparison of all 7 in a single controlled experiment is entirely novel.
