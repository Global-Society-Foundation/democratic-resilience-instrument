# Contributing

The DRI is published before validation so that it can be tested and challenged. Proposals from researchers and practitioners are welcome.

---

## Proposing a change

Open an issue on GitHub. A proposal must contain:

- the construct affected, by item number
- the proposed wording in full
- the reason for the change
- any supporting evidence, published or from your own data

> [!IMPORTANT]
> Proposals that do not name a construct will be closed without review.

## Decisions

Proposals are reviewed by the instrument maintainers. Expect a first response within two weeks. Accepted changes are recorded in [`CHANGELOG.md`](CHANGELOG.md), with the contributor credited by name unless they ask otherwise.

## What is unlikely to be accepted before validation

**Adding items to a dimension.** The instrument is deliberately short. Expansion is triggered only by the diagnostic criteria in [`methodology/administration-and-validation.md`](methodology/administration-and-validation.md), not a perceived gap.

**Changing the four dimensions or the equal weighting.** Both are being tested in the pilot. Changing them beforehand would make the validation uninterpretable.

## Required companion edits

Any change to an item's scale, anchors or scoring direction must update, **in the same submission**:

- the item row in the dimension file
- the dimension file header
- §5 of [`methodology/administration-and-validation.md`](methodology/administration-and-validation.md)
- the format list in [`methodology/scale-standardisation.md`](methodology/scale-standardisation.md)
- the instrument design section of [`README.md`](README.md)

Search the package for the old wording before submitting.

## Translations

Translations are welcome and must meet the four steps in [`methodology/bias-mitigation.md`](methodology/bias-mitigation.md) §2: translation, independent back-translation, native-speaker review, and cognitive pretesting. State whether machine translation was used for the first draft.

Submit the translated item bank, the back-translation, and a short note on what the cognitive pretesting found.

## Sharing pilot data

Studies fielding the DRI before validation are asked to share anonymised item-level data, so that it contributes to the validation evidence base.

> [!WARNING]
> Data must carry study IDs only, never names or contact details.

## Licence and attribution

The DRI is licensed [CC BY 4.0](LICENSE.md). Contributions are accepted under the same licence. Contributors retain authorship of their contribution and are credited in the changelog and, where the contribution is substantial, in the validation paper.

## Contact

hello@globalsocietyfoundation.org
