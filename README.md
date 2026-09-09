# Job Description Skill Extraction using NLP

## SkillExtract AI

**Extract. Normalize. Understand Skills from Job Descriptions.**

SkillExtract AI is an NLP-based project that extracts technical skills from unstructured job descriptions, normalizes different skill variations, categorizes skills, evaluates multiple extraction approaches, and presents skill analytics through Power BI.

The project also includes a Streamlit-based web application that allows users to enter a job description and get structured skill information.


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



# 🔄 End-to-End NLP Pipeline

The overall project follows this workflow:

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

Multiple approaches were explored for skill extraction.

**1. Rule-Based Approach**

A skill taxonomy was created containing:

-Canonical skill names
-Skill categories
-Skill aliases and variations

Dictionary and pattern-based matching were then used to identify skills from job descriptions.

Example

Different forms of the same skill can be normalized:

-Python3        → Python
-Python 3       → Python
-PowerBI        → Power BI
-Power-BI       → Power BI
-Postgres       → PostgreSQL
-MS Excel       → Excel
-Scikit Learn   → Scikit-learn

### Advantages

-Simple to implement
-Easy to understand
-Fast execution
-Suitable when the skill taxonomy is well defined

Limitation

The approach depends heavily on the coverage of the skill taxonomy.

# 🤖 Machine Learning Approach

A Machine Learning approach was also explored for skill classification.

### Method

TF-IDF + Logistic Regression

TF-IDF was used to convert text into numerical features, while Logistic Regression was used as the classifier.

Dataset Preparation

-Total labelled examples: 2525
-Training examples: 2020
-Testing examples: 505
-Skill labels: 21
-Train-Test split: 80/20

### Performance
-Accuracy: 0.9793
-F1 Score: 0.9842

This approach provided strong performance on the constructed evaluation dataset.

# 🤗 Transformer Approach

A pretrained BERT-NER model was also tested as a transformer baseline.

Model

dslim/bert-base-NER

The model was used to test whether a general-purpose pretrained NER model could identify technical terms.

Important Limitation

The model was not fine-tuned specifically for this project's skill categories.

For example, technical terms may be identified as general entity types such as MISC, rather than project-specific categories such as:

-Python       → SKILL
-SQL          → DATABASE
-AWS          → CLOUD_PLATFORM
-Docker       → TOOL
-Kubernetes   → TECHNOLOGY

Therefore, domain-specific fine-tuning would be required for a production-level transformer-based skill extraction system.

# 📊 Model Evaluation

Different approaches were evaluated using:

-Accuracy
-Precision
-Recall
-F1 Score

### Comparison

 Approach                   Accuracy     Precision     Recall     F1 Score

-Dictionary Matching         0.9529        0.9595      0.9782     0.9678
-Regex Matching              0.9870        0.9782      0.9782     0.9782
-Custom NER                  0.7316         0.9782      0.7317    0.8265
-ML                          0.9793         0.9861      0.9832    0.9842
-TF-IDF                      0.9253         0.9589       0.9498    0.9516

The evaluation helped compare the strengths and limitations of rule-based, NER, and machine learning approaches.

# 🔍 Error Analysis

Error analysis was performed to understand where the extraction system can make mistakes.

Error categories

-False Positive
-False Negative
-Wrong Entity
-Partial Entity
-Duplicate Skill
-Unknown Skill
-Synonym Problem
-Spelling Problem
-Taxonomy Gap

Key observations

Some errors were related to:

-Skill variations
-Duplicate or differently formatted skills
-Synonyms
-Taxonomy coverage
-Incorrect or inconsistent labels

Error analysis helped identify areas where the skill taxonomy and extraction logic can be improved.

# 📚 Skill Analytics

The extracted and normalized skills were converted into a structured analytics dataset.

Analytics Dataset

-Total skill records: 9980
-Unique skills: 20
-Unique job roles: 30

Skill Categories

The final skill categories include:

-Programming
-Database
-Analytics
-Cloud
-Machine Learning

This structured data was used for Power BI analysis.

# 📊 Power BI Dashboard

A Power BI dashboard was created to analyse the extracted skills.

Dashboard provides insights into:

-Most common/in-demand skills
-Skills by job role
-Skill category distribution
-Job-role-wise skill requirements
-Top skills
-Interactive skill analysis

The dashboard converts raw extracted skill data into meaningful visual insights.

### Business Value

The dashboard can help:

-Recruiters understand skill requirements
-HR teams analyse technical skill demand
-Job seekers identify commonly required skills
-Training platforms understand skill requirements
-Organisations perform skill-gap analysis

# 💻 SkillExtract AI Web Application

SkillExtract AI is the final web-based application developed using Python and Streamlit.

The application allows users to enter a job description and automatically extract, normalize, and categorize technical skills.

Application Flow

