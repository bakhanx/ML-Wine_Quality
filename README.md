# ML-Wine_Qaulity

# Title : Wine-Quailty and scikit_learn

<img src="https://user-images.githubusercontent.com/46181173/118449468-2742cd00-b72e-11eb-84b2-ddc014d3a9c0.png" width="50%">

## Wine Quality 데이터 학습, 평가(교차검증) <br>

1. 목적 : Wine Quality데이터를 가지고 (SVM / DecisionTree / RandomForest) 분류기를 이용하여 와인의 퀄리티를 예측, 학습, 평가한다 <br>
2. 내용 및 방법 : 데이터 읽기 및 분석, 모델 성능평가<br>
3. 결과 : 성능 비교 후 우수 분류기 파라미터 튜닝 및 결과 분석
   - 성능 비교표
   - 파라미터 튜닝
   - ROC Curve
   - Classification Report
   - cut-off
   - Importance

## 데이터 읽기 및 분석

1599 rows x 12 columns <br>

1. Input variables (based on physicochemical tests)
   - fixed acidity (고정 산도)
   - volatile acidity (휘발성 산도)
   - citric acid (구연산)
   - residual sugar (잔류 설탕)
   - chlorides (염화물)
   - free sulfur dioxide (유리 이산화황)
   - total sulfur dioxide (총 이산화황)
   - density (밀도)
   - pH
   - sulphates (황산염)
   - alcohol (알코올)
2. Output variable (based on sensory data)
   - quality (score between 0 and 10)

<img src="https://user-images.githubusercontent.com/46181173/118449592-46d9f580-b72e-11eb-9d92-efe658006345.png" width = "80%"><br>

1. alchol, volatile acidity는 quality와 비교적 높은 상관관계를 갖는다.
2. citric acid, density는 fixed acid와 비교적 높은 상관관계를 갖는다.

## 모델 성능평가

1. SVM
2. DecisionTree
3. RandomForest

## 성능비교 (정확도)

- SVC : 0.862500
- DecisionTree : 0.860417
- RandomForest : 0.893750 <br>

RandomForest의 성능이 가장 좋음

## 파라미터 튜닝 및 성능 확인

1. Box plot
   <img src="https://user-images.githubusercontent.com/46181173/118450532-42620c80-b72f-11eb-96b9-a5887ec791df.png"><br>
   Tree의 수가 많아질수록 Scores가 대체로 높아짐을 확인

2. ROC Curve

   <img src="https://user-images.githubusercontent.com/46181173/118450552-4726c080-b72f-11eb-9cda-6e36cb7b335a.png"> <br>
   모델의 성능이 좋음을 확인

3. Classification Report

   - Precision : 0.91
   - Recall : 0.96
   - f1-score : 0.89

# Cut-Off

F1 = (2 X recall X precision) / (recall+preicision) <br>
정밀도와 재현율이 모두 강한 분류기를 선호 F1_score<br><br>
예측 확률을 예측으로 변환 할 때 가장 좋은 F1 Score를 위한 cut-off 탐색

<img src="https://user-images.githubusercontent.com/46181173/118451467-404c7d80-b730-11eb-9b12-6e77473ad941.png">
0.3 ~0.5 cut-off 에서 높은 값을 보임

# Importance

<img src="https://user-images.githubusercontent.com/46181173/118451026-c5836280-b72f-11eb-81da-244f2c9588e3.png">
alchol, sulphates, volatile acidty, density 순으로 영향을 크게 미침 <br><br>

<p>
<img src="https://user-images.githubusercontent.com/46181173/118452281-f57f3580-b730-11eb-99b5-59b82424e58f.png" width="45%">

<img src="https://user-images.githubusercontent.com/46181173/118452289-f748f900-b730-11eb-8e43-4aa7db507590.png" width="45%"> 
</p>

alchohol은 quality와 양의 관계 <br>
volite acidity는 quality와 음의 관계
