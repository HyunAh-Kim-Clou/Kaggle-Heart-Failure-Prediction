# Kaggle: Heart Failure Prediction


[대회 페이지](
https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction)

[발표 자료](
https://github.com/HyunAh-Kim-Clou/Kaggle-Heart-Failure-Prediction/blob/main/HeartFailure_hyunah.pptx)

<br/>


# 대회 개요

심장 혈관의 질환들(Cardiovascular diseases)(CVDs) 은 죽음의 원인 중 1번째로 전 세계적으로 많이 발생한다. 이는 매년 17.9만 명에 이를 정도로 추정되며, 이는 전 세계 죽음의 31%에 해당한다.

CVD 사망자 5명 중 4명은 심장마비와 뇌졸중으로 사망하며, 이 중 3분의 1은 70세 이하에서 조기 사망한다. 심부전은 CVD로 인해 발생하는 일반적인 일이며, 이 데이터셋에는 가능한 심장질환을 예측하는 데 사용할 수 있는 11가지 기능이 포함되어 있다.

심혈관 질환이 있거나 (고혈압, 당뇨병 등 이미 질병이 하나 이상의 위험 인자의 존재로 인해) 심혈관 위험이 높은 사람은 ML 모델이 큰 도움이 될 수 있는 조기 발견과 관리가 필요하다.

<br/>


# 데이터셋 설명

- Age : 환자의 나이 (years)
- Sex : 환자의 성별 [M=Male, F=Female]
- ChestPainType : 가슴 통증 유형 [TA=특정 협심증, ATA=무정형한 협심증, NAP=협심증 통증 없음, ASY=증상없음]
- RestingBP : 휴식기 혈압 (mm Hg)
- Cholesterol : 혈청 콜레스테롤 (mm/dl)
- FastingBS : 단식 혈당 [1: 120이상 mg/dl, 0: 그렇지 않음]
- RestingECG : 휴식기 심전도 결과 
- Normal: 정상
- ST: having ST-T 파동 비정상성 (T 파동 역치 and/or ST 상승 또는 하강 of > 0.05 mV)
- LVH: showing probable or definite 좌심실 비대증
- MaxHR: 도달한 최대 심박수 최대값 [60 ~ 202 사이의 수치 값]
- ExerciseAngina: 활동 원인이 되는 협심증 [Y: Yes, N: No]
- Oldpeak: ST [하강에서 측정된 수치 값]
- ST_Slope: 영향을 미치는 ST segment 정상의 기울기 [Up: 오르막, Flat: 평평, Down: 내리막]
- HeartDisease: output class [1: 심장병, 0: 정상]

<br/>


# 수행한 작업 및 분석

### 0. 결측치 처리

해당 변수와의 분포와 가장 유사한 확률분포를 선택할 수록 좋은 성능을 보임

### 1. CatBoost 실험

결측지 여부에 상관없이 비슷한 성능을 보임

### 2. SVC 실험

하이퍼 파라미터 C 값을 조정함에 따라 계속적인 성능 향상을 보여줌

### 3. CatBoost & Random Forest로 feature 중요도 시각화

- SHAP library를 활용하여 CatBoost 예측 결과 시각화
- scikit-learn library를 활용하여 Random Forest 모델 시각화


<br/>


# 깨달은 점

- 심장병 관련 징후들에 대한 의학적 지식을 깨달을 수 있었음
- 결측치 처리 방법에 대한 고찰
  - 변수들의 분포에 따라 평균값 및 감마분포로 대치
- 모델 시각화를 통해 어떤 feature가 가장 많은 영향을 주는 지 파악
- 결측치에 robust하다고 해서 가장 좋은 성능을 내는 것은 아니었음

