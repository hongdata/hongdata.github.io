---
layout: post
title:  "Data Normalization (데이터 정규화)"
categories: Theory
published : True
tags: 이론 통계학 빅데이터 
excerpt: ''
mathjax: true
---

**데이터 정규화**
데이터 전처리를 이해하는데 있어 중요한 기능중 하나로, 데이터의 범위를 일치시키거나 분포를 유사하게 만들어주는 기능.

<img src='{{ "/images/data-normalization1.png"}}'>
위의 그림에서 보았을 때, Age와 income의 featrue를 비교하는 어려운데, 
이 값을 그대로 적용할 경우 선형회귀분석의 경우에는 본질적으로 income의 값의 범위가 훨씬 크기때문에 
income의 feature가 결과값에 더 큰 영향을 준다.

그러나 값의 range가 더 크다고하여 income이 실제로 더 중요한 예측변수라고 보기는 어렵다. 
이것을 방지하기위해, 우리는 데이터의 범위를 0~1의 범위로 변환시켜 데이터 정규화를 진행할 수 있다.


<img src='{{ "/images/data-normalization2.png"}}'>

데이터 정규화의 방법에는 위와같이 세 가지 방법으로 진행해볼 수 있다.
python 적용 예시 :
<img src='{{ "/images/data-normalization3.png"}}'>
<img src='{{ "/images/data-normalization4.png"}}'>
<img src='{{ "/images/data-normalization5.png"}}'>
