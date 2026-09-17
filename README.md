# Democratic Resilience Instrument (DRI)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22810037.svg)](https://doi.org/10.5281/zenodo.22810037)
[![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/)

**A shared measurement instrument for evaluating whether civic technology actually strengthens democratic resilience.**

Civic technology initiatives claim to strengthen democratic resilience. The field has no shared way to check. The DRI operationalises democratic resilience — society's capacity to recover from challenges to, and promote renewal in, democratic systems — into twenty items across four dimensions, measured at the level of citizens.

> [!NOTE]
> **This page is a summary. The working paper is the citable source of record.**
>
> The paper — with the full argument, the complete reference list and the annex on theoretical sources — is published on Zenodo: **[doi.org/10.5281/zenodo.22810037](https://doi.org/10.5281/zenodo.22810037)**
>
> This repository holds the working parts: the item bank and the methodology files. Cite the paper; use the repository.

---

## What's in this repository

| Path | What's in it |
|---|---|
| [`instrument/`](instrument/) | The twenty items, in Forms A and B, at national and EU level — one file per dimension |
| [`methodology/`](methodology/) | How the instrument is administered, scored and validated — four files, listed below |
| [`CONTRIBUTING.md`](CONTRIBUTING.md) | How to propose a change to item wording, scoring or scope |
| [`CHANGELOG.md`](CHANGELOG.md) | Every change to the instrument, by version |
| [`LICENSE.md`](LICENSE.md) | CC BY 4.0 |

**The four methodology files**

- [`administration-and-validation.md`](methodology/administration-and-validation.md) — how items are administered and validated. Binding on anyone fielding the DRI
- [`scale-standardisation.md`](methodology/scale-standardisation.md) — scaling and composite construction
- [`bias-mitigation.md`](methodology/bias-mitigation.md) — social desirability bias and cross-cultural measurement invariance
- [`validation-roadmap.md`](methodology/validation-roadmap.md) — from pilot to validation paper

---

## The problem

Democratic resilience is a central concern in Europe and a recurring justification for investment in civic technology. The EU's European Democracy Shield foresees a central role for civic tech, and the proposed AgoraEU programme carries a budget of EUR 8.5 billion in the next multiannual financial framework.

Yet the field has no shared measurement standards beyond conceptual frameworks. Evaluations are project- or organisation-specific, which limits the longitudinal data that would show whether civic tools make societies more democratically resilient. Cumulative learning across the field is minimal, and evidence-based investment in democratic infrastructure at scale is hampered as a result.

## The four dimensions

Each dimension carries five items.

**1. Media and political literacy** — *cognitive / epistemic*
Knowledge of democratic institutions and processes · perceived civic self-efficacy · ability to identify mis- and disinformation · understanding of political complexity and trade-offs · understanding of the media ecosystem.

**2. Throughput legitimacy** — *institutional / procedural*
Perceived inclusiveness of decision-making · perceived accountability of elected representatives · perceived responsiveness of institutions to citizen input · perceived concentration of power in the executive · perceived efficacy of institutional checks on government power.

**3. Democratic political culture** — *attitudinal / normative*
Consistent commitment to democratic norms · rejection of anti-democratic alternatives · positive affective orientation toward democracy · sense of belonging to a shared political community · openness to opposing views.

**4. Democratic stress tolerance** — *dispositional / behavioural*
Willingness to defend democratic norms under threat · resistance to authoritarian appeals under crisis framing · tolerance for political adversaries and outgroups · capacity to maintain civic engagement under political disillusionment · willingness to accept democratic outcomes that conflict with one's own preferences.

> **A note on Dimension 2.** It measures the perceived quality of a system, so a low score may accurately describe the system rather than a deficit in the respondent — scepticism can be a mark of democratic competence. Inference is drawn from change within individuals against a comparison group in the same context, never from levels.

## How it works

**Mixed scales by dimension.** Dimension 1 uses mostly knowledge tests. Dimensions 2, 3 and 4 combine 5-point Likert scales with 0–10 feeling thermometers. Scenario-based items ask respondents to evaluate situations rather than rate their own beliefs, which mitigates social desirability bias.

**Two waves, two cohorts.** The survey is administered at two time points to a treated cohort and an untreated comparison cohort.

**Scoring.** Each respondent's answers at each wave convert into four dimension scores and an equally weighted composite. These are intermediate quantities: they are differenced per participant, then averaged within each cohort.

**The estimate.** A study reports the difference between the two cohorts' average change — a difference-in-differences design. A statistically significant difference between the treated group's change and the comparison group's change over the same period is evidence of improved democratic resilience.

**Forms and levels.** Every item exists in two alternative forms (A and B), so no respondent answers the same question twice, and at two levels (national and EU), so the questionnaire matches the scope of the programme being assessed. Respondents receive one form per wave, with form order randomised per participant to reduce form-difficulty confounding.

> [!IMPORTANT]
> **Not yet empirically validated.** The DRI is published as a working paper for critical engagement, not as a settled instrument. There is no pilot data, no confirmed factor structure, and no reliability or invariance evidence. It is public now so that it can be criticised before it is used. See [Validation status](#validation-status).

## Validation status

The DRI is positioned as infrastructure for the field, pending empirical validation.

| | Status |
|---|---|
| Theoretical grounding | Complete — see the paper's annex |
| Item bank (20 items, Forms A/B, national/EU) | Complete |
| Scoring and standardisation | Specified |
| Pilot data | **None** |
| Factor structure confirmation | **Not done** |
| Reliability and measurement invariance | **Not done** |
| Translations | **English only** |

We welcome proposals for experiments that apply the DRI to civic technology programmes. See [Collaborate](#collaborate).

## Using the DRI

The DRI is free to reuse and adapt with attribution.

1. Read the [working paper on Zenodo](https://doi.org/10.5281/zenodo.22810037) for the constructs and their justification. The summary on this page is not a substitute if you are going to field the instrument.
2. Read [`methodology/administration-and-validation.md`](methodology/administration-and-validation.md) before fielding anything.
3. Take the items from [`instrument/`](instrument/), choosing the level (national or EU) that matches your programme's scope.
4. Score per [`methodology/scale-standardisation.md`](methodology/scale-standardisation.md).
5. Tell us what broke. Open an issue — that is what this repository is for.

If you adapt the items, please say which version you started from, so your results stay traceable.

## Versioning

The version number tells you whether scores are comparable.

- **MAJOR** — item wording, item count, response scales or dimension structure change. **Scores are not comparable across major versions.**
- **MINOR** — additions that preserve comparability: a translation, added scoring guidance, new documentation.
- **PATCH** — typos, broken links, formatting.

Always cite the version you used. All changes are logged in [`CHANGELOG.md`](CHANGELOG.md).

## Contributing

We are specifically interested in challenges to item wording, the four-dimension structure, the scoring logic, and anything you believe is unmeasurable as stated.

Open an issue to propose a change to item wording, scoring or scope — see [`CONTRIBUTING.md`](CONTRIBUTING.md).

## Collaborate

We welcome proposals for experiments that apply the DRI to civic technology programmes, and are looking for partner universities, organisations and researchers for pilot studies and co-authorship of the validation paper.

Contact **Dr. Sophie Vériter** — sophie@globalsocietyfoundation.org

## Citation

Cite the working paper, not this repository.

> Vériter, S. L. (2026). *The Democratic Resilience Instrument (DRI) as an Evaluation Framework for Civic Technology.* Zenodo. v1.0, September 2026. DOI: [10.5281/zenodo.22810038](https://doi.org/10.5281/zenodo.22810038)

```bibtex
@techreport{veriter2026dri,
  title       = {The Democratic Resilience Instrument (DRI) as an Evaluation
                 Framework for Civic Technology},
  author      = {V{\'e}riter, Sophie L.},
  institution = {Zenodo},
  year        = {2026},
  month       = {9},
  version     = {1.0},
  doi         = {10.5281/zenodo.22810038},
  url         = {https://doi.org/10.5281/zenodo.22810038}
}
```

**Two DOIs, and when to use which.** Zenodo mints a permanent DOI for the record as a whole and a separate one for each version.

| DOI | Resolves to | Use it when |
|---|---|---|
| [`10.5281/zenodo.22810037`](https://doi.org/10.5281/zenodo.22810037) | Always the latest version | Linking to the paper in general — a website, an email, a reading list |
| [`10.5281/zenodo.22810038`](https://doi.org/10.5281/zenodo.22810038) | v1.0 specifically, permanently | **Citing in academic work**, or recording which version you fielded |

If you report DRI results, cite the version DOI. Scores are only comparable within a major version — see [Versioning](#versioning).

## Theoretical foundations

The DRI's conceptual architecture draws on democratic theory, primarily from European and Western contexts where the methodology is designed to be tested first. The paper's annex details how each source is used.

| Source | Contribution to the DRI |
|---|---|
| Holloway & Manwaring (2023) | Requires any resilience claim to state its scope; their finding that the field lacks operationalisation is the gap this instrument addresses |
| Dahl (1971) | Guarantees inform the knowledge tests (D1); opportunities justify measuring perceived inclusiveness and responsiveness (D2, D3) |
| Habermas (1996) | Process quality as a source of legitimacy (D2); grounds openness to opposing views (D3) |
| Norris (2012) | Democratic deficit validates measuring perceptions of democratic quality (D2, D3); the information channel justifies media and disinformation items (D1) |
| Schmidt (2013) | Names D2 and shapes its five constructs; negativity asymmetry justifies reverse-scored items |
| Walz et al. (2025) | Capacity justifies measuring resilience before any stressor occurs; citizen-held resources explain D3 and D4 |
| Merkel (2026) | Civil society and political community as citizen-facing arenas (D3); three modes of stress reaction structure D4 |
| Bauer & Becker (2020) | Anti-pluralist lines inverted from government action into citizen perception (D2); four strategies supply the threat model behind D4 scenarios |

This table is condensed. The full annex and the complete reference list are in the [working paper](https://doi.org/10.5281/zenodo.22810037).

## License

[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) — see [`LICENSE.md`](LICENSE.md).

Free to reuse and adapt with attribution.

## Acknowledgements

With thanks to Dr. Inga Steinberg for her generous feedback, Gabriel Bassat Goldfarb for research assistance, and Hannes Felsberg and Jeremy Apert for their advice on the DRI.

---

*The Democratic Resilience Instrument is a project of the [Global Society Foundation](https://globalsocietyfoundation.org).*
