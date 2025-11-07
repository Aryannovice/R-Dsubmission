# R-Dsubmission
# Parametric Curve Estimation — Flam R&D Assignment

**Author:** Ayush Pandey — B.Tech CSE (AI), Amrita Vishwa Vidyapeetham

**Desmos (assignment) link:** [https://www.desmos.com/calculator/rfj91yrxob](https://www.desmos.com/calculator/rfj91yrxob)

---

## Required result (final unknowns)

These are the values required by the assignment (place them clearly at the top):

* **θ̂ = 29.58281377457789°** (0.5163175023707157 rad)
* **M̂ = −0.05** (hit lower bound)
* **X̂ = 55.013609464940664)

**Assignment metric:**

* **L₁ ≈ 25.401461375629392**

---

## Quick summary (minimal)

1. Loaded the CSV and computed the uniform parameter samples (t_k).
2. Derived a rotation identity that gives closed-form expressions for (X) and (M) from ((\theta,t)) — found this unstable for some samples due to log-domain/sign issues.
3. Formulated a bounded nonlinear least-squares problem and solved it using Levenberg–Marquardt (via `scipy.optimize.least_squares` with `method='trf'`) using an analytic Jacobian.
4. Verified results visually (plots) and numerically (RSS, (L_1), covariance diagnostics).

For detailed derivations, Jacobian, LM system, and diagnostics, **see the full report** (`report.pdf`).

---

## Files in this repository (important)

* `report.pdf` — full LaTeX report (derivations, formulas, diagnostics, and figures). **Read this for full methodology.**
* `README.md` — this file (summary + links).
* `code/fit_curve.py` — Python script implementing the fit (analytic Jacobian), plotting, and metrics.
* `colab/ParametricCurve_Fit.ipynb` — Google Colab notebook (interactive run & reproduce).
* `data/data.csv` — input CSV (if included; otherwise note dataset is omitted for privacy).
* `figures/` — saved plots: `curve_fit.png`, `residuals_vs_t.png`, `residual_hist.png`, `u_check.png`, `v_check.png`.
* `video/` — placeholder for short explanation video link (add Drive link below).

---

## Video explanation

A short (≈2 min) spoken explanation of motivation, choices (why LM + Jacobian), and step-by-step workflow will be provided here:

**Video link (add your Drive link):** `DRIVE_LINK_HERE`

(Ensure the Drive link is set to "Anyone with the link can view".)

---

## How to reproduce (quick)

You can run the Colab notebook or run locally.

### Google Colab (recommended)

Open and run: `colab/ParametricCurve_Fit.ipynb` — this runs end-to-end (load data → fit → plots → save results).

### Local (conda/venv)

```bash
git clone https://github.com/<your-username>/<repo>.git
cd <repo>
python3 -m venv venv
source venv/bin/activate   # or venv\Scripts\activate on Windows
pip install -r requirements.txt   # (numpy, scipy, pandas, matplotlib)
python code/fit_curve.py
# outputs saved in figures/ and fit_summary.csv
```

---

## Notes

* The minimal requirement of the assignment is the three unknowns above and the Desmos link; this README provides them up front so graders can see the required result immediately.
* The `report.pdf` contains full derivations and discussion if more detail is required.
* If the data CSV is not included due to privacy, the Colab notebook contains a small synthetic example and instructions to upload the CSV when grading.

---

## Contact

Ayush Pandey — ayush.pandey07@<your-email> (or link to LinkedIn: [https://www.linkedin.com/in/ayush-pandey07](https://www.linkedin.com/in/ayush-pandey07))

*End of README*
