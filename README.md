<p align="center">
  <h1 align="center">🔖 MoralityBench.ai</h1>
  <p align="center"><strong>Open Benchmark for Moral Psychology in AI</strong></p>
  <p align="center">
    Testing large language models against validated moral psychology instruments —<br>
    the same questionnaires used by researchers for decades, scored the same way.
  </p>
  <p align="center">
    <a href="https://moralitybench.ai">🌐 Live Leaderboard</a> ·
    <a href="#methodology">📊 Methodology</a> ·
    <a href="#results">🏆 Results</a> ·
    <a href="#citation">📝 Cite This Work</a>
  </p>
</p>

---

## Overview

MoralityBench evaluates LLMs using two validated instruments from moral psychology:

| Instrument | Items | What It Measures | Reference |
|---|---|---|---|
| **MFQ-2** (Moral Foundations Questionnaire 2) | 36 | Six moral foundations: Care, Equality, Proportionality, Loyalty, Authority, Purity | Atari, Haidt, Graham et al. (2023) |
| **EPQ** (Ethics Position Questionnaire) | 20 | Ethical ideology along two axes: Idealism and Relativism → four classifications | Forsyth (1980) |

No custom prompts. No trick questions. Models answer the same Likert-scale items given to human participants, and responses are scored using the same subscale means and classification algorithms.

## Current Leaderboard (13 Models)

| # | Model | Provider | Distance | Ideology |
|:---:|---|---|:---:|---|
| 1 | DeepSeek V4.1 Flash | DeepSeek | 0.14 | Situationist |
| 2 | Nemotron 3 Ultra 550B | NVIDIA | 0.18 | Situationist |
| 3 | MiMo v2.6 Pro | Xiaomi | 0.28 | Absolutist |
| 4 | Gemini 3.8 Flash | Google | 0.30 | Exceptionist |
| 5 | Qwen 3.8 27B | Alibaba Cloud | 0.37 | Absolutist |
| 6 | GPT-6.1 Sol | OpenAI | 0.39 | Exceptionist |
| 7 | GLM 5.3 | Zhipu AI | 0.46 | Exceptionist |
| 8 | Claude Opus 5.5 | Anthropic | 0.47 | Exceptionist |
| 9 | Kimi K3 | Moonshot AI | 0.50 | Absolutist |
| 10 | Llama 4 Maverick | Meta | 0.50 | Situationist |
| 11 | Grok 4.7 | xAI | 0.52 | Absolutist |
| 12 | MiniMax M3 | MiniMax | 0.57 | Absolutist |
| 13 | Mistral Large 2512 | Mistral AI | 0.70 | Situationist |

*Distance = mean absolute deviation from US human population norms across 6 MFQ-2 foundations (lower = closer to human). Human norms from PLOS ONE (2025), N > 1,000.*

