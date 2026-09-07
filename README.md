# Replication Materials

This repository contains the Python Jupyter notebooks used to construct the dataset and reproduce the analyses reported in the accompanying study of a curriculum-grounded retrieval-augmented generation (RAG) AI tutor in higher education.

## Study overview

The study examines patterns of student interaction with a curriculum-grounded RAG tutor, including AI-use intensity, course engagement, homework copying, course relevance, and academic performance.

The analytical dataset contains 140 enrolled students, of whom 44 registered for and used the AI tutor, generating 990 question–answer interactions.

The analyses include descriptive statistics and three OLS regression models examining:

1. the relationship between AI-tutor use and academic performance during the incentivized period;
2. the relationship between AI-tutor use and broader course engagement; and
3. the relationship between voluntary, post-incentive AI use and subsequent academic performance.

All regression models use HC3 heteroskedasticity-robust standard errors.

## Repository structure

The notebooks should be executed in the following order:

### 1. `1_database_build_pub.ipynb`
Constructs the initial chat-level database from the raw chat logs. The notebook reconstructs question–answer pairs, removes unmatched and duplicate observations, links anonymized student identifiers to assessment data, and creates the initial chat-level variables.

### 2. `2_profiles_times.ipynb`
Creates student-level temporal usage measures and classifies AI users into non-user, occasional, and regular user profiles. It also calculates usage by study period and identifies examination-related and post-incentive activity.

### 3. `3_homework_flag.ipynb`
Identifies copied homework submissions using text-matching procedures and applies the documented manual corrections. It subsequently creates student-level measures of homework-copying behavior.

### 4. `4_user_level.ipynb`
Aggregates the chat-level information to the student level and combines AI-use measures with course assessment and engagement data.

### 5. `5_descriptive_analysis_pub.ipynb`
Produces the descriptive analyses reported in the study, including query-category distributions, question and answer lengths, user-profile comparisons, temporal usage patterns, course engagement, and academic performance.

### 6. `6_regression_analysis_pub.ipynb`
Estimates the three final OLS regression models, conducts robustness checks, and performs regression diagnostics including heteroskedasticity, residual normality, autocorrelation, multicollinearity, and residual-versus-fitted analyses.

## Data availability

The underlying student-level data, including chat logs and academic assessment data, are not publicly included in this repository because they contain confidential information relating to individual students.

The notebooks therefore document the complete data-processing and analysis workflow, while the original input data and certain intermediate files are withheld.

The final analytical results reported in the study were generated from the data described in the accompanying article.

## Reproducibility

The notebooks are provided in execution order so that the complete analytical workflow can be followed from database construction through descriptive and regression analyses.

Some intermediate files used during data preparation were created during the data-cleaning and anonymization process and are not included in the public repository. Consequently, the repository should be understood as a documented replication package rather than a fully self-contained reproduction environment.

## Software

The analyses were conducted in Python using standard scientific computing and statistical libraries, including:

- pandas
- numpy
- scipy
- statsmodels
- scikit-learn
- matplotlib
- seaborn
- openpyxl

## Anonymization

All student identifiers used in the analytical workflow are anonymized. No directly identifying student information is included in the repository.
