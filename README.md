Development of an AI Model for Glaucoma Detection through Deep Learning
### 1. 프로젝트 소개

#### 1.1. 배경 및 필요성

녹내장은 눈 속의 압력이 증가하여 시신경이 손상되고 부분적 또는 완전한 시력 손실로 이어질 수 있는 심각한 안과 질환입니다.
이 연구는 딥러닝 기반 특징 추출을 통해 초기 단계에서 녹내장을 감지하는 것을 목표로 합니다. 망막 또는 안저 이미지는 눈 질환을 감지하는 데 중요한 소스입니다. 녹내장의 주요 원인은 눈의 형태를 유지하는 액체의 양의 불균형으로 인해 시신경유두(ONH)에 가해지는 압력이 증가하여 손상을 초래하는 것입니다. 안저 이미지를 분석하여 녹내장을 조기에 감지할 수 있는 AI 모델을 개발하고, 이를 통해 환자의 예후를 개선하고 시력 손실의 위험을 줄이는 것을 목표로 하고 있습니다.

#### 1.2. 목표 및 주요 내용

본 연구의 주요 목표는 다음과 같습니다:

- 녹내장 조기 발견: 망막 안저 이미지를 활용하여 초기 단계에서 녹내장을 감지할 수 있는 딥러닝 기반 시스템을 개발합니다.

- 전처리 및 분할: 이미지 품질 향상 및 잡음 감소를 위한 전처리 기법을 구현하고, OC 마스크가 없는 데이터셋에서 관심 영역(ROI)을 추출하기 위한 분할 작업을 수행합니다.

- 특징 추출: 컨볼루션 신경망(CNN), 로컬 이진 패턴(LBP), 방향성 그래디언트 히스토그램(HOG), 가속화된 강인 특징(SURF)과 같은 하이브리드 특징 기술을 사용하여 시신경 유두(OD) 및 시신경 컵(OC) 영역에서 세부적인 특징을 추출합니다.

- 특징 선택 및 순위 매기기: MR-MR 방식을 사용하여 가장 대표적인 특징을 선택하고 순위를 매겨 효율적이고 정확한 특징 표현을 보장합니다.

- 분류: 서포트 벡터 머신(SVM), 랜덤 포레스트(RF), K-최근접 이웃(KNN)과 같은 다중 클래스 분류기를 사용하여 안저 이미지를 건강한 상태와 질환 상태로 분류합니다.

- 성능 평가: 제안된 시스템의 성능을 평가하기 위한 다양한 실험을 수행하여 녹내장 조기 발견에서 높은 정확도를 목표로 합니다.
  
### 2. 상세설계

#### 2.1. 시스템 구성도
![image](https://github.com/user-attachments/assets/c42361b2-594c-46c0-92a8-61cafaedaff1)

#### 2.2. 사용 기술

  |package | version |
  |--------|---------|
  | tensorflow | 2.17.0 |
  | kaggle | 1.6.17 |
  | keras | 3.5.0 |
  | numpy | 1.26.4 |
  | openCV | 4.10.0 |
  | scikit-image| 0.22.0 |
  | scikit-learn | 1.2.2 |
  | xgboost | 2.1.1 |
  | mrmr-selection | 0.2.8 | 
  
  

### 3. 설치 및 사용 방법
- 저장소를 클론합니다.
- 클론한 저장소에서 preprocess_image.ipynb 파일을 Jupyter Notebook을 통해 실행하려면 다음을 따르세요:
- Kaggle에서 데이터셋을 다운로드하려면 다음을 사용하세요:
   ```
  pip install kaggle
  ```
   주의: 먼저 Kaggle API를 설정하고 API 키를 사용하여 인증해야 합니다.
  Kaggle API 설정 방법:
  ```
  !kaggle datasets download -d deathtrooper/multichannel-glaucoma-benchmark-dataset
  ```
  Kaggle에 로그인한 후, "Account" 페이지에서 "Create New API Token"을 클릭하여 kaggle.json 파일을 다운로드합니다.
  kaggle.json 파일을 폴더에 저장합니다.
  이후 명령어를 통해 데이터셋을 다운로드할 수 있습니다.
- 다음으로 Jupyter Notebook을 사용하여 dataset_notebook.ipynb 파일을 실행하세요. 이 노트북은 메타데이터를 참고하여 전처리된 이미지를 건강한 이미지와 질환 있는 이미지로 분류합니다.
- 다음 단계로, 전처리된 이미지에서 특징을 추출하고 신경망 조합을 사용하여 이미지를 분류하는 CNN 딥러닝 모델을 실행합니다.
- 
### 4. 소개 및 시연 영상
<!--[![영상 이름](유튜브 영상 썸네일 URL)](유투브 영상 URL)-->
[![2024년 전기 졸업과제 41 Octas](https://img.youtube.com/vi/wpYf8Kyj2xE/0.jpg)](https://www.youtube.com/watch?v=wpYf8Kyj2xE)    


### 5. 팀 소개

| Name              | Contact Information     | Roles                                                   | 
|-------------------|-------------------------|---------------------------------------------------------|
| Nemekhbayar Nomin | sharon.nemhee@gmail.com | 데이터 수집, 특징 추출 알고리즘 구현, 분류 알고리즘 구현    |
| Battulga Bazarsad | nicoffeingg@gmail.com   | 이미지 전처리, 관심 영역(ROI) 감지, 특징 선택 알고리즘 구현 |
