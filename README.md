# 36-1. 난소암 데이터 활용 AI 모델 개발

<br>

## 모델 종류
1. 난소종양 객체 탐지 모델(CT 이미지) v1.0: CT 이미지를 대상으로 난소종양 양⋅악성 분류 및 영역 탐지
2. 난소종양 객체 탐지 모델(초음파 이미지) v1.0: 초음파 이미지를 대상으로 난소종양 유형 분류 및 영역 탐지
3. 난소암 재발기간 예측 모델 v1.0: 메타데이터를 활용하여 난소암 환자의 첫 재발이 나타나는 기간 예측

## AI 모델별 소스코드 및 환경 
### 1. 난소종양 객체 탐지 모델(CT 이미지) v1.0
---
- 폴더
  1) data
  2) log
  3) model
- 파일
  1) ss
  2) ss
  3) ss
  4) ss
- 개발 환경
  - `Python 3.8.10`
  - **Framework** : CUDA(), Pytorch(xx)

### 2. 난소종양 객체 탐지 모델(초음파 이미지) v1.0
---
- 폴더
  1) data
  2) log
  3) model
- 파일
  1) ss
  2) ss
  3) ss
  4) ss
- 개발 환경
  - `Python 3.8.10`
  - **Framework** : CUDA(), Pytorch(xx)
    
### 3. 난소암 재발기간 예측 모델 v1.0
---
- 폴더
  1) data
     - 'preprocess_test.py'를 실행하면 생성되는 전처리 완료 테스트 데이터 위치 
  2) log
     - 'evaluate.py'를 실행하면 생성되는 로그 파일 저장 위치
  3) model
     - 'rfRegressor.pkl' 학습 완료 모델 파일 저장 위치
- 파일
  1) preprocess_test.py : 모델 성능 검증을 위한 테스트셋 전처리 실행 파일
  2) evaluate.py : 모델 성능 검증 파일
  3) utils.py : 1, 2번 파일 실행을 위한 모듈
- 개발 환경
  - `Python 3.10.9`
  - **Framework** : CUDA(11.8), scikit-learn(1.2.2)
