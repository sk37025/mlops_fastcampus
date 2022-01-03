# CONTENTS 

- [01.기존 ML 프로젝트 진행방식의 한계](#01.기존_ML_프로젝트_진행_방식의_한계)
- [02.ML DevOps = MLOps](#02.ML_DevOps_=_MLOps)
- [03.MLOps의 구성 요소](#03.MLOps의_구성_요소)
- [04.앞으로의 강의에 대하여](#04.앞으로의_강의에_대하여)


# 01.기존 ML 프로젝트 진행 방식의 한계

- 기존 ML 프로젝트 진행 방식 돌이켜보기 
- 성능이 가장 좋았던 모델의 정보가 기억나나요? 
> 모델에 대한 정보를 checkpoint로 저장하는 것 뿐만이 아니라 모델들 사이의 평가지표가 잘 모니터링이 안되어있는 것이 기존 ML 프로젝트의 한계   

> 학습 환경과 배포 환경은 같지 않음 (validaion set에서는 좋았지만 test set에서는 좋지 않은 경우가 존재함)

- 그나마 체계적으로 관리를 해놓은 상황이라면 (parameter까지 잘 정리해놓은 경우), 상황은 더 나을 수 있음.

## 하지만 여러 명이 함께 협업해야 한다면? 

> 모든 사람들이 파이썬 버전, 토치, 텐서, 맥 등 각각 다른 환경에서 사용한다면? 재현이 가능할까요? 

- 하나의 컴퓨터를 공유해야 한다면? (하나의 서버에서만 모델을 돌려야 한다면?)

> 소수의 기업을 제외하고 이러한 ML을 서비스화하는 기업은 많지 않음 

__이상__ 속 ML 서비스화 

데이터 준비 >>> 모델 구현 >>> 모델 배포 >>> 돈 


# 02.ML DevOps = MLOps

### 전통적인 Software 개발 방식 
- 코드 구현 > 빌드 > 배포 

### ML 프로젝트와 SW 프로젝트의 유사성 

1. 버전 관리 
> 데이터 버전 관리, 모델 버전 관리 

2. 테스트 자동화 
> 모델 학습 자동화, 모델 성능 평가 자동화 

3. 모니터링 
> 서빙 모델 모니터링, 데이터 변화 모니터링, 시스템 안정성 모니터링 

### AI 서비스와 일반 SW의 차이점 

> AI service = sw + Data

#### 아직은 생소한 분야!!!!

MLOps란? 
> `ML을 효율적으로 개발하고 성공적으로 서비스화하고 운영할 때 필요한 모든 것을 다루는 분야`

# 03.MLOps의 구성 요소

> 데이터, 모델, 서빙 파트 3개로 나뉘어져 있음.  

## 1. 데이터 

### 1-1. 데이터 수집
> Sqoop, Flume, Kafka, Flink, Spark Streaming, Airflow

### 1-2. 데이터 저장
> MySQL, Hadoop, Amazon S3, MinIO

### 1-3. 데이터 관리 
> TFDV, DVC, Feast, Amundsen 

## 2. 모델 

### 2-1. 모델 개발 
> Jupyter Hub, Docker, Kubeflow, Optuna, Ray, katib

### 2-2. 모델 버전 관리 
> Git, MLflow, Github Action, Jenkins

### 2-3. 모델 학습 스케쥴링 관리
> Grafana, Kubernetes 

## 3. 서빙 

- 데이터를 받으면, ml모델의 예측을 수행하는 것을 서버에서 실행하는 것을 의미함.
- 의존성이 없게끔 컨테이너에 환경들이 저장되어 있어야 함. 

### 3-1. 모델 패키징 
> Docker, Flask, FastAPI, BentoML, Kubeflow, TFServing, seldon-core

### 3-2. 서빙 모니터링 (alarm)
> Prometheus, Grafana, Thanos

### 3-3. 파이프라인 매니징 
> Kubeflow, argo workflows, Airflow

이 모든 것을 제공하는 cloud >> Aws SageMaker, GCP Vertex AI, Azure Machine Learning

# 04.앞으로의 강의에 대하여

ML 이론/ SW 구현 능력 / 클라우드 지식 들이 필요함! 
