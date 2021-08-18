# fingerprint_recognition

:running: CNN을 활용하여 지문 인식 Model 학습 Mini project


# Model Architecture
![아키텍처](https://user-images.githubusercontent.com/55770741/129839530-28e5d7e0-0b89-4706-be0a-6de10765cb55.JPG)
+ 같은 가중치(하나의 Model)을 사용하여 Input 과 DB에 있는 데이터를 학습한다
+ Model의 Output 2개의 vector를 subtract 하여 Conv, Pool로 한번 더 분석을 해준 다음, Flatten과 Dense, Sigmoid를 사용하여 두 개가 같은지 다른지 판별


  

# Result
![지문](https://user-images.githubusercontent.com/55770741/129840222-ab683119-0628-4718-8c91-ef57bf56d13f.JPG)
+ 같은 것은 1 다른것은 0으로 값을 반환

# Dependencies
+ Python
+ numpy
+ keras
+ matplotlib
+ sklearn
+ imgaug

# Dataset
Sokoto Coventry Fingerprint Dataset (SOCOFing) https://www.kaggle.com/ruizgara/socofing/home

# 새로 배운 점
:sunny: imgaug library를 사용해서 image를 살짝씩 변형하여 많은 데이터를 만들 수 있다  
:cloud: Sequential API를 사용하여 Model을 구현해보았는데, Model을 만드는 것이 매우 쉽고 사용하기가 간단했다, 하지만 복잡한 수식을 가진 Model은 구현하지 못한다는 단점이 있다.  
:zap: 수 많은 data를 한 번에 Test하기 위해서 Data generator를 이용해봤다. Sequence라는 것을 상속받는 클래스이고, init, __len__, __getitem__, on_epoch_end를 기본적으로 가지고 있는데,   init는 인자를 받고, len은 index를 반환해주는 역할을 하며, getitem은 index횟수 만큼 특정 동작을 하며, on_epoch_end는 반복을 하게 도와준다
