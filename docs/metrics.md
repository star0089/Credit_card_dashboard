# Metric definitions and validation

## Inputs and grain

customer.csv has demographic/customer fields. credit_card.csv has card attributes, annual fees, transaction aggregates, interest, acquisition cost and week/quarter labels. Each file has 10,108 rows and unique Client_Num values. The observed grain is one record per client in each file, not one row per transaction.

## Reconciled controls

- Total_Trans_Amt sum: 44,522,013.
- Interest_Earned sum: 7,843,382.23.
- Annual_Fees sum: 2,950,015.
- Their combined sum: 55,315,410.23, matching the dashboard PDF's Revenue total.

This arithmetic suggests the report combines spending, fees and interest. It does not establish the original DAX expression. Transaction spending should not be presented as issuer revenue without a documented business definition. Profit requires costs and losses beyond these totals.

Week_Start_Date values range from 2023-01-01 to 2023-12-24. Clarify whether dates refer to acquisition, assignment or reporting periods before interpreting time trends.

## Validation and boundaries

CSV row counts, unique IDs and numeric totals were recomputed from committed inputs. PDF text was inspected to reconcile the headline metric. No CSVs or exported reports were altered.

Original report relationships, filters, DAX, refresh behavior, source provenance, currency and licensing remain unverified. Satisfaction and acquisition-cost fields need definitions before actionable recommendations. No causal effect or business improvement is claimed.

Client_Num coverage matches exactly between both CSVs: zero unmatched keys in either direction.
