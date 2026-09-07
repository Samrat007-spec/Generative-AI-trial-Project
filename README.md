# Generative-AI-trial-Project
Resume–Job Description Compatibility AI

An intelligent Applicant Tracking System (ATS) and recruiter-assistance solution that evaluates how well a candidate's resume matches a job description. The system uses semantic understanding to assess skills, tools, experience, responsibilities, education, and domain relevance—going beyond simple keyword matching.

Overview

The Resume–Job Description Compatibility AI converts unstructured resume and job-description text into structured HR insights. It identifies exact and semantic matches, highlights critical gaps, calculates multi-dimensional compatibility scores, and produces actionable recommendations for candidates and recruiters.

Key Features

Extracts structured information from resumes and job descriptions

Detects exact, semantic, missing, and transferable skills

Evaluates experience depth, relevance, recency, and domain alignment

Compares past responsibilities with role expectations

Calculates transparent ATS-style compatibility scores

Generates recruiter-focused strengths, concerns, and hiring insights

Recommends resume improvements, projects, skills, and certifications

Suggests improvements to vague or overloaded job descriptions

Produces clean, machine-readable JSON for application integration

Generates a professional HR-style final report

Analysis Workflow

Structured Data Extraction – Parses the resume and job description.

Semantic Matching – Compares related concepts instead of relying only on identical keywords.

Skill Similarity Analysis – Scores related skill pairs from 0.0 to 1.0.

Compatibility Scoring – Measures skill, experience, responsibility, and domain fit.

Recruiter Insights – Summarizes strengths, risks, achievements, and mismatches.

Candidate Recommendations – Suggests practical ways to improve suitability.

HR Recommendations – Identifies unclear, unnecessary, or mismatched JD requirements.

Final Report – Produces a complete professional evaluation.

Input Format

RESUME:
[Paste the complete candidate resume here]

JOB DESCRIPTION:
[Paste the complete job description here]

Both the resume and job description are required. If either input is missing or unclear, the system should request clarification before generating a score.

Output Schemas

1. Structured Data Extraction

{
  "resume": {
    "skills": [],
    "tools": [],
    "experience_years": "",
    "domain": "",
    "responsibilities": [],
    "education": "",
    "certifications": [],
    "achievements": []
  },
  "jd": {
    "required_skills": [],
    "preferred_skills": [],
    "tools": [],
    "domain": "",
    "responsibilities": [],
    "experience_required": "",
    "education_required": ""
  }
}

2. Semantic Skill and Experience Matching

{
  "matching_skills": [],
  "semantic_matches": [],
  "missing_skills": [],
  "transferable_skills": [],
  "responsibility_match": [],
  "domain_match": "",
  "domain_gap": ""
}

3. Skill Similarity Analysis

{
  "skill1": "",
  "skill2": "",
  "similarity_score": "0.0 - 1.0",
  "reasoning": "",
  "substitutable": "Yes/No"
}

For multiple comparisons, return an array of skill-similarity objects.

4. Compatibility Scoring

{
  "skill_score": "",
  "experience_score": "",
  "responsibility_score": "",
  "domain_score": "",
  "overall_score": "",
  "assessment_summary": ""
}

Scoring Model

The overall evaluation considers:

Skill relevance and demonstrated depth

Tools and technologies

Relevant professional and project experience

Domain exposure

Responsibility alignment

Communication, problem-solving, and other soft skills

Score

Fit Level

0–39

Poor Fit

40–59

Partial Fit

60–74

Good Fit

75–89

Strong Fit

90–100

Excellent Fit

Scores should be evidence-based. Missing resume evidence must not be treated as confirmed experience.

Example Job Description

Role: Data Scientist

The target role involves analyzing complex structured and unstructured datasets, cleaning and preprocessing data, conducting exploratory data analysis, building and deploying machine-learning models, and communicating business insights. Core requirements include Python or R, SQL, statistics, probability, hypothesis testing, predictive modeling, model evaluation, and visualization with tools such as Tableau, Power BI, or Matplotlib. Knowledge of regression, classification, clustering, time-series analysis, recommendation systems, and common data-science libraries is expected. Big-data, cloud-platform, and data-pipeline experience are valuable additions.

Final HR Report

The final report should contain:

Candidate Summary

Job Description Summary

Skills Match Breakdown

Experience Match

Responsibility Match

Missing Skills

Transferable Skills

Scoring Summary

Recruiter Insights

Candidate Recommendations

HR Recommendations

Recruiter Insights

The system generates five to eight concise insights covering:

Strongest evidence of suitability

Weak or unsupported areas

Hiring risks and concerns

Responsibility alignment

Quantified achievements

Critical technical or domain mismatches

Interview topics that require validation

Candidate Recommendations

Recommendations may include:

Missing technical or business skills to learn

Stronger, achievement-focused resume bullet points

Relevant portfolio project ideas

Role-aligned certification suggestions

ATS-friendly terminology and formatting

Tailoring guidance based on essential JD requirements

HR and JD Recommendations

The system can identify:

Vague or generic requirements

Responsibilities that need measurable scope

Unnecessary or conflicting tool requirements

Seniority and experience mismatches

Missing success metrics

More accurate and inclusive industry phrasing

Suggested Project Structure

resume-jd-compatibility-ai/
├── app.py
├── requirements.txt
├── README.md
├── src/
│   ├── extractor.py
│   ├── semantic_matcher.py
│   ├── scorer.py
│   ├── recommender.py
│   └── report_generator.py
├── prompts/
│   └── analysis_prompt.txt
├── examples/
│   ├── sample_resume.txt
│   ├── sample_jd.txt
│   └── sample_output.json
└── tests/
    └── test_pipeline.py

Recommended Technology Stack

Language: Python

Data processing: Pandas, NumPy

Semantic matching: Sentence Transformers or embedding APIs

Machine learning: Scikit-learn

NLP: spaCy or Transformers

API: FastAPI

Interface: Streamlit or React

Validation: Pydantic and JSON Schema

Testing: Pytest

Quality and Safety Rules

Use semantic evidence rather than keyword frequency alone.

Do not invent skills, education, achievements, or experience.

Distinguish required skills from preferred qualifications.

Explain every major score using resume evidence.

Avoid using protected personal characteristics in hiring recommendations.

Treat the evaluation as decision support, not an automatic hiring decision.

Return valid JSON whenever a JSON schema is requested.

If JSON validation fails, return corrected JSON only, without markdown or additional commentary.

Use Cases

Resume screening and candidate shortlisting

ATS compatibility analysis

Resume tailoring before job applications

Recruiter interview preparation

Candidate skill-gap analysis

Job-description quality review

Career coaching and portfolio planning

Disclaimer

This project is intended to support human decision-making. Final hiring decisions should be made by qualified reviewers using consistent, job-related criteria and appropriate legal and organizational policies.

License

Add the license appropriate for your project, such as the MIT License.

If you find this project useful, consider giving it a star on GitHub.
