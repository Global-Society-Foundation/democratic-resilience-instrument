# Administration and Validation

This note explains how to field the DRI, what may be claimed from the results, and what changes once the instrument is validated.

> [!IMPORTANT]
> **This file is binding.** A study departing from it is not administering the DRI, and its scores are not comparable with others'.

---

## 1. What a respondent receives

**20 items** — five per dimension, one per construct.

**One level only** — national or EU. Constructs 3.5, 4.3 and 4.4 are identical at both levels.

**One form per wave** — A or B.

Allow 20–25 minutes to complete the survey. Participants should skip questions they don't know the answer to, rather than answering randomly.

At baseline only, and at the end of the survey, also collect:

- Year of birth
- Country of residence
- Area of residence (a big city · the suburbs or outskirts of a big city · a town or small city · a country village · a farm or home in the countryside)
- Gender (woman · man · prefer to self-describe [free text] · prefer not to say)
- Highest level of education (lower secondary or below · upper secondary · post-secondary · bachelor's degree · master's degree · doctoral degree · prefer not to say)
- Prior participation in a similar programme — "Before this programme, had you taken part in a civic technology programme, a participatory or deliberative process, or a civic education initiative?" (no · yes once · yes more than once · not sure)
- Income — "Which of these descriptions comes closest to how you feel about your household's income nowadays?" (living comfortably on present income · coping on present income · finding it difficult on present income · finding it very difficult on present income · prefer not to say)

These are covariates[^1] and **never enter the composite**.

[^1]: Covariate wording follows the European Social Survey (area of residence, income), ISCED 2011 (education) and ISO 3166-1 (country), enabling benchmarking against European population data.

## 2. Choosing the level

By the level of government the intervention concerns. Municipal or national politics: national level. EU institutions, EU policy, cross-border European civic life: EU level. Programmes spanning both: the level the intervention aims to change — state the choice when reporting.

Fixed for the study. Never switch between waves; never give both levels to one person.

## 3. Forms and form order

Form A and Form B measure the same constructs in different words. Neither is exclusively for pre- or post-test. **Form order is randomised per participant and fixed for the study.** Half receive A then B, half B then A. Nobody receives the same form twice.

Randomise before fieldwork, against the participant record. Store `form_order` as `AB` or `BA` and branch on it in both waves. Randomise within each site, cohort or country.

The two forms are not yet established as equal in difficulty. Until they are, **form order enters every model as a term**.

## 4. Study design

### 4.1 Control group

A comparison (control) group is required to draw inference. **The estimated effect is the difference between the change in the treated group and in a control group over the same period.**

| Design | How participants are assigned | Note |
|---|---|---|
| Randomised control | Randomly: half receive the programme during the study, half do not receive it at all | Strongest, but rarely acceptable to partners |
| **Waitlist control** | Randomly: half receive the programme during the study, half receive it once the study ends | **Default.** As strong as a randomised control for the study period, and nobody is denied the programme |
| Matched comparison | Not randomly: recruit non-participants who resemble the treated group on age, education, prior political engagement and country | Weakest. Requires statistical adjustment for any remaining differences, and baseline imbalance must be reported |

All three designs require both groups to be measured in the same calendar window. A waitlist control is assigned at the same time as the treated group and completes both surveys on the same dates, but only receives the civic tech programme afterwards.

### 4.2 Sample size

Plan for **200 participants in each group (400 in total)** completing both waves. At that size the study detects a difference between the two groups' changes of around 0.3 standard deviations, and it meets the 200-respondent minimum the factor analysis in [`bias-mitigation.md`](bias-mitigation.md) requires.

Recruit 25–30 per cent above target to absorb attrition, since only participants completing both waves enter the analysis. Confirm the figure with a power calculation once an expected effect size is available, and state it in the pre-registration.

### 4.3 If no comparison group is possible

The instrument may still be administered and the pre/post scores reported as a description of the participating cohort. But **no claim of causal effect may be made.** Report it as observed change in that cohort and state that no counterfactual was available.

### 4.4 Administering the survey

The survey is administered in two waves. Both groups (treatment and control) receive the survey on the same dates. Everything the treated group receives, the comparison group receives, except the intervention itself:

- the same level (national or EU),
- the same two measurement dates and the same interval between them,
- form order randomised within both the treated and comparison group, so half of these two groups get Form A first and half Form B first,
- the same anchors, the same missing-data rules.

### 4.5 Language

