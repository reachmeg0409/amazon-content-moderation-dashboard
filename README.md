**Trust & Safety Analytics Dashboard for Amazon Content Moderation Operations**


**Executive Summary**

This project delivers a comprehensive Power BI dashboard analyzing Amazon’s internal content moderation across multiple marketplaces and content types. Using robust data modeling and tailored DAX measures, it uncovers trends in violations, team efficiencies, and platform risks, supporting strategic decisions for improved trust and safety operations.

**Business Problem**

Amazon faces challenges in managing large-scale content moderation across its diverse global marketplace. The business needs actionable insights into violation patterns, team workloads, AI flagging effectiveness, and operational risks to enhance compliance and optimize resource allocation.

**Dataset Overview**

The dataset simulates real-world moderation activity:

  Source: Amazon’s moderation logs (simulated, not sensitive).

  Scope: 100,000+ cases across reviews, product titles, images, ASINs, marketplaces, and teams.

| Column Name           | Description                                           |
| --------------------- | ----------------------------------------------------- |
| Date                  | Review date                                           |
| Content_ID            | Unique ASIN/content record                            |
| Content_Type          | Type of content moderated                             |
| ASIN_Category         | Product category (Electronics, Books, etc.)           |
| Marketplace           | Region (US, UK, IN, etc.)                             |
| Moderator_Team        | Team responsible for moderation                       |
| Violation_Type        | Type of policy or content violation                   |
| Moderation_Action     | Action taken (Removed, Suppressed, etc.)              |
| Review_Outcome        | Result of review (Valid Violation, etc.)              |
| Review_Time_Minutes   | Time spent reviewing (2–180 min)                      |
| Flagged_By            | Source that triggered moderation (AI, Customer, etc.) |



**Data Cleaning & Modeling**

  • Imported raw logs into Power BI, checked for missing and duplicate records.

  • Standardized categorical columns (Marketplace, Moderator_Team, etc.).

  • Star schema design:

    1. Fact table: Moderation

    2. Dimensions: Date, Moderator_Team, Marketplace, Content_Type, ASIN_Category

  • Data validated for reporting granularity and hierarchical roll-ups.

**DAX Logic & KPIs**
  
Advanced DAX measures developed:

    • Violation % by Category/Marketplace:  Violation Percentage= COUNT(All Records) / COUNT(Violation)
                                                                
    • Avg Review Time per Team:  Avg Time=AVERAGE(Review_Time_Minutes)       

    • False Positive Rate, Critical Violation %

    • AI vs Human flagging effectiveness, Escalation Rate, Category Sensitivity

**Dashboard Highlights**

**Team Performance Monitoring:** Bar charts compare escalation rates and review times across moderation teams.

**Platform Risk Analysis:** Donut and line charts highlight marketplaces/regions with highest violation/incident rates.

**Flagging Source Evaluation:** Segmented stacked charts show detection distribution between AI and human sources.

**Category Sensitivity:** Visuals pinpoint sensitive product categories prone to frequent violations.

**Operational Load Forecasting:** Line graphs display review volumes for staffing and resource planning.

**Key Insights**

  • Certain regions (e.g., US, UK) and product categories (Electronics, Books) showed higher violation rates.

  • Teams with highest avg review times often also faced more complex escalations.

  • AI flagging was effective but had a higher false positive rate than human flaggers.

  • Review volumes increased during promotional periods, suggesting the need for scalable resources.

**Recommendations**

  • Invest in AI flagging improvements to reduce false positives.

  • Reallocate resources to high-risk categories and marketplaces.

  • Provide targeted training for teams with longer average review times.

  • Use operational load forecasting to plan moderation capacity ahead of demand spikes.
 
**Screenshots**

<img width="1328" height="821" alt="image" src="https://github.com/user-attachments/assets/3757fb0c-0ca8-4f64-8982-424d46b48294" />


**Appendix – DAX Measures**

      Total Violations = COUNTROWS('Moderation')
      Critical Violation % = CALCULATE([Total Violations], 'Moderation'[Violation_Type]="Critical") / [Total Violations]
      False Positive % = CALCULATE([Total Violations], 'Moderation'[Review_Outcome]="False Positive") / [Total Violations]
      Avg Review Time = AVERAGE('Moderation'[Review_Time_Minutes])
      Escalation Rate = CALCULATE([Total Violations], 'Moderation'[Moderation_Action]="Escalated") / [Total Violations]
      AI Flagging % = CALCULATE([Total Violations], 'Moderation'[Flagged_By]="AI") / [Total Violations]



    
