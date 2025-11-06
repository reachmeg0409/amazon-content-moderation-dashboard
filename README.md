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

  Imported raw logs into Power BI, checked for missing and duplicate records.

  Standardized categorical columns (Marketplace, Moderator_Team, etc.).

  Star schema design:

  1. Fact table: Moderation

  2. Dimensions: Date, Moderator_Team, Marketplace, Content_Type, ASIN_Category

  Data validated for reporting granularity and hierarchical roll-ups.

**DAX Logic & KPIs**
  
Advanced DAX measures developed:

    Violation % by Category/Marketplace:  Violation Percentage= COUNT(All Records) 
                                                                COUNT(Violation)

    Avg Review Time per Team:  Avg Time=AVERAGE(Review_Time_Minutes)                            
 

    
