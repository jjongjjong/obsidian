
첫번째 방법은 비정형 데이터인 심전도 데이터를 ECG features로 변환하여, 해석가능한 머신러닝 conventional machine learning model과 its feature importance를 활용하는 것입니다. 
두번째 방법은 딥러닝 모델이 어느 영역의 심전도를 집중하는지 보여주는 GradCAM이나 Saliency map과 같은 방법을 적용하는 것입니다. 


첫번째 방법은 비정형 빅데이터를 활용한 머신러닝 성능을 충분히 끌어올리지 못한다.[ref](https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-023-01989-3). 두번째 방법은 개별 ECG에 대한 모델의 local interpretation만 보여줄 수 있다. 그러나 식약처와 같은 검증 기관에서는 전반적으로 모델이 기존 의학 지식와 부합하는지에 대한 model의 global interpretation을 확인하고 싶어한다. 

그래서 우리 팀은 model의 global interpretation을 위해서 Testing with Concept activation vectors(TCAV)와 Clustering을 활용하여 모델 해석을 하였다.  

The first method involves transforming unstructured ECG data into ECG features and utilizing conventional machine learning models along with their feature importance for interpretation. However, It fails to achieve a advantage of using unstructured big data [ref](https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-023-01989-3) to maximize the performance. The second approach is to apply techniques like GradCAM or Saliency maps to show which regions of the ECG the deep learning model is focusing on. It only offers a local interpretation of the model for individual ECGs. However, verification agencies such as the MFDS are keen to confirm if the model itself aligns with existing medical knowledge as a global interpretation. Consequently, our team utilized Testing with Concept Activation Vectors (TCAV) and Clustering for global model interpretation and showed that the deep learning model is detecting LVSD ECG based on the high-risk ECG features for LVSD as indicated by established medical electrocardiographic knowledge. 

각 Block은 심전도의 feature들을 추출하여 다음 블럭으로 전달한다.각 res block이 추출한 feature들은 model interpretation을 위해서 사용되었다. 

 ~~입력 데이터에 가까운 block의 feature일 수록 morphological한 정보를 담고 있으며, 멀어질수록 추상적인 정보를 담고 있다.~~ 


우리는 첫번째 residual 블럭에서 추출한 feature들을 활용하여 clustering을 수행하였다. 

우리는 TCAV 결과의 정성적 검증을 하기 위해서, 
우리는 TCAV score가 높은 block의 feature들을 이용하여 clustering을 수행하였다. 



우리는 deep learning model의 feature를 clustering하여, LVSD phenotype을 제안하고 모델의 설득력을 높이고자 하였다. 
각 cluster의 centroid ECG를 확인하였다. 그 결과, AiTiALVSD feature들은 
AiTiALVSD의 feature가 LVSD를 예측하기 위해서 어떤 feature 분포를 생성하고 있는지 확인하였다. 

우리는 Deep learning 기반의 새로운 LVSD phenotyping 방법을 제안하고자 한다. 기존에도 deep learning의 feature를 활용한 phenotyping 시도가 있었다. 그러나 어느 feature를 사용할 지에 대한 결정이 자의적이고 근거가 부족했다. 우리는 TCAV score가 높은 block의 feature를 활용하여 clustering을 수행하였다. TCAV분석은 captum python packge version 0.6.0(ref)를 활용하여 수행하였다. 

