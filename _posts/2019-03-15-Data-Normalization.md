---
layout: post
title:  "Data Normalization (데이터 정규화)"
categories: Theory
published : True
tags: 이론 통계학 빅데이터 정규화
excerpt: ''
mathjax: true
---

### **데이터 정규화**  
데이터 전처리를 이해하는데 있어 중요한 기능중 하나로,  
데이터의 범위를 일치시키거나 분포를 유사하게 만들어주는 기능. 
  
일반적으로 정규화는 데이터의 분포에 변경을 주고  
스케일링은 분포에는 변경이 없지만, 데이터의 범위를 일치시켜주는 기능을 합니다.  
  
**정규화**  
정규화는 데이터에 log를 사용하거나, box-cox transformation을 이용하여 분포를 바꿔줍니다.  
<img src='/images/distribution.png' width = "600" >  
<br>
<br>
<br>
**스케일링**  
<img src='/images/data-normalization1.png' width = "600" >  
위의 그림에서 보았을 때, Age와 income의 featrue를 비교하는 어려운데,  
이 값을 그대로 적용할 경우 선형회귀분석의 경우에는 본질적으로 income의 값의 범위가 훨씬 크기때문에  
income의 feature가 결과값에 더 큰 영향을 준다.  

그러나 값의 range가 더 크다고하여 income이 실제로 더 중요한 예측변수라고 보기는 어렵다.  
이것을 방지하기위해, 우리는 아래와같이 세 가지 방법을 통해  
데이터의 범위를 0~1의 범위로 변환시켜 데이터 정규화를 진행할 수 있다.  
<img src='/images/data-normalization2.png' width = "600"><br/>


<br>
<br>
python 적용 예시 :    
<img src='/images/data-normalization3.png' width = "600">
<img src='/images/data-normalization4.png' width = "600">
<img src='/images/data-normalization5.png' width = "600">
