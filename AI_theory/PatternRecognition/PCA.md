# #PCA (Principal Components Analysis)

---
</br>


 공분산행렬 분해를 통하여 얻어지는 고유벡터(e1,e2,...) 와 고유값(c1,c2, ...)가 분산이 큰 ㅈ주축을 보여 데이터 분포를 linear Complication의
 식 형태로 데이터 분포를 나타내는 것이다. ( L = e1c1 + e2c2 + ... )  
 
 이 때, front 성분은 자세한 특징이 많고, 뒷부분에는 노이즈가 낀 정보가 있어서 노이즈 필터링을 통해 뒷부분을 날림으로써 차원 축소를 시킬 수 있다.
 레이블이 없어도 되나, 단점으로 노이즈부분과 앞부분 정보의 경계까 모호하여, e를 몇개 가질 것인지의 파라미터 조정을 일일이 해야한다는 단점이 있다.
 
 ```python
 from sklearn.Decomposition import PCA
 
 pca = PCA(n_components = 2)
 X_train = pca.fit_transform(X_train)
 X_test = pca.fit_transform(X_test)
 ```
