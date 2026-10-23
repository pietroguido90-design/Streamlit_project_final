# 📊 Vanguard A/B Test Interactive Dashboard

An executive-grade, interactive Streamlit application designed to analyze user behavior, conversion funnels, onboarding friction, and statistical significance for the **Vanguard A/B Experiment**.

---

## 📌 Executive Summary

Vanguard conducted an A/B experiment to evaluate whether a redesigned user interface (UI) could improve completion rates in their online investment process. 

* **Business Target:** Achieve a minimum **+5.0 percentage point increase** in completion rate over the Control group to make the redesign cost-effective.
* **Key Finding:** The Test UI achieved a completion rate of **69.29%** compared to **65.58%** in the Control group (+3.71 percentage point uplift).
* **Statistical Significance:** A Two-Sample Z-Test confirms the lift is statistically significant ($Z = 9.7871$, $p < 0.0001$).
* **Business Recommendation:** **Do not roll out the current version yet.** Although conversion increased, it fell short of the 5.0 percentage point threshold ($1.29\%$ gap) due to severe friction and backward navigation at **Step 1**.

---

## 🚀 Key Features of the Dashboard

This Streamlit application provides a comprehensive suite of analytical tools organized into interactive tabs:

1. **🏆 Completion Rate (Main KPI):** 
   * Side-by-side comparison of Control vs. Test completion rates.
   * Includes a dynamic **5.0 percentage point target threshold line** ($70.58\%$).
2. **📉 Funnel Analysis:** 
   * Tracks client retention percentage across each sequential process step (`Start` ➔ `Step 1` ➔ `Step 2` ➔ `Step 3` ➔ `Confirm`).
3. **🔀 Sankey Navigation Flow:** 
   * Interactive Sankey diagram mapping real step-to-step user transitions, highlighting forward navigation vs. backward loops.
4. **⏱️ Time-on-Step Analysis:** 
   * Evaluates median seconds spent on each step, revealing that users spend **23% longer on Step 1** in the Test UI.
5. **⚠️ Error Rate Analysis:** 
   * Measures backward navigation events per step, exposing a spike in return trips to `Start` from `Step 1` (**19.05% in Test vs. 10.86% in Control**).
6. **👥 Demographics & Drop-off Heatmap:** 
   * Features a step-by-step drop-off rate heatmap grouped by client age brackets (`Under 35`, `35-49`, `50-64`, `65+`).
   * Built-in dynamic **Two-Sample Z-Test calculator** for hypothesis validation.

---

## 🛠️ Tech Stack & Dependencies

* **Language:** Python 3.9+
* **Dashboard Framework:** [Streamlit](https://streamlit.io/)
* **Data Processing:** [Pandas](https://pandas.pydata.org/), [NumPy](https://numpy.org/)
* **Data Visualization:** [Plotly Express & Plotly Graph Objects](https://plotly.com/python/)
* **Statistical Analysis:** [SciPy (stats)](https://scipy.org/)

---

## 📂 Repository Structure

```text
├── Version4.py                 # Main Streamlit application script
├── vanguard_tableau_final.csv  # Preprocessed experiment dataset
├── requirements.txt            # Python dependencies list
└── README.md                   # Project documentation
```

---

## 🔧 Installation & Local Setup

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/vanguard-ab-test-dashboard.git
cd vanguard-ab-test-dashboard
```

### 2. Create and Activate a Virtual Environment
```bash
# macOS/Linux
python3 -m venv venv
source venv/bin/activate

# Windows
python -m venv venv
venv\Scripts\activate
```

### 3. Install Dependencies
Create a `requirements.txt` file containing:
```text
streamlit
pandas
numpy
plotly
scipy
```
Then run:
```bash
pip install -r requirements.txt
```

### 4. Run the Streamlit Application
```bash
streamlit run VanguardsAPP.py
```
The dashboard will open automatically in your browser at `http://localhost:8501`.

---

## 💡 Key Business Recommendations

1. **Refine Onboarding Usability (Step 1):** Simplify the instructions and layout on `Step 1` to eliminate cognitive load and prevent users from returning to `Start`.
2. **Targeted UX Redesign for Senior Clients:** Address high late-stage drop-offs in the `65+` demographic ($17.2\%$ drop-off at confirmation).
3. **Re-Test Against Threshold:** Run a follow-up A/B experiment after modifying `Step 1` to verify if the revised interface reaches the required **70.58% (+5.0 pp)** feasibility threshold.

---

## 👤 Author

* **Simonpietro Guido**
* **Pariya Lakani**
* **Yurii Slobodchukov**
* Data Analytics Bootcamp Project
