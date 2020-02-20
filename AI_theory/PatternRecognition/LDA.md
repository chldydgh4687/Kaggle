# #LDA (Linaer Discriminant Analysis)
---
</br>

 PCA에서 label 이 있다면 더 이상적인 차원 축소를 할 수 있지 않을까에서 시작되어 벡터를 사용한 PCA와는 달리 클래스내 (inter) 에서 분산, 클래스
 간(intra)의 평균 거리로 평균/ 분산의 수식으로 평균은 크게, 분산은 작게하여, 데이터를 1D로 사영시 클래스간 겹치는 데이터가 없게 해주는 직선을
 찾는 것을 목표로 한다.  
 
 다만 label이 없을 때 불가하다는 단점이 있다.
 </br>
 ```python
 from sklearn.discriminant_analysis import LinearDiscriminantAnalysis
 
 lda = LinearDiscriminantAnalysis()
 lda.fit(train_X,train_Y)
 lda.predict(test_X)
 ```
