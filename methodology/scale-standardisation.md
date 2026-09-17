# Scale Standardisation

This note explains how scale is standardised across items and dimensions in the DRI methodology.

---

## 1. Why standardise scale?

Scale standardisation explains how raw item scores in three different response formats get normalised onto a common scale and then combined into a single DRI composite score.

The 20-item bank mixes three response formats:

- **0–1** (Dimension 1) — knowledge tests and scenario-based items.
- **5-point** (Dimensions 1, 2, 3 and 4) — agreement and support/oppose items.
- **0–10 feeling thermometer** (Dimension 3) — affective orientation and openness.

These cannot be averaged directly: a "3" on a 5-point scale and a "3" on a 10-point scale don't mean the same thing, and some items are reverse-coded. We must standardise scale.

## 2. How we standardise the DRI scales

**Min-max rescaling using theoretical (fixed) bounds.** Each item is rescaled using its scale's defined minimum and maximum.

| Format | Transformation |
|---|---|
| 0–1 items | Stay as-is, coded 0 or 1 |
| 5-point Likert | `(raw − 1) / 4` |
| 0–10 thermometer | `raw / 10` |

**Rationale.** Z-scoring requires a stable reference sample's mean and SD locked in before it can be reused across pre/post waves and future administrations, which is risky given the pilots' likely modest size to begin with. Theoretical min-max sidesteps that and keeps the composite bounded at 0–1, for easier communication to funders and partner practitioners.

**Planned robustness check.** Once significant pilot data exists, also compute a z-scored version of the composite as a supplementary analysis in the validation paper, to test whether min-max is hiding any distortion from items with unusually high or low response variance. See [`validation-roadmap.md`](validation-roadmap.md).

### Examples

- **0–1.** A respondent who scores 1 on item 1.5.2 is normalised as 1 / 1 = 1. An incorrect answer scores 0 and normalises as 0 / 1 = 0. No rescaling needed.
- **5-point Likert.** A respondent who selects "agree" on item 2.1.2 (raw = 4) normalises as (4 − 1) / 4 = **0.75**. If reversed: a respondent who selects "disagree" (raw = 2) is first recoded as 6 − 2 = 4, then normalised as (4 − 1) / 4 = **0.75**.
- **0–10 thermometer.** A respondent who answers 7 normalises as 7 / 10 = **0.7**.

## 3. Measurement model

The four dimensions determine which reliability statistics can meaningfully be applied to each.

A **reflective** dimension is one in which a single underlying trait causes the answers. Its items are interchangeable indicators of that trait, and they should therefore correlate strongly with one another; if they do not, something is wrong with the scale.

A **formative** dimension is one in which the items are distinct components that jointly constitute the construct rather than symptoms of it. Its items need not correlate, and there is no theoretical reason to expect them to.

| Dimension | Model |
|---|---|
| D1 Media and political literacy | Formative |
| D2 Throughput legitimacy | **Provisionally reflective** — tested in the pilot |
| D3 Democratic political culture | Formative (not uniformly) |
| D4 Democratic stress tolerance | Formative |

**Dimension 1 is formative.** Knowledge of democratic institutions, perceived civic self-efficacy, the ability to identify manipulation techniques, reasoning about political trade-offs, and understanding of the media ecosystem are separate capacities. A respondent may possess any one of them without the others, and media and political literacy is what results from holding them together rather than a trait that produces them.

**Dimension 2 is provisionally reflective.** All five items ask respondents to evaluate the quality of the same decision-making process from different angles, so someone who perceives that process as responsive is likely also to perceive it as accountable and inclusive. This classification is treated as a hypothesis rather than a settled fact, and is tested in the pilot through the factor analysis set out in [`bias-mitigation.md`](bias-mitigation.md) §3. **If it does not hold, Dimension 2 is reclassified as formative and reported accordingly.**

**Dimension 3 is formative, though not uniformly so.** Rejection of anti-democratic alternatives, affective orientation toward democracy, and sense of belonging to a shared political community may behave as a correlated cluster, while consistency of commitment across partisan contexts and openness to opposing views measure dispositions that are conceptually and empirically distinct from the rest.

**Dimension 4 is formative.** Willingness to defend democratic norms under threat, resistance to authoritarian appeals under crisis framing, tolerance for political adversaries, capacity to sustain engagement under disillusionment, and willingness to accept unfavourable democratic outcomes are separate behavioural dispositions that together describe stress tolerance without implying one another.

## 4. Reliability reporting

Coefficient alpha and related internal-consistency statistics are interpretable **only for reflective dimensions**, because they test the assumption that the items are interchangeable. They are therefore applied to **Dimension 2 only**, where a value of roughly .70 or above is expected, and are not applied to the other three.

> [!WARNING]
> For the formative dimensions, low internal consistency is a property of the design. It is **not** grounds for revising, replacing or expanding a dimension. Reporting a low alpha figure for these dimensions without this caveat would invite the misreading that the instrument is unreliable, when the statistic simply does not apply.

In place of internal consistency, three forms of evidence are reported for the formative dimensions:

1. **The inter-item correlation matrix**, presented descriptively to document how the components relate to one another, rather than as a pass-or-fail test.
2. **Each item's contribution to the variance of its dimension score**, which identifies any item carrying no information. An item whose removal leaves the dimension score essentially unchanged is a candidate for replacement.
3. **Test-retest stability** — the primary reliability evidence. The instrument is administered twice to the same respondents roughly two weeks apart with no intervention in between, and the correlation between the two composite scores is reported. Stability over a short interval, in the absence of anything that should have changed the underlying capacities, is the appropriate reliability evidence for an index built from distinct components.

## 5. Step-by-step aggregation into the DRI composite score

1. Recode any reverse-scored items.
2. Normalise every item using theoretical min-max bounds for its format.
3. Average the normalised items within each dimension to get four dimension scores.
4. Average the four dimension scores, equally weighted, into the composite DRI score.

Equal weighting across dimensions is the current default. Factor loadings from pilot tests may support reweighting dimensions rather than treating all four as equally important. That re-evaluation is scheduled in [`validation-roadmap.md`](validation-roadmap.md).
