Healthcare Billing Audit & Insurance Fairness Analysis
A data analytics project simulating a hospital billing-integrity audit — identifying statistically abnormal charges and testing whether billing amounts vary by insurance provider, across 40,000+ patient records.

📌 Business Problem
Hospitals face two recurring billing risks:

Inconsistent or erroneous charges that go unnoticed without systematic review
Payer-linked bias — where billing depends on who's paying rather than the service delivered
This project answers two questions a hospital finance/compliance team would actually ask:

Which billing amounts are statistically abnormal for their medical condition?
Does average billing vary meaningfully by insurance provider for the same condition?
🗂️ Dataset
~55,000 patient records (post de-duplication) with demographics, medical condition, insurance provider, doctor, hospital, admission details, and billing amount.

Source: Healthcare Dataset – Kaggle

🛠️ Tools Used
Excel — data cleaning, AVERAGEIF, STDEV.S, VLOOKUP, PERCENTILE, Pivot Tables
Power BI — interactive dashboard, DAX aggregations, slicers, visualizations
🔍 Method
Cleaned inconsistent name formatting and removed duplicate records
Calculated average and standard deviation of billing amount per medical condition
Computed a Z-Score per patient to flag deviation from the norm — then switched to a percentile-based method (top/bottom 5%) after discovering the billing values were uniformly distributed, which made Z-scores unreliable for this dataset
Cross-checked average billing by insurance provider to test for payer-linked bias
Built a Power BI dashboard with KPI cards, condition-wise and insurance-wise billing charts, and an outlier distribution view, with interactive slicers
📊 Key Findings
Metric	Value
Total Patients	40,235
Average Billing	₹25,630
High Outliers	2,731
Low Outliers	2,766
~10% of all records (≈5,497 patients) fall outside the normal billing range for their medical condition — a meaningful population for manual review
Average billing by medical condition stays narrow across categories, with no extreme unexplained spikes
Average billing by insurance provider stayed within a tight ₹24,800–₹26,200 band — no evidence of payer-linked billing bias
✅ Recommendations
Route flagged outlier records to a manual billing review queue, prioritized by deviation size
Automate a monthly dashboard refresh to catch anomalies early, not just at year-end audit
Periodically re-run the insurance-provider comparison as a standing compliance check
📁 Files in this repo
Healthcare_Billing_Audit_Case_Study.docx — full write-up (problem, method, findings, recommendations)
healthcare_dashboard.pbix — Power BI dashboard
healthcare_dataset_FINAL.xlsx — cleaned dataset with outlier flags and pivot analysis
👤 Author
Chetna Sidana
