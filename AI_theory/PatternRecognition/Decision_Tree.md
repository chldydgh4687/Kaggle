# #Decision Tree ( 결정 트리 )
---

</br>

 분류와 회귀모델에 적용할 수 있는 전통적인 머신러닝의 모델이다. 트리의 구성은 루트와 리프노드 사이의 가지를 엣지로하여 트리를 구성한다.
 목표로 좋은 질문을 던져서 학습시키며, 좋은 질문은 Test셋을 얼마나 많이 rejection을 시켜 가장 가지가 적은 트리로 직결되는 것을 이상적인
 목표로 한다. 학습의 예측 결과 값은 Leafnodes에서 모든 답의 평균 중 가장 많은 답을 낸 것을 채택한다.
 </br>
 
 좋은 질문의 기준은 낮은 값 엔트로피로 계산을 통하여 높은 Information gain 을 얻는 것을 이상적인 목표로 한다. 위 엔트로피 계산 말고도 정규화의
 log가 없는 gini, 와 미분이 되지 않아 잘 쓰이지 않는 misclassificiation이 존재한다.
</br>

이제 가지를 언제까지 칠 것인가에 대해 설명해보겠다. 조건에는 세 가지의 조건이 있다.  
 - 엔트로피 계산이 '0' 일 경우
 - 임계값을 주는 경우 
 - 노드의 개수에 고정 임계값을 주는 방식
 
 이 때, 과적합 혹은 조기 수렴의 문제가 있을 수 있고, 트리와 노드가 많이 생길 경우, 과적합이 일어날 확률도 높기 때문에, 위 상황에 대처하기 
위해 가지를 잘라내는 프루닝 방식이 있다.  
</br>
 이러한 트리의 장점으로는 큰데이터에 적용이 잘 되며, 양적말고도 질적 자료도 활용이 되어, 회귀 문제도 해결이 가능하다. 또한, SVM에 비해 파라미터
수정할 부분이 적으며, 스케일링 없이도 적용이 잘 된다. 미싱데이터에 강하며, 성능이 우수하다. 단점으로는 차원이 큰 데이터에서는 잘 작동하지 
않으며, 노이즈에 취약하다.  
</br>

- how to use (example)

```python

from sklearn.tree import DecisionTreeClassifier
from sklearn.tree import DecisionTreeRegressor

clf = DecisionTreeClassifier(random_state=0)
clf.fit(train_X, train_Y)
clf.predict(test_X)

```
