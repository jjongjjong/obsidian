# Faithfulness 
설명이 모델의 예측 동작을 어느 정도 따르는지를 정량화합니다(더 중요한 특징이 모델 결과에 더 큰 역할을 한다고 주장). important하다고 하면 예측에 정말 **성실히** 큰 기여를 하고 있을 것.

## 1. Sanity checks
- 명백하고 자명한 task를 통해서 설명 모델을 test하는 방법
	- 동그라미, 세모 모양 맞추기
	- R-peak 높이 맞추기, RR interval 맞추기 등
	- 기존 PTB 논문에서는 Peak 높이를 맞추는 것으로 했음. 
	- ![[Pasted image 20231018222346.png]]
- 각 도메인에서 Sanity check으로 할 수 있는 것은 무엇일까? 

## 2. Randomization test
- Sanity checks의 Next step
	- 