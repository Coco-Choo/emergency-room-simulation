# 🚑 Emergency Room Simulation – Discrete Event Simulation (DES)

## 📘 Case Study Overview

This project models and analyzes patient flow in an Emergency Room using **Discrete Event Simulation (DES)**. The simulation captures the dynamics of patient triage, priority levels, waiting time, doctor utilization, and treatment stages for two types of patients:  
- **NIA** (Need Immediate Attention)  
- **CW** (Can Wait)

The goal is to simulate 20 days of continuous ER operations and evaluate how process changes affect **waiting times**, **flow times**, and **doctor utilization**.

---

## 🏥 Simulation Logic

### 👩‍⚕️ Patient Arrival
- Patients arrive randomly (based on collected real-world weekday data of 100 patients).
- Each patient is classified as:
  - **NIA** (priority level 3)
  - **CW** (priority level 1)

### 🔁 Treatment Process

| Patient Type | Phase 1                  | Priority Shift | Phase 2                   |
|--------------|--------------------------|----------------|---------------------------|
| **NIA**      | 40 ± 30 min treatment    | ↓ to priority 2| 30 ± 20 min final care    |
| **CW**       | 15 ± 10 min treatment    | ↑ to priority 2| 10 ± 5 min final care     |

- All patients share one treatment queue.
- Patients with priority 2 (after first treatment) compete with new arrivals.
- Doctors are interchangeable — either can treat any patient at any phase.

---

## ⚙️ Simulation Setup

- Simulated for: **20 days (24 hours/day)**
- Patients: **100 (based on real-world data)**
- Simulation Tool: *R*
- Priority-based queue discipline

---

## 📊 Analysis Objectives

1. Analyze the impact of queue structure and priority rules on **waiting time**
2. Measure **average flow-time** for NIA and CW patients, before and after suggested improvements
3. Evaluate **doctor utilization** and suggest changes to balance workload

---

## 🔍 Key Results

| Metric                          | Before Optimization | After Optimization |
|---------------------------------|---------------------|--------------------|
| Avg Flow Time (NIA)             | 357 minutes         | 72.1 minutes       |
| Avg Flow Time (CW)              | 35 minutes          | 29.2 minutes       |
| Avg Doctor Utilization (%)      | Approx. 100%        | Approx. 60%        |
| Avg Wait Time (minutes)         | 12.1(CW), 292(NIA)  | 4.03(CW), 2.28(NIA)|

---

## ✅ Suggestions for Improvement

- Implementing dynamic doctor allocation strategies to adjust staffing based on real-time demand.
- Refining patient prioritization criteria to ensure that high-urgency cases receive immediate attention.
- Redistributing workloads among available doctors to enhance operational efficiency.

---
