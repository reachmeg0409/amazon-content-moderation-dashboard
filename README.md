Trust & Safety Analytics Dashboard for Amazon Content Moderation Operations

Executive Summary

This project delivers a comprehensive Power BI dashboard analyzing Amazon’s internal content moderation across multiple marketplaces and content types. Using robust data modeling and tailored DAX measures, it uncovers trends in violations, team efficiencies, and platform risks, supporting strategic decisions for improved trust and safety operations.

Business Problem

Amazon faces challenges in managing large-scale content moderation across its diverse global marketplace. The business needs actionable insights into violation patterns, team workloads, AI flagging effectiveness, and operational risks to enhance compliance and optimize resource allocation.

Dataset Overview

The dataset simulates real-world moderation activity:

Source: Amazon’s moderation logs (simulated, not sensitive).

Scope: 100,000+ cases across reviews, product titles, images, ASINs, marketplaces, and teams.



Data Cleaning & Modeling

  Imported raw logs into Power BI, checked for missing and duplicate records.

  Standardized categorical columns (Marketplace, Moderator_Team, etc.).

  Star schema design:

    Fact table: Moderation

    Dimensions: Date, Moderator_Team, Marketplace, Content_Type, ASIN_Category

  Data validated for reporting granularity and hierarchical roll-ups.
