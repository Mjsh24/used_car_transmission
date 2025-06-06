# 중고차 변속기 예측 프로젝트 🚗📊

## 📦 데이터셋
- [Kaggle](https://www.kaggle.com/code/yogidsba/predict-used-car-prices-linearregression): 인도 중고차 데이터셋 (약 6000여 건)
- 주요 컬럼:
  - `Kilometers_Driven`, `Fuel_Type`, `Mileage`, `Power`, `Price`
  - 타겟 컬럼: `Transmission` (0 = Manual, 1 = Automatic)
  - 가격은 환율(1INR = 16.73KRW) 적용하여 백만 원 단위로 변환

## 🎯 목표
- 차량의 제원 정보(출력, 주행거리, 연비 등)를 바탕으로 **변속기 유형(수동/자동)을 예측**하는 머신러닝 모델 구축
- **의사결정트리(DecisionTreeClassifier)**를 활용하여 예측 모델을 설계하고, 중요 피처를 시각화
- 예측 결과를 기반으로 **중고차 추천 시스템 개발 가능성** 검토

## ✅ 진행 과정
1. 데이터 수집 및 전처리:
   - 결측치 처리, 범주형 인코딩, 파생 변수 생성
   - 가격 데이터는 환율 적용 후 백만 원 단위로 변환
2. 모델 학습:
   - `DecisionTreeClassifier`를 사용한 예측 모델 학습 (max_depth=5)
   - `GridSearchCV`를 통한 최적 하이퍼파라미터 탐색
3. 성능 평가:
   - ROC 곡선 및 AUC 점수 계산 (AUC = 0.898)
   - 테스트 정확도 약 88%
4. 모델 시각화:
   - Graphviz를 활용한 의사결정트리 시각화
   - 주요 피처의 중요도 시각화

## 📌 결론
- 출력(Power)과 주행거리(Kilometers_Driven)가 **변속기 유형 예측에 가장 큰 영향**을 미침
- ROC AUC = 0.898로 **높은 분류 성능을 기록**
- 예측 결과를 통해 **자동차 구매 플랫폼에 중고차 추천/필터링 기능으로 활용 가능**함을 확인

## 🚀 시사점
- 중고차 시장에서 **자동차 제원만으로 변속기 유형을 예측할 수 있는 모델**이 존재하면 사용자 편의성이 크게 향상될 가능성
- 의사결정트리 모델은 해석력이 높아, **구매자에게 예측 근거를 시각적으로 제공**할 수 있는 장점이 있음

## 🛠️ 개선점
- 타겟 변수(`Transmission`)의 불균형 문제 보완
- 연료 유형(`Fuel_Type`)이 예측에 미치는 영향이 적었던 점에 대한 추가 분석
- 차량 연식 데이터를 포함하여 **예측 성능을 높일 수 있는 가능성** 검토
