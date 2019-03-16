---
layout: post
title:  "Regression (회귀분석)"
categories: Theory
published : True
tags: 이론 통계학 빅데이터 
excerpt: ''
mathjax: true
---

### 회귀분석의 유래
회귀분석이란, 1800년대 유전학자 Francis Galton에 의해 유래되었으며  
그가 발표한 논문에서 " 부모의 키가 매우 크다고해서 아들의 키가 매우 크지는 않으며,  
부모의 키가 매우 작다고해서 아들의 키도 매우 작지는 않다."  
라는 관계를 발견하며 결국 자식들의 키는 평균의로 회귀(Regression)한다 라고하여  
여기서부터 회귀분석이라는 용어가 사용되었다고 합니다.  
<br>
<br>
### 회귀분석이란 ?
회귀분석을 한마디로 정의하자면 "x가 한단위 변화할 때 y의 값" 으로 y = 2x 정도로 이해하시면 느낌이 쉽게 오실겁니다.  
  
회귀분석에는 단순회귀분석(Linear Regression)과 다중회귀분석이(Multiple Regression) 있는데요.  
단순회귀분석을 독립변수가 하나인 것이고  
다중회귀분석은 독립변수가 두 개 이상인 것입니다.  
  
회귀분석에는 독립변수(independent variable)와 종속변수(depednt variable)이 있는데요.  
독립변수는 우리가 머신러닝에서 사용하는 feature(혹은 predictor) 이고  
종속변수는 우리의 target label이 됩니다.  
여기서 independet variable(Predictor) = x, dependent variable(target) = y 라는 점을 기억해두셔야 합니다.  
( y = 2x 인것을 x = 2y 로 표현하면 안된다는 겁니다. )  
<br>
<br>
### 회귀분석식
<img src ="/images/regression-1.jpg" width = '600'>  
intercept는 절편 이라고 이야기하는데요, x가 0일때 y의 값을 입니다.  
그리고 그 뒤의 slope, b_1x로 기울기가 결정됩니다.  
  
  
"x가 0일때, y가 38423이며 x가 1씩 증가할 수록 y가 821씩 감소한다." 를 그래프를 그리면 아래와 같이 그래프를 그릴 수 있습니다.  
<img src ='/images/regression-3.jpg' width = '600'>  
  
  
다중 회귀분석도 같은 개념으로 이해하시면 되고 아래 그래프를 보면 쉽게 이해되실거라 생각합니다.  
<img src ="/images/regression-2.jpg" width = '600'>
