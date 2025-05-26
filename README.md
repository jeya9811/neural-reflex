implementation of neural reflexes   
=================================
신경반사의 구현   
-----------
Using the MNIST dataset of handwritten digits, we explored the feasibility of implementing a basic artificial neural network to mimic a biological phenomenon known as “reflex”—a response that bypasses the brain, as opposed to a typical cognitive reaction processed through the brain.   

This “reflex” was assumed to be detectable not at the final output layer of the artificial neural network, but preemptively at the hidden layers.   

Model Architecture:   
> Input Layer: 784 nodes   
> Hidden Layer 1: 300 nodes (ReLU activation)   
> Hidden Layer 2: 100 nodes (ReLU activation)   
> Output Layer: 10 nodes (Softmax activation)   

Training Parameters:   
> Optimizer: Adam   
> Loss Function: Sparse Categorical Crossentropy   
> Batch Size: 32   
> Epochs: Up to 100 (managed with EarlyStopping)   

After training on the MNIST data, the model achieved a test accuracy of 97.77%.   

For analysis, we extracted the output values from the hidden layers for each test sample and organized them by label. These values were then visualized using box plots.   

![image](https://github.com/user-attachments/assets/4e9deb99-fbed-4df9-9145-af74992da690)   
![image](https://github.com/user-attachments/assets/f36d7733-d3fd-45ef-bd31-240959309361)   

ANOVA (Analysis of Variance)   
> Null Hypothesis (H₀): The means of hidden layer output sums are equal across all label groups.   
> Alternative Hypothesis (H₁): At least one group’s mean is different.   

For both hidden layers, the p-values were found to be below the 0.05 significance level, indicating statistically significant differences in means between label groups.   

Additionally, pairwise Kolmogorov–Smirnov (KS) tests were performed between label distributions. Although a few pairs showed no significant difference at the 0.05 level, the majority of pairs exhibited distinct distributional differences.   

Through this experiment, we gained the insight that in certain situations, it may be possible to predict the outcome before reaching the output layer of the model.   

***
신경반사의 구현   
-----------   

숫자 손글씨 데이터셋인 MNIST를 이용하여 만든 기초적인 신경망으로 생명체로 하여금 물건을 만지고 뇌를 거치고 반응하는 방식이 아닌 뇌를 거치지 않고 처리하는 "신경반사"의 구현 가능성을 보았습니다.   

이러한 "신경반사"를 인공신경망의 끝까지 이르기 전에 은닉층에서 이를 미리 감지하는 것으로 가정하였습니다.   

모델 구조:   
> 입력층: 784개 노드   
> 은닉층 1: 300개 노드 (ReLU 활성화 함수)   
> 은닉층 2: 100개 노드 (ReLU 활성화 함수)   
> 출력층: 10개 노드 (Softmax 활성화 함수)   
   
학습 파라미터:   
> 옵티마이저: Adam   
> 손실함수: Sparse Categorical Crossentropy   
> 배치 사이즈: 32   
> 최대 에폭: 100 (조기종료 EarlyStopping으로 관리)   

MNIST 데이터 학습 후 테스트 결과 97.77%의 정확도를 가지는 모델 확보.   

해당 모델에 각 테스트 파일을 입력하였을 때 히든 레이어의 출력값을 레이블 별로 정리하고 이를 박스플롯으로 시각화   

![image](https://github.com/user-attachments/assets/b22c702d-0d7b-42b3-bf8c-e68223dc139d)   
![image](https://github.com/user-attachments/assets/bf217d64-3e0d-4bbe-8c77-dddec0311277)    

분산분석.   
귀무가설: 모든 라벨 그룹의 은닉층 합 평균이 같다.   
대립가설: 적어도 한 그룹의 평균이 다르다.   
이때 두 은닉층 전부 p-value가 유의수준 0.05보다 낮으며   
각 라벨별로 짝을 지어 KS검정 또한 진행한 결과 몇몇 경우에 유의수준 00.05에서 분포가 서로 다르지 않다고 결론이 나오는 경우가 있지만 대부분의 경우에 분포가 다른 형태를 보였다.   

이 실험을 통해 특정 상황에서 모델의 출력 레이어까지 이르기 전에 결과의 예측이 가능하다는 통찰을 얻게 되었다.    
