# 📊 Content-Monetization-Modeler
Content Monetization Modeler – YouTube Ad Revenue Prediction

## 📌 Project Overview

This project predicts estimated YouTube ad revenue using an end-to-end Machine Learning workflow. The objective is to analyze video performance data, engineer meaningful features, compare multiple regression models, select the best-performing model, and deploy the final model through an interactive Streamlit application.

The application allows users to enter video performance details and receive a revenue prediction. A separate Business Insights page provides model performance analysis, feature importance, Actual vs Predicted visualization, and actionable business insights.

---

## 🎯 Project Objectives

- Clean and preprocess content monetization data.
- Perform exploratory data analysis.
- Create meaningful features related to audience engagement and watch behavior.
- Train and compare multiple regression models.
- Evaluate models using R² score.
- Select the best-performing regression model.
- Analyze important revenue-influencing features using Lasso coefficients.
- Save the final machine learning pipeline.
- Build an interactive Streamlit prediction application.
- Create a Business Insights page with visual analytics.
- Compare Actual vs Predicted revenue.
- Generate actionable business recommendations.

---

## 🛠️ Tech Stack

- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Joblib
- Streamlit
- Google Colab
- GitHub

---

## 📂 Repository Structure

```text
Content-Monetization-Modeler/
│
├── Content_Monetization_Modeler.ipynb
├── app.py
├── content_monetization_lasso_pipeline.pkl
├── actual_vs_predicted.csv
├── model_results.csv
├── lasso_coefficients.csv
│
├── pages/
│   └── Business_Insights.py
│
├── requirements.txt
└── README.md
```

---

## 📊 Dataset

The dataset contains video performance and contextual information used to predict YouTube advertising revenue.

### Important Features

- Views
- Likes
- Comments
- Watch Time (minutes)
- Video Length (minutes)
- Subscribers
- Category
- Device
- Country
- Upload Date

### Engineered Features

- Engagement Rate
- Like Rate
- Comment Rate
- Watch Time per View
- Average Watch Time
- Watch Time Ratio
- Year
- Month
- Day of Week
- Quarter

### Target Variable

```text
ad_revenue_usd
```

---

# 🔄 Machine Learning Pipeline

### Step 1 — Data Cleaning

Performed using Pandas and NumPy.

Tasks completed:

- Checked missing values
- Checked duplicate records
- Corrected data types
- Identified numerical and categorical features
- Handled data quality issues
- Prepared the dataset for machine learning

---

### Step 2 — Exploratory Data Analysis

Performed exploratory analysis to understand:

- Distribution of revenue
- Video performance patterns
- Relationship between views and revenue
- Relationship between engagement and revenue
- Watch time patterns
- Category-level differences
- Device and country-level patterns

---

### Step 3 — Feature Engineering

Created additional features to capture audience engagement and viewing behavior.

#### Engagement Rate

```text
Engagement Rate = (Likes + Comments) / Views
```

#### Like Rate

```text
Like Rate = Likes / Views
```

#### Comment Rate

```text
Comment Rate = Comments / Views
```

#### Watch Time per View

```text
Watch Time per View = Watch Time / Views
```

#### Average Watch Time

```text
Average Watch Time = Watch Time per View × 60
```

#### Watch Time Ratio

```text
Watch Time Ratio = Average Watch Time / Video Length
```

Date-based features were also created:

- Year
- Month
- Day of Week
- Quarter

---

### Step 4 — Data Preprocessing

The machine learning pipeline includes:

- Numerical feature scaling
- Categorical feature encoding
- One-Hot Encoding
- Feature transformation
- Regression model

The preprocessing and final model were combined into a single Scikit-learn pipeline.

---

### Step 5 — Train Multiple Regression Models

The following models were trained and evaluated:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest
- Gradient Boosting

---

# 📈 Model Performance

The models were evaluated using the R² score.

| Model | R² Score |
|---|---:|
| Linear Regression | 0.9525 |
| Ridge Regression | 0.9525 |
| **Lasso Regression** | **0.9526** |
| Random Forest | 0.9523 |
| Gradient Boosting | 0.9524 |

---

# 🏆 Final Model

**Lasso Regression** was selected as the final model because it achieved the highest R² score.

```text
R² Score = 0.9526
```

Final Lasso configuration:

```text
Lasso(alpha=0.001, max_iter=10000)
```

The complete preprocessing and Lasso model were saved as:

```text
content_monetization_lasso_pipeline.pkl
```

---

# 🔍 Lasso Feature Analysis

Lasso coefficients were analyzed to identify the features that have the strongest influence on predicted revenue.

### Top Features

| Feature | Coefficient |
|---|---:|
| Watch Time | 59.6040 |
| Likes | 8.6517 |
| Comments | 2.1260 |
| Views | 0.6611 |
| Month | 0.1937 |
| Device TV | -0.1473 |
| Quarter | -0.1051 |
| Year | 0.0987 |
| Country IN | 0.0870 |
| Device Desktop | 0.0796 |

---

# 💻 Streamlit Application

The project includes a **two-page Streamlit application**.

---

## 📊 Page 1 — Revenue Prediction

The main Streamlit page allows users to enter:

- Views
- Likes
- Comments
- Watch Time
- Video Length
- Subscribers
- Upload Date
- Category
- Device
- Country

The application automatically calculates engineered features such as:

- Engagement Rate
- Like Rate
- Comment Rate
- Watch Time per View
- Average Watch Time
- Watch Time Ratio
- Year
- Month
- Day of Week
- Quarter

