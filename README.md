#  통계적 근거와 비즈니스 임팩트를 연결하는 Data Scientist 박지수입니다.

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

국내 대기업 실무 환경을 타겟팅하여 대용량 데이터 처리와 비즈니스 리스크 방어에 집중한 프로젝트입니다.

#### 1. 제조 산업 타겟 : [센서 데이터 기반 설비 고장 예지보전 시스템](https://github.com/Jisoopak0822/Predictive-Maintenance/blob/main/ai4i_baseline.ipynb)

*다운타임 손실 방어를 위한 클래스 불균형 제어 및 통계적 임계값 최적화*

* **문제 정의**: 3.4%에 불과한 극심한 고장 데이터 불균형 및 센서 간 다중공선성 리스크 존재.
* **해결 과정**:
* **PCA 차원 축소**: 상관성이 높은 온도 센서들을 1개의 주성분으로 압축해 다중공선성 제거.
* **Data Leakage 차단**: 모델 평가의 신뢰성을 위해 Train 데이터에만 한정하여 SMOTE를 적용해 1대 1 데이터 균형 확보.
* **Threshold 튜닝**: 단순 점검을 의미하는 오탐보다 라인 셧다운을 유발하는 미탐 비용이 압도적으로 크다는 비즈니스 논리에 기반해 모델 임계값을 0.5에서 0.3으로 하향 조정.


* **비즈니스 성과**: 고장 탐지 재현율 지표를 59%에서 **78%로 대폭 향상**시키며 잠재적 공정 정지 다운타임 리스크를 선제적으로 방어.

#### 2. 금융 데이터 파이프라인 : [대용량 금융 이력 기반 신용 대출 부실 예측 시스템](https://github.com/your-username/your-repo-name)

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
