**#Intergenerational Malnutrition Analysis: India NFHS-5**


A comprehensive epidemiological analysis examining intergenerational biological gradients in maternal-child nutritional outcomes across 29 Indian states using National Family Health Survey (NFHS-5) data.
🎯 Overview
This project investigates the Developmental Origins of Health and Disease (DOHaD) hypothesis through ecological analysis of:

Maternal nutritional status (underweight, central obesity via WHR)
Child nutritional outcomes (stunting, wasting)
Maternal anaemia prevalence (indicator of nutritional stress)
Thin-Fat Index (TFI) - an ecological proxy for maternal metabolic stress

The analysis employs state-level data aggregation, descriptive statistics, regression modeling, and mediation analysis to establish relationships between maternal metabolic phenotypes and intergenerational nutritional outcomes.
📊 Research Objectives
Objective 1: Descriptive Landscape
Characterize the distribution of maternal underweight, central obesity, and thin-fat index across states
Examine maternal anaemia and child stunting prevalence
Assess state-level correlations between indicators
Objective 2: Intergenerational Biological Gradient
Quantify child stunting prevalence across three maternal BMI categories:
Underweight (BMI <18.5)
Normal (BMI 18.5–24.9)
Overweight/Obese (BMI ≥25.0)
Calculate relative risk (RR) estimates
Perform Kruskal-Wallis and Mann-Whitney U tests with Bonferroni correction
Objective 3: Ecological Predictors of TFI
Multiple OLS regression with robust (HC3) standard errors
Assess child stunting, maternal anaemia, rurality, and education as predictors
Perform variance inflation factor (VIF) analysis for multicollinearity
Objective 4: DOHaD Mediation Analysis
Test indirect pathways: Maternal Anaemia → Child Stunting → TFI
Baron-Kenny pathway analysis
Sobel test for indirect effects
Bootstrap mediation analysis (5000 iterations) via Pingouin
📁 Project Structure
intergenerational-malnutrition-india/

intergenerational-malnutrition-india/
│
├── README.md                                          # Project overview & guide
├── requirements.txt                                   # Python dependencies
├── LICENSE                                            # MIT License
├── .gitignore                                         # Git ignore file
│
├── code/
│   └── intergenerational_malnutrition_analysis.py     # Main analysis script
│
├── data/
│   ├── NFHS5_data_dictionary.csv                      # (Optional) Variable definitions
│   └── README_data.md                                 # Data source documentation
│
├── outputs/
│   ├── figures/
│   │   ├── Figure1_Objective1_Descriptive.png
│   │   ├── Figure2_Objective2_StuntingByBMI.png
│   │   ├── Figure3_Objective3_Regression_Scatter.png
│   │   ├── Figure3b_Objective3_CoefficientPlot.png
│   │   ├── Figure4_Objective4_Mediation.png
│   │   └── Figure5_Supp_BubbleChart.png
│   │
│   └── results/
│       └── NFHS5_Malnutrition_Analysis_Results.xlsx
│
├── docs/
│   ├── METHODOLOGY.md                                 # Statistical methods
│   ├── RESULTS_SUMMARY.md                             # Key findings
│   └── TROUBLESHOOTING.md                             # Common issues & fixes
│
└── .github/
    └── workflows/
        └── (Optional: CI/CD workflows)



  🛠️ Requirements
Python Version
Python 3.8+
Dependencies
pandas>=1.3.0

numpy>=1.20.0

matplotlib>=3.3.0

seaborn>=0.11.0

scipy>=1.7.0

statsmodels>=0.13.0

pingouin>=0.5.0

openpyxl>=3.6.0
System Requirements
OS: Windows / macOS / Linux
RAM: Minimum 2GB (recommended 4GB+)
Disk Space: ~500MB for data and outputs
🚀 Getting Started
1. Clone the Repository
git clone https://github.com/yourusername/intergenerational-malnutrition-india.git

cd intergenerational-malnutrition-india
2. Install Dependencies
pip install -r requirements.txt
3. Prepare Your Data
Place the following Excel files in your data directory:

C:\Users\[Your Username]\OneDrive\Desktop\New folder (5)\

├── BMI - Copy.xlsx

├── WHR.xlsx

├── Prevalence of anaemia in adults.xlsx

├── Prevalence of anaemia in children.xlsx

├── Nutritional status of children.xlsx

└── Antenatal care indicators.xlsx

Expected Column Structure (will be renamed automatically):

