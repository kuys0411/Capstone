# 머신러닝을 이용한 보안 프로그램 설계

# 프로젝트 목표
머신러닝 기술을 보안에도 적용할 수 있다는 것을 제시해준다. 멀웨어를 분류할 수 있는 머신러닝 모델을 설계함으로써 최소한의 인력으로 비정상 패킷을 분류할 수 있게한다. 

# 기대효과 
1. 하루가 다르게 진화, 발전하고 있는 사이버 공격에 대한 효율적인 대처
2. IoT 악성코드 증가 추세 + IoT 보안 지출 증가  -> 머신러닝을 이용한 효율적인 보안솔루션을 제공

# 주로 사용한 Malware Sample
Neris 
-사용자가 모르는 사이에 패킷 송수신이 발생
1. SPAM을 송신
2. Click-fraud (광고서비스 자동 클릭하여 조회수를 높이는 기능)

기타 멀웨어: Rbot, Virut, Murlo, SIS.ay

# 개발환경
-구현언어 및 IDE: Pyhton (Spyder)

-라이브러리: pandas, numpy

-프레임워크

keras - https://keras.io/

Scikit-learn -  http://scikit-learn.org/stable/

# Keras 특징
1. 직관적인 API 인터페이스
2. 단순화, 모듈화
3. 다양한 딥러닝 프레임워크와의 쉬운 연동

# 과정
1. 데이터 수집(감염 전 Normal packet file, 감염 후의 Malware packet file)
2. Netmate tool을 사용한 Flow변환, Feature추출
3. 데이터 시각화를 통한 Feature 선별작업
4. Label 부여
5. Feature Normalization
6. 머신러닝 알고리즘 모델 (학습 & 테스트)
   -딥러닝 알고리즘(CNN)
   -머신러닝 알고리즘(RandomForest, DecisionTree, MLP, SVM...)
7. 5-fold Cross Validation방식으로 검증
8. 분류 정확도 비교 
   - Accuracy, Recall, Precision 
9. 최적의 알고리즘 제시 
   - CNN, DecisionTree, Randomforest (약 99%의 분류 정확도)

# 1 Flow = TCP/UDP Packet을 5-tuple을 기준으로 묶음
1. Source IP
2. Source Port
3. Destionation IP
4. Destination Port
5. Protocol

# CNN(Convolution Neural Network)
딥러닝 알고리즘으로 주로 영상, 음성인식 분야에서 사용되나 flow당 feature값을 이미지로 가정하고 진행함

(선별한 Feature 35개를 5x7 이미지로 가정하고 Convolutional Layer를 적용)

# 사용한 데이터 출처
https://mcfp.weebly.com/the-ctu-13-dataset-a-labeled-dataset-with-botnet-normal-and-background-traffic.html

# Netmate tool에 의해 추출되는 Feature 목록
https://github.com/DanielArndt/flowtbag/wiki/features




 



