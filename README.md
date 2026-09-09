# Job Description Skill Extraction using NLP

## SkillExtract AI

**Extract. Normalize. Understand Skills from Job Descriptions.**

SkillExtract AI is an NLP-based project that extracts technical skills from unstructured job descriptions, normalizes different skill variations, categorizes skills, evaluates multiple extraction approaches, and presents skill analytics through Power BI.

The project also includes a Streamlit-based web application that allows users to enter a job description and get structured skill information.

---

## 📌 Project Overview

Job descriptions contain important technical skills, but these skills are usually embedded inside unstructured text.

For example:

> "We are looking for a Data Analyst with Python, SQL, Power BI and Excel skills."

Manually identifying these skills from multiple job descriptions can be time-consuming and inconsistent.

This project uses Natural Language Processing (NLP), rule-based techniques, machine learning approaches, and a pretrained transformer baseline to identify technical skills from job descriptions.

The extracted skills are then:

- Normalized
- Categorized
- Evaluated
- Analysed
- Visualized
- Integrated into a web application

---

## 🎯 Problem Statement

Job descriptions are mostly unstructured text where technical skills can appear in different formats.

Some common challenges are:

- Technical skills are embedded in long job descriptions.
- Manual skill identification requires time and effort.
- Different names or formats can represent the same skill.
- Raw text is difficult to aggregate and analyse.
- Inconsistent skill names can affect analytics.
- A structured skill representation is useful for recruitment and skill analysis.

---

## 🎯 Project Objectives

The main objectives of this project are:

1. Understand and clean job description data.
2. Perform Exploratory Data Analysis (EDA).
3. Extract technical skills from job descriptions.
4. Create a skill taxonomy.
5. Normalize skill names and aliases.
6. Categorize skills into meaningful groups.
7. Compare different NLP and ML approaches.
8. Perform model evaluation and error analysis.
9. Build skill analytics using Power BI.
10. Develop a web-based skill extraction application using Streamlit.

---

# 📊 Dataset

The project uses a job description dataset containing **2525 initial records**.

### Dataset Summary

| Description | Value |
|---|---:|
| Initial Records | 2525 |
| Duplicate Records | 25 |
| Working Records | 2500 |
| Number of Fields | 12 |
| Unique Job Titles | 30 |

### Main Dataset Fields

- `job_id`
- `job_title`
- `company`
- `company_name`
- `company_id`
- `location`
- `job_description`
- `keywords`
- `experience`
- `education`
- `salary`
- `job-time`

The `keywords` field was used as the ground-truth skill information for the evaluation process.

---

# 🧹 Data Cleaning

The dataset was inspected and cleaned before NLP processing.

### Cleaning steps included:

- Missing value checking
- Duplicate record detection
- Duplicate record removal
- URL/link removal
- Email ID removal
- Special character handling
- Extra space removal
- Text standardization

The dataset initially contained 2525 records. After identifying and removing 25 duplicate records, **2500 working records** were used for analysis.

---

# 📈 Exploratory Data Analysis

EDA was performed to understand the dataset and identify useful patterns.

### EDA included:

- Job title distribution
- Location analysis
- Company analysis
- Job description length analysis
- Missing-value analysis
- Duplicate analysis
- Skill-related observations

The dataset contains **30 unique job titles**, which helped analyse skill requirements across different job roles.

---

# 🔄 End-to-End NLP Pipeline

The overall project follows this workflow:

```text
Job Description
       ↓
Text Preprocessing
       ↓
Skill Extraction
       ↓
Skill Normalization
       ↓
Skill Categorization
       ↓
Model Evaluation
       ↓
Skill Analysis
       ↓
Power BI Dashboard
       ↓
Streamlit Application

# 🧠 Skill Extraction

Skill extraction is the core part of this project.

The main objective is to identify technical skills from job descriptions and convert the unstructured text into structured skill information.

For example:

### Input

```text
We are looking for a Data Analyst with Python,
SQL, Power BI and Excel skills.