The saved Lasso pipeline then generates the estimated YouTube ad revenue.

---

## 💼 Page 2 — Business Insights

The Business Insights page provides:

- Model Performance Comparison
- Lasso Feature Analysis
- Top Revenue Influencing Features
- Actual vs Predicted Revenue Visualization
- Key Model Findings
- Business Insights
- Business Recommendations

---

# 📊 Actual vs Predicted Analysis

The final Lasso model was used to generate predictions for the test dataset.

Total prediction records:

```text
24,000
```

The results are stored in:

```text
actual_vs_predicted.csv
```

The file contains:

```text
Actual Revenue
Predicted Revenue
```

The Business Insights page visualizes the relationship between actual and predicted revenue.

---

# 💡 Business Insights

The analysis provides the following key insights:

- Watch time is the strongest revenue-influencing feature in the final Lasso model.
- Likes have a positive relationship with predicted revenue.
- Comments also contribute positively to predicted revenue.
- Views have a positive contribution to the model.
- Audience engagement and viewer retention are important factors for content monetization.
- Improving watch time can be an important strategy for increasing monetization potential.

---

# 🎯 Business Recommendations

Based on the machine learning results, content creators and businesses can:

- Improve viewer retention.
- Create engaging video introductions.
- Improve video storytelling and pacing.
- Encourage viewers to like and comment.
- Optimize video titles and thumbnails.
- Monitor audience retention.
- Analyze viewer drop-off points.
- Create content that increases watch time.
- Use engagement data to improve future content.
- Continuously monitor content performance.

---

# 📁 Project Files

### Content_Monetization_Modeler.ipynb

Contains the complete machine learning workflow:

- Data loading
- Data cleaning
- EDA
- Feature engineering
- Data preprocessing
- Model training
- Model evaluation
- Model comparison
- Lasso coefficient analysis
- Final model creation
- Prediction testing

---

### app.py

Main Streamlit application for:

- User input
- Automatic feature engineering
- Revenue prediction
- Model input visualization

---

### pages/Business_Insights.py

Second Streamlit page containing:

- Model performance
- Feature analysis
- Actual vs Predicted visualization
- Business insights
- Business recommendations

---

### content_monetization_lasso_pipeline.pkl

Saved final machine learning pipeline containing preprocessing and the Lasso regression model.

---

### model_results.csv

Contains the performance results of all evaluated regression models.

---

### lasso_coefficients.csv

Contains the coefficients generated by the final Lasso model.

---

### actual_vs_predicted.csv

Contains the actual and predicted revenue values for the 24,000 test records.

---

# 🔄 Project Workflow

```text
Raw Content Monetization Dataset
              ↓
       Data Cleaning
              ↓
    Exploratory Data Analysis
              ↓
      Feature Engineering
              ↓
    Data Preprocessing
              ↓
     Train-Test Split
              ↓
    Regression Modeling
              ↓
       Model Evaluation
              ↓
      Model Comparison
              ↓
    Lasso Feature Analysis
              ↓
      Final Model Selection
              ↓
     Save ML Pipeline
              ↓
     Streamlit Application
              ↓
 ┌──────────────────────────┐
 │                          │
 ↓                          ↓
Revenue Prediction     Business Insights
 │                          │
 ↓                          ↓
User Prediction       Visual Analytics
                            ↓
                    Business Recommendations
```

---

# 🧪 Model Testing

The final saved model pipeline was loaded and tested with new input data.

Test result:

```text
Number of predictions: 1
Predicted Revenue: 252.31695300223
```

This confirms that the saved pipeline successfully accepts new user inputs and generates revenue predictions.

---

# ▶️ How to Run the Project

## Clone Repository

```bash
git clone https://github.com/<your-username>/Content-Monetization-Modeler.git
```

Move into the project directory:

```bash
cd Content-Monetization-Modeler
```

---

## Install Required Libraries

```bash
pip install pandas numpy scikit-learn matplotlib streamlit joblib
```

---

## Run Streamlit Application

```bash
streamlit run app.py
```

---

## Open the Application

Streamlit will provide a local URL:

```text
http://localhost:8501
```

Open the URL in your browser.

The application contains two pages:

```text
📊 Content Monetization Modeler
💼 Business Insights
```

---

# 📌 Project Results

The project successfully:

- Cleaned and prepared the dataset.
- Performed exploratory data analysis.
- Created meaningful engagement and watch-time features.
- Trained five regression models.
- Compared model performance using R².
- Selected Lasso Regression as the final model.
- Achieved an R² score of **0.9526**.
- Performed Lasso coefficient analysis.
- Identified watch time as the strongest feature.
- Saved the complete ML pipeline.
- Generated predictions for 24,000 test records.
- Built an interactive two-page Streamlit application.
- Added model performance visualization.
- Added Actual vs Predicted visualization.
- Added business insights and recommendations.

---

# 📚 Skills Demonstrated

- Data Cleaning
- Exploratory Data Analysis
- Feature Engineering
- Data Preprocessing
- Regression Modeling
- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest
- Gradient Boosting
- Model Evaluation
- Model Selection
- Feature Selection
- Feature Scaling
- Categorical Encoding
- Data Visualization
- Python
- Pandas
- NumPy
- Scikit-learn
- Streamlit
- Model Deployment
- Business Analytics
- Business Insight Generation

---

# 👩‍💻 Author

**Silviya X**
