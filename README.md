# Find_Waldo Code Study
## 설명
Find_Waldo 코드를 같이 공부하고 그 결과를 정리한 저장소입니다.

## 원본코드
코드: https://github.com/kairess/find_waldo   
데이터셋: https://www.kaggle.com/kairess/find-waldo

## 코드 설명
CNN을 사용하여 모델을 만들고 이미지를 학습해 이미지에서 waldo가 있는 곳을 찾는 코드입니다.

## 버전


## 기여
01. Data Generator : tak-jj
02. Build Model : seungbummm
03. Set Class weight and train model : jukitty
04. Evaluation : Seokwoo-Kang

## 피드백
아래 소스 코드가 그리 깔끔하게 잘 작성되지 않아서 직관적으로 보이지 않습니다.

Keras에 패키지들이 하나 둘 막히는 것이 프로젝트의 방향이 바뀌는 것 같아서 장기적으로는 아래 방식이 좋지 않을 것 같습니다. 섹터를 나누고 그 섹터에서 CNN으로 분류하는 것은 해결되지 않는 문제가 다소 있어 보입니다.

Tensorlfow는 지속적으로 업데이트가 되고 있고 문서화도 비교적 충실하게 되어 있어서 문제를 해결하는데 도움을 받을 수 있습니다.


 CNN을 이용한 접근 보다는 Tensorflow Object Detection API을 사용하는 접근이 더 적당해 보입니다.
 


 CNN을 이용한 접근 보다는 Tensorflow Object Detection API을 사용하는 접근이 더 적당해 보입니다. 

# READ.me
'월리를 찾아라'의 주제는 CNN을 이용한 접근보다는 ```Tensorflow Object Detection API```를 사용하는 접근이 더 적당해 보인다.
1. 더 직관적인 소스코드로 작성이 가능하다.
2. Keras의 패키지들이 하나 둘 막히는 이유가 있을 것이라고 생각된다. 문서화가 잘 되어있는 ```Tensorflow```를 사용하도록 하자.


우리는 여기에서 또 하나의 의문점이 들었다. '월리가가 있다, 없다 로 나뉘는데 왜 ```Binary cross entropy```를 사용하는 이진분류 문제로 풀어낸 것이 아닌 ```.fit_generator()``` 메서드를 사용하여 ```class weight```으로 접근 했을까?' 이 부분에 대해선 선생님께 여쭤보았다.   


 선생님께선 '이 코드는 단순히 월리가 있다, 없다가 아닌 다양한 캐릭터들을 분류하여 월리의 확률이 높은 캐릭터를 찾아내는 방식으로 접근한 것으로 보인다'라고 말씀해주셨다. 이 경우는 ```soft max```를 사용해도 가중치로 충분히 분류가 가능하기 때문이다.