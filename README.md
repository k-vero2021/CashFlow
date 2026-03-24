# CashFlow
Project idea: CashFlow Shield - Payment Health, Customer Pain &amp; Recovery.

README
2025 Payment Health, Customer Pain & Recovery Dashboard
Flagship fintech portfolio case built on synthetic transaction data with an executive dashboard, six marts, and end-to-end analytics logic.

Project focus	Payments, complaints, and recovery	Dashboard scope	1 executive screen, 8 signals
Data basis	Synthetic data pack	Audience	Executive / hiring manager / BI reviewers
Core marts	6 daily marts	Primary tools	SQL, Python, BI

1. What this project is
This project simulates a real fintech decision environment. It is designed to show how a company can track money entering the payment system, identify where value leaks out, understand when payment issues become customer pain and measure how much value can be recovered through collections and recovery operations.
The dashboard is intentionally lean. It focuses on eight executive signals instead of a crowded analyst view: four KPI cards at the top and four decision charts below. The goal is clarity for a busy decision-maker, while deeper logic stays documented in marts, SQL, Python notebooks and technical specs.
2. Business problem
Payment issues reduce cash-in and create direct revenue leakage.
The same issues can trigger complaints, increase support pressure and erode customer trust.
Not all lost value is final: part of the at-risk value can be recovered through collections and operational follow-up.
Leadership needs one screen that connects money, friction and recovery instead of reviewing separate reports.
3. Dashboard logic
Core storyline: money enters the system → part of it converts successfully → part of it leaks → customers feel the friction → the business either loses that value or wins part of it back.
Eight dashboard signals
Dashboard signal	Source mart	Primary field(s)	Business meaning
Gross Payment Volume	mart_executive_kpis_daily	gross_payment_volume_usd	Total payment value processed in the selected period.
Payment Success Rate	mart_executive_kpis_daily	payment_success_rate	Share of payment attempts completed successfully.
Complaint Rate	mart_executive_kpis_daily	complaint_rate_per_1k_tx / complaint_rate	Customer complaint pressure relative to transaction flow.
Recovery Cure Rate	mart_executive_kpis_daily	repayment_cure_rate	Share of problem cases resolved successfully.
Lost Value	mart_payment_funnel_daily	lost_value_usd	Value lost due to failed or declined payments.
Top Decline Reason	mart_decline_reason_daily	decline_reason + failed_value_usd	Main reason behind the highest lost payment value.
Top Complaint Driver	mart_complaints_voc_daily	issue + complaint_rate_per_1k_tx	Complaint issue with the highest impact on customer experience.
Recovered Amount	mart_repayment_funnel_daily	recovered_amount_usd	Value recovered from previously at-risk or overdue cases.
4. Mart structure
mart_executive_kpis_daily: Daily executive view with payment, complaint, risk and recovery KPIs.
mart_payment_funnel_daily: Daily payment funnel and lost value by payment context.
mart_decline_reason_daily: Daily root-cause view of failed and declined payments.
mart_complaints_voc_daily: Daily voice-of-customer view of complaint pressure and resolution quality.
mart_complaints_by_payment_context: Complaint concentration by payment rail, channel and merchant context.
mart_repayment_funnel_daily: Daily collections and recovery funnel by DPD bucket and account context.
5. Data foundation
Source tables: customers, accounts, merchants, transactions, complaints, collections_cases, risk_alerts, experiments and consent_events.
Key design rule: dimensions provide customer and account context, while executive and operational marts are driven by event dates from transactions, complaints, collections and risk alerts.
6. One-screen layout
Top panel: four KPI cards — Gross Payment Volume, Payment Success Rate, Complaint Rate, Recovery Cure Rate.
Bottom panel: four charts — Lost Value trend, Top Decline Reason, Top Complaint Driver, Recovered Amount trend.
Design goal: minimal visual noise, one decision path and obvious business meaning.
7. Why this is valuable
It connects payment health, customer pain and recovery into one executive decision flow.
It shows not just what is wrong, but where the loss starts and which lever can recover value first.
It is portfolio-ready for product analytics, growth analytics, BI, business analysis and system analysis roles in fintech.
It can be demonstrated as a dashboard, a mart layer, a SQL case, a Python case and a requirements case.

8. Executive summary
This dashboard is not a collection of isolated metrics. It tells a business story: money enters the system, part of it converts, part of it leaks, customers feel the friction and the business either loses that value or wins some of it back. That makes the dashboard useful not only for monitoring, but for prioritizing action.
