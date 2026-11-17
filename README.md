# 박지수 | Data Science · Machine Learning · AI

안녕하세요. 수학을 전공하고 통계학 석사과정을 마친 박지수입니다.

저는 데이터를 분석할 때 **결과가 왜 그렇게 나왔는지 설명할 수 있는지**를 중요하게 생각합니다. 숫자가 예상과 다르게 나올 때가 오히려 공부가 많이 되는 순간이었습니다. 미국 주택시장 프로젝트에서는 소득과 주택가격의 상관관계가 높게 나왔지만 금융위기 시기에는 서로 다른 움직임을 보였고, 예측 프로젝트에서는 특정 알고리즘을 고집하기보다 실제 검증 결과를 기준으로 접근 방법을 비교했습니다.

대학 수업에서 시작한 분석을 보고서로만 끝내지 않고, 관심이 생긴 문제는 따로 코드를 작성하고 실험하며 확장해 왔습니다. 최근에는 **모델링뿐 아니라 결과를 실제로 사용할 수 있는 형태로 만드는 일**에도 관심을 갖고 RAG 기반 문서 검색 API를 개발하고 있습니다.

**관심 분야:** Statistical Analysis · Predictive Modeling · NLP/AI · Information Retrieval

---

## 대표 프로젝트

### 01. [미국 주택시장과 경제지표의 관계 분석 (2000–2023)](https://github.com/Jisoopak0822/US-Housing-Market-Economic-Analysis)

**R · ggplot2 · EDA · Pearson Correlation | Baruch College, STA 9750 · 5인 팀 프로젝트**

미국의 집값은 인구가 늘어나서 오르는 걸까, 아니면 소득과 소비가 늘어나서 오르는 걸까? 이 질문을 가지고 Zillow, Census, BEA 자료를 지역·연도별로 정리해 비교했습니다.

저는 팀에서 **시각화와 변수 간 관계 분석**을 맡았고, 팀 리더를 도와 추가 자료를 찾거나 그래프에서 읽을 수 있는 해석을 정리하는 역할도 했습니다. 처음에는 인구와 주택가격의 관계가 뚜렷할 것이라 예상했지만, 분석 결과 인구 지표와의 상관계수는 **0.22**로 약했습니다. 반면 가처분소득은 **0.72**, 소비지출은 **0.73**으로 더 높았습니다.

흥미로웠던 부분은 이 결과가 **모든 시기에 동일하게 적용되지는 않는다**는 점이었습니다. 2008년 금융위기 전후에는 주택가격이 크게 떨어졌지만 소득·소비의 움직임은 그만큼 일치하지 않았습니다. 그래서 상관계수만 제시하기보다 시계열 그래프와 지역별 비교, 주택가격 변화 애니메이션을 함께 사용해 결과를 설명했습니다.

서로 다른 기관의 데이터를 연도와 지역 단위로 맞추는 과정도 중요했습니다. 특히 지역별 인구 지표가 **총인구가 아니라 주별 인구의 평균**으로 집계된 값이어서, 이를 실제 인구 유입이나 이주 규모로 해석할 수 없다는 한계가 있었습니다. 이 프로젝트를 통해 데이터의 정의를 확인하지 않으면 그래프가 그럴듯해도 결론은 잘못될 수 있다는 점을 배웠습니다.

