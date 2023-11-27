# 036-049. 난소암 데이터 활용 AI 모델 개발

<br>

## 📌 모델 종류
1. 난소종양 객체 탐지 모델(CT 이미지) v1.0: YOLOv8
2. 난소종양 객체 탐지 모델(초음파 이미지) v1.0: YOLOv8
3. 난소암 재발기간 예측 모델 v1.0: RandomForestRegressor

## ⚙️ AI 모델별 소스코드 및 환경 
### 1. 난소종양 객체 탐지 모델(CT 이미지) v1.0
---
- task: CT 이미지를 대상으로 난소종양 양⋅악성 분류 및 영역 탐지
- 폴더
  1) data
      - 데이터셋: 구축 데이터셋
      - tmp_data: 원천데이터와 라벨링데이터를 학습용으로 전처리한 데이터 셋
  2) log: 모델의 평가 결과 로그 기록
  3) model: 학습이 완료된 모델
  4) preprocess: 데이터 전처리 파일 저장 경로
  5) yolov8: 학습 및 테스트 실행 파일 및 사전학습 모델
- 파일
  1) ly2.py : 구축 데이터를 학습용 데이터의 형식에 맞게 변환하는 전처리 실행 파일
  2) yolov8_ready_seg.py : 모델 학습 및 평가 실행 파일
- 개발 환경
  - `Python 3.8.10`
  - **Framework** : CUDA(11.8), Pytorch(2.0.0)

### 2. 난소종양 객체 탐지 모델(초음파 이미지) v1.0
---
- task: 초음파 이미지를 대상으로 난소 양성종양 유형(multi-class) 분류 및 영역 탐지
- 폴더
  1) data
      - 데이터셋: 구축 데이터셋
      - tmp_data: 원천데이터를 학습용으로 전처리한 데이터 셋
  2) log: 모델의 평가 결과 로그 기록
  3) model: 학습이 완료된 모델
  4) preprocess: 데이터 전처리 파일 저장 경로
  5) yolov8: 학습 및 테스트 실행 파일 및 사전학습 모델
- 파일
  1) ly2.py : 구축 데이터를 학습용 데이터의 형식에 맞게 변환하는 전처리 실행 파일
  2) yolov8_ready_seg.py : 모델 학습 및 평가 실행 파일
- 개발 환경
  - `Python 3.8.10`
  - **Framework** : CUDA(11.8), Pytorch(2.0.0)
    
### 3. 난소암 재발기간 예측 모델 v1.0
---
- task: 메타데이터를 활용하여 난소암 환자의 첫 재발이 나타나는 기간 예측
- 폴더
  1) data
     - raw_data의 상위 폴더이자, 'preprocess_all.py'를 실행하면 전처리 완료 데이터셋이 저장되는 위치
  2) raw_data
     - 전처리를 위한 전체 원본 메타데이터 위치
  3) model
     - 'rfRegressor.pkl' 학습 완료 모델 파일 저장 위치 
  4) log
     - 'evaluate.py' 파일을 실행하면 저장되는 평가 로그 파일 저장 위치
- 파일
  1) preprocess_all.py : train, validation, test set 전처리 실행 파일
  2) preprocess_test.py : 모델 성능 검증을 위한 테스트셋 전용 전처리 실행 파일
  3) train.py : 모델 학습 및 검증 결과 출력 파일
  4) evaluate.py : 모델 성능 검증 파일
  5) utils.py : 1 ~ 4번 파일 실행을 위한 모듈
- 개발 환경
  - `Python 3.10.9`
  - **Framework** : CUDA(11.8), scikit-learn(1.2.2)