The instrument is written in English. Version 1.0 is available in English only. Further languages are added as pilot sites are confirmed, or are contributed by adopters.

Each language requires four steps ([`bias-mitigation.md`](bias-mitigation.md) §2). Machine translation may be used for the **first draft**, and must be disclosed. It may **not** be used for back-translation. **Native-speaker review** and **cognitive pretesting** are required in every language.

Some Dimension 1 items need adaptation rather than translation — not every country has a constitutional court, for example.

### 4.6 Analysis

Each participant appears twice in the data, once per wave. Analyse both waves together in one model, with the following terms:

- **time** (baseline or follow-up) — the change common to everyone.
- **group** (treated or comparison) — any difference between the groups at the outset.
- **time × group** — the extra change in the treated group over and above the comparison group. **This is the treatment effect.**
- **form order** — absorbs any difference in difficulty between Form A and Form B.
- **a random intercept per participant** — accounts for two rows belonging to one person.

Run the same model on the composite and on each of the four dimension scores.

#### Example

Suppose 200 participants per arm (400 in total), each measured twice. Composite scores are normalised to 0–1 per [`scale-standardisation.md`](scale-standardisation.md). The cohort means:

| | Baseline | Follow-up | Change |
|---|---|---|---|
| Comparison | 0.51 | 0.54 | +0.03 |
| Treated | 0.55 | 0.62 | +0.07 |

The treated cohort gained 0.07. The comparison cohort gained 0.03 without the intervention. The estimate of interest is the difference between those changes: **time × group = +0.04, 95% CI [0.01, 0.07]**. This is the estimand.

The remaining terms are context. `group` (+0.04) is the gap between cohorts before treatment. `time` (+0.03) is the drift both cohorts showed regardless. `form order` (−0.01) absorbs any difficulty difference between Forms A and B and is not interpreted substantively.

The same model is run on each dimension:

| Outcome | time × group | 95% CI |
|---|---|---|
| Composite | +0.04 | [0.01, 0.07] |
| D1 Media and political literacy | +0.09 | [0.05, 0.13] |
| D2 Throughput legitimacy | +0.02 | [−0.02, 0.06] |
| D3 Democratic political culture | +0.01 | [−0.03, 0.05] |
| D4 Democratic stress tolerance | +0.03 | [−0.01, 0.07] |

**Finding:** *Over four weeks, the treated cohort's composite rose 0.04 more than the comparison cohort's (95% CI 0.01–0.07), concentrated in Dimension 1.*

## 5. Response scales and anchors

The bracketed anchor in the dimension files names the family. Respondents see all five labels.

| Format | Used in | Recorded as |
|---|---|---|
| Binary | Items 1.1, 1.3, 1.4, 1.5 | 1 correct / 0 incorrect |
| Five-point | 1.2 · all of D2 · 3.1, 3.2, 3.4 · all of D4 | 1 to 5 |
| Eleven-point | 3.3, 3.5 | 0 to 10 |

| Family | 1 | 2 | 3 | 4 | 5 |
|---|---|---|---|---|---|
| Agreement | Strongly disagree | Disagree | Neither agree nor disagree | Agree | Strongly agree |
| Support | Strongly oppose | Oppose | Neither support nor oppose | Support | Strongly support |

**Support** applies to items 3.1, 4.1 and 4.2 only. Every other five-point item uses **Agreement**.

Eleven-point items show only the endpoints. Item 3.3: *not positively – extremely positively* (Form A), *not favourably – extremely favourably* (Form B). Item 3.5: *not at all – completely*, both forms.

## 6. Question and option order

- Randomise the four options within every multiple-choice item.
- Randomise item order within each dimension. Dimensions in fixed order, 1 to 4.
- Do not group items by construct or display construct labels.

## 7. Timing

The DRI survey is administered at two time points:

- **Baseline** — within seven days before first exposure to treatment.
- **Follow-up** — within fourteen days after the intervention ends.

Keep a minimum of **four weeks** between administrations (duration of the intervention).

*Shorter than four weeks:* the four-week minimum holds. Hold the follow-up, record it, and report retained rather than immediate change.

*Longer than six months:* add an interim wave rather than widening the gap. Only two forms exist, so the third wave repeats one — repeat the baseline form and record which.

## 8. Missing data and scoring

**No "don't know" option.** On knowledge items it measures confidence; on attitudinal items the neutral midpoint already covers it. **Skipping is allowed and must be clearly indicated**, to avoid respondents getting correct answers by chance. A skipped item is missing, not zero.

