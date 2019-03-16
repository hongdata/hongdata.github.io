---
layout: post
title:  "Data Evaluation (모델평가)"
categories: Theory
published : True
tags: 이론 통계학 빅데이터 모델평가
excerpt: ''
mathjax: true
---


## 모델 평가
예측을위한 feature와 알고리즘 등을 정리하여 Machine Learning 모델을 만들었다면,  
이 모델이 제대로 만들어진 것인지, 어느정도 예측력을 발휘할지 확인을 해봐야 합니다. 


## scikit-learn train_test_split
우리가 가진 데이터가 100개 라고 가정한다면,  
70개의 데이터를 사용해서 모델을 만들어보고  
나머지 30개의 데이터는 결과값을 모의 예측하는데 사용하는겁니다.  
scikit-learn에서는 train_test_split이라는 함수를 제공하여 아래와 같이 간단하게 나눌 수 있습니다.

```
from sklearn.model_selection import train_test_split

train_data, test_data, train_label, test_label = train_test_split(X_train_data, X_train_label, test_size = 0.3, random_state=0)
```

X_train_data : 독립변수  
X_train_label : 종속변수  
test_size : test data의 비율 (0.3이라면 30%를 의미하며 default 값은 0.25입니다.)  
random_state : random seed 번호  

train_data , test_data : training set  
train_label , test_label : testing set  


## K-fold cross validation (교차검증)  
교차검증이란, 데이터를 K개의 fold로 나누어 여러번 검증하는 것입니다.  

우리가 앞서 100개의 데이터를 이용하여  
1번~70번까지의 데이터로 훈련데이터를 만들고, 71번~100번 데이터로 검증데이터를 만들어 모델 평가를 1회 진행했다면,  
K-fold 교차검증방법을 이용해 5회 fold를 만들어 진행하는 경우에는  
1~20 : 검증데이터, 21~100: 훈련데이터 -> 1회 훈련  
21~40 : 검증데이터, 그 외 훈련데이터 -> 2회 훈련  
41~60 : 검증데이터, 그 외 훈련데이터 -> 3회 훈련  
71~80 : 검증데이터, 그 외 훈련데이터 -> 4회 훈련  
81~100 : 검증데이터, 그 외 훈련데이터 -> 5회 훈련 처럼 여러차례 검증해보는 방식입니다.  

<img src= "/images/modelevaluation.jpg" width="600">  
<이미지 출처 : https://www.dummies.com/programming/big-data/data-science/resorting-cross-validation-machine-learning/>  

교차검증의 경우, 연산이 몇 배로 늘어난다는 단점이 있지만  
데이터의 수가 충분하지 않은 경우 underfitting도 예방할 수 있으며  
랜덤하게 데이터를 나누어 1회만 검증 할 경우, 나누어진 데이터의 구성에 따라  
(우연찮게 예측하기 쉬운 데이터들이과 그렇지 않은 데이터들로 나누어졌다거나..)  
높거나 낮은 예측률을 발휘하는 등의 상황을 예방할 수 있습니다.  

파이썬에 실제로 적용되는 함수로는 방법에 따라 꽤 다양하게 존재해서 다음 기회에 몇 가지 살펴보는거로 하겠습니다.  


## Confusion matrix (오분류표)  

<img src = "/images/modelevaluation-2.png" width="600">  
<이미지 출처 : https://www.dataschool.io/simple-guide-to-confusion-matrix-terminology/>   
Confusion matrix 또한 모델 평가방법에서 꼭 거쳐봐야할 방법 중 하나입니다.  

오분류표의 개념에는 다음과 같은 것들이 있습니다.  
true positives (TP): Yes로 예상했고 실제 값 또한 Yes로 제대로 분류한 경우.  
true negatives (TN): No로 예상했고 실제 값 또한 No로 제대로 분류한 경우.  
false positives (FP): Positive로 예상했지만 실제 값이 No로 오분류한 경우. (1종오류)  
false negatives (FN): No로 예상했지만 실제 값이 Yes로 오분류한 경우. (2종오류)  

Accuracy : 정분류율
(TP+TN)/total = (100+50)/165 = 0.91  

Misclassification Rate : 오분류율
(FP+FN)/total = (10+5)/165 = 0.09  (= 1-Accuray)  

True Positive Rate ("Sensitivity" or "Recall") : 실제 Yes인 값들 중 Yes로 예측한 비율 (민감도 혹은 재현률)  
TP/actual yes = 100/105 = 0.95  

False Positive Rate: 실제로 No인 값들을 Yes로 예상한 비율  
FP/actual no = 10/60 = 0.17  

True Negative Rate ("Specificity") : 실제로 No인 값들 중 No로 예측한 비율 (특이도)  
TN/actual no = 50/60 = 0.83 (=1-False positie rate)  

Precision: Yes로 예측한 값들 중 실제로 Yes인 비율 (정밀도)  
TP/predicted yes = 100/110 = 0.91  

Prevalence: 전체 데이터 중 Yes의 값이 얼마나 많이 일어났는가  
actual yes/total = 105/165 = 0.64  

파이썬으로 plot 생성하는 방법은 아래 링크 참고하세요.  
https://scikit-learn.org/stable/auto_examples/model_selection/plot_confusion_matrix.html
