#  통계적 근거를 바탕으로 비즈니스 의사결정을 지원하는 Data Scientist 박지수 입니다.

수학과 통계학 석사 과정에서 다진 탄탄한 이론적 배경을 바탕으로, 단순한 모델 예측을 넘어 대용량 데이터 파이프라인 구축과 비즈니스 비용 최적화에 집중합니다. 데이터 이면의 인과관계를 분석하고, 제조, 금융, 통신 등 현업의 문제를 해결하는 실용적인 머신러닝 솔루션을 설계합니다.

---

### 🛠 Technical Toolbox

* **Languages**:   
* **Machine Learning & Stats**: Scikit-learn, LightGBM, Random Forest, PCA, SMOTE, 통계적 가설 검정
* **Data Engineering**: SQLite, 대용량 데이터 Chunking, RDBMS 논리적 및 물리적 설계, 데이터 정규화
* **Deep Learning & NLP**: PyTorch, CNN, Sentiment Analysis
* **Visualization**: Pandas, NumPy, Matplotlib, Seaborn, Tableau

---

###  Featured Projects : 핵심 실무 프로젝트

#### 1. 이커머스 전환율 최적화 : [A/B 테스트 및 리텐션 분석](https://github.com/Jisoopak0822/-A-B-/blob/main/README.md)

*사용자 행동 로그 기반 구매 퍼널 병목 진단 및 통계적 실험 설계*

- **문제 정의**: 이커머스 행동 로그에서 View → Cart → Purchase 구매 여정을 분석하여 전환율 개선 우선순위를 도출.
- **Funnel Analysis**: 동일 사용자·상품 기준 행동 순서를 추적한 결과 **View → Cart 4.69%, Cart → Purchase 36.98%, View → Purchase 1.74%**로 View → Cart 구간을 주요 개선 후보로 식별.
- **Experiment Design**: Purchase Conversion Rate를 Primary KPI로 설정하고 **Power Analysis, MDE, Sample Size Calculation**을 통해 A/B 테스트 설계.
- **Statistical Testing**: Treatment에서 **+12.42% Relative Lift**를 관찰했으며 Two-Proportion Z-Test 결과 **p=0.0182**, 95% CI **[+0.038%p, +0.405%p]**를 확인.
- **Business Decision**: 통계적으로 유의했지만 사전 정의한 **15% MDE에는 미달**하여 즉시 Full Rollout보다 Treatment 개선 및 추가 실험을 제안.
- **Retention Analysis**: Right Censoring을 고려하여 **7일 재구매율 15.25%, 14일 재구매율 26.32%** 산출.

**Tech:** Python, Pandas, NumPy, SciPy, Statsmodels, Matplotlib, Seaborn · A/B Testing · Power Analysis · Hypothesis Testing · Retention Analysis

국내 대기업 실무 환경을 타겟팅하여 대용량 데이터 처리와 비즈니스 리스크 방어에 집중한 프로젝트입니다.

#### 2. 제조 산업 타겟 : [비용 민감형 설비 고장 예지보전 시스템](https://github.com/Jisoopak0822/Predictive-Maintenance/blob/main/README.md)

*희소 고장 데이터에서 미탐 비용을 최소화하는 Predictive Maintenance 의사결정 시스템*

- **문제 정의**: 전체 설비 데이터 중 실제 고장은 약 **3.4%**에 불과해 Accuracy 중심 모델링만으로는 고장 설비를 안정적으로 탐지하기 어려운 클래스 불균형 문제가 존재.
- **모델링 전략**: Baseline, Class Weight, SMOTE 기반 불균형 처리 전략과 Logistic Regression, Random Forest, Gradient Boosting, LightGBM을 비교하여 모델 성능을 검증.
- **평가 기준 개선**: Accuracy뿐 아니라 **Recall, Precision, F1-score, ROC-AUC, PR-AUC**를 함께 평가하고, 희소 고장 탐지 성능을 반영하기 위해 PR-AUC 중심으로 모델을 비교.
- **Data Leakage 방지**: Train/Test 분리 이후 Scaling, PCA, Sampling이 학습 데이터에서만 수행되도록 Pipeline을 구성해 평가 신뢰성 확보.
- **비용 기반 Threshold 최적화**: 기본 임계값 0.5를 고정하지 않고, 고장 미탐지(False Negative) 비용과 불필요한 점검(False Positive) 비용을 반영한 Cost Function을 설계해 최적 의사결정 임계값 탐색.
- **운영 의사결정 연결**: 예측 확률을 Normal / Watch / Preventive Inspection / Critical 단계로 구분해 유지보수팀이 고위험 설비를 우선 점검할 수 있는 **Risk-Based Maintenance Policy**로 확장.
- **비즈니스 목표**: 단순 예측 정확도 향상이 아니라 **생산라인 다운타임 리스크 감소와 예방정비 자원의 효율적 배분**을 지원하는 데이터 기반 유지보수 의사결정 체계 구축.


