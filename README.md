# 💰 판매 요인 분석과 수요 예측을 통한 가격 최적화
<br/>

## 🧑‍💻 프로젝트 개요  
카테고리, 제품 특성, 판매 플랫폼 등 다양한 요인이 판매량에 영향을 미치지만, 많은 경우 개인 경험이나 단순 시장 조사에 기반하여 가격을 결정하고 있습니다. 본 프로젝트는 **일일 판매 데이터를 기반으로 머신러닝 모델을 학습**하여 **수요를 예측**하고, 이를 토대로 **최적 가격을 제안**하여 판매자의 의사결정을 지원하고자 진행되었습니다.  
<br/><br/>

## 📦 데이터셋
- 소매 상점 일일 판매 데이터 (from. Kaggle)
<br/><br/>


## 🛠️ 모델 학습 상세 설명
- **최종 사용 모델**: `XGBoost`

- **학습 방법**:  
  - 데이터 전처리: 이상치 처리, 날짜 변환(`Year`, `Month`, `Day`), 
  - EDA를 통해 가격, 할인율, 경쟁사 가격, 시즌성 등 판매량 영향 요인 파악
  - 피처 엔지니어링: 시계열 변수 추가(1일전, 7일전, 30일 평균), 라벨 인코딩, 타겟 변수 Yeo-Johnson 변환을 통해 정규분포 형태로 변환
  - RMSE를 활용하여 모델 성능 평가 & 변수 중요도 파악
  - LightGBM, XGBoost 비교후 모델 선정
<br/><br/>


## 🧩 주요 역할 및 프로젝트 진행 내용
- 판매 데이터 분석 및 EDA
- Lag/rolling feature 생성 및 시계열 특성 반영
- 머신러닝 회귀 모델 학습 및 성능 개선 시도
- 가격 탄력성 추정 및 시뮬레이션을 통한 최적 가격 제안 구조 설계  
<br/><br/>


## 🛠️ 사용 기술 스택
- Python
- LightGBM, XGBoost, scikit-learn
- pandas, numpy, matplotlib, seaborn  
<br/><br/>


## 🎯 Result
- 해당 전자상거래의 경우 특정 요소에 의한 판매량 증감의 추세는 보이지 않는다.
<br/><br/><br/>

**분석 결과**
- 가격 하나의 요소보다 카테고리나 제품의 특성을 같이 고려한 금액 설정이 중요함.
- 할인율과 판매량의 관계는 선형(linear) 관계가 아니며, 최적 할인율은 제품과 계절 등 종합적 요소를 고려해 다르게 책정해야 한다.
- 해당 플랫폼에서는 계절, 날씨, 프로모션은 판매량과의 관계가 크지 않은 것으로 확인됨.
- 제품의 브랜드와 특성을 살린 최적 가격 정책 필요.
<br/><br/><br/>

**1) 가격과 판매량 관계 탐색**
<img width="490" height="316" alt="image" src="https://github.com/user-attachments/assets/98441db7-40e4-401d-a344-35364bf12478" />
<br/><br/><br/>


**2) 할인율 효과 분석**

<img width="490" height="316" alt="image" src="https://github.com/user-attachments/assets/05a24756-4980-457c-a78b-bbda9cacab6c" />
<img width="1183" height="327" alt="image" src="https://github.com/user-attachments/assets/4f665d60-08fa-4642-b4b3-a858be73666f" />


<br/><br/><br/>

**3) 프로모션 및 기타 요인과의 관계성**

<img width="490" height="316" alt="image" src="https://github.com/user-attachments/assets/43ccb900-ee6d-448f-9198-8457ca372c51" />
<br/><br/><br/>

**4) 경쟁사 가격 효과**

<img width="490" height="316" alt="image" src="https://github.com/user-attachments/assets/69d677c7-8899-4138-a93f-9bf3daeacc06" />
<br/><br/><br/>

**시계열 특성 추가**

<img width="490" height="300" alt="image" src="https://github.com/user-attachments/assets/f8ffd194-382e-4453-8f2d-cd6da551304b" />
<br/><br/><br/>


**모델학습 결과**
- XGBoost, LightGBM 모두 RMSE값이 1로 동일함.
- LightGBM
<img width="882" height="315" alt="image" src="https://github.com/user-attachments/assets/044fadb0-4a07-4f87-9539-fcf4e630d7cd" />
<br/><br/><br/>

- 변수 중요도
<img width="879" height="308" alt="image" src="https://github.com/user-attachments/assets/4faf2cf6-2d32-42d7-b21f-8e1838818f97" />
<br/><br/><br/>

- XGBoost
<img width="880" height="317" alt="image" src="https://github.com/user-attachments/assets/3130cd72-36ae-42f3-aae7-d1aa00765035" />
<br/><br/><br/>

- 변수 중요도
<img width="880" height="308" alt="image" src="https://github.com/user-attachments/assets/343889f6-de49-42b3-b4eb-0ebd1e9b1cb1" />
<br/><br/><br/>

**가격 추천**

<img width="500" height="540" alt="image" src="https://github.com/user-attachments/assets/df01e7f1-7738-4205-abdb-276f6129adf7" />
<br/><br/><br/>








