# #RandomForest  
---  
</br>

Bootstrap을 통한 Train 셋에서 중복 허용하여 랜덤적으로 n개를 뽑아 Train 샘플링을 한다. 이를 통해 특정 데이터셋에서만 작용하는 과적합을 막을 
수 있다. Train셋의 특징이 k라 할 때, 중복 허용하지 않고 해당 샘플에서 sqrt(K) = d (이상적인 개수) 개를 뽑으려 한다. 이 개수대로 의사 결정
트리를 만든다.  
 
</br>

 위 과정을 반복하여 깊고 짧은 트리 여러 개가 생성되고, 각 트리에서 많은 답에서 가장 많이 나온 답을 선택하고 이와 같이 다수결의 답을 내는 것을
 RandomForest라 한다. 위의 과정에서 Bootstrap을 분류모델에 적용한 case를 bagging이라고 한다.  
</br>
 
 #### RF와 DT의 차이점
  RF는 DT와는 달리 좋은 질문을 주는 것이 아닌 무작위 랜덤적인 질문을 던져서 노이즈에 취약함과 과적합을 피할 수 있으나, 단점으로 연산량이
  많다는 단점이 있다.
 
- ####How to use RF
```python
from sklearn.ensemble import RandomForestClassifier
from sklearn.ensemble import RandomForestRegressor

clf = RandomForestClassifier(n_cstimators = 100, n_jobs = 1)
clf.fit(X_train,Y_train)
clf.predict(X_test)
```


- #### Parameter

n_estimators = 트리의 개수  
  
criterion = 'gini', 'entropy'  

max_depth = 최대 깊이   

n_jobs = 병렬 일하는 속도  

random_state = 부트스트랩의 랜덤성 적용  

class_weight = 'balanced'  