Login / Create Account
          ↓
Paste Job Description
          ↓
Extract Skills
          ↓
Skill Normalization
          ↓
Skill Categorization
          ↓
Display Final Results

# 🖥️ Application Features

User Authentication

The application provides:

-Create Account
-Login
-Personalized welcome message
-Logout

Job Description Input

Users can paste a job description into the application.

* Skill Extraction

The backend processes the text using the project's skill taxonomy and matching logic.

* Skill Normalization

Different variations of skills are converted into standard names.

* Skill Categorization

Each detected skill is assigned to a category.

# 🧪 Application Example

Input

-We are looking for a Data Analyst with Python, SQL, Power BI and Excel skills.

Output

-Python    → Programming
-SQL       → Database
-Power BI  → Analytics
-Excel     → Analytics

Another Example

Input

-We are looking for a Data Scientist with experience in Python, Pandas, NumPy, Scikit-learn and AWS.

Output

-Python        → Programming
-Pandas        → Programming
-NumPy         → Programming
-Scikit-learn  → Machine Learning
-AWS           → Cloud

# ⚙️ Technology Stack

Programming - Python

Data Processing - Pandas

NLP / Machine Learning

-TF-IDF
-Logistic Regression
-Rule-Based Matching
-Regex / Pattern Matching
-BERT-NER baseline

Visualization - Microsoft Power BI

Web Application - Streamlit

Data Storage -  CSV-based skill taxonomy , JSON-based user information 

Deployment - GitHub, Streamlit Community Cloud

# 🗂️ Project Structure
SkillExtract_AI/
│
├── app.py
├── README.md
├── requirements.txt
├── data/
│   └── skill_taxonomy.csv
├── model/
└── utils/
    └── skill_utils.py

# 📦 Installation

Clone the repository:  git clone https://github.com/Tanuholkar27/SkillExtract_AI.git

Navigate to the project directory: cd SkillExtract_AI
Install the required dependencies: pip install -r requirements.txt

# ▶️ Run the Application

Start the Streamlit application: streamlit run app.py

The application will open in your browser.

# 📋 Requirements
The application currently uses: streamlit, pandas

# 🌐 Live Application

The application is deployed using Streamlit Community Cloud.

Live Demo: https://skillextractai-j8h6nu3rtj5nqkwh4z5y4n.streamlit.app/

# 📌 Important Application Note

The current live application uses:

Skill Taxonomy
      +
Matching Logic
      +
Aliases
      +
Normalization
      +
Category Mapping

The ML and Transformer approaches were explored and evaluated as part of the project, but they are not directly integrated into the current live Streamlit application.

The application can only identify skills covered by its current taxonomy and matching logic.

# 📈 Key Learnings

Through this project, I learned how to:

-Work with unstructured text data
-Clean and prepare job description data
-Perform EDA
-Build a skill taxonomy
-Extract skills using rule-based techniques
-Use dictionary and regex matching
-Normalize skill variations
-Categorize technical skills
-Convert text into numerical features using TF-IDF
-Apply Logistic Regression
-Evaluate NLP/ML approaches
-Perform error analysis
-Analyse structured skill data using Power BI
-Build a Streamlit web application
-Deploy an application using GitHub and Streamlit Community Cloud

# 🚀 Future Improvements

Possible future improvements include:

-Expand the skill taxonomy.
-Add unknown-skill detection.
-Create a larger and more diverse labelled dataset.
-Fine-tune a transformer model specifically for skill extraction.
-Integrate a production database.
-Improve authentication and user management.
-Add resume-to-job matching.
-Add skill-gap analysis.
-Add candidate ranking.
-Provide learning recommendations based on skill gaps.
-Improve production scalability.
-Add reliable time-based skill trend analysis when date information is available.

# 💼 Business Use Cases

The project can support several potential use cases:

Recruitment & HR :- Automatically identify required skills from job descriptions.
Job Portals :- Standardize job skills for better job search and filtering.
Resume Screening :- Compare candidate skills with job requirements.
Skill Gap Analysis :- Identify missing skills for a particular job role.
Career & Learning Platforms :- Recommend skills and learning paths based on job requirements.

# 🏁 Conclusion

This project demonstrates an end-to-end NLP workflow for converting unstructured job descriptions into structured technical skill information.

The complete workflow is:

RAW JOB DESCRIPTION
        ↓
DATA CLEANING
        ↓
EDA
        ↓
SKILL EXTRACTION
        ↓
SKILL NORMALIZATION
        ↓
SKILL CATEGORIZATION
        ↓
MODEL EVALUATION
        ↓
ERROR ANALYSIS
        ↓
POWER BI ANALYTICS
        ↓
STREAMLIT APPLICATION

The project combines NLP, machine learning, data analytics, visualization, and application development to create a practical job skill extraction solution.
