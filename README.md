# 신용카드 사용자 연체 예측 AI 경진대회 (데이콘)
# 1. 개요
- 교내 통계학 특강 팀프로젝트를 위해 참가 
- 팀원: 고태영, 오혜린, 이세령, 정민경, 황재원
- 기간: 2021.04~ 2021.06
- skill tool: Python
- evaluation: Logloss

# 2. 데이터 
- Raw: 개인별 신용카드 사용 데이터 (성별, 차량 소유 여부 등 20개의 variable)
- Binary transform, Positive conversion, outlier 제거, log transform 등 데이터 전처리 수행
- PCA를 사용한 child_num, Famlily 변수 재정의 등

# 3. Modeling
- ML: Catboost, LGBM, RF 모델링. 각각 GridSearch 통한 파라미터 튜닝 진행
- Tabnet: 정형 데이터에서 강점을 가지는 딥러닝 아키텍처
- 각 모델의 성능 비교하여 최종 제출
<img width="1173" alt="image" src="https://user-images.githubusercontent.com/79994991/167252518-4b229ab2-e4e7-42da-a55e-0a5725239799.png">

# 4. 한계점
1. Not to make enough derived variables
2. Not to do cleansing
3. Worry in vain
  1) Unnecessary to deal with nominal variables Catboost can automatically convert categorical variables and
  use them without the user having to do anything else.
  2) Unnecessary to deal with missing values.
  Just replace Nan is the best. We consider smote and model-based imputation, but they didn’t work.
4. Lack of duplicate data processing
5. No need to Hyper-parmeter tunning
The model performance improvement is negligible compared to the effort required to tune the hyperparameters.
