<h1 align="center"> 🎅 기대 수명 예측하기 </h1>
<h4 align="center"> 2023-1 데이터마이닝개론 중간 프로젝트</h4>

## Introduction
* 주제: 기대 수명을 예측하는 선형 회귀 모델 만들기   
* 분석 기간: 2023.04
* 참여자
  * [정다운](https://github.com/daunjj)


### 1. 데이터 탐색(EDA) 
* 데이터: 비공개
* 과정:
  1. 기본적인 통계 정보 확인
  2. 변수 간 상관관계 시각화
  <img src="https://github.com/daunJJ/DataMining_AI/assets/109944763/3aa8084e-4792-4ae5-8021-e7adcccbd186" width="340" height= "300"/>

  3. '기대수명'과 상관계수가 높은 특성 변수 확인

### 2. 선형 회귀 모델 적합
* 목표: 두 가지 데이터를 가지는 선형 회귀 모델 적합하기 
* 학습:
  1. '기대수명'과 상관관계가 높은 5개의 변수만 이용한 선형 회귀 모델
     * R2 score: 0.81
  2. 모든 수치형 변수를 포함하는 선형 회귀 모델
     * R2 score: 0.83
  
  -> 변수의 개수가 늘어날수록 모델의 설명력이 높아지나, 데이터 수집, 비용 등의 고려하여 적절한 수의 변수를 사용해야 한다. 

### 3. Regularization penalty 추가 
* 목표: 규제텀을 추가하여 과적합을 방지하고, 모델의 성능 개선하기 
* 학습:
  1. 규제텀의 weight를 조절하며 Lasso Linear Regression 적합
  2. 규제텀의 weight를 조절하며 Ridge Linear Regression 적합
 
  <img src="https://github.com/daunJJ/DataMining_AI/assets/109944763/28f31761-89df-40ca-873a-eb8bef824b79" width="300" height= "250"/>

  -> 기대와 달리 모델의 성능이 개선되지 않음 

### 4. 회귀 모델 성능 개선 
* 목표: 다양한 접근법을 시도하여 모델의 성능 개선하기 
* 과정:
  1. 사용하지 못했던 '범주형 변수' 사용하기
     * 고유값 개수가 많은 'Country'변수는 Label Encoding
     * 고유값 개수가 적은 'Status'변수는 One-hot Encoding
  2. StandardScaler를 이용해 데이터 정규화
    
* 결과: 최종적으로 0.84 R2 score 달성

********************

<h1 align="center"> 🐴 Best Image Classification Model </h1>
<h4 align="center"> 2023-1 데이터마이닝개론 기말 프로젝트</h4>

## Introduction
* 주제: 다양한 딥러닝 모델을 사용하여 이미지 class 분류하기  
* 분석 기간: 2023.06
* 참여자
  * [정다운](https://github.com/daunjj)


### 1. CIFAR10 데이터셋 분류 
* 데이터: 10개의 class를 가지는 [CIFAR 데이터셋](https://www.cs.toronto.edu/~kriz/cifar.html)

  <img src="https://github.com/daunJJ/DataMining_AI/assets/109944763/1f59abff-645c-402e-9c65-3d0f4da42519" width="300" height= "250"/>
* 목표: 이미지 Class를 분류하는 딥러닝 모델의 성능을 개선하기 위한  다양한 접근법 시도하기
* 학습:
  1. 기본 모델 적합 (VGG16 모델 사용) 
  2. 하이퍼 파라미터 조절
     * learning rate, epoch 조절
  3. 옵티마이저 변경
     * Adam에서 SGD 옵티마이저로 변경
  4. 모델 변경
     * GoogLeNet으로 변경 
  5. 하이퍼 파라미터 조절
     * batch size 조절 
* 결과: 최종적으로 94.16% Accuracy 달성

### 2. CIFAR10 데이터셋 분류 
* 데이터: 10개의 class를 가지는 [STL10 데이터셋](https://cs.stanford.edu/~acoates/stl10/)

  <img src="https://github.com/daunJJ/DataMining_AI/assets/109944763/bbfbc6c6-1898-460d-930f-79e263d61760" width="300" height= "250"/>
* 목표: 이미지 Class를 분류하는 딥러닝 모델의 성능을 개선하기 위한  다양한 접근법 시도하기
* 학습:
  1. 기본 모델 적합 (Resnet 모델 사용) 
  2. 하이퍼 파라미터 조절
     * batch size, learning rate, epoch 수를 적절하게 선정
  3. torchvision.transforms 모듈 조절
     * 이미지 resize, normalize 등 다양한 시도
  4. convolution layer 추가
* 결과: 최종적으로 74.64% Accuracy 달성 

