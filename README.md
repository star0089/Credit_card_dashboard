# Credit Card Customer & Transaction Dashboard

Power BI report exports exploring cardholder segments, spending, interest and acquisition-cost fields.

**Status:** Two CSV datasets and two dashboard PDFs are available. A PBIX file, Power Query transformations and original DAX measures are not committed, so interactive refresh and dashboard calculations cannot be fully audited.

## Business questions

- Which card categories and customer segments contribute most to the report's headline totals?
- How do transaction amounts and interest compare across the available quarter/week labels?
- How do acquisition-cost fields and customer satisfaction vary across segments?

These are descriptive comparisons, not measured campaign impact or profitability findings.

## Explore the reports

- [Transaction report PDF](Credit_card_Transaction_report.pdf)
- [Customer report PDF](Credit_card__customer_report.pdf)
- [Customer data](customer.csv)
- [Credit-card data](credit_card.csv)
- [Metric definitions and limitations](docs/metrics.md)

## Verified dataset checks

| Check | Observed result |
| --- | ---: |
| Customer CSV rows / unique Client_Num | 10,108 / 10,108 |
| Credit-card CSV rows / unique Client_Num | 10,108 / 10,108 |
| Sum of Total_Trans_Amt | 44,522,013 |
| Sum of Interest_Earned | 7,843,382.23 |
| Sum of Annual_Fees | 2,950,015 |
| Sum of fees + transaction amount + interest | 55,315,410.23 |

The final sum reconciles to the exported dashboard's “Revenue” total. **Transaction spending is not normally issuer revenue**, so this is a reconstructed report metric, not validated accounting revenue. The original DAX definition is unavailable. Currency is not confirmed in the source metadata.

Both CSVs have unique Client_Num values; confirm matching key coverage before creating the relationship. These records contain aggregated transaction fields, not individual transaction events.

## Recreate an exploratory report

1. Open Power BI Desktop and import both CSV files.
2. Inspect data types, missing values and key coverage.
3. Create a relationship using Client_Num only after checking uniqueness and unmatched keys.
4. Build segment visuals using customer attributes and card metrics.
5. Document each measure and reconcile totals with the CSVs.

This recreates an exploratory model; it does not reproduce the original report exactly without its PBIX and DAX.

The PDFs are static exports. Interactive slicers and refresh require the original Power BI project.

## Limitations and next steps

Dataset provenance, license, currency and field semantics are not recorded. Week labels span 2023, but one row per client does not demonstrate weekly panel coverage or an event-level transaction history. Trends require clarification of what each date represents.

Next: add the original PBIX, a measure dictionary, source attribution and a clear separation of transaction volume, fee income, interest income and profit.

**Mahesh Vyas** · [LinkedIn](https://www.linkedin.com/in/data-mahesh/) · [GitHub](https://github.com/star0089)
