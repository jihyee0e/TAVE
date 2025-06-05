## 머신러닝을 이용한 경기 국면별 기업 부실 예측

### 프로젝트 개요

프로젝트명: 경기 국면별 기업 부실 예측

목적: 경기 국면(확장기와 수축기)에 따른 기업의 부실 위험을 예측하여 신용 위험 변동을 분석하고 중소기업의 재무건전성을 평가하는 모델을 개발

### 담당 및 역할 수행
1. 주제 구체화 및 정의
   - 논문을 참고하여 경기 국면별로 확장기와 수축기 연도를 지정
   - 부실 기업의 기준을 정의하여 분석의 명확성 확보
     
2. 데이터 전처리
   - 중소기업 추출: 평균 자산 5,000억 원 이상인 기업을 제외하여 분석 대상을 중소기업으로 한정
   - 특수목적회사 제거: '인베스트먼트', '투자' 등의 키워드를 포함한 기업을 필터링하여 순수 제조업 기업만 남김
   - 거래소 코드 검토: 중복된 코드 확인 및 거래소 코드를 기준으로 기업 분류
   - 재무비율 이상치 처리: 결측치를 0으로 대체하고 이상치 처리
   - 데이터 불균형 처리: 언더샘플링과 오버샘플링을 활용하여 불균형 데이터 문제 해결
     
3. 모델링
   - feature: Recursive Feature Elimination, Select From Model, Permutation Importance 등을 활용하여 중요한 피처를 선택
   - 확장기 모델: Logistic Regression, SVM

     ![Image](https://github.com/user-attachments/assets/b1664586-0a52-43c0-ae0f-667d33dc7e8c)
     
   - 수축기 모델: Logistic Regression

     ![Image](https://github.com/user-attachments/assets/e9ccff45-8ba3-46e5-b78a-c45406a4ab03)

4. 결론 및 한계점
   - 결론: 경기 국면에 따라 기업의 신용 위험 요인이 달라질 수 있음을 발견
     
     ![Image](https://github.com/user-attachments/assets/0ec94150-b8ff-4cf9-9df7-23b3cca42a1f)
     
   - 한계점:
      - 부실 기업 정의에 필요한 추가 데이터
      - 다양한 재무비율 변수의 선택 필요성
      - 외감기업 데이터의 신뢰성 문제 인식
