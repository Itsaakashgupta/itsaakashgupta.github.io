---
date: 2021-01-09 05:20:35 +0300
draft: false
title: 🐾 Animal Shelter Operations Analytics
subtitle: This project analyzes animal shelter operations data to uncover actionable insights related to intake patterns, outcomes, live-release performance, length of stay (LOS), and repeat intakes.
tags: [PowerBI, MySQL]
image: '/images/animal_shelter.png'
demo_url: 'https://app.powerbi.com/view?r=eyJrIjoiZDVjNTExZWItMWU4OS00Y2JiLWIyMzAtOTBlM2ZkZGVkZDNjIiwidCI6IjcyODYxZmY5LTM0ZmMtNGUyYy1iNjgzLTAwZTQxNmY2NjBmYyJ9'
weight: 98
seo:
  page_description: 
  canonical_url: 
  featured_image: 
  author_twitter_handle: 
  open_graph_type:
  no_index: false
---

## 📌 Introduction

This project **analyzes animal shelter operations** data to uncover actionable insights related to **intake patterns, outcomes, live-release performance, length of stay (LOS), and repeat intakes.**

The objective is not only to visualize trends, but to support data-driven decision-making for:

- Shelter capacity planning

- Staffing and resource allocation

- Improving save rates

- Reducing length of stay

- Designing prevention and outreach programs

The project was built as part of the **ZoomCharts / DataDNA Analytics Challenge**, with a strong emphasis on **storytelling, interactivity, and business impact.**

# 📂 Dataset Overview

### Dataset Name:
Animal Shelter Intakes and Outcomes – City of Long Beach Animal Care Services

## What the dataset is about

The dataset contains detailed records of animals entering and leaving the shelter, including:

- Animal characteristics

- Intake circumstances

- Outcomes and timelines

- Shelter stay duration

Each row represents an **individual intake record**, allowing longitudinal analysis for repeat intakes.


## 🧾 What the Dataset Contains

Key data fields include:

- **Animal Information:** Species, breed, age, sex, color

- **Intake Details:** Intake date, intake type, intake condition, intake source

- **Outcome Details:** Outcome type, outcome date, live-release indicators

- **Operational Metrics:** Length of stay, current shelter status

This structure enables analysis across **time, species, age groups, conditions, and outcomes.**

# 🧹 Data Preparation & Cleaning

Significant effort was invested in preparing the data for reliable analysis.

## Key Cleaning Steps

- **Handled missing Date of Birth (DOB)** values and corrected date formats using locale-aware parsing

- **Corrected negative age** values caused by DOB recorded after intake date

- **Standardized text fields**, including animal names and categorical columns

- **Replaced missing secondary colors** with an explicit category to avoid visual exclusion

- **Created a standardized outcome** classification to group outcomes into meaningful categories (Live, Deceased, Current, Other)

# 🔧 Data Transformation & Feature Engineering

To support deeper analysis, several transformations and calculated fields were created.

## Key Transformations & Measures

- **Age at Intake** (calculated correctly with error handling)

- **Age Groups** (Baby, Young, Adult, Senior)

- **Length of Stay (LOS)** calculated dynamically for both completed and active cases

- **Live Release Rate (LRR)** excluding current residents from the denominator

- **Repeat Intake Flag** to identify animals entering the shelter multiple times

- **Calendar Table** for robust time intelligence (YoY, monthly, weekday analysis)

These transformations enabled **accurate KPIs, trend analysis, and segmentation.**

# 📊 Analysis & Dashboard Highlights

The Power BI report focuses on answering real operational questions, including:

- How intake and outcome volumes change over time

- Seasonal and weekday intake patterns affecting staffing

- Differences in adoption, LRR, and LOS by species and age

- Intake conditions and outcome types driving long shelter stays

- Identification of high-risk groups contributing to repeat intakes

- Data-driven actions to improve save rates and reduce LOS

Interactive visuals were built using **ZoomCharts** to enable:

- Drill-down exploration

- Cross-filtering

- Intuitive navigation for business users


## 🔍 Biggest Takeaways from the Dataset

- Intake volumes show **clear seasonal and weekday patterns,** enabling proactive staffing and foster planning

- **Cats experience longer LOS than dogs,** particularly during summer intake surges

- Adoption rates have improved significantly over time, but **live-release rates remain volatile**

- **Age, species, and intake condition** are strong predictors of LOS and outcomes

Repeat intakes are concentrated in specific outcome pathways, indicating prevention gaps

These insights highlight that **targeted interventions outperform blanket solutions.**



# 📈 Data-Driven Recommendations

Based on the analysis, the most impactful actions include:

- Expanding foster capacity ahead of seasonal peaks

- Targeted adoption campaigns for seniors and long-stay animals

- Medical fast-tracking for mild-condition cases

- Post-adoption and post–return-to-owner follow-ups

- Community prevention programs focused on high-volume intake sources


##🌱 Personal Learning & Growth

Through this project, I strengthened my skills in:

- Power BI data modeling and advanced DAX

- Designing KPIs that reflect real operational logic

- Turning exploratory analysis into decision-ready insights

- Using ZoomCharts for interactive, business-focused storytelling

- Writing clear, stakeholder-friendly analytical narratives

Most importantly, I learned that **effective analytics is about clarity, prioritization, and impact—not just visuals.**

# 🧾 Conclusion

This project demonstrates how operational data can be transformed into **meaningful insights that improve outcomes,** optimize resources, and support animal welfare.

By combining solid data preparation, thoughtful KPI design, and interactive storytelling, the dashboard delivers value to both **analysts and decision-makers.**