* **비즈니스 성과**: 고장 탐지 재현율 지표를 59%에서 **78%로 대폭 향상**시키며 잠재적 공정 정지 다운타임 리스크를 선제적으로 방어.

#### 3. 금융 데이터 파이프라인 : [대용량 금융 이력 기반 신용 대출 부실 예측 시스템](https://github.com/Jisoopak0822/-/blob/main/home_credit_portfolio.ipynb)

*메모리 한계 극복을 위한 RDBMS 구축 및 통계적 파생 변수 발굴*

* **문제 정의**: 수백만 행에 달하는 2.68GB 규모의 다중 로그 데이터를 Pandas 단일 메모리로 처리할 때 발생하는 메모리 초과 크래시 현상.
* **해결 과정**:
* **데이터 아키텍처**: Python Chunking 기법과 SQLite를 연동하여 메모리 초과 없는 무중단 데이터 적재 파이프라인 구축.
* **SQL 파생 변수 생성**: 170만 건의 과거 타기관 이력 테이블을 LEFT JOIN 및 서브쿼리로 집계하여 씬 파일러 고객 특성을 반영한 총 채무액과 과거 대출 건수 파생 변수 창출.


* **비즈니스 성과**: 데이터 전처리 메모리 점유율을 70% 이상 절감했으며, 직접 설계한 파생 변수가 LightGBM 모델의 **Feature Importance 2위와 4위**에 랭크되며 부실 예측의 핵심 드라이버임을 통계적으로 증명.

---

### 📚 Academic & Foundation Projects : 기초 역량 및 딥러닝 프로젝트

데이터 아키텍처 설계와 딥러닝 자연어 처리에 대한 기반 역량을 다진 프로젝트입니다.

#### 3. [Twitter 텍스트 감성 분류 : CNN 기반 Deep Learning](https://github.com/your-username/your-repo-name)

* **Objective**: 160만 건의 Sentiment140 데이터셋을 활용한 대규모 텍스트 감성 분류 CNN 모델 구축.
* **Key Results**: 커널 크기 및 임베딩 차원 하이퍼파라미터 튜닝을 통해 **80.08%의 Test Accuracy** 달성.
* **Competencies**: PyTorch, NLP 전처리, 연산 비용 최적화 분석.

#### 4. [HR 컨설팅 기업을 위한 맞춤형 RDBMS 설계](https://github.com/your-username/your-repo-name)

* **Objective**: 분산된 스프레드시트 업무 환경을 대체할 중앙 집중형 관계형 데이터베이스 스키마 설계.
* **Key Results**: 급여, 커미션, 프로젝트 트래킹 데이터를 무결성 있게 관리하는 **제4정규형 15개 테이블 스키마** 구축.
* **Competencies**: SQL DDL DML, ERD 데이터 모델링, 비즈니스 로직 설계.

#### 5. [Amazon Prime Video 콘텐츠 트렌드 분석 : 탐색적 데이터 분석](https://colab.research.google.com/drive/1ZG9cNJF2YlDcU-lyAoapcfhKzLcJnd40?usp=sharing)

* **Objective**: 스트리밍 플랫폼의 시청 트렌드 및 장르 분포 분석을 통한 마케팅 인사이트 도출.
* **Key Results**: Python 기반 자동화 탐색적 데이터 분석 파이프라인 구축 및 인사이트 시각화.
* **Competencies**: Python Pandas Seaborn, 데이터 스토리텔링.

---
