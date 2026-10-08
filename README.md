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

## 03. Credit Risk Modeling & Loan Approval Optimization

### [신용위험 예측 기반 대출 승인 전략 및 예상 신용손실 분석](https://github.com/Jisoopak0822/Credit-Risk-Modeling-Loan-Approval-Optimization/blob/main/README.md)

**약 30만 건의 고객 신청 정보와 170만 건의 외부 신용 이력을 통합하여 신용위험을 예측하고, 대출 승인율과 예상 손실 간 Trade-off를 분석한 금융 의사결정 지원 프로젝트**

- **Business Problem** — 금융기관의 신용손실 관리와 우량 고객의 대출 기회 확보라는 상충하는 목표를 정의하고, 승인율과 신용위험을 함께 고려하는 분석 프레임워크 설계.
- **Data Engineering** — Python Chunk Processing과 SQLite를 활용해 대규모 금융 데이터를 적재하고, SQL `GROUP BY` 및 `LEFT JOIN`으로 고객 단위 Credit Risk Data Mart 구축.
- **Risk Analytics & Feature Engineering** — 소득 대비 대출금, 기존 미상환 부채, 과거 신용 기록 등을 활용해 금융 리스크 관련 파생 변수 생성 및 고객군별 상환 곤란 비율 분석.
- **Predictive Modeling** — Logistic Regression과 LightGBM의 ROC-AUC, PR-AUC 및 Calibration 성능을 비교하고, 데이터 누출을 방지하는 전처리 파이프라인 구축.
- **Business Optimization** — 위험확률 Threshold에 따른 대출 승인율, 위험 고객 차단율 및 정상 고객 거절률을 분석하고, 가상의 비즈니스 제약조건을 반영한 승인 정책 비교.
- **Financial Impact Simulation** — PD·LGD·EAD 가정에 기반한 예상 신용손실 및 위험조정 수익 시뮬레이션을 통해 대출 승인 정책별 금융성과 비교.

**What this project demonstrates**  
Business-Oriented Data Science · Credit Risk Analytics · SQL Data Engineering · Predictive Modeling · Financial Decision Optimization

**Tech:** Python · SQL · SQLite · Pandas · Scikit-learn · LightGBM · Probability Calibration · Financial Simulation
---

# Academic & Foundation Projects

핵심 프로젝트 외에 데이터베이스 설계와 딥러닝/NLP 기반 역량을 확장한 프로젝트입니다.

### [CNN 기반 Twitter Sentiment Classification](https://github.com/Jisoopak0822/Twitter-Sentiment-Classification-via-CNN/blob/main/README.md)
160만 건의 Sentiment140 데이터를 활용해 PyTorch CNN 모델을 구축하고 **Test Accuracy 80.08%** 달성.

`PyTorch · CNN · NLP · Hyperparameter Tuning`

### [HR Consulting RDBMS Design](https://github.com/Jisoopak0822/-HR-Consulting-Firm-Database-System/blob/main/Project%20Final%20Report.pdf) 
급여·커미션·프로젝트 데이터를 관리하기 위한 **15개 테이블 관계형 데이터베이스와 ERD** 설계.

`SQL · RDBMS · ERD · Normalization`

### [Amazon Prime Video EDA](https://github.com/Jisoopak0822/Amazon-Prime-Video-Content-Analysis/blob/main/README.md)
콘텐츠 장르 및 시청 트렌드를 분석하고 데이터 기반 마케팅 인사이트를 시각화.

`Python · Pandas · Seaborn · EDA`
---
