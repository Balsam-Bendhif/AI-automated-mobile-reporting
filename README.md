# 🤖 AI-Powered Mobile Analytics Reporting Platform

> An intelligent end-to-end platform for automating mobile application analytics, KPI analysis, anomaly detection, AI-powered insights and automated business reporting.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-Backend-3ECF8E?logo=supabase&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-Automation-EA4B71?logo=n8n&logoColor=white)
![OpenAI](https://img.shields.io/badge/AI-OpenAI-412991?logo=openai&logoColor=white)
![Claude](https://img.shields.io/badge/AI-Claude-D97757)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

---

## 📌 Overview

This project is an end-to-end platform designed to automate the mobile application analytics reporting process.

It combines **Data Engineering, Python, SQL, REST APIs, n8n, Generative AI and automated reporting** to transform raw application data into structured KPIs, analytical insights and business reports.

### Main Pipeline

```text
Data Sources
     ↓
Data Collection
     ↓
Data Cleaning & Validation
     ↓
PostgreSQL / Supabase
     ↓
KPI Calculation
     ↓
Anomaly Detection
     ↓
OpenAI / Claude Analysis
     ↓
Report Generation
     ↓
Email / Slack Distribution





🎯 Objectives
The platform aims to:
- Automate mobile application data collection
- Clean and validate incoming data
- Store historical analytical data
- Calculate business KPIs
- Detect significant performance variations
- Generate AI-powered insights
- Produce actionable recommendations
- Automatically generate reports
- Distribute reports through Email and Slack



🏗️ Architecture
                 ┌─────────────────────────┐
                 │     DATA SOURCES        │
                 │ Google Play / App Store │
                 └────────────┬────────────┘
                              ↓
                 ┌─────────────────────────┐
                 │     DATA COLLECTION     │
                 │ REST APIs / OAuth / JWT │
                 └────────────┬────────────┘
                              ↓
                 ┌─────────────────────────┐
                 │ DATA CLEANING & QUALITY │
                 │          Python         │
                 └────────────┬────────────┘
                              ↓
                 ┌─────────────────────────┐
                 │      DATA STORAGE       │
                 │ PostgreSQL / Supabase   │
                 └────────────┬────────────┘
                              ↓
                 ┌─────────────────────────┐
                 │      KPI ANALYSIS       │
                 └────────────┬────────────┘
                              ↓
                 ┌─────────────────────────┐
                 │    ANOMALY DETECTION    │
                 └────────────┬────────────┘
                              ↓
                 ┌─────────────────────────┐
                 │      AI ANALYSIS        │
                 │    OpenAI / Claude      │
                 └────────────┬────────────┘
                              ↓
                ┌─────────────┼─────────────┐
                ↓             ↓             ↓
              Email          PDF           PPTX
                ↓             ↓             ↓
              Gmail          Slack         Slack

The complete process is orchestrated using n8n.



🔄 Workflow


1. Data Collection
The platform is designed to collect mobile application data from:
- Google Play Developer Reporting API
- Apple App Store Connect API

Authentication:
Google Play → OAuth 2.0
App Store Connect → JWT

The collection layer handles API requests, pagination, response processing and error management.



2. Data Cleaning & Validation
Raw data is processed before being used for analytics.

The processing layer performs:
- Duplicate detection
- Missing-value handling
- Date normalization
- Type validation
- Range validation
- Consistency checks
- Abnormal-value detection

Example validation rules:

Installations >= 0
Uninstallations >= 0
Rating ∈ [0, 5]
Crash Rate ∈ [0, 1]
Revenue >= 0



3. Data Storage

Processed data is stored using:
- PostgreSQL
- Supabase

The database provides historical storage, analytical queries, relational integrity, indexing and access control.

⭐ Data Warehouse Model
The analytical database follows a Star Schema.

Main fact table:
FaitMetriqueJournaliere

Main dimensions:
DimApplication
DimPlateforme
DimDate
DimPays




Architecture:



                  DimApplication
                        │
                        │
DimPlateforme ── FaitMetriqueJournaliere ── DimDate
                        │
                        │
                     DimPays

This structure is designed for efficient analytical queries and historical reporting.




📊 KPI Analysis


The platform calculates several business indicators:

KPI	Description
Install Growth Rate	Growth compared with a previous period
Uninstall Rate	Uninstallations relative to installations
Average Rating	Application rating evolution
Crash Rate	Failed sessions relative to total sessions
ARPU	Revenue per active user


These KPIs provide the structured analytical context used by the AI layer.



🚨 Anomaly Detection


The platform compares current observations with historical performance to identify significant variations.
Examples include:
- Sudden rating drops
- Uninstall spikes
- Crash-rate variations
- Unexpected KPI changes
- Significant performance changes


Historical Performance
        ↓
Current Performance
        ↓
Comparison
        ↓
Anomaly Detection
        ↓
Severity Classification



The detected anomalies are then passed to the AI layer for contextual interpretation.



🧠 Generative AI

Generative AI is integrated after the deterministic data-processing and analytical stages.
The project supports OpenAI and Claude for AI-powered analysis.
Raw Data
   ↓
Data Processing
   ↓
KPI Calculation
   ↓
Anomaly Detection
   ↓
Structured Analytical Context
   ↓
OpenAI / Claude
   ↓
Business Interpretation
   ↓
Recommendations


The AI layer generates:

- Natural-language interpretation
- Business insights
- Explanations
- Executive summaries
- Recommendations

The LLM does not replace deterministic KPI calculations.




✨ Prompt Engineering

Structured prompts are used to control the generated analysis.
The AI context can include:
- Reporting period
- Application
- Platform
- KPI values
- Previous-period comparisons
- Detected anomalies
- Severity levels
- Analytical instructions
- Required output format

The objective is to produce consistent, relevant and actionable business analysis.



⚙️ n8n Workflow Automation

n8n acts as the central workflow orchestration engine.
A typical workflow is:


Schedule Trigger
       ↓
Data Collection
       ↓
Data Processing
       ↓
Database Storage
       ↓
KPI Calculation
       ↓
Anomaly Detection
       ↓
AI Analysis
       ↓
Report Generation
       ↓
Distribution

Example scheduled execution:
Monday 09:00
     ↓
Collect latest data
     ↓
Analyze performance
     ↓
Generate reports
     ↓
Send reports

This eliminates repetitive manual reporting operations.



🔀 Reporting Workflow


After the analytical stage, the workflow branches into multiple reporting outputs:



                 KPI + AI Analysis
                        ↓
              ┌─────────┼─────────┐
              ↓         ↓         ↓
            Email      PDF       PPTX
              ↓         ↓         ↓
            Gmail     Slack      Slack


Each branch produces a different business deliverable.



📄 Automated Reporting


Email Report
The automated email can contain:
- Executive summary
- Key KPIs
- Main performance changes
- Detected anomalies
- Recommendations


PDF Report
The PDF provides a detailed analytical report suitable for management reporting, weekly reviews, sharing and archiving.


PowerPoint Report
The presentation can include:
- KPI overview
- Performance evolution
- Platform comparison
- Important anomalies
- AI insights
- Recommendations



🐳 Docker & Deployment

Docker is used to provide a reproducible environment.



Docker Environment
      │
      ├── n8n
      ├── Python
      └── Application Components
             │
             ├── PostgreSQL / Supabase
             ├── OpenAI / Claude
             ├── APIs
             ├── Gmail
             └── Slack

Docker provides:

- Reproducibility
- Portability
- Environment isolation
- Easier deployment


🧪 Testing

The project includes several testing levels.


Unit Testing
- Data cleaning
- Validation
- KPI calculations
- Anomaly detection



Integration Testing

APIs
 ↓
Python
 ↓
Database
 ↓
LLM
 ↓
Reporting
 ↓
Distribution

End-to-End Testing

The complete workflow is tested from data collection to final report distribution.




🛠️ Technology Stack

Category	Technologies
Programming	Python, SQL, JavaScript
Data Engineering	ETL / ELT, Data Cleaning, Validation
Database	PostgreSQL, Supabase
APIs	REST APIs
Mobile Data	Google Play API, App Store Connect API
Authentication	OAuth 2.0, JWT
Workflow Automation	n8n
AI / LLM	OpenAI, Claude
AI Techniques	Generative AI, Prompt Engineering
Reporting	HTML, PDF, PowerPoint
Communication	Gmail, Slack
Infrastructure	Docker
Version Control	Git, GitHub
Data Modeling	Star Schema


🔐 Security & Confidentiality

Production credentials and confidential business information are not included in this repository.
Sensitive information such as API keys, database credentials, OAuth credentials and private tokens is managed through environment variables.
The public repository uses safe or synthetic data where necessary.

🎥 Project Demo

A complete walkthrough of the platform, from data processing to AI-powered reporting and automated delivery.

▶️ Watch the full project demonstration on Google Drive : https://drive.google.com/file/d/1Q7D4F8_HbPHpTn_0DcP0JD5nAe6vQ61b/view?usp=drive_link




🎓 Academic Project
Master's Final-Year Project
Project Title
Conception et développement d'une plateforme intelligente d'automatisation du reporting analytique des applications mobiles

The project combines:
- Data Engineering
- Business Intelligence
- Generative AI
- Workflow Automation
- API Integration
- Data Warehousing
- Automated Reporting
👩‍💻 Author
Balsam Bendhif
Data Analyst | Data & AI | Automation
