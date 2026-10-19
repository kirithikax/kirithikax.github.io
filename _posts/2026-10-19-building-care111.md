---
title: 'Building CARE111: Translating Frontline Triage into a Python Decision Engine'
date: 2026-10-19
permalink: /posts/2026/10/building-care111/
tags:
  - Clinical AI
  - Triage Systems
  - Python
  - Active Project
---

In high-pressure emergency triage environments like the NHS 111 service, time and accuracy are critical. One persistent operational bottleneck occurs when calls originate from care home staff regarding residents who present without specific, easily categorised symptoms, yet require assessment. While care workers often have accurate vital signs readily available, standard symptom-based triage algorithms can struggle to rapidly process these raw numbers into an immediate escalation decision. 

To address this, we are currently developing **CARE111**—an active computational decision-support system designed to ingest raw clinical observations from care workers, calculate risk using established medical frameworks, and immediately flag patients requiring urgent clinician review.

### The Clinical Logic and Parameters
The core function of CARE111 evaluates whether a patient's vital signs deviate significantly from their established baselines or standard acceptable ranges. The system processes six primary observations: Respiration Rate, Oxygen Saturations (SpO₂), Systolic Blood Pressure, Pulse Rate, Level of Consciousness, and Temperature.

Rather than looking at these metrics in isolation, the architecture applies a dual-evaluation method. First, it integrates the **NEWS2** framework to assign a clinical deterioration score. Second, it runs a comparative baseline analysis. For example, while a respiration rate of 22 might only trigger a moderate alert in a healthy adult, CARE111's logic flags a critical warning if the patient's baseline is typically 10-11. 

### Current Development and Next Steps
This project is currently in active development. I am collaborating with Quine Schuuring to comprehensively map observation combinations—including edge cases where only a single parameter is severely out of range. 

We are translating these clinical heuristics into a deterministic Python decision-engine. To ensure clinical validity, our hypotheses are undergoing rigorous review with a panel of practising clinicians across general practice and paediatrics (including Dr. Isaiah See, Dr. Minsari Ogega, Dr. Siddiq Shirgaonkar, and Dr. Angela Wang). Once the clinical logic is refined, the Python engine will be deployed as an open-source repository, laying the groundwork for a future predictive model.