우리는 TCAV score가 제일 높게 나오는 block의 feature들을 clustering하여 새로운 phenotyping을 제안하고자 하였다. we assumed that the hidden feature of high TCAV score block would most likely encompass an accurate representation that aligns with recognizable medical knowledge of electrocardiographic appearances. 각 클러스터링의 결과를 분석함으로써 AiTiALVSD가 효과적인 LVSD representation를 구축하였음을 확인하였다. development dataset의 LVSD positive 심전도 feature들을 활용하여 K-means clustering을 학습하였다. 클러스터의 수는 Kelbow algorithm [ref][https://www.google.com/search?q=Finding+a+%E2%80%9CKneedle%E2%80%9D+in+a+Haystack%3A+Detecting+Knee+Points+in+System+Behavior&rlz=1C5CHFA_enKR954KR955&oq=Finding+a+%E2%80%9CKneedle%E2%80%9D+in+a+Haystack%3A+Detecting+Knee+Points+in+System+Behavior&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBBzQxNGowajeoAgCwAgA&sourceid=chrome&ie=UTF-8] 를 활용하여 선정하였다. clustering algorithm은 sklearn python package version 1.1.1(ref) 를 이용하여 수행되었다. 

We aimed to propose a new phenotyping by clustering the features of the block with the highest TCAV score. We assumed that the hidden features of the block with a high TCAV score would most likely provide an accurate representation that aligns with recognizable medical knowledge of electrocardiographic appearances. By a quantitative comparison of demographic findings, electrocardiographic and echocardiographic features of each cluster, we confirmed that AiTiALVSD effectively constructed an LVSD representation. Using the LVSD positive ECG features from the development dataset, we trained the K-means clustering algorithm. The number of clusters was determined using the Kelbow algorithm [ref]. The clustering algorithm was executed using the sklearn python package version 1.1.1 [ref].


## TCAV

TCAV is a technique for interpreting the decisions made by a machine learning model, particularly deep neural networks. It was developed by researchers at Google and is designed to provide insights into the internal workings of a model in a way that is understandable to humans. 

The main idea behind TCAV is to represent high-level concepts as features of neural network layer. These vectors, known as Concept Activation Vectors (CAVs), can be used to measure the extent to which a given concept is present in the inputs processed by the model. By calculating a TCAV score for a concept, we can quantify the overall importance of that concept for the decisions made by the model. 

Below is the detailed process of TCAV we applied.


우리는 Physionet open dataset를 활용하여 concept을 정의하고, concept dataset를 구축하였다. physionet challenge dataset은 총 6개의 다른 병원에서 모여진 ECG dataset을 통합한 데이터이다. Physionet 데이터 셋은 총 N개의 심전도가 26가지 부정맥 labeling이 되어 있는 multilabel ECG dataset이다. 각 심전도는 1개 이상의 부정맥 라벨을 가지고 있다. figure N은 physionet의 label 분포를 보여준다. 
우리는 라벨을 이용하여 아홉가지의 target concept을 정의하였다.  우리는 target conecept을 AiTiALVSD가 LVSD판단에 있어서 positively 활용하고 있는지 TCAV score를 통해 확인하고자 하였다. 아홉가지의 concept은 다음과 같다. atrial fibrillation and atrial flutter (AF), left bundle branch block (LBBB), right bundle branch block (RBBB), left axis deviation (LAX), right axis deviation (RAX), prolonged qt, nonspecific intraventricular conduction disorder (conduction disorder), abnormal q wave and abnormal t wave (abnormal Q,T wave). AF와 abnormal Q,T wave concept은 두 가지의 라벨을 합하여 정의하였다.  각 concept dataset을 구축할 때, concept dataset마다 겹치는 심전도가 없도록 N개의 심전도를 추출하였다. concept에 사용되지 않은 나머지 label들에서 무작위로 약 200개 샘플을 추출하여 10개의 random concept dataset을 구축하였다. 하나의 concept dataset를 구성할 때, 각 병원마다 추출된 데이터의 수가  균등하도록 추출하였다. 이는 특정 concept dataset이 target 부정맥을 대표하지 못하고, 특정 data source에 대한 bias를 대표하게 되는 것을 방지하기 위함이다. 만약 label이 부족한 data source의 경우에만 다른 data source에서 추가적으로 추출하였다. Table S1은 concept dataset의 data source 분포를 보여준다. 결과적으로 9개의 target concept datasets와 10개의 random concept datasets를 구성하였다. 

Figure N은 AiTiALVSD의 각 블럭마다 TCAV score 결과를 보여준다. 아홉가지 컨셉은 모두 random concept와 비교하여 유의하게 TCAV score가 높은 것을 확인할 수 있었다. 이는 AiTiALVSD가 LVSD 예측을 함에 있어서 제시된 아홉가지 컨셉을 positive하게 활용하는 것을 의미한다.  반면에 LVSD high risk와 관련없는 random concept 데이터는 LVSD 예측에 있어서 영향을 미치지 못한다는 것을 보여준다. 
특히 첫번째 블럭에서는 LAX, LBBB, AF, abnormal Q wave, abonormal T wave, Proonged QT interval 총 6가지 컨셉에서 가장 높은 TCAV 점수를 받았다. 우리는 이에 근거하여, clustering analysis를 수행할 때 첫번째 블럭에서 생성하는 feature를 활용하였다. 





## Noise robustness
실제 환경에서의 ECG 측정은 다양한 노이즈에 영향을 받을 수 있습니다. 예를 들면, 환자의 움직임, 기계적 진동, 전기적 인터페어런스 등으로 인한 노이즈가 있을 수 있습니다. 이런 노이즈가 AiTiALVSD의 성능에 어떠한 영향을 미치는지 알아보는 것은 중요합니다. 이는 모델의 실제 환경에서의 성능과 안정성을 평가하고 보장하는 데 필수적이기 때문입니다. AiTiALVSD의 노이즈 강인성을 평가하기 위해, 우리는 6가지 다양한 종류의 노이즈를 인위적으로 생성하였습니다. 이러한 노이즈들은 실제 ECG 측정에서 흔히 발생할 수 있는 요소들을 바탕으로 선정되었습니다. 각각의 노이즈를 적용한 데이터 셋을 사용하여 AiTiALVSD의 성능 변화를 관찰하였고, 이를 통해 어떤 노이즈 요소가 모델의 성능에 가장 큰 영향을 미치는지, 그리고 AiTiALVSD가 노이즈 robustness한지 확인하였습니다. 


The table provides  our ECG model's performance with the original ECG data and when subjected to each ECG noise. Specifically, when the ECG data is affected by "Power line Noise", "Baseline Wander", "Baseline Shift", "Partial White Noise", and "Time Mask", the model's performance metrics, including AUROC, AUPRC, Sensitivity, Specificity, PPV, and NPV, remain statistically indistinguishable from the results achieved with the original ECG data. This is evidenced by the overlapping 95% confidence intervals for these metrics. However, it's worth noting that under the influence of "EMG Noise", there are significant difference in Specificity 0.088 and PPV 0.197 from the original ECG. However, supplementary figure N에서 보듯이, EMG noise는 심전도의 형태를 알아볼 수 없을 정도의 노이즈로써 사용하지 못하는 심전도로 분류된다. 그럼에도 불구하고 AiTiALVSD proves to be resilient to most of the ECG noise types, underscoring its reliability in real-world scenarios where noise interference is common. 
## Clustering

우리는 AiTiALVSD가 만들어 내는 hidden feature를 더 깊이 탐색하기 위하여, clustering 분석을 수행하였다. 우리는 특히 TCAV 분석을 통해서 first 블럭이 생성하는 features가 더 유의하다는 것을 확인할 수 있었고, 


In our study, we sought to understand the patterns and characteristics of ECGs that were positively predicted by the AiTiALVSD. To achieve this, We conducted a cluster analysis using the features from the first block where the TCAV score was highly distributed. We specifically used only the positive predicted ECG samples because our primary objective was to uncover the types of ECGs that the model predicted as positive. For the cluster analysis, we employed the K-mean algorithm (ref). To determine the optimal number of clusters, we utilized the elbow algorithm( ref). We set the number of clusters to five, which is the most appropriate to capture the inherent patterns within the data. The clustering model was trained using a total of 60,125 positive predicted samples from the training set. supplementary figure N.1 학습된 clustering 모델의 군집을 보여준다.  우리는 clinical trial dataset에서 각 클러스터의 대표 심전도를 찾기 위해서 cluster centroid를 활용하였다. 우리는 
그리고 clinical trial dataset 심전도에서 가자


우리는 AiTiALVSD가 이해하고 있는 LVSD의 특징을 분석하기 위해서 클러스터링 분석을 수행하였다. 각 클러스터 군집의 심전도 특징을 비교하고 시각적으로 확인함으로써 우리는 구체적인 심전도 차이를 구분하고자 했다. 클러스터링 분석의 자세한 과정은 아래와 같다. 
1. Selection of ECG sample과 AiTiALVSD features: To understand the patterns of ECGs that were positively predicted by the AiTiALVSD, 우리는 positive predicted ECG samples만을 활용하였다. cluster algorithm은 총60,125개의 positive predicted ECG samples로 학습되었으며, clinical trial의 positive predicted sample를 활용하여 클러스터 결과를 시각화하였다. 우리는 AiTiALVSD의 첫번째 블럭에서 추출된 features를 클러스터링의 input으로 활용하였다. 첫번째 블럭의 feature는 313 길이의 64개의 channels로 구성되어있다. 우리는 차원의 저주와 컴퓨터 리소스 문제를 해결하기 위해서 각 channel wise 평균하여 64 사이즈의 feature로 변환하였다. 변환된 64 사이즈의 feature를 활용하여 cluster algorithm을 학습하였다. 
2. Clustering algorithm and determining the number of clusters: For the cluster analysis, we employed the K-mean algorithm (ref). To determine the optimal number of clusters, we utilized the elbow algorithm( ref). We set the number of clusters to five, which is the most appropriate to capture the inherent patterns within the data. The clustering algorithm was executed using the sklearn python package version 1.1.1 (ref)
3. Result visualization: 학습된 cluster model 결과 시각화하기 위해서 t-distributed stochastic neighbor embedding (T-SNE) 방법을 이용하여 데이터 차원 축소를  활용하였다. T-SNE를 활용하여 64 사이즈의 feature를 2차원의 데이터로 차원을 축소시킨 후 scatter plot을 통해서 결과를 시각화하였다. Supplementary Figure N은 각각 train dataset과 clinical dataset의  clustering 시각화 결과를 보여준다. 학습에 활용되지 않은 clinical trial dataset에서도 명확한 군집들이 형성되어 있는 것을 확인할 수 있었으며, 이는 AiTiALVSD feature가 내부적으로 심전도의 특징에 따라 phenotyping하고 있다는 것을 의미한다. 
4. Selection of  representative ECG for each cluster: 우리는 각 군집이 하나의 phenotype를 정의한다고 가정하여, 각 군집 간의 비교를 수행하였다.  각 군집의 통계적 characteristic baseline을 t-test를 통해 통계적으로 비교하였다. 더불어 우리는 representative ECG를 선정하기 위해서 각 cluster의 centroid와 가장 가까운 심전도를 clinical trial dataset에서 선정하였다. Figure N은 각 cluster에서 선정된 phenotype ECG를 보여준다. 


We performed clustering analysis to analyze the characteristics of LVSD that AiTiALVSD recognizes. By comparing the electrocardiogram (ECG) features of each cluster group and visually verifying them, we aimed to distinguish specific ECG differences. The details of the clustering analysis are as follows:

1. **Selection of ECG sample and AiTiALVSD features**: To understand the patterns of ECGs positively predicted by AiTiALVSD, we only used positively predicted ECG samples. The cluster algorithm was trained on a total of 60,125 positively predicted ECG samples, and the clustering results were visualized using positive predicted samples from the clinical trial. We utilized features extracted from the first block of AiTiALVSD as input for clustering. Features from the first block consist of 64 channels, each of length 313. To address the curse of dimensionality and computational resource issues, we averaged each channel-wise, converting them into 64-sized features. We trained the cluster algorithm using these transformed 64-sized features.
2. **Clustering algorithm and determining the number of clusters**:  For the cluster analysis, we employed the K-means algorithm (ref). To determine the optimal number of clusters, we used the elbow method (ref). We set the number of clusters to five, which seemed most appropriate to capture the inherent patterns within the data. The clustering algorithm was executed using the sklearn python package version 1.1.1 (ref).
3. **Result visualization**: To visualize the results of the trained cluster model, we employed the t-distributed stochastic neighbor embedding (T-SNE) method for dimensionality reduction. Using T-SNE, we reduced the 64-sized features into 2D data and visualized the results through a scatter plot. Supplementary Figure N shows the clustering visualization results for both the training dataset and the clinical dataset. We observed distinct clusters forming even in the unused clinical trial dataset, indicating that the AiTiALVSD feature internally phenotypes based on ECG characteristics.
4. **Selection of representative ECG for each cluster**: We assumed that each cluster defines a single phenotype and performed comparisons between the clusters. We statistically compared the baseline characteristics of each cluster using a t-test. Furthermore, to select a representative ECG, we chose the ECG closest to the centroid of each cluster from the clinical trial dataset. Figure N displays the phenotype ECG selected from each cluster.