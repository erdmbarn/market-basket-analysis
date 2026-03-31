# Market Basket Analysis — BIL 476 Data Mining Project

**Student:** Erdem Baran (211101034)  
**Course:** BIL 476 — Data Mining, Spring 2026  
**TOBB University of Economics and Technology**

---

## Project Overview

This project applies market basket analysis to the UCI Online Retail dataset. Two frequent itemset mining algorithms, Apriori and FP-Growth, are compared in terms of runtime and scalability. Association rules are evaluated using five interestingness measures: support, confidence, lift, Kulczynski, and cosine.

**Key findings:**
- FP-Growth is up to 30× faster than Apriori at 1% minimum support
- Strongest rule: Regency Teacup set (lift = 24.12)
- Lift and support are nearly uncorrelated (r = −0.014)

---

## Dataset

**UCI Online Retail Dataset**  
URL: https://archive.ics.uci.edu/dataset/352/online+retail  
Also available on Kaggle: https://www.kaggle.com/datasets/jihyeseo/online-retail-data-set-from-uci-ml-repo

Download `Online Retail.xlsx` and place it in the same folder as the notebook before running.

---

## Requirements

Install all dependencies with:

```bash
pip install pandas numpy matplotlib seaborn mlxtend openpyxl scipy jupyter
```

**Tested with:** Python 3.10, mlxtend 0.23

---

## How to Run

1. Clone this repository:
```bash
git clone https://github.com/erdmbarn/market-basket-analysis.git
cd market-basket-analysis
```

2. Download the dataset and place `Online Retail.xlsx` in the project folder.

3. Open the notebook:
```bash
jupyter notebook market_basket_eda.ipynb
```

4. Run cells sequentially from top to bottom.

**Google Colab alternative:**  
Upload the notebook and dataset to Colab, then change `DATA_PATH` in Cell 2 to:
```python
DATA_PATH = '/content/Online Retail.xlsx'
```

---

## Repository Structure

```
market-basket-analysis/
├── market_basket_eda.ipynb       # Main analysis notebook
├── report_humanized.tex          # IEEE LaTeX report source
├── eda_overview.png              # EDA figures
├── top_products.png
├── basket_size_dist.png
├── apriori_vs_fpgrowth.png       # Algorithm comparison
├── rule_measures.png             # Interestingness measures scatter
├── measures_correlation.png      # Correlation heatmap
├── association_rules_results.csv # All discovered rules
└── README.md
```

---

## Notebook Sections

| Section | Content |
|---|---|
| 0 | Library imports |
| 1 | Dataset loading |
| 2 | Basic dataset info & missing values |
| 3 | EDA visualizations |
| 4 | Preprocessing pipeline (5 steps) |
| 5 | Transaction matrix construction |
| 6 | Apriori vs FP-Growth comparison |
| 7 | Association rules + Kulczynski/Cosine |
| 8 | Misleading rules analysis |
| 9 | Summary statistics & CSV export |

---

## Results Summary

| Metric | Value |
|---|---|
| Raw records | 541,909 |
| After preprocessing | 396,470 |
| UK transactions | 354,015 |
| Transaction matrix | 16,579 × 3,828 |
| Sparsity | 99.5% |
| Frequent itemsets (support=2%) | 239 |
| Association rules (lift≥1) | 76 |
| Top rule lift | 24.12 (Regency Teacup set) |
| FP-Growth speedup at 1% support | 30× over Apriori |
