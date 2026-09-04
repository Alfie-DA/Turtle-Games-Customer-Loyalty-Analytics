# Turtle Games: Customer Loyalty Analytics

An end-to-end data analytics project for **Turtle Games**, a global games manufacturer and retailer. The project explores customer behaviour, identifies meaningful customer segments, measures review sentiment, and develops models to support loyalty and retention decisions.

## Project overview

Turtle Games wanted to better understand the factors associated with customer loyalty and use those findings to improve marketing and retention activity. This analysis answers four core questions:

- Which factors are most strongly associated with loyalty points?
- Are there distinct customer segments in the customer base?
- What are customers saying about Turtle Games products?
- How reliably can future loyalty points be predicted?

## Key findings

- **Spending score is the strongest loyalty indicator.** It has a positive relationship with loyalty points and explains 45.2% of their variation in the single-variable analysis.
- **Remuneration is also positively associated with loyalty**, explaining 38% of variation; age has virtually no explanatory value.
- **Five customer segments** were identified through K-means clustering: premium customers, value seekers, low-value customers, high-income/low-spend customers, and core customers.
- **Customer sentiment is generally positive.** Most review polarity scores sit between neutral and mildly positive, though a small number of strongly negative reviews should be investigated.
- A multiple linear regression model achieved **R² = 0.8399** using age, remuneration, and spending score. Its diagnostics indicate non-linearity, uneven error variance, and influential outliers, so predictions for high-value customers should be treated carefully.

## Business recommendations

| Customer group | Suggested action |
| --- | --- |
| High income, high spend | Offer VIP rewards, exclusive releases, and premium loyalty benefits. |
| Low income, high spend | Use bundles, promotions, and value-led offers. |
| High income, low spend | Target with tailored incentives to increase engagement and spend. |
| Core customers | Prioritise retention activity and relevant loyalty communications. |
| Low income, low spend | Use cost-efficient, low-touch marketing. |

In addition, review strongly negative feedback to identify recurring product or service issues, and validate predictive models on new data before using them for customer-level decisions.

## Analysis methods

- Exploratory data analysis (EDA)
- Data cleaning and preparation
- Correlation and regression analysis
- Decision tree regression
- K-means clustering
- Natural language processing (NLP) and sentiment analysis
- R-based exploratory data analysis
- Multiple linear regression diagnostics and prediction scenarios

## Tools and technologies

**Python**

- pandas, NumPy
- Matplotlib, Seaborn
- statsmodels
- scikit-learn
- TextBlob, NLTK, WordCloud
- SciPy

**R**

- ggplot2
- dplyr

The Python notebook covers data preparation, individual regressions, decision-tree modelling, clustering, and sentiment analysis. The R script provides exploratory visualisations and the multiple linear regression model, including diagnostic plots and a prediction scenario.

## Data

The project uses a customer-review dataset (`turtle_reviews.csv`) containing numerical customer attributes and text fields, together with supporting metadata. The working analysis uses a cleaned version of the data, `clean_reviews.csv`.

> Keep source data out of version control if it contains confidential or personally identifiable customer information.

## Project files

```text
.
├── data/
│   ├── turtle_reviews.csv       # Raw data (The dataset is not included in this repository because of data-sharing restrictions. It is available on request for review purposes.
│   └── clean_reviews.csv        # Generated cleaned analysis data (Available upon request due to data sharing restrictions)
├── Solomon_Alfred_DA301_Assignment_Notebook.ipynb
│                              # Main Python analysis workflow
├── Solomon_Alfred_DA301_Assignment_Rscript.R
│                              # R EDA and multiple linear regression
├── visualizations/            # Exported charts and model diagnostic plots
├── Solomon_Alfred_DA301_Assignment_Report.docx
│                              # Written findings and recommendations
└── README.md
```

## Getting started (Please request the data before running the analysis)

1. Clone the repository.
2. Place `turtle_reviews.csv` in `data/`.
3. Create a Python environment and install the required packages.
4. Open `Solomon_Alfred_DA301_Assignment_Notebook.ipynb` in Jupyter Notebook or JupyterLab.
5. Run the cells in order. The cleaning step creates `clean_reviews.csv`, which is used by the modelling, clustering, and sentiment-analysis sections.
6. Run `Solomon_Alfred_DA301_Assignment_Rscript.R` in RStudio to reproduce the R visualisations and multiple linear regression analysis.

Example Python package installation:

```bash
pip install pandas numpy matplotlib seaborn statsmodels scikit-learn textblob nltk wordcloud scipy jupyter
```

The notebook also needs the NLTK English stopwords corpus. Run this once in Python:

```python
import nltk
nltk.download("stopwords")
```

Install the R packages before running the R script:

```r
install.packages(c("ggplot2", "dplyr"))
```

> **Note on file paths:** the current Python notebook reads and writes CSV files in the same folder as the notebook, whereas the R script reads `data/clean_reviews.csv`. Before publishing, either update the notebook paths to use `data/`, or move its generated `clean_reviews.csv` into the `data/` folder before running the R script.

## Model caveats

The decision tree produced an extremely high training R² (0.9937), which is likely a sign of overfitting rather than dependable real-world performance. The multiple linear regression model is more interpretable, but its diagnostic plots show that its assumptions are not fully met. Future work should include holdout validation, cross-validation, feature engineering, and testing more robust models.

## Author

Solomon Alfred

---

*This project was completed as part of the DA301 data analytics coursework.*
