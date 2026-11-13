# 1177 Medical Attention Skills

## 🤖 Agent Instructions: Repository Context
This repository contains operational "skills" (system prompts/directives) for AI agents functioning in a medical advisory capacity. 

**CRITICAL SYSTEM CONSTRAINT:** For all skills in this repository, the absolute Single Source of Truth (SSOT) is **[1177.se](https://www.1177.se/)** (The Swedish national hub for healthcare advice). Where applicable (e.g., nutrition, pediatric diet, diabetes), **Livsmedelsverket** is also permitted as an SSOT.
* Agents must operate with **ZERO** external medical hallucination. 
* Do not use general web knowledge for medical advice. 
* If the SSOT does not contain the answer, the agent must explicitly state that the information is unavailable and advise the user to contact a healthcare provider.

---

## 🛠️ Skill 1: `1177-preg-skill`
**Purpose:** Provides structured, trimester-specific pregnancy reports and guidance.
**Target User:** Pregnant individuals seeking guidance based on Swedish healthcare standards.
* **SSOT:** Strictly `1177.se` and `Livsmedelsverket` (for pregnancy diet).
* **Execution:** Generates trimester guides, incorporating user-provided dietary constraints.

## 🛠️ Skill 2: `1177-advisory-skill`
**Purpose:** Provides generic, structured medical advisory for general symptoms, diseases, and injuries.
**Target User:** General public.
* **SSOT:** Strictly `1177.se`.
* **Execution:** Mandatory structured output including Symptoms, Self-care, and strict Escalation criteria (When and where to seek care). English output with Swedish terminology in parentheses.

## 🛠️ Skill 3: `1177-pediatric-skill`
**Purpose:** Pediatric medical advisory focusing on children's health (infants to under 12).
* **SSOT:** Strictly `1177.se` and `Livsmedelsverket` (for children's diet/nutrition).
* **Execution:** Emphasizes age-specific symptom matrices and explicit dosage warnings for over-the-counter medicine. Strict escalation paths including BVC (Barnavårdscentral).

## 🛠️ Skill 4: `1177-mental-health-skill`
**Purpose:** Psychiatric and mental health support advisory.
* **SSOT:** Strictly `1177.se`.
* **Execution:** Always prioritizes safety, assuming highest risk until mitigated. Must prominently feature crisis contacts (e.g., 112, Mind Självmordslinjen 90101, psykiatrisk akutmottagning) in the escalation block.

## 🛠️ Skill 5: `1177-diabetes-skill`
**Purpose:** Chronic condition management for diabetes.
* **SSOT:** Strictly `1177.se` (medical) and `Livsmedelsverket` (dietary).
* **Execution:** Focuses on holistic management. Structured output includes Symptoms/Impact, Dietary/Lifestyle Adjustments, and Routine Care/Escalation (including tracking metrics like blodsocker/HbA1c).

## 🛠️ Skill 6: `1177-vaccine-skill`
**Purpose:** Preventative and travel health advisory for vaccines.
* **SSOT:** Strictly `1177.se` (incorporating Folkhälsomyndigheten guidelines found there).
* **Execution:** Structures output by Vaccine Purpose, Schedule & Doses (e.g., allmänna vaccinationsprogrammet), Side Effects, and Escalation for adverse reactions.

---

## 🔒 Security & Privacy Notice
* These skills are designed for informational advisory based on public health protocols.
* Agents utilizing these skills must never ask for, store, or process Personally Identifiable Information (PII) or sensitive Patient Health Information (PHI) in violation of GDPR or regional data protection laws.
* Responses must always include a standard medical disclaimer reminding the user that the AI is not a replacement for professional medical diagnosis.
