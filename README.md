# Hormonal Therapy and Recurrence-Free Survival in Node-Positive Breast Cancer

A survival analysis of the German Breast Cancer Study Group 2 (GBSG2) data, investigating whether hormonal therapy (tamoxifen) is associated with longer recurrence-free survival in women with node-positive breast cancer, and whether this association remains after adjusting for baseline patient characteristics.

**Report:** [GBSG2_analysis.pdf](GBSG2_analysis.pdf)

## Data

686 patients from the GBSG2 study (Schumacher et al., 1994), available in the R package `TH.data`. The dataset includes treatment (hormonal therapy yes/no), recurrence-free survival time with censoring, and baseline characteristics: age, menopausal status, tumour size, tumour grade, number of positive lymph nodes, and progesterone and oestrogen receptor levels.

The dataset contains more patients than were randomised in the original trial, and treated patients were older and more often postmenopausal, so treatment cannot be assumed to be randomly assigned.

## Methods

- **Non-parametric analysis:** Kaplan–Meier estimation, median and three-year recurrence-free survival, and log-rank test.
- **Cox proportional-hazards regression:** unadjusted and adjusted models, with covariates selected in advance on clinical grounds.
- **Model checking:**
  - functional form of continuous covariates (martingale residuals), leading to log-transformation of positive nodes and progesterone receptor level;
  - proportional-hazards assumption (scaled Schoenfeld residuals), with a sensitivity analysis stratified by tumour grade;
  - influential observations (dfbeta residuals);
  - deviance residuals.

## Key results

| | Hazard ratio (95% CI) |
|---|---|
| Unadjusted | 0.69 (0.54 to 0.89) |
| Adjusted, final model | 0.69 (0.53 to 0.88) |
| Stratified model | 0.68 (0.53 to 0.88) |

- Hormonal therapy was associated with an estimated 31% lower hazard of recurrence. The estimate was stable across model specifications and sensitivity analyses.
- Three-year recurrence-free survival was 71% with hormonal therapy, compared with 61% without.
- Because treatment was not fully randomised, the results should be interpreted as an association rather than a causal effect.


## Author

James Stanford
