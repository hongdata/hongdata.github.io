---
layout: post
title:  "데이터 정규화"
categories: Theory
published : True
tags: #이론 #통계학 #빅데이터
excerpt: false
mathjax: true
---

<p>데이터 정규화</p>
<p>데이터 전처리를 이해하는데 있어 중요한 기능중 하나로, 데이터의 범위를 일치시키거나 분포를 유사하게 만들어주는 기능.</p>
<p style="text-align: left; clear: none; float: none;">[##_1N|cfile27.uf@99F20E395C87BE441CBF73.png|width="700" height="394" filename="data-normalization1.png" filemime="image/jpeg" style="width: 700px; height: 394px;"|_##]</p>
<p><br /></p>
<p>위의 그림에서 보았을 때, Age와 income의 featrue를 비교하는 어려운데, 이 값을 그대로 적용할 경우 선형회귀분석의 경우에는&nbsp;본질적으로&nbsp;income의 값의 범위가 훨씬 크기때문에 income의 feature가 결과값에 더 큰 영향을 준다.&nbsp;</p>
<p>그러나 값의 ragnge가 더 크다고하여&nbsp;income이 실제로 더 중요한&nbsp;예측변수라고 보기는 어렵다. 이것을 방지하기위해, 우리는 데이터의 범위를 0~1의 범위로 변환시켜 데이터 정규화를 진행할 수 있다.&nbsp;</p>
<p><br /></p>
<p style="text-align: left; clear: none; float: none;">[##_1N|cfile5.uf@9972073D5C87C03D1DCC0B.png|width="700" height="398" filename="data-normalization2.png" filemime="image/jpeg" style="width: 700px; height: 398px;"|_##]</p>
<p>데이터 정규화의 방법에는 위와같이 세 가지 방법으로 진행해볼 수 있다.</p>
<p><br /></p>
<p>python 적용 예시 :&nbsp;</p>
<p style="text-align: left; clear: none; float: none;">[##_1N|cfile23.uf@997487485C87C0EE34AA09.png|width="700" height="393" filename="data-normalization3.png" filemime="image/jpeg" style="width: 700px; height: 393px;" original="yes"|_##]</p>
<p style="text-align: left; clear: none; float: none;">[##_1N|cfile29.uf@9961EF485C87C0EE110265.png|width="700" height="396" filename="data-normalization4.png" filemime="image/jpeg" style="width: 700px; height: 396px;" original="yes"|_##]</p>
<p style="text-align: left; clear: none; float: none;">[##_1N|cfile27.uf@99639C485C87C0EF34B168.png|width="700" height="390" filename="data-normalization5.png" filemime="image/jpeg" style="width: 700px; height: 390px;" original="yes"|_##]</p>
<p><br /></p>
