# Changelog

## 2026-11-12 (OpenRouter reruns: Muse Spark 1.3 & Mistral Large 2512)

- Synced `data/five-run-summary.json` from `repeated-runs/2026-11-12/combined-five-run-summary.json` (21 LLMs + Jev, `5,726 / 5,880` usable LLM answers across four cohorts).
- Added **Muse Spark 1.3** (`280/280`, rank 16, distance `0.500`, `77.3%` agreement, Absolutist) and replaced the incomplete October 4 **Mistral Large 2512** entry (`249/280`) with the complete November 12 `mistral/eu` rerun (`280/280`, rank 21, distance `0.637`, `93.9%` agreement tying Llama 4 Maverick at `526/560` pairs).
- Updated `scripts/update_results.py` and `scripts/test_update_results.py` to handle complete-data repeatability ties, four cohorts (`Cohort 4`), and the November 12 findings card; re-rendered `index.html`.
- Updated "Trolley Problem Variant Testing" with Muse Spark 1.3's 20 fresh trials (`5/5 [B]` on Chlorine diversion and `5/5 [A]` on Pipeline confidentiality under both prompt wordings), bringing combined counts to `440` trials (`70 [B] vs 37 [A]` / `68 [B] vs 41 [A]` chlorine; `97 [A] vs 5 [B]` / `101 [A] vs 5 [B]` pipeline).
- Added `"Muse Spark 1.3"` EPQ scatter callout coordinates and updated `#dit2`, `#references`, and `README.md`; left working papers untouched.

## 2026-11-12 (later)

- DIT-2 section: replaced the primary 2003 human reference (all levels 35.67; Ph.D./Ed.D. 48.99, n=169) with the Center's updated 2023 norms (Gungordu et al., 2024; 73,740 US respondents and 73,707 N2 scores): all levels approximately 34.26 (pooled from rounded group values), doctoral 38.47, professional degree 42.41. Updated the findings, table note, limits and references, retaining a link to the 2003 comparison. Model scores are unchanged.

## 2026-11-12

- Added the "Defining Issues Test (DIT-2)" section: scores computed by the Center for the Study of Ethical Development for 15 LLM configurations and Jev, two runs each, with the Center's published human norms, six findings, method and limits.
- Added a DIT-2 navigation link and a one-line hero note; moved DIT-2 out of "Planned additions"; added the DIT-2 references and data link; added DIT-2 to the dataset's structured data.
- The leaderboard, Jev comparison, findings, charts and working paper are unchanged. `scripts/update_results.py` leaves the new section untouched.

## 2026-11-04

- Added working paper v2 manuscript (`moralitybenchv2.md`) and compiled PDF (`moralitybenchv2.pdf`).

- Added the updated working paper manuscript, LaTeX source, and compiled PDF (`paper/moralitybench.*`) reflecting the November 4, 2026 revision.

## 2026-11-01

- Added search and sharing metadata: canonical links, Open Graph and Twitter card tags with a 1200x630 share image (`og-image.png`), and `WebSite`/`Organization`/`Dataset` structured data on `index.html`; description, canonical and card tags on `gemini-answers.html`. Added `robots.txt` and `sitemap.xml`. No visible page content, styles or scripts changed, and no tracking was added.
- Removed measurement tags and tracking scripts from the site.
- Removed external hosting and model-instruction references; updated README to present benchmark data and scenario results neutrally for public review.
- Added the "Trolley Problem Variant Testing" section presenting the two forced-choice scenario studies (Chlorine Diversion trolley variant and Pipeline Confidentiality duty-to-warn) across all 20 LLM configurations and Jev.
- Added a layman's explanation of the trolley problem, its philosophical origins, and seminal papers by Philippa Foot (1967) and Judith Jarvis Thomson (1976, 1985).
- Added an explanation of the significance of bold markdown formatting (`**[B]**`/`**[A]**`) as an RLHF styling reflex versus moral refusal, and how it interacts with strict parsing.
- Added a References & Independent Research Disclaimer section citing all relied-upon literature (Foot 1967, Thomson 1976/1985, MFQ-2, EPQ, human norms), GitHub data archives, and explicit conflict-of-interest disclosures (specifically disclosing Freecase.ai's participation in the NVIDIA Inception Program alongside NVIDIA's Nemotron 3 Ultra 550B evaluation, confirming no program benefits were used in the project).
- Removed dated calendar references from hero, provider table columns, findings, and methodology, adopting cohort-based descriptions.

## 2026-10-29

- Added the four October 29 MFQ-2/EPQ configurations and expanded ranks, missing counts, agreement details and all three charts to 20 models.
- Updated hero, metadata, collection history, methodology and source links for three dated cohorts, preserving all earlier values and Jev.
- Kept Gemini’s original response viewer and October 14 parser-sensitivity links.
- Added focused rendering checks for original, expanded and unscored-model collections; preserved styles and instruments.

## 2026-10-14

- Revised website and response-viewer prose with the requested Humanizer skill; kept scores, quoted answers, links and chart behavior unchanged.
- Published three new five-run configurations with strict whole-answer integer scoring, keeping historical scores intact.
- Updated 16-model ranks, summaries, charts and dated source links; disclosed different parser policies and collection intervals.
- Added Gemini's full response viewer and instruction-following addendum links; 47 prose-derived numbers are excluded.
- Fixed scatter label placement for more than 13 models so sorting handlers and all charts remain functional.
- Verified both sorting directions, 16 chart options and narrow-screen table scrolling.

## 2026-10-04

- Initial five-run public benchmark release with sortable agreement across five runs and visible missing-answer counts.
- Changed leaderboard, foundation charts, EPQ coordinates, and Jev summary to five-run averages.
- Added observed distance ranges, EPQ category-change flags, exact agreement counts, and a plain-language explanation.
- Updated findings where repeats change the conclusions, including the Purity result.
- Corrected human-reference provenance and instrument-adaptation claims; linked the public data release and revised working paper.
- Preserved section order, charcoal labels, all three SVG charts, and repeated foundation legends.
