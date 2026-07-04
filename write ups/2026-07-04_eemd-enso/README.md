Date: 2026-07-04

This folder contains the focused follow-up analysis on ENSO/Nino3 and PADD regional gasoline. The analysis uses the decomposed gasoline target, not raw gasoline prices:

Below are some of the results I got following our last meeting. I worked with the decomposed PADD regional gasoline and ENSO/Nino3.
I used cpc_nino3_sst as the ENSO predictor and I fliipped it to obtain positive correlation instead of negative. 
Then the following analysis was done:

1. Compared flipped Nino3 and EEMD gasoline side by side at 0, 8, and 9 month ENSO leads
ENSO/gasoline timing:
- `nino3_overlay_lead0.png`
- `nino3_overlay_lead8.png`
- `nino3_overlay_lead9.png`
- `nino3_lead_lag.png`

2. Calculated gasoline autocorrelation to test whether the decomposed gasoline process has memory
Autocorrelation figures checks:
- `autocorr.png`
- `autocorr_table.png`

3. Built rolling AR1 models and compared them with AR1 plus flipped Nino3 at 8 and 9-month leads.
AR figures:
- `ar1_baseline_gain.png`
- `ar1_enso_gain.png`
- `ar1_predictions.png`
- `ar1_coeffs.png`


The AR1 baseline uses only the previous month of to predict `gasoline(t) = c + a*gasoline(t-1)`:
The ENSO added modeled includes flipped Nino3 at 8 or 9 months `gasoline(t) = c + a*gasoline(t-1) + b*flipped_nino3(t-lead)`
The model effectiveness was measured using rolling out-of-sample 24-month prediction windows and RMSE.
AR1 improved RMSE by about 37.8-44.0% compared with the rolling average baseline showing the EEMD gasoline component has meaningful short-run memory
Adding flipped Nino3 at an 8-month lead improved RMSE beyond AR1 by about 1.7-6.5%, depending on the region. This suggests ENSO may add modest information beyond gasoline's own short-run persistence.
