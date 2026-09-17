# Bias Mitigation

This note addresses threats to validity in the DRI, what is already done about each, and what the pilots will test.

---

## 1. Social desirability

**Issue.** Respondents may give the answer they believe is expected rather than their own. This affects the attitudinal items in Dimensions 2, 3 and 4 more than Dimension 1's knowledge items, which have objectively correct answers.

**Mitigation strategies in use:**

- **Scenario framing.** Items 3.1, 4.1, 4.2 and 4.5 present a situation and ask the respondent to judge it, rather than asking them to rate themselves. Scenarios anchor on "a party you support", so the socially expected answer is not obvious from the stem.
- **Plausible distractors.** Options in the knowledge and scenario items are formal-sounding and defensible, so the correct answer cannot be found by elimination.
- **Response conditions.** Confidentiality is stated at intake, response options are randomised within each multiple-choice item, and construct labels are never shown to respondents ([`administration-and-validation.md`](administration-and-validation.md) §6).

**Alternative.** Field a short validated social desirability scale alongside the instrument in the pilot and report its correlation with each dimension score. A high correlation on a given dimension is evidence that its items are transparent and need rewriting.

## 2. Cultural and linguistic measurement invariance

**Issue.** The DRI is intended for use across languages and political cultures. The same item may not mean the same thing in each, and scores that are not comparable cannot be pooled.

**Planned mitigation strategies:**

- **Back-translation.** Translate into each target language, then back-translate independently and check for drift in meaning.
- **Native-speaker review.** Confirm the translation reads naturally and carries the same meaning, not only the same words.
- **Cognitive pretesting.** Test translated items with a small sample in each context to catch idiomatic or culturally loaded phrasing. Especially relevant for Dimension 3 items referencing national political community.
- **Multi-group testing.** Once pilot data exists, run multi-group confirmatory factor analysis across language and country groups to test configural, metric and scalar invariance.

## 3. Throughput legitimacy, political trust, and institutional reality

**Issue.** Dimension 2 asks respondents to evaluate institutional processes. Perception-based ratings of institutional quality are known to be coloured by general trust in, or approval of, whoever currently holds power. This raises two separate questions.

- **Is Dimension 2 a trust scale in disguise?** If general trust drives the scores, the dimension is not measuring throughput legitimacy specifically.
- **Do external events contaminate change over time?** *Resolved by design.* The comparison group required in [`administration-and-validation.md`](administration-and-validation.md) §4 is exposed to the same political events as the treated group, so their effect cancels when the two changes are differenced.

**Planned mitigation strategy, from a pilot sample:**

1. **Field a short validated trust battery** alongside the Dimension 2 items: three European Social Survey items (trust in parliament, in politicians, in political parties) plus one government-approval item. For EU-level administration, substitute trust in the European Parliament. Four items maximum.
2. **Fit a two-factor model:** Dimension 2 items on one factor, the three trust items on the other, allowed to correlate. The approval item enters as an observed covariate, not as its own factor — a single indicator cannot identify one. Compare against a one-factor model in which all items load together. The models are nested, so use a scaled chi-square difference test. Report the comparative fit index and root mean square error of approximation descriptively. Information criteria are not available under the estimator appropriate to ordinal items.
3. **Assess discriminant validity** using the heterotrait-monotrait ratio of correlations, which detects problems more reliably than the Fornell-Larcker criterion.

   | HTMT | Interpretation |
   |---|---|
   | Below 0.85 | Acceptable |
   | 0.85 – 0.90 | Marginal |
   | Above 0.90 | The two constructs are not distinguishable |

   Set no lower bound: a correlation of around 0.65 between throughput legitimacy and political trust is expected and healthy.
4. **Below 200 respondents** the factor model is not stable. Fall back to the correlation between the two composite scores corrected for attenuation (divide by the square root of the product of the two reliabilities) and apply the same 0.85 threshold.

**If the check fails:** revise Dimension 2 item wording toward more concrete, mechanism-specific phrasing before considering relabelling the dimension.

## 4. Acquiescence

**Issue.** Some respondents agree with statements regardless of content. Most of the instrument uses an agreement scale, so this would inflate scores on the dimensions built from it.

**Mitigation strategies in use:**

- **Reverse-scored items.** Dimension 2 items 2.3 and 2.4, and Dimension 3 items 3.1 and 3.2, are worded so that agreement indicates lower resilience. A respondent agreeing indiscriminately therefore scores high on some items and low on others, and the effect partly cancels.
- **Randomised item order** within each dimension, so reverse-scored items are not clustered and cannot be answered as a block.

**Alternative.** Compute each respondent's mean response across all agreement-family items, using raw scores *before* reverse-coding. A respondent without acquiescence bias should average near the scale midpoint. Report the distribution and, if it is skewed upward, the correlation between this index and the composite score.
