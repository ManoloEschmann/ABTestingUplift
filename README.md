# 📊 Promotion AB Test & Uplift Modeling Case Study

This repository presents an end-to-end data science workflow for evaluating and optimizing retail promotions via AB testing, causal inference, and uplift modeling. The analysis aims to answer:
- **Which promotion delivers the highest sales?**
- **Does customizing the promotion by store age or market size improve results?**

---

## 📦 Dataset

- **Source:** [WA_Marketing-Campaign.csv on Kaggle](https://www.kaggle.com/datasets/chebotinaa/fastfoodmarketingcampaignabtest)
- **Features:**
  - `SalesInThousands` - Weekly sales revenue (in thousands)
  - `Promotion` - Promotion type (1, 2, 3)
  - `MarketSize` - Market type (`Small`, `Medium`, `Large`)
  - `AgeOfStore` - Store age in years
  - `week` - Week of campaign
  - `LocationID` - Store identifier

---

## 📋 Analysis Overview

### 1. Exploratory Data Analysis (EDA)
- Promotion and sales distributions
- Cross-tabulations and visualizations by market size and store age

### 2. Statistical Modeling
- OLS regression to estimate each promotion’s effect, controlling for market size, store age, and week

### 3. Uplift Modeling Approaches
- **S-Learner:**  
  Single regression model with promotion as a feature
- **T-Learner:**  
  One regression model per promotion; cross-compare segment predictions
- **Heterogeneous Treatment Effect (HTE) Analysis:**  
  Visualize and quantify the (causal) effect of changing promotions in each segment

### 4. Policy Recommendation
- Compare the *best overall* policy vs. segment-by-segment tailored policies

---

## 📈 Key Results

- **Promotion 1** consistently delivers the highest or near-highest expected sales in almost all segments.
- **Promotion 2** produces significantly lower sales in every segmentshould be avoided.
- **Promotion 3** only occasionally surpasses Promotion 1 in niche segments, but the difference is small.
- **Uplift modeling** shows negligible or negative “personalized uplift”:  
  - *Segment tailoring leads to a predicted sales change of* **-0.47K** *(about* **-0.8%** *) over a single-promotion policy.*
- **Conclusion:** Stick with Promotion 1 for all stores.

---

## 🗺️ Business Takeaways

- **Use Promotion 1** as the standard campaign.
- **Do not use Promotion 2** (consistently underperforms).
- **Segmented (personalized) promotion assignment does not materially improve results** over the best single-promotion approach.
- Regularly revisit the data as market dynamics or promotion effectiveness may change.

---

## 🛠️ How To Run

1. **Install dependencies**
  
2. **Run the Python notebook or script**
    - Use `ab_testing.ipynb` or convert to Jupyter notebook (`.ipynb`)
    - The script auto-downloads the data from [Kaggle](https://www.kaggle.com/datasets/chebotinaa/fastfoodmarketingcampaignabtest)

3. **Outputs**
    - Data visualizations
    - Model effect summaries
    - Uplift effect plots
    - Business policy recommendations

---

## 📚 References

- [Kaggle: Fast Food Marketing Campaign AB Test Dataset](https://www.kaggle.com/datasets/chebotinaa/fastfoodmarketingcampaignabtest)
- [Interpretable Machine Learning Book: Uplift Modeling](https://christophm.github.io/interpretable-ml-book/uplift.html)
- [Case Study: Uplift Models Comparison](https://www.kdnuggets.com/2020/06/case-study-uplift-models-comparison.html)

---

## 🤝 Contributions

Feedback and PRs are welcome. Please open an issue for suggestions or corrections.

---

**_This repository demonstrates how to combine causal inference and machine learning to optimize business interventions in a rigorous, data-driven way._**
