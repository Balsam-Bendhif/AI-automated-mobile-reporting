# 🤖 AI-Powered Mobile Analytics Reporting Platform

> An intelligent end-to-end platform for automating mobile application analytics, KPI computation, anomaly detection, AI-powered analysis and automated business reporting.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?logo=postgresql&logoColor=white)
![Supabase](https://img.shields.io/badge/Supabase-Backend-3ECF8E?logo=supabase&logoColor=white)
![n8n](https://img.shields.io/badge/n8n-Workflow%20Automation-EA4B71?logo=n8n&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Containerized-2496ED?logo=docker&logoColor=white)
![OpenAI](https://img.shields.io/badge/LLM-OpenAI-412991?logo=openai&logoColor=white)
![Claude](https://img.shields.io/badge/LLM-Claude-D97757)

---

# 📌 Overview

**AI-Powered Mobile Analytics Reporting** is an intelligent platform designed to automate the complete lifecycle of mobile application analytics reporting.

The project combines:

- Data Engineering
- Business Intelligence
- Cloud Computing
- Workflow Automation
- Generative Artificial Intelligence
- API Integration
- Data Warehousing
- Automated Reporting

The objective is to transform raw mobile application data into structured KPIs, detect significant performance variations, generate contextual AI analysis and automatically distribute professional reports.

The complete process can be summarized as:

```text
Data Collection
      ↓
Data Cleaning & Quality Control
      ↓
Data Storage
      ↓
KPI Computation
      ↓
Anomaly Detection
      ↓
Generative AI Analysis
      ↓
Report Generation
      ↓
Automated Distribution
```

---

# 🎯 Project Context

Mobile application platforms generate large volumes of analytical data such as:

- installations
- uninstallations
- ratings
- reviews
- revenue
- crashes
- impressions
- application performance indicators

However, this information is distributed across different platforms and often requires several manual operations before it can be transformed into a useful business report.

Traditional reporting may involve:

1. Extracting data from different platforms
2. Consolidating datasets
3. Cleaning and validating information
4. Calculating KPIs
5. Creating visualizations
6. Identifying unusual variations
7. Writing analytical comments
8. Preparing presentations
9. Writing summary emails
10. Distributing the final reports

This process can become repetitive, time-consuming and difficult to scale.

The purpose of this project is therefore to automate the reporting value chain from data collection to final business deliverables.

---

# ❓ Problem Statement

The central problem addressed by this project is:

> **How can the complete mobile application analytics reporting process be automated, from raw data collection to intelligent business deliverables, while maintaining data reliability, scalability and analytical relevance?**

---

# 🎯 Objectives

The main objective is to design and develop an intelligent platform capable of automating mobile application analytics reporting.

The platform aims to:

- Automatically collect mobile application data
- Consolidate data from different platforms
- Clean and validate incoming data
- Store historical information
- Calculate analytical KPIs
- Detect unusual performance patterns
- Generate contextual AI analysis
- Produce actionable recommendations
- Generate professional reports
- Automate email summaries
- Distribute reports through communication channels
- Provide a modular and scalable architecture

---

# 🏗️ Global Architecture

The platform is organized into several functional layers:

```text
                         ┌─────────────────────────────┐
                         │      MOBILE DATA SOURCES    │
                         │                             │
                         │ Google Play / App Store     │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │      DATA COLLECTION        │
                         │                             │
                         │ REST APIs                   │
                         │ OAuth 2.0 / JWT             │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │   DATA CLEANING & QUALITY   │
                         │                             │
                         │ Python                      │
                         │ Validation / Transformation │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │    DATA STORAGE             │
                         │                             │
                         │ Supabase / PostgreSQL       │
                         │ Star Schema                 │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │       KPI ANALYSIS          │
                         │                             │
                         │ Daily / Weekly / Monthly    │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │    ANOMALY DETECTION        │
                         │                             │
                         │ Historical comparison      │
                         │ Severity classification     │
                         └──────────────┬──────────────┘
                                        │
                                        ▼
                         ┌─────────────────────────────┐
                         │     GENERATIVE AI           │
                         │                             │
                         │ OpenAI / Claude             │
                         │ Prompt Engineering          │
                         └──────────────┬──────────────┘
                                        │
                         ┌──────────────┼──────────────┐
                         │              │              │
                         ▼              ▼              ▼
                      ┌───────┐      ┌───────┐      ┌───────┐
                      │ HTML  │      │ PPTX  │      │ Email │
                      │ / PDF │      │       │      │       │
                      └───┬───┘      └───┬───┘      └───┬───┘
                          │              │              │
                          └──────────────┼──────────────┘
                                         ▼
                              Automated Distribution
```

The complete workflow is orchestrated using **n8n**, which acts as the automation and integration layer.

---

# 🔄 End-to-End Data Pipeline

The complete data flow follows this architecture:

```text
External APIs
      │
      ▼
Data Ingestion
      │
      ▼
Data Cleaning
      │
      ▼
Data Validation
      │
      ▼
PostgreSQL / Supabase
      │
      ▼
KPI Calculation
      │
      ▼
Anomaly Detection
      │
      ▼
LLM Analysis
      │
      ▼
Report Generation
      │
      ├──────────────┬──────────────┐
      ▼              ▼              ▼
     PDF            PPTX          Email
      │              │              │
      └──────────────┴──────────────┘
                     ▼
             Automated Delivery
```

---

# 🌐 Data Collection

The platform is designed around two major mobile application ecosystems:

## Google Play

The project uses the **Google Play Developer Reporting API** for retrieving application performance information.

Authentication is based on:

```text
OAuth 2.0
```

The collection layer is designed to handle:

- authentication
- API requests
- pagination
- response parsing
- network errors
- retry mechanisms
- rate limiting

---

## Apple App Store

The platform also integrates the **App Store Connect API**.

Authentication is based on:

```text
JWT
```

The connector retrieves and processes the required mobile application metrics.

The two connectors provide a common analytical layer despite the differences between the source platforms.

---

# 🧹 Data Cleaning & Quality Control

Raw data cannot be directly used for reliable analytics.

The processing layer therefore performs several quality-control operations.

Examples include:

- duplicate detection
- duplicate removal
- date normalization
- missing-value handling
- type validation
- range validation
- consistency checks
- abnormal-value flagging

The objective is to make the dataset reliable before KPI computation.

Example validation rules include:

```text
Installations >= 0
Uninstallations >= 0
Rating ∈ [0, 5]
Crash Rate ∈ [0, 1]
Revenue >= 0
```

---

# 🗄️ Data Storage

The platform uses:

- **PostgreSQL**
- **Supabase**

Supabase provides the hosted backend environment while PostgreSQL provides the relational database engine.

The database is responsible for:

- persistent storage
- historical data
- analytical queries
- relational integrity
- indexing
- access control

---

# ⭐ Data Warehouse Model

The analytical database uses a **Star Schema** adapted to Business Intelligence requirements.

The main fact table is:

```text
FaitMetriqueJournaliere
```

It is connected to several dimensions:

```text
                 DimApplication
                       │
                       │
DimPlateforme ── FaitMetriqueJournaliere ── DimDate
                       │
                       │
                    DimPays
```

## Dimensions

The main dimensions are:

- `DimApplication`
- `DimPlateforme`
- `DimDate`
- `DimPays`

## Fact Table

The main fact table stores daily quantitative metrics associated with:

- applications
- platforms
- dates
- countries

This structure is optimized for analytical queries and aggregations.

---

# 📊 KPI Computation

The platform automatically calculates performance indicators at different time granularities.

## Main KPIs

| KPI | Description | Frequency |
|---|---|---|
| Install Growth Rate | Percentage change compared with a previous period | Weekly / Monthly |
| Uninstall Rate | Uninstallations relative to installations | Daily |
| Weighted Average Rating | Rating calculation with greater importance given to recent observations | Weekly |
| Crash Rate | Failed sessions relative to total sessions | Daily |
| ARPU | Revenue per active user | Monthly |

The KPI layer transforms raw operational metrics into indicators that can be interpreted by business teams.

---

# 🚨 Anomaly Detection

The platform includes an anomaly detection layer designed to identify significant deviations in application performance.

The system compares current observations with historical behavior.

Examples of anomalies include:

- sudden rating drops
- uninstall spikes
- unusual crash-rate variations
- significant performance changes
- unexpected KPI movements

Each detected anomaly can be associated with a severity level.

Example:

```text
Normal
   │
   ├── Moderate variation
   │
   └── Critical variation
```

The anomaly detection results are then provided to the AI layer for contextual interpretation.

---

# 🧠 Generative AI Layer

Generative AI is integrated after the deterministic data-processing and analytical stages.

The architecture follows:

```text
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
LLM
    ↓
Business Interpretation
    ↓
Recommendations
```

The LLM is therefore not responsible for replacing the analytical calculations.

Instead, it enriches the calculated results with:

- natural-language interpretation
- contextual analysis
- explanations
- recommendations
- executive summaries

---

# ✨ Prompt Engineering

The AI layer uses structured prompts to control the generated output.

The prompt can include:

- reporting period
- application information
- platform
- KPI values
- previous-period comparisons
- detected anomalies
- severity
- required output format
- analytical instructions

The generated response is then integrated into the reporting layer.

The goal is to obtain:

- consistent structure
- relevant analysis
- actionable recommendations
- controlled numerical interpretation

---

# ⚙️ n8n Workflow Automation

**n8n** acts as the central workflow orchestration engine.

A typical workflow can be represented as:

```text
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
LLM Analysis
       ↓
Report Generation
       ↓
Distribution
```

The workflow can be scheduled automatically.

For example:

```text
Every Monday
      ↓
Collect latest data
      ↓
Analyze performance
      ↓
Generate reports
      ↓
Send reports
```

This removes the need for manual execution of the reporting process.

---

# 📄 Automated Reporting

The platform supports several types of outputs.

## HTML Report

The HTML report can contain:

- executive summary
- KPI overview
- platform comparison
- performance evolution
- detected anomalies
- AI analysis
- recommendations

---

## PDF Report

The HTML report can be converted into a PDF document suitable for:

- management reporting
- archiving
- sharing
- weekly performance reviews

---

## PowerPoint Presentation

The platform can also generate a presentation containing:

- performance overview
- KPI evolution
- platform comparison
- important anomalies
- AI insights
- recommendations

This format is designed for meetings and management presentations.

---

## Email Summary

An automated email provides a concise summary of the reporting period.

The email can include:

- key performance indicators
- major changes
- detected anomalies
- main recommendations
- links or attachments to reports

---

# 📤 Multi-Channel Distribution

The reporting outputs can be distributed through multiple channels.

```text
                         AI Analysis
                              │
             ┌────────────────┼────────────────┐
             │                │                │
             ▼                ▼                ▼
           Email             PDF              PPTX
             │                │                │
             ▼                ▼                ▼
          Gmail             Slack            Slack
```

This allows different users to receive the format most appropriate for their needs.

---

# 🐳 Docker & Cloud

Docker is used to provide a portable and reproducible application environment.

The conceptual architecture is:

```text
Cloud Environment
       │
       ▼
Docker Environment
       │
       ├── n8n
       ├── Python Services
       └── Application Components
               │
               ▼
        External Services
        ├── Mobile APIs
        ├── Supabase
        ├── LLM APIs
        ├── Gmail
        └── Slack
```

Docker provides:

- environment isolation
- reproducibility
- portability
- easier deployment
- consistent execution environments

---

# 🔐 Security

Security is considered throughout the architecture.

## Authentication

Google Play:

```text
OAuth 2.0
```

App Store Connect:

```text
JWT
```

## Secret Management

Production credentials must never be committed to GitHub.

Examples include:

```text
OPENAI_API_KEY
ANTHROPIC_API_KEY
SUPABASE_KEY
SLACK_BOT_TOKEN
GOOGLE_CREDENTIALS
APPLE_PRIVATE_KEY
```

A `.env.example` file can be provided:

```env
SUPABASE_URL=
SUPABASE_KEY=

OPENAI_API_KEY=
ANTHROPIC_API_KEY=

SLACK_BOT_TOKEN=

GOOGLE_CLIENT_ID=
GOOGLE_CLIENT_SECRET=

APPLE_KEY_ID=
APPLE_ISSUER_ID=
APPLE_PRIVATE_KEY=
```

The real `.env` file must remain local.

---

# 🔒 Row Level Security

Supabase/PostgreSQL can use **Row Level Security (RLS)** to restrict access to data according to the authenticated context.

This provides an additional security layer for applications and users sharing the same analytical infrastructure.

---

# 🧪 Testing Strategy

The project uses several levels of testing.

## Unit Testing

Individual components are tested independently:

- data cleaning
- validation
- KPI calculation
- anomaly detection

## Integration Testing

Integration tests verify communication between:

- APIs
- Python services
- PostgreSQL
- Supabase
- LLM services
- reporting components
- distribution services

## End-to-End Testing

The complete workflow is tested from:

```text
Data Collection
      ↓
Processing
      ↓
Analysis
      ↓
Report Generation
      ↓
Distribution
```

## Performance Testing

The system is evaluated with different data volumes and application configurations.
---

# 🚨 Anomaly Detection Validation

Six controlled anomaly scenarios were evaluated.

The tested cases included:

- sudden rating drop
- uninstall spike
- gradual rating decline
- another uninstall spike
- small crash-rate variation
- another sudden rating drop

---

# 🛠️ Technology Stack

| Category | Technologies |
|---|---|
| Programming | Python, SQL, JavaScript |
| Data Engineering | ETL / ELT, Data Cleaning, Data Validation |
| APIs | REST APIs |
| Mobile Data | Google Play Developer Reporting API, App Store Connect API |
| Authentication | OAuth 2.0, JWT |
| Database | PostgreSQL |
| Backend | Supabase |
| Workflow Automation | n8n |
| Artificial Intelligence | OpenAI GPT, Claude / Anthropic |
| AI Techniques | LLMs, Prompt Engineering, Generative AI |
| Reporting | HTML, CSS, PDF, PowerPoint |
| Communication | Gmail API, Slack API |
| Infrastructure | Docker, Cloud |
| Version Control | Git, GitHub |
| Data Modeling | Star Schema, UML, Business Intelligence |

---

# 🔄 Example Weekly Workflow

A typical weekly execution can follow this sequence:

```text
Monday Morning
      │
      ▼
Collect Google Play Data
      │
      ▼
Collect App Store Data
      │
      ▼
Clean & Validate
      │
      ▼
Store in PostgreSQL
      │
      ▼
Calculate KPIs
      │
      ▼
Compare with Previous Period
      │
      ▼
Detect Anomalies
      │
      ▼
Generate AI Analysis
      │
      ├───────────────┐
      │               │
      ▼               ▼
Generate PDF      Generate PPTX
      │               │
      └───────┬───────┘
              ▼
        Email / Slack
```

The objective is to make the reporting cycle reproducible and automated.

---

# 🌟 Key Features

- ✅ Automated mobile data ingestion
- ✅ Google Play integration
- ✅ App Store integration
- ✅ Data cleaning and validation
- ✅ Historical data storage
- ✅ PostgreSQL database
- ✅ Supabase backend
- ✅ Star Schema data model
- ✅ KPI computation
- ✅ Anomaly detection
- ✅ Generative AI analysis
- ✅ AI-powered recommendations
- ✅ Prompt Engineering
- ✅ Automated HTML reports
- ✅ Automated PDF reports
- ✅ Automated PowerPoint generation
- ✅ Automated email summaries
- ✅ Slack distribution
- ✅ n8n workflow orchestration
- ✅ Docker-based architecture
- ✅ OAuth 2.0 authentication
- ✅ JWT authentication
- ✅ Row Level Security


---

# 📚 Methodology

The project follows a structured engineering methodology:

```text
1. Problem Identification
        ↓
2. Requirements Analysis
        ↓
3. Technology Study
        ↓
4. Architecture Design
        ↓
5. Data Modeling
        ↓
6. Pipeline Implementation
        ↓
7. AI Integration
        ↓
8. Workflow Automation
        ↓
9. Security Implementation
        ↓
10. Testing
        ↓
11. Validation
        ↓
12. Results Analysis
```

The project includes software design and Business Intelligence modeling approaches such as:

- UML
- Star Schema
- data modeling
- workflow modeling
- API architecture
- Cloud architecture


## LLM Variability

Generative AI can produce variable outputs.

Structured prompts, controlled inputs and validation mechanisms are therefore necessary.


## Scalability

For a very large portfolio of applications, additional engineering could be required around:

- distributed processing
- workload management
- caching
- partitioning
- observability
- cost optimization

## Data Governance

A production implementation would require additional governance around:

- data retention
- access control
- audit logs
- monitoring
- privacy
- credential rotation


# 🧪 Portfolio Demonstration

The public version can reproduce the complete architecture using synthetic or public-safe data:

```text
Sample Mobile Data
        ↓
Python Ingestion
        ↓
Data Cleaning
        ↓
Supabase / PostgreSQL
        ↓
KPI Calculation
        ↓
Anomaly Detection
        ↓
LLM Analysis
        ↓
Report Generation
        ↓
PDF / PPTX / Email
        ↓
Slack
```

This allows the technical concepts to be demonstrated without exposing confidential information.

---

# 🎓 Academic Project

This project was developed as part of a Master's final-year project.

### Project Title

> **Conception et développement d'une plateforme intelligente d'automatisation du reporting analytique des applications mobiles**

The project combines:

- Data Engineering
- Business Intelligence
- Cloud Computing
- Generative AI
- Workflow Automation
- API Integration
- Data Warehousing
- Automated Reporting

---

# 👩‍💻 Author

## Balsam Bendhif
