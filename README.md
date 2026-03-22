# Linear A — A Computational Study

**What this is:** a computational investigation of the Minoan Linear A script — corpus tooling, statistical tests, a structural analysis of the libation formula, and a *working hypothesis* about the language family.

**What this is not:** a solved decipherment. **Linear A remains officially undeciphered.** Nothing here is peer-reviewed or accepted by the field, and the headline metrics produced by the scripts (e.g. a 93.6% model posterior) overstate the real confidence — see the caveats below.

If you take away one thing: this is a serious, well-controlled *attempt*, presented honestly about its limits.

---

## Honest status

| Claim | Confidence | Notes |
|---|---|---|
| Functional meaning of administrative texts (lists, totals, allocations) | **85–95%** | Rests on universal accounting structure + decoded numbers + known ideograms — does **not** require knowing the language. |
| Structural grammar (case system, agreement) | **65–75%** | Derived from variant analysis of the libation formula. |
| Libation-formula structure (who / what / to-whom / verb) | **75–85%** | Strong positional data from the attested variants. |
| Specific confirmed words (KU-RO, PA-I-TO, …) | **90%+** | Confirmed via Linear B and context. |
| **Language family = Hurro-Urartian** | **40–55%** | **Best-fit lean, not proven.** The most internally consistent of four candidates (Hurrian, Luwian, Semitic, Tyrrhenian) — but unproven. |
| Full word-for-word linguistic translation | **15–25%** | We can describe what most texts *do*; we cannot reliably read every word. |
| **Dictionary-confirmed translation rate** | **~21%** | See `TOTAL_TRANSLATION.txt`. 164 dictionary matches; ~752 of 990 word groups are hapax (mostly personal names); the rest are decomposition *attempts*, not verified translations. |

> ⚠️ **Read the numbers carefully.** Earlier framing of this project as "96.4% complete" counted *decomposition attempts*, not verified translations. The honest, dictionary-confirmed rate is **~21%** (`TOTAL_TRANSLATION.txt`). Likewise the **93.6%** figure from `LINEAR_A_CROSS_DOMAIN_CONVERGENCE.py` is a *model posterior*, not a probability of being correct — it overstates confidence because the evidence "domains" are not fully independent (see caveats). The honest confidence in the Hurro-Urartian hypothesis is **~40–55%**.

---

## Method

1. **Corpus tooling** — Python scripts over digitized Linear A data (GORILA and SigLA databases) to search, cross-reference, and organize the corpus (`FULL_CORPUS_SEARCH.py`, `LinearAInscriptions.js`, `CORPUS_ALL_TABLETS.txt`).
2. **Administrative / structural analysis** — Minoan accounting tablets follow the same header → item-quantity → total structure as Sumerian, Egyptian, and Linear B bureaucracies. This yields *functional* translation of the administrative corpus **without** linguistic decipherment.
3. **Libation-formula analysis** — the formula (`A-TA-I-*301-WA-JA …`) is the richest linguistic evidence. ~41 variants are attested across 27 sites; the scripts here computationally test a **7-variant well-preserved subset** to derive a 6-position structure and grammatical agreement rules.
4. **Statistical controls** (`LINEAR_A_STATISTICAL_CONTROLS.py`) — baseline-vs-competing-families, ablation, permutation/bootstrap, lexical chance-match, and sign-reading perturbation.
5. **Cross-domain convergence** (`LINEAR_A_CROSS_DOMAIN_CONVERGENCE.py`) — combines linguistic, archaeogenetic, trade, material-culture, religious, chronological, competing-family, and pre-Greek-substrate evidence into a Bayesian posterior.

The hypothesis builds on **P. G. van Soesbergen's** Hurrian model (2016/2017).

---

## The `*301` sign

`*301` is a pivotal Linear-A-only sign that the Linear B overlap does **not** cover. **This project does not assign it a syllabic value.** Distributionally it patterns like a commodity ideogram (likely **honey/mead**) in administrative/sealing contexts (~289 tokens, mostly on sealings), and its role *inside the libation formula* is left **unresolved**. We do not read it as a syllable.

*(A separate, contemporaneous effort — Tom Di Mino's Semitic / proto-Hebrew hypothesis — instead reads `*301` as the syllable "na". We do not, and we reach a different language family. Both are unproven.)*

---

## Key caveats (what a critic should know up front)

- **Not a decipherment.** Linear A is undeciphered; this is a hypothesis-generation and testing exercise.
- **The 93.6% posterior overstates confidence.** Its evidence "domains" are not fully independent — at minimum the linguistic-fit, competing-families, and pre-Greek-substrate scores all rest on the same hand-coded feature profile, and multiplying correlated evidence inflates the result. Loanwords from trade contact are not proof of genetic relationship.
- **No bilingual text exists.** The family question (Hurrian / Luwian / Semitic / Tyrrhenian, or a true isolate) cannot be settled without one.
- **Not peer-reviewed.** No external academic review has been undertaken.
- **Scope of the lexicon:** the proposed Minoan→English dictionary is **46 words/morphemes** (`LINEAR_A_COMPLETE_TRANSLATION_OUTPUT.txt`), tiered by confidence.

---

## Files

- `LINEAR_A_TRANSLATION_ATTEMPT.md` — the main analysis write-up (confidence-tagged throughout).
- `LINEAR_A_STRUCTURAL_ANALYSIS.py` — libation-formula structure, entropy, agreement rules.
- `LINEAR_A_STATISTICAL_CONTROLS.py` — baselines, ablation, permutation, perturbation.
- `LINEAR_A_CROSS_DOMAIN_CONVERGENCE.py` — the Bayesian convergence model (read its caveat).
- `LINEAR_A_PHONOLOGICAL_ANALYSIS.py`, `LINEAR_A_HURRIAN_COMPARISON.py`, `LINEAR_A_ENHANCED_COMPARISON.py` — comparative analyses.
- `LINEAR_A_COMPLETE_TRANSLATION.py` / `TRANSLATE_ALL.py` — the translation engine and bulk run.
- `UNDECIPHERED_SIGNS_CRACKED.txt` — distributional re-classification of high-frequency "undeciphered" signs as commodity/admin markers.
- `TOTAL_TRANSLATION.txt` — the honest translation-rate report (~21%).
- `COMPLETE_WORD_LIST.txt`, `CORPUS_ALL_TABLETS.txt`, `COMPLETE_CORPUS_REFERENCE.txt` — corpus data.

## Sources

- SigLA Database — Salgarella & Castellan (2020), sigla.phis.me
- GORILA Corpus — Godart & Olivier (1976–1985)
- Younger, J. G. — Linear A Texts in Phonetic Transcription (ku.edu)
- Van Soesbergen, P. G. (2016/2017) — Hurrian hypothesis
- Corazza, Montecchi, Valério, Tamburini (2020) — Linear A fraction-sign values
- Davis, B. — statistical/phonotactic analysis of Linear A
- Beekes — Pre-Greek substrate
