# 📡 Telecom Customer Churn Prediction Project  
**Capstone Project – Module 2: AI Engineering**  
*Purwadhika Digital Technology School*

## 1. Project Introduction  
Build a complete **end-to-end machine-learning pipeline** that predicts which customers of a fictional telecom company are about to **churn** (cancel their subscription).  
Every stage of the data-science lifecycle is covered: business problem → clean data → explore → engineer features → train 6 models → pick the winner → prove the dollars saved.

## 2. Business Problem & Objective  
- **Problem**: In telecom, losing a customer costs 5–10× more than keeping one.  
- **Objective**: Flag high-risk churners **early** so the retention team can send the right offer and keep revenue flowing.

## 3. Project Methodology  
1. **Data Cleaning** – zero duplicates, consistent types  
2. **EDA** – beautiful charts that reveal who churns and why  
3. **Feature Engineering** – smart new columns:  
   - `ProfilRisiko` (risk profile)  
   - `EstimatedTotalCharges` (lifetime value proxy)  
   - `JumlahLayanan` (service bundle count)  
   - Ordinal + One-Hot encoding for every category  
4. **Modeling** – head-to-head battle of 6 classifiers:  
   Logistic Regression | Random Forest | XGBoost | SVM | KNN | **Naive Bayes**  
5. **Evaluation** – **Recall is king** (catch as many real churners as possible)  
6. **Business Simulation** – “What if we run this model every month?”

## 4. Key Results & Insights  
- **Winner: Naive Bayes** → **80 % Recall** on test set  
  (catches 8 out of every 10 future churners)  
- Most powerful predictors = the features **we invented**, especially money-related ones.  
- Monthly **net savings: ~$4,272**  
  (60 % retention success × $25 average save – 15 % campaign cost)

## 5. Tech Stack  
- Python 3  
- Jupyter Notebook  
- Pandas & NumPy → data wrangling  
- Matplotlib & Seaborn → story-telling visuals  
- Scikit-learn → preprocessing, models, metrics  
- XGBoost → gradient boosting  
- Pickle → `final_model.pkl` ready for production  

## 6. File Structure  
```
.  
├── capstone_2_thariq_ahmad.ipynb          # Full notebook (run top-to-bottom)  
├── final_model.pkl                        # Trained Naive Bayes, load & predict!  
├── WA_Fn-UseC_-Telco-Customer-Churn.csv   # Raw dataset  
└── README.md                              # You’re reading the English version  
```

## 7. Reproduce in 5 Minutes  
```bash
# 1. Clone
git clone https://github.com/your-username/your-repo.git
cd your-repo

# 2. Virtual env
python -m venv venv
# Windows
.\venv\Scripts\activate
# macOS / Linux
source venv/bin/activate

# 3. Install
cat > requirements.txt <<EOF
pandas
numpy
matplotlib
seaborn
scikit-learn
xgboost
jupyter
EOF
pip install -r requirements.txt

# 4. Fire up Jupyter
jupyter notebook
```
Open `capstone_2_thariq_ahmad.ipynb` → **Run All**.  
Watch the model train, charts pop, and dollar savings appear.

## Ready when you are  
Load the model in one line:  
```python
import pickle
model = pickle.load(open('final_model.pkl', 'rb'))
prediction = model.predict(new_customer_data)
```
Start saving customers (and money) today! 🚀