BMI - Copy.xlsx: State, Var, SubVar, pct_thin, pct_mild_thin, pct_mod_sev_thin, pct_ow_obese, pct_ow, pct_obese, N
WHR.xlsx: State, Var, SubVar, pct_whr_normal, pct_whr_high, N
Prevalence of anaemia in adults.xlsx: State, Var, SubVar, pct_anaemia_mild, pct_anaemia_mod, pct_anaemia_sev, pct_anaemia_any, N
Prevalence of anaemia in children.xlsx: State, Var, SubVar, pct_child_anaemia_mild, pct_child_anaemia_mod, pct_child_anaemia_sev, N
Nutritional status of children.xlsx: State, Var, SubVar, pct_stunting, N_stunt, pct_wasting, pct_child_ow, N
4. Update File Paths
Edit lines 21-24 in the Python script:

DATA_DIR = r"C:\Users\[Your Username]\OneDrive\Desktop\New folder (5)/"

OUT_DIR  = r"C:\Users\[Your Username]\OneDrive\Desktop\New folder (5)\outputs/"

For macOS/Linux:

DATA_DIR = "/Users/[Your Username]/Desktop/data/"

OUT_DIR  = "/Users/[Your Username]/Desktop/outputs/"
5. Run the Analysis
python intergenerational_malnutrition_analysis.py

The script will:

✅ Load and process NFHS-5 data
✅ Perform descriptive statistics
✅ Conduct statistical tests (Kruskal-Wallis, Mann-Whitney U)
✅ Fit OLS regression models
✅ Execute mediation analysis
✅ Generate 5 publication-ready figures (PNG, 180 DPI)
✅ Export results to Excel workbook
📈 Key Outputs
Console Output
=======================================================================

 MASTER DATASET — 29 Indian States (NFHS-5)

=======================================================================

[State-level summary statistics table]

=======================================================================

 ANALYSIS COMPLETE — SUMMARY OF KEY FINDINGS

=======================================================================

OBJECTIVE 1 (Descriptive Landscape):

  • Maternal underweight: X.X% (±X.X) — range X.X–X.X%

  • Central obesity (WHR≥0.85): X.X% (±X.X)

  ...

[Results for Objectives 2, 3, 4]
Excel Report (Multi-sheet)
Master_State_Dataset - State-level summary (29 states, 10 variables)
Obj1_Descriptive_Stats - Shapiro-Wilk tests, normality assessment
Obj2_Stunting_by_BMI - Weighted stunting by maternal BMI category
Obj2_Mann_Whitney_Tests - Pairwise comparisons (p-values, effect sizes)
Obj2_Relative_Risk - RR estimates with interpretation
Obj3_Regression_Results - β, 95% CI, standardized coefficients, p-values
Obj3_VIF - Variance inflation factors for multicollinearity check
Obj4_BK_Mediation - Baron-Kenny pathway summary
Obj4_Bootstrap_Mediation - Bootstrap CI for indirect/direct/total effects
Visualizations (High-resolution PNG, 180 DPI)
Figure 1: Horizontal bar charts of state indicators + correlation heatmap
Figure 2: Country-level stunting by maternal BMI + state-level box plots
Figure 3: 4-panel scatter plots showing TFI associations
Figure 3b: Forest plot of regression coefficients
Figure 4: DOHaD pathway diagram + bootstrap mediation forest plot
Figure 5: Bubble chart of ecological associations
🔍 Methodological Notes
Statistical Tests
Normality: Shapiro-Wilk test
Group Comparisons: Kruskal-Wallis (K≥3), Mann-Whitney U (K=2)
Multiple Testing Correction: Bonferroni (α' = 0.05/3 for pairwise tests)
Regression: OLS with HC3 robust standard errors (heteroscedasticity-consistent)
Multicollinearity: VIF > 5 indicates concern
Mediation Framework
Maternal Anaemia (X)

        ↓ (path a)

    Child Stunting (M)

        ↓ (path b)

    Thin-Fat Index (Y)

        ↑_________________

        (direct effect c')

Indirect Effect (ACME) = a × b
Direct Effect (c') = relationship after accounting for M
Total Effect (c) = c' + (a × b)
Proportion Mediated = (ACME / Total Effect) × 100%
Data Aggregation
Input: SubVar-level (Rural/Urban, Education strata, etc.) prevalence percentages and sample sizes
Process: Convert percentages to counts → aggregate by state → recalculate weighted percentages
Output: State-level indicators suitable for ecological analysis