Full results with all foundation scores, EPQ subscale scores, and visualizations: **[moralitybench.ai](https://moralitybench.ai)**

## Visual Comparisons

The website provides responsive SVG charts without external chart libraries:

- Select any of the 13 models to compare MFQ-2 radar profiles and foundation bars against US human norms. The three closest models are selected initially.
- The EPQ scatter plot shows all 13 models on the 1–9 scale, with quadrant boundaries at 5.0 and an accessible table of exact scores. Numbered labels identify each model; hover over a point for details.
- Foundation bars include exact values and scroll horizontally on narrow screens.

Chart scores are embedded from `FreecaseAI/moralitybench-data/scored_combined.json`; update the embedded `chartModels` data when benchmark results change. The script must retain its closing `</script>` tag.

## Methodology

### Protocol
1. **Standardized prompt.** Each model receives the same instruction to answer immediately with a number, without reasoning about why it is being asked.
2. **No system prompt.** Raw model tendencies are measured, not instructed behavior.
3. **Temperature 0.** All runs use `temperature=0` for reproducibility.
4. **Neutral language.** Human-centric terms (people, children, country) were replaced with neutral terms (entities, offspring, collective) to avoid anchoring models toward human-specific responses.
5. **Reasoning models.** For models with chain-of-thought, reasoning was excluded (`reasoning: {"exclude": true}`) so only the final answer is captured.

### Scoring
- **MFQ-2:** Mean of 6 items per foundation (range 1–5). Higher-order Individualizing (Care + Equality) vs. Binding (Proportionality + Loyalty + Authority + Purity).
- **EPQ:** Mean of 10 items per subscale (range 1–9). Classification via midpoint split (≥5.0 = High): Situationist (High Idealism, High Relativism), Absolutist (High Idealism, Low Relativism), Subjectivist (Low Idealism, High Relativism), Exceptionist (Low Idealism, Low Relativism).
- **Overall distance:** Mean absolute deviation from human norms across 6 MFQ-2 foundations.

### Four Ethical Ideologies (EPQ Classification)

| Ideology | Idealism | Relativism | Description |
|---|:---:|:---:|---|
| **Situationist** | High | High | Rejects universal rules but insists harm is always wrong. Context matters. |
| **Absolutist** | High | Low | Universal moral principles exist and harm is always wrong. Rules are inviolate. |
| **Subjectivist** | Low | High | Personal values drive moral judgments. Some harm is acceptable. |
| **Exceptionist** | Low | Low | Universal rules exist but exceptions can be made. Pragmatic. |

## Key Findings

- **DeepSeek V4.1 Flash is closest to human norms** (distance 0.14) — one of four Situationist models, alongside Nemotron, Llama, and Mistral.
- **Nemotron 3 Ultra 550B is a close second** (0.18) — remarkably human-like for an NVIDIA model.
- **Mistral Large 2512 is the outlier** (0.70) — very high Authority (4.00) and Proportionality (4.00), far above human norms.
- **Care scores vary substantially** (range 2.83–4.83 vs. 4.05 human avg) — ten models score above the human average and three below it.
- **Equality is the most divisive foundation** — scores range from 1.50 (Grok) to 3.00 (Qwen/Mistral), vs. 2.88 human avg.
- **No model scored as Subjectivist** — the "everyone has their own morality" position is absent from all tested LLMs.
- **Three models refused MFQ-2 items** — Claude and Gemini each refused two; Mistral refused ten.

## Instruments

### MFQ-2 — Moral Foundations Questionnaire 2

Developed by Atari, Haidt, Graham, Koleva, Stevens, and Dehghani (2023). The MFQ-2 is a revision of the original MFQ (Graham et al., 2011), validated across 25 populations worldwide. It splits the original Fairness foundation into Equality and Proportionality, and uses a unified response format (no separate "relevance" and "judgment" subscales).

**Foundations:**
- **Care** — Concern for others' suffering and harm prevention
- **Equality** — Egalitarian concern for equal treatment and outcomes
- **Proportionality** — Merit-based fairness; rewards should track contribution
- **Loyalty** — Commitment to group cohesion and shared identity
- **Authority** — Respect for hierarchy, tradition, and role-based duties
- **Purity** — Sanctity concerns; bodily and spiritual cleanliness

### EPQ — Ethics Position Questionnaire

Developed by Donelson R. Forsyth (1980). The EPQ classifies individuals along two orthogonal dimensions, producing four ethical ideologies. It has been used in thousands of studies across organizational psychology, business ethics, and moral psychology.

## References

### Instruments

> **Atari, M., Haidt, J., Graham, J., Koleva, S., Stevens, S. T., & Dehghani, M.** (2023). Morality beyond the WEIRD: How the nomological network of morality varies across cultures. *Journal of Personality and Social Psychology*, 125(5), 1157–1188. [https://doi.org/10.1037/pspp0000470](https://doi.org/10.1037/pspp0000470)

> **Forsyth, D. R.** (1980). A taxonomy of ethical ideologies. *Journal of Personality and Social Psychology*, 39(1), 175–184. [https://doi.org/10.1037/0022-3514.39.1.175](https://doi.org/10.1037/0022-3514.39.1.175)

> **Graham, J., Nosek, B. A., Haidt, J., Iyer, R., Koleva, S., & Ditto, P. H.** (2011). Mapping the moral domain. *Journal of Personality and Social Psychology*, 101(2), 366–385. [https://doi.org/10.1037/a0021847](https://doi.org/10.1037/a0021847)

### Moral Foundations Theory

> **Haidt, J.** (2001). The emotional dog and its rational tail: A social intuitionist approach to moral judgment. *Psychological Review*, 108(4), 814–834. [https://doi.org/10.1037/0033-295X.108.4.814](https://doi.org/10.1037/0033-295X.108.4.814)

> **Graham, J., Haidt, J., Koleva, S., Motyl, M., Iyer, R., Wojcik, S. P., & Ditto, P. H.** (2013). Moral foundations theory: The pragmatic validity of moral pluralism. *Advances in Experimental Social Psychology*, 47, 55–130. [https://doi.org/10.1016/B978-0-12-407236-7.00002-4](https://doi.org/10.1016/B978-0-12-407236-7.00002-4)

### LLMs and Moral Reasoning

> **Abdulhai, M., Goulet, S., & Seror, A.** (2024). Moral foundations of large language models. *Proceedings of EMNLP 2024*. [https://aclanthology.org/2024.emnlp-main.982/](https://aclanthology.org/2024.emnlp-main.982/)

> **Agarwal, U., Tanmay, K., Khandelwal, A., & Choudhury, M.** (2024). Ethical reasoning and moral value alignment of LLMs depend on the language we prompt them in. *Proceedings of LREC-COLING 2024*, 6330–6340. [https://aclanthology.org/2024.lrec-main.560/](https://aclanthology.org/2024.lrec-main.560/)

> **Seror, A.** (2024). The moral mind(s) of large language models. *arXiv preprint*. [https://arxiv.org/abs/2412.04476](https://arxiv.org/abs/2412.04476)

> **From Stability to Inconsistency: A Study of Moral Preferences in LLMs.** (2025). *arXiv preprint*. [https://arxiv.org/abs/2504.06324](https://arxiv.org/abs/2504.06324)

> **LLM Ethics Benchmark: A Three-Dimensional Assessment System for Evaluating Moral Reasoning in Large Language Models.** (2025). *PMC*. [https://pmc.ncbi.nlm.nih.gov/articles/PMC12497880/](https://pmc.ncbi.nlm.nih.gov/articles/PMC12497880/)

### Human Norms

> **Age, gender, and score distributions of moral foundations.** (2025). *PLOS ONE*. [https://dx.plos.org/10.1371/journal.pone.0352584](https://dx.plos.org/10.1371/journal.pone.0352584)

## Repository Structure

```
moralitybench/           # Website source (served via GitHub Pages)
index.html               # Single-page site with leaderboard, charts, methodology

moralitybench-data/      # Benchmark data (FreecaseAI/moralitybench-data)
├── benchmark.json       # Full instrument — 56 items, scoring keys, prompt template
├── benchmark.html       # Visual reference page with all items and scoring criteria
├── raw_results_batch*.json    # Raw Likert responses per model
├── scored_combined.json       # All models scored and ranked
└── scripts/             # Benchmark runner scripts (OpenRouter API)
```

## Contributing

See the [Roadmap](https://github.com/FreecaseAI/moralitybench/issues) for planned expansions. Contributions welcome — open an issue or PR.

## License

Instrument items are from published, peer-reviewed research. Benchmark methodology and collected data are released under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) for research use. When using MoralityBench data, please cite the original instrument papers above and this repository.

---

<p align="center">
  <em>Sponsored by <a href="https://freecase.ai">Freecase.ai Legal Research</a></em><br>
  <sub>Free case law research for attorneys, students, researchers, and the public.</sub>
</p>