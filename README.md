## 통계적 실험과 머신러닝으로 비즈니스 의사결정을 설계하는 Data Scientist 박지수입니다.

수학·통계학 기반의 정량적 분석 역량을 바탕으로 **실험 설계, 예측 모델링, 대용량 데이터 처리**를 실제 비즈니스 의사결정 문제에 연결하는 데 집중합니다.

단순히 높은 모델 Accuracy를 만드는 것보다  
**어떤 지표를 최적화해야 하는지, 어떤 오류가 더 비싼지, 분석 결과를 실제 의사결정으로 어떻게 연결할지**를 중요하게 생각합니다.

이커머스 A/B Testing, 제조 Predictive Maintenance, 금융 신용위험 분석 프로젝트를 통해 **문제 정의 → 데이터 처리 → 통계/ML 모델링 → 검증 → 비즈니스 의사결정**의 전체 분석 과정을 구현했습니다.

---

### 🛠 Technical Skills

- **Languages:** Python, SQL
- **Statistics & Experimentation:** A/B Testing, Hypothesis Testing, Power Analysis, Confidence Interval, Retention Analysis
- **Machine Learning:** Scikit-learn, LightGBM, Random Forest, Gradient Boosting, Logistic Regression, PCA, SMOTE
- **Data Engineering:** SQLite, SQL JOIN/Aggregation, Chunk Processing, RDBMS Design, Data Pipeline
- **Deep Learning & NLP:** PyTorch, CNN, Sentiment Analysis
- **Visualization & Analytics:** Pandas, NumPy, Matplotlib, Seaborn, Tableau

---

# Featured Projects

## 01. E-commerce Experimentation
### [A/B 테스트 및 구매 퍼널·리텐션 분석](https://github.com/Jisoopak0822/-A-B-/blob/main/README.md)

**구매 전환 데이터를 기반으로 병목 구간을 진단하고, 통계적 실험을 통해 제품 변경 여부를 판단한 프로젝트**

- **Problem** — View → Cart → Purchase 구매 퍼널을 분석하여 전환율 개선 우선순위를 정의.
- **Funnel Analysis** — View → Cart **4.69%**, Cart → Purchase **36.98%**, View → Purchase **1.74%**를 확인하고 View → Cart 구간을 핵심 병목으로 식별.
- **Experiment Design** — Purchase Conversion Rate를 Primary KPI로 설정하고 **Power Analysis와 MDE 기반 Sample Size**를 산출해 A/B 테스트 설계.
- **Statistical Validation** — Treatment에서 **+12.42% Relative Lift**, Two-Proportion Z-Test **p=0.0182**, 95% CI **[+0.038%p, +0.405%p]** 확인.
- **Decision** — 통계적 유의성은 확보했지만 사전 정의한 **15% MDE에는 미달**했기 때문에 단순 Full Rollout 대신 Treatment 개선 후 추가 실험을 제안.
- **Retention** — Right Censoring을 고려해 **7일 재구매율 15.25%, 14일 재구매율 26.32%** 산출.

**What this project demonstrates**  
Experiment Design · Statistical Inference · Funnel Analysis · Product Decision Making

**Tech:** Python · Pandas · NumPy · SciPy · Statsmodels · Matplotlib · Seaborn

---

## 02. Predictive Maintenance
### [비용 민감형 설비 고장 예지보전 시스템](https://github.com/Jisoopak0822/Predictive-Maintenance/blob/main/README.md)

**희소한 고장 데이터를 단순 분류 문제가 아닌 유지보수 비용 최적화 문제로 재정의한 프로젝트**

- **Problem** — 실제 고장이 전체 데이터의 약 **3.4%**에 불과한 Class Imbalance 환경에서 Accuracy 중심 평가의 한계를 분석.
- **Modeling** — Logistic Regression, Random Forest, Gradient Boosting, LightGBM과 **Class Weight / SMOTE** 전략을 비교.
- **Evaluation** — Recall, Precision, F1, ROC-AUC, **PR-AUC**를 함께 평가해 희소 고장 탐지 능력을 검증.
- **Leakage Prevention** — Train/Test 분리 후 Scaling, PCA, Sampling이 학습 데이터에만 적용되도록 Pipeline을 구성.
- **Cost-sensitive Decision** — False Negative와 False Positive의 비용 차이를 Cost Function으로 정의하고 **고정 threshold 0.5 대신 비용 기반 최적 threshold** 탐색.
- **Key Result** — 고장 탐지 Recall을 **59% → 78%**로 개선.
- **Operational Policy** — 예측 확률을 Normal / Watch / Preventive Inspection / Critical 단계로 변환해 고위험 설비를 우선 점검하는 **Risk-Based Maintenance Policy** 설계.

**What this project demonstrates**  
Imbalanced Classification · Cost-sensitive ML · Threshold Optimization · ML Decision Policy

**Tech:** Python · Scikit-learn · LightGBM · PCA · SMOTE · Pandas · NumPy

---

## 03. Credit Risk & Data Engineering
### [대용량 금융 이력 기반 신용대출 부실 예측](https://github.com/Jisoopak0822/-/blob/main/home_credit_portfolio.ipynb)

**메모리 제약이 있는 환경에서 대규모 금융 데이터를 처리하고 신용위험 예측 변수를 생성한 프로젝트**

- **Problem** — 약 **2.68GB 규모의 다중 테이블 데이터**를 Pandas로 한 번에 처리할 때 발생하는 메모리 초과 문제 해결.
- **Data Pipeline** — Python Chunk Processing과 SQLite를 결합해 대용량 데이터를 안정적으로 적재하는 파이프라인 구축.
- **SQL Feature Engineering** — 약 **170만 건의 과거 대출 이력**을 JOIN 및 Aggregation하여 고객별 총 채무액, 과거 대출 건수 등의 파생 변수 생성.
- **Modeling** — 생성된 고객·대출 이력 변수를 LightGBM 기반 부실 예측 모델에 적용.
- **Key Result** — 데이터 처리 과정의 메모리 사용량을 **70% 이상 절감**하고, 직접 생성한 파생 변수들이 모델 Feature Importance **2위와 4위**를 기록해 높은 예측 기여도를 확인.

**What this project demonstrates**  
Large-scale Data Processing · SQL · Feature Engineering · Credit Risk Modeling

**Tech:** Python · SQL · SQLite · Pandas · LightGBM · Chunk Processing

---

# Academic & Foundation Projects

핵심 프로젝트 외에 데이터베이스 설계와 딥러닝/NLP 기반 역량을 확장한 프로젝트입니다.

### CNN 기반 Twitter Sentiment Classification
160만 건의 Sentiment140 데이터를 활용해 PyTorch CNN 모델을 구축하고 **Test Accuracy 80.08%** 달성.

`PyTorch · CNN · NLP · Hyperparameter Tuning`

### [HR Consulting RDBMS Design](https://github.com/Jisoopak0822/-HR-Consulting-Firm-Database-System/blob/main/Project%20Final%20Report.pdf) 
급여·커미션·프로젝트 데이터를 관리하기 위한 **15개 테이블 관계형 데이터베이스와 ERD** 설계.

`SQL · RDBMS · ERD · Normalization`

### Amazon Prime Video EDA
콘텐츠 장르 및 시청 트렌드를 분석하고 데이터 기반 마케팅 인사이트를 시각화.

`Python · Pandas · Seaborn · EDA`
---