- **Dimension score:** requires four of five items. Average the normalised items answered.
- Two or more missing = no dimension score.
- **Composite:** requires all four dimension scores.
- Report exclusions and the wave in which they occurred.

Full procedure in [`scale-standardisation.md`](scale-standardisation.md). Three things never vary:

1. Recode reverse-scored items **before** normalising.
2. Normalise against **theoretical** bounds, not the sample range.
3. Weight the four dimensions **equally**.

Any value outside its declared bounds after recoding is a data error.

## 9. Consent, ethics and data protection

Article 9 of the General Data Protection Regulation covers data *revealing* political opinions, and the Court of Justice reads "revealing" to include opinions that can be inferred, not only stated. Dimension 1's knowledge items do not qualify. Several Dimension 3 items do — agreeing that a country "would be better run by a strong leader who can make important decisions without having to get parliament's approval" is a political opinion in the ordinary sense. Because some items fall inside Article 9, the dataset as a whole does. It requires an Article 9 condition, usually explicit consent, alongside an Article 6 lawful basis:

- **Explicit, unbundled consent.**
- **Privacy notice:** controller, purpose, retention, right to withdraw.
- **Storage:** where responses sit, and whether the platform transfers outside the EU.
- **Ethical approval** where an institution requires it — usually mandatory for university partners, which will expect the special-category classification.
- **Assignment disclosure:** tell participants they may be assigned to a comparison group, how assignment works, and when that group receives the intervention.

### Linking waves without identifying people

Assign each participant a study ID before fieldwork, the same record that carries `form_order`. Response data contains the ID only, never names or email addresses. Keep the list linking IDs to contact details in a separate, access-restricted file, and delete it at the point stated in the privacy notice. Data shared or published carries re-randomised IDs.

### Do not volunteer individual scores to participants

Feeding scores back between waves changes what the follow-up measures. An individual score is also too imprecise to interpret. Participants who request their own data under Article 15 must of course receive it.

## 10. Reporting

State:

- instrument version and level;
- how the comparison group was formed, its size, and baseline comparability;
- the form-order design and whether form order entered the model;
- sample per wave, attrition, exclusions;
- **all four dimension scores alongside the composite, never the composite alone**;
- interval between waves.

## 11. Validation status

> [!WARNING]
> **The DRI is currently unvalidated.**

Until the validation paper is published:

- label results **provisional**, since the composite is not yet shown to behave as one measure and equal weighting is an assumption;
- report dimensions prominently, because a composite average conceals divergence;
- include form order in every model;
- share anonymised item-level data toward the validation evidence base.

Afterwards, three things may change — use and report the version current when you field:

- Weighting may become factor-derived.
- Items may be replaced where they fail to discriminate or add no information, logged in [`CHANGELOG.md`](../CHANGELOG.md).
- Form equivalence, once established, makes counterbalancing recommended rather than mandatory; until that appears in the changelog, §3 applies in full.

The validation timeline is detailed in [`validation-roadmap.md`](validation-roadmap.md).

## 12. Expanding a dimension

Expand a dimension only where the pilot reveals a specific, diagnosable problem:

- an item that nearly all respondents answer correctly, or nearly none do, and which therefore fails to discriminate;
- an item whose removal leaves the dimension score essentially unchanged, and which therefore carries no information;
- a facet of the construct that reviewers identify as clearly unrepresented.

**Low internal consistency in a formative dimension is not such a signal and does not trigger expansion.**

## 13. Checklist before fielding

- [ ] Level chosen and fixed
- [ ] Comparison group in place; design recorded
- [ ] Both groups scheduled across the same calendar window
- [ ] Study ID assigned per participant, on the same record as `form_order`
- [ ] `form_order` balanced within site and within each group, stored outside the survey
- [ ] Both waves branch on `form_order`; both ID and `form_order` are written to the export
- [ ] Response data carries the study ID only (no names, no email addresses)
- [ ] ID-to-contact list held separately, access restricted, with a deletion date set
- [ ] Two test responses through both waves, confirming no repeated form
- [ ] Response options randomised within every multiple-choice item
- [ ] Anchors match §5
- [ ] No "don't know" option
- [ ] Baseline covariates collected
- [ ] Consent, privacy notice, assignment disclosure, ethical approval
- [ ] At least four weeks between administrations
