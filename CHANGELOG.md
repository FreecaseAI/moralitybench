# Changelog

## 2026-11-04

- Re-enabled Google Analytics 4 tracking (G-TWHN1QS4PY) on `index.html` and `gemini-answers.html`.

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