[분석 코드·그래프·애니메이션·보고서 보기](https://github.com/Jisoopak0822/US-Housing-Market-Economic-Analysis)

### 02. [부동산 과세평가액 예측 | Property Valuation Competition](https://github.com/Jisoopak0822/--------keggle-competition)

**Python · LightGBM · Feature Engineering · RMSE | STA 9890 수업 경진대회 및 후속 재분석**

2015–2018년의 과세평가 이력과 건축물 정보를 이용해 **2019년 부동산 과세평가액**을 예측했습니다. 처음 수업 프로젝트에서는 R과 XGBoost·앙상블로 접근했고, 이후 Python으로 다시 분석하면서 예측 대상을 정의하는 방법부터 바꿔 보았습니다.

가장 최근 평가액을 그대로 쓰는 기준 모델, 평가액 자체를 예측하는 LightGBM, 두 모델의 평균을 비교했습니다. 그런데 과거 평가액이 이미 주어지는 문제라면 **전체 가격보다 전년도 대비 변화량을 예측하는 편이 낫지 않을까?** 싶었습니다. 실제로 동일한 홀드아웃 데이터에서 직접 예측 모델의 RMSE **45,404.28**보다 변화량 모델의 **29,775.36**이 더 낮았습니다.

점수가 좋아진 뒤에도 이력이 없는 부동산이나 고가 부동산에서는 오차가 컸습니다. 그래서 전체 점수만 보고 끝내지 않고, **어떤 집에서 잘 맞고 어떤 집에서 틀리는지**를 따로 살펴봤습니다. 마감 후 Kaggle 제출에서 확인한 점수는 Public **31,600.658**, Private **30,339.595**이며, **공식 대회 순위나 수상 실적은 아닙니다.**

[모델 비교, 오류 분석 및 코드 보기](https://github.com/Jisoopak0822/--------keggle-competition)

---

## 딥러닝 · AI 구현 프로젝트

### 03. [CNN 기반 Twitter 감성 분류](https://github.com/Jisoopak0822/Twitter-Sentiment-Classification-via-CNN/blob/main/README.md)

**Python · PyTorch · CNN · NLP**

약 **160만 건의 Sentiment140 데이터**로 트윗의 긍정·부정을 분류하는 CNN 모델을 구축했습니다. 텍스트를 모델이 처리할 수 있는 형태로 바꾸고, 학습 설정을 조정하며 성능 변화를 확인했습니다. **Test Accuracy 80.08%**를 기록했습니다.

이 프로젝트에서는 이미지뿐 아니라 문장에도 합성곱 신경망을 적용할 수 있다는 점을 직접 구현하며 이해했습니다. 동시에 Accuracy 하나로 모델이 모든 문장을 잘 분류한다고 말할 수는 없다는 점도 생각하게 됐습니다.

[모델 구성과 결과 보기](https://github.com/Jisoopak0822/Twitter-Sentiment-Classification-via-CNN/blob/main/README.md)

### 04. [Operational RAG | 기술 문서 검색 시스템](https://github.com/Jisoopak0822/operational-rag-portfolio)

**Python · FastAPI · BM25 · TF-IDF · RRF · Pytest**

기술 문서에서 오류 코드나 해결 절차를 찾을 때, 관련 없는 문서가 먼저 검색되면 그다음 단계의 답변도 믿기 어렵다는 생각에서 시작했습니다. 그래서 우선 **검색 결과를 확인하고 API로 반환하는 과정**부터 구현했습니다.

BM25와 문자 기반 TF-IDF 검색 결과를 **RRF(Reciprocal Rank Fusion)**로 합치고, 문서 출처와 검색 결과를 확인할 수 있도록 구성했습니다. FastAPI로 `/health`, `/chat` 엔드포인트를 만들고 주요 기능에 대한 **Pytest 9개 테스트**를 통과시켰습니다.

평가 질문 4개에서는 Recall@3, Hit@3, MRR@3가 모두 1.0이었지만, 샘플이 작기 때문에 일반적인 검색 품질을 입증한 결과로 보지는 않습니다. 현재는 **로컬 검색 프로토타입 단계**이며, LLM 답변 생성이나 실서비스 배포까지 완성한 프로젝트라고 소개하지 않습니다. 다음에는 임베딩 검색과 재순위화, 더 큰 평가 데이터셋으로 확장하고 싶습니다.

[구현 코드와 테스트 결과 보기](https://github.com/Jisoopak0822/operational-rag-portfolio)

---

## 개인 프로젝트 및 추가 작업

### [HR Consulting RDBMS 설계](https://github.com/Jisoopak0822/-HR-Consulting-Firm-Database-System/blob/main/Project%20Final%20Report.pdf)

**SQL · RDBMS · ERD · Normalization**

급여, 커미션, 프로젝트 관리 데이터를 다루기 위한 **15개 테이블의 관계형 데이터베이스와 ERD**를 설계했습니다. 데이터를 분석하기 전에, 서로 연관된 정보가 어떤 키로 연결되고 어떤 구조로 저장되어야 하는지를 고민한 작업입니다.

### [이커머스 A/B 테스트 · 퍼널 분석](https://github.com/Jisoopak0822/-A-B-/blob/main/README.md)

**Python · Hypothesis Testing · Funnel · Retention**

구매 퍼널에서 **View → Cart 전환율 4.69%**를 병목 구간으로 확인했습니다. A/B 테스트에서 **상대 개선율 12.42%, p=0.0182**가 나왔지만, 사전에 정한 **15% MDE**에는 미치지 못해 전면 적용보다 추가 실험을 제안했습니다. 통계적 유의성과 실제로 도입할 만한 개선 폭은 다르다는 점을 고민한 프로젝트입니다.

### [설비 고장 예측 · Predictive Maintenance](https://github.com/Jisoopak0822/Predictive-Maintenance/blob/main/README.md)

**Python · Scikit-learn · Imbalanced Classification · Threshold Optimization**

고장 비율이 약 **3.4%**인 데이터에서 Accuracy만 보면 고장을 놓칠 수 있어 Recall과 오탐 비용을 함께 고려했습니다. 여러 모델과 불균형 처리 방법을 비교했고, 고장 탐지 Recall을 **59%에서 78%로 개선**했습니다. 현장에서는 어떤 오류가 더 비싼지에 따라 의사결정 기준이 달라진다는 점을 배웠습니다.

### [신용위험 예측 · Credit Risk Modeling](https://github.com/Jisoopak0822/Credit-Risk-Modeling-Loan-Approval-Optimization/blob/main/README.md)

**Python · SQL · SQLite · LightGBM · Risk Analytics**

약 **30만 건의 신청 정보와 170만 건의 신용 이력**을 고객 단위로 결합하고 신용위험을 예측했습니다. SQLite와 청크 단위 적재를 사용했고, 분류 임계값에 따라 **위험 고객을 놓치는 문제와 정상 고객을 거절하는 문제**가 어떻게 달라지는지 비교했습니다. 예상 손실 계산은 실제 금융기관 정책이 아닌 가정 기반 시뮬레이션입니다.

### [Amazon Prime Video 콘텐츠 EDA](https://github.com/Jisoopak0822/Amazon-Prime-Video-Content-Analysis/blob/main/README.md)

**Python · Pandas · Seaborn · EDA**

콘텐츠 장르와 구성의 특징을 탐색하고 시각화했습니다. 복잡한 모델이 필요한 문제와, 먼저 데이터를 이해하고 설명하는 일이 중요한 문제를 구분하는 연습이 됐습니다.

---

## 사용 기술

| 분야 | 기술 |
|---|---|
| 프로그래밍 및 데이터 처리 | Python, R, SQL, Pandas, NumPy, SQLite |
| 통계 분석 | 가설검정, 신뢰구간, A/B 테스트, 상관분석, 실험 설계 |
| 머신러닝 | Scikit-learn, LightGBM, Random Forest, Logistic Regression, PCA, SMOTE |
| 딥러닝 및 NLP | PyTorch, CNN, 텍스트 전처리 |
| 검색 시스템 및 API | FastAPI, BM25, TF-IDF, RRF, Pytest |
| 시각화 | ggplot2, Matplotlib, Seaborn, Tableau |

---

제가 앞으로 더 깊게 공부하고 싶은 부분은 **좋은 모델을 만드는 과정뿐 아니라, 그 모델의 평가 결과를 믿을 수 있게 검증하고 실제 사용 환경에 연결하는 방법**입니다. 프로젝트마다 잘된 점뿐 아니라 아직 해결하지 못한 부분도 남겨 두고, 다음 작업에서 개선할 기준으로 삼고 있습니다.
