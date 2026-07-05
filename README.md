# Heart Disease Security Audit 

A adversarial robustness audit of a Multi-Layer Perceptron (MLP) trained to predict heart disease, using a CaFA-inspired greedy attack on the UCI Cleveland Heart Disease dataset.

## What this project does

Trains a validated MLP classifier on clinical tabular data, then subjects it to three escalating adversarial attacks to evaluate the trade-off between **mathematical robustness** and **clinical plausibility**.

| Phase | Attack Type | AUC Result |
|-------|-------------|------------|
| Baseline | Clean model | 0.91 |
| Phase 2A | Naïve rule-based spoof (2 features, ±20%) | 0.91 — no degradation |
| Phase 2B | Unrestricted greedy search (3 features, 80% budget) | 0.20 — implausible |
| Phase 2C | Constrained CaFA-style attack (5 features, 5% × 5 steps) | 0.62 — **stealthy** |

**Key finding:** a strictly constrained, integer-rounded, distributed perturbation budget can covertly collapse model confidence while remaining clinically imperceptible.

---

## Files

- `Heart_Disease_Security_Audit_ZainabZahara.ipynb` — full pipeline, attacks, and evaluation
- `AI_for_Medicine_Project_ZainabZahara.pdf` — written report

---

## How to run

1. Open the notebook in Google Colab
2. Install dependencies: `pandas`, `scikit-learn`, `matplotlib`
3. Run all cells in order — `random_state=42` is set throughout

---

## Stack


Python · scikit-learn · pandas · matplotlib · Google Colab
