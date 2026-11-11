# Beyond Triage: Evaluating Clinical History for Capacity-Constrained Emergency Care Prioritisation

## Research question

Does adding prior healthcare-utilisation information to current-visit features improve the ranking of emergency-department visits by likelihood of hospital admission, particularly when only a limited proportion of visits can be prioritised for further assessment?

## Motivation

Emergency departments operate under capacity constraints, making it important to understand how available clinical information relates to hospital admission. This project examines whether historical healthcare-utilisation variables add useful predictive information beyond features recorded during the current visit.

The analysis evaluates predictive performance and admission capture at different prioritisation capacities. The objective is to assess the incremental value of historical information, not to develop a clinical triage tool.

## Approach

- Prepare and inspect emergency-department visit data.
- Compare a current-visit feature model with a model that also includes historical healthcare-utilisation features.
- Evaluate discrimination using ROC-AUC and average precision.
- Assess probability predictions using Brier score and log loss.
- Compare the proportion of admissions captured when prioritising the highest-ranked 10%, 20% and 30% of visits.
- Estimate uncertainty in differences between models using paired bootstrap analysis.

## Preliminary findings

On the current held-out test set, the model incorporating historical information achieved a ROC-AUC of 0.8754, compared with 0.8685 for the current-visit model. At 20% and 30% prioritisation capacity, the historical-information model captured approximately 0.97 and 1.30 percentage points more admissions, respectively. The estimated difference at 10% capacity was smaller, and its confidence interval included zero.

These are preliminary results. Their interpretation depends on verifying dataset provenance, predictor availability at the intended prediction time, and the independence assumptions underlying validation and uncertainty estimates.

## Limitations and ongoing work

- Verify the original dataset source, definitions and documentation.
- Assess potential predictor leakage and whether all features would be available at the intended prediction time.
- Investigate whether repeated patients are present and whether validation should account for patient-level grouping.
- Consolidate duplicated analyses and improve reproducibility.
- Re-run the complete notebook from a fresh runtime before reporting final results.

## Scope and intended use

This is a retrospective predictive-modelling study using existing data. Hospital admission is the outcome being predicted; it is not a direct measure of clinical urgency, patient benefit or the quality of triage decisions. The results should not be interpreted as evidence that the model is ready for clinical deployment.
