
### Research Scientist: 어떻게 SOTA를 뛰어넘을 수 있을까?

#### Concept

Research Scientist는 AI에 관련된 원천 기술을 연구하는 포지션입니다. 특정 비즈니스 도메인 (i.e., 자율주행, 카셰어링 등)에만 적용할 수 있는 주제가 아닌, 여러 비즈니스 도메인에 적용될 수 있는 근간이 되는 원천 기술을 연구하는 포지션이라고 생각합니다.

다양한 도메인에 적용할 수 있는 원천 기술을 연구하기 때문에, Research Scientist들은 여러 도메인의 연구자들이 이해하고 실험 결과를 납득할 수 있는 Public Benchmark Dataset을 이용하는 경우가 많습니다. **Research Scientist는 Public Benchmark Dataset에서 이전 연구가 달성한 최고 성능 (State-of-the-Art; SOTA)를 넘어서는 기법을 연구하고, 이전 SOTA의 한계점을 보완하는 기법을 연구하기도 합니다.**

2010년 즈음부터 지금까지 이미지, 텍스트(자연어), 시계열, 생성(Generation) 등의 다양한 기법들의 SOTA가 개선되면서 AI 연구가 점점 성장하고 있습니다. 아직 해결되지 않은 문제들과 연구 주제들도 무수히 많이 남아있어, 더 많은 연구들이 등장할 것으로 기대하고 있습니다.

#### Key Responsibility

Research Scientist는 과거에 제안된 연구들을 파악하고 새로운 연구를 수행해야 하기 때문에, 주로 요구되는 Responsibility는 아래와 같습니다. (조직마다 다르고, 시간이 흐름에 따라 변경될 수 있습니다)

- 기존에 제안된 연구들을 이해하고 구현할 수 있는 능력
- 기존 연구의 한계점을 개선할 수 있는 기법에 대한 Ideation 능력
- 독립적으로 연구 목적을 수립하고 실험 계획, 평가, 공유(논문 작성 등)를 수행할 수 있는 능력
- 다른 연구자들과 원활하게 소통하고 협력할 수 있는 능력

#### Research Questions

원활한 이해를 돕기 위해 Research Scientist가 고민할 만한 Research Question들을 한 번 정리해 보았습니다.

- Gradient Descent를 기반으로 Learning Objective를 달성하는 것이 아니라, 인간처럼 Reasoning을 하는 AI를 만들 수는 없을까?
- 이미지를 이해하는 여러 Neural Networks Architecture가 있는데, 특정한 패턴에 bias 되지 않고 더 인간처럼 이미지를 이해하는(혹은 인간보다 더 뛰어나게) 구조는 없을까?
- 최근에 제안된 Language Model (BERT, RoBERTa, S-BERT 등)보다 더 인간처럼 (혹은 인간보다 더 뛰어나게) 지식을 이해하는 모델은 없을까?


### Applied Research Scientist: 우리 비즈니스 도메인의 문제를 어떻게 풀 수 있을까?

#### Concept

Applied Research Scientist는 특정 비즈니스 도메인의 문제를 풀 수 있는 AI를 연구하고, 연구된 모델을 배포하는 일을 수행하는 포지션입니다. **Research Scientist가 여러 도메인에 범용적으로 적용될 수 있는 AI를 연구한다면, Applied Research Scientist는 특정 도메인에 최적화된 AI를 연구하고 이를 Production 환경에 맞게 구현하는 역할도 수행합니다.**

Applied Research Scientist는 Public Benchmark Dataset을 이용하기도 하지만, 현실에서 발생한 Real-world Dataset을 주로 이용합니다. Real-world Dataset 이란 현실에서 발생하는 데이터 셋으로, 쏘카의 경우 카셰어링 서비스를 운영하면서 발생하는 여러 데이터 (i.e., 차량 이미지, 차량 센서, 채팅 텍스트 등)를 의미합니다. 조직이 직면하고 있는 문제를 해결하기 때문에, Public Benchmark Dataset은 논문에서 제안된 여러 기법의 성능을 확인하는 데 사용하고 주된 문제 해결에는 Real-world Dataset을 사용합니다. 하지만 세상만사 쉬운 일이 없듯이 public benchmark에서는 높은 성능을 달성한 기법(모델)이 Real-world Dataset에서는 잘 동작하지 않는 경우가 많습니다. **Applied Research Scientist는 Public Benchmark와 Real-world의 차이를 고민하면서, SOTA 기법이 우리 도메인에서 왜 안되는지 (혹은 왜 잘 되는지)를 파악하고, 제안된 여러 기법들을 최적화하거나 새로운 기법을 디자인하기도 합니다.**

AI 연구에서 더 나아가, Applied Research Scientist는 Software Engineer, Data Engineer와 협업하여 AI 모델을 배포하는 과정에도 참여합니다. 리서치용으로 작성했던 코드를 배포 가능한 형태로 리팩토링하고, 다른 조직과 커뮤니케이션하며 배포에 필요한 요소들을 결정합니다. 그뿐만 아니라, AI 모델의 추론(Inference) 결과를 모니터링하여 Dataset Shift나 Feature Drift, Out-of-Distribution 샘플이 프로덕션에 들어오는지를 파악합니다.

#### Key Responsibility

Applied Research Scientist는 도메인의 문제를 해결할 수 있는 AI를 연구하고, 다른 조직과 협업하여 배포하는 과정까지의 업무를 수행하므로, 주로 요구되는 Key Responsibility는 아래와 같습니다.

- 도메인에 대한 이해
- 기존에 제안된 연구들을 이해하고 구현할 수 있는 능력
- 기존에 제안된 연구를 도메인에 최적화하거나 더 나은 방법을 Ideation 할 수 있는 능력
- 독립적으로 연구 목적을 수립하고 실험 계획, 평가, 공유(논문 작성 등)를 수행할 수 있는 능력
- 다른 연구자, 엔지니어, End-User 들과 커뮤니케이션하고 니즈를 파악할 수 있는 능력

#### Research Questions

원활한 이해를 돕기 위해 Applied Research Scientist가 고민할 만한 Research Question들을 한 번 정리해 보았습니다.

- 논문 A는 ImageNet, SUN, Place 365에서 높은 성능을 달성했는데, 우리 도메인에서는 성능이 높지 않은데, 그 이유가 뭘지? 우리 데이터와 Public Benchmark에는 어떤 차이가 있어서 그럴까?
- 우리 도메인에서 다루는 데이터는 Public Benchmark들과는 너무 다른데, 우리 도메인에서 잘 동작하는 새로운 Neural Architecture를 디자인해 볼까?
- 모델 B가 배포되었을 때 낮은 Overhead를 달성하려면 코드를 어떻게 리팩토링 해야 할까? 모델에 들어가는 Input은 어떻게 설계하고, Inference 결과는 어떤 테이블에 어떻게 적재하지?


### Data Scientist: 데이터를 기반으로 어떤 Action을 할 수 있을까?

#### Concept

마지막으로, Data Scientist는 비즈니스 도메인에서 발생한 다양한 데이터를 분석하는 포지션입니다. 비즈니스의 여러 실무자와 커뮤니케이션하며 문제를 해결하며, 그 과정에서 필요한 다양한 업무를 진행합니다. 이때, 가장 중요한 것은 단순 Report가 아닌 Action을 위한 데이터 분석을 수행한다는 점입니다. 목적 없이 데이터를 분석하는 것이 아니라, 분석 결과를 기반으로 실무자가 실제 Action을 수행하기 위한 데이터 분석을 진행합니다.

#### Key Responsibility

Data Scientist는 주로 비즈니스 도메인에서 발생하는 다양한 종류의 데이터를 다룹니다. 쏘카의 Data Scientist 포지션으로 예를 들어보겠습니다. 쏘카의 Data Scientist는 서비스의 앱, 웹 로그, 유저의 서비스 이용 데이터, 차량의 센서 데이터 등 다양한 영역에서 비즈니스 문제 해결을 위한 문제 정의, 가설 설정, 실험 설계와 성과 측정을 진행합니다. 쏘카는 주로 분석하는 데이터를 기준으로 Business Data Scientist와 Product Data Scientist로 나누어 채용하고 있는데, 공통적으로 요구되는 역량은 아래와 같습니다.

- 비즈니스 임팩트를 위한 문제 정의, 가설 설정, 실험 설계와 성과 측정 능력
- 데이터 기반 비즈니스 알고리즘 개발 능력
- 효과적인 데이터 분석을 위한 핵심 지표의 도출과 관리, 예측 모델링 능력

#### Research Questions

원활한 이해를 돕기 위해 Data Scientist가 고민할 질문들을 정리해 보았습니다. 이번에는 원활한 이해를 위해 Business Data Scientist와 Product Data Scientist로 나누어서 가져와 보았습니다.

- (Business) 이번 주말에 강남역 10번 출구 쏘카 존의 예약 건은 얼마나 될까?
- (Business) 2022년에 서울시 은평구에 몇 대의 차량을 배차하면 대 당 매출이 얼마나 될 것으로 예측할 수 있을까?
- (Business) 가장 적은 매출이 나올 지역을 데이터에 기반해 찾아주는 알고리즘을 어떻게 만들 수 있을까?
- (Product) 쏘카의 Funnel 중 가장 전환율이 낮은 부분은 어디일까? 그 부분을 개선하기 위해서는 어떤 Action을 할 수 있을까? 어떤 실험을 진행하면 이에 대한 결론을 얻을 수 있을까?
- (Product) 새로운 기능 개발을 시작하려고 하는데, 이 기능 개발이 성공했다고 보려면 어떤 Metric을 결정해야 할까? 그 Metric을 보기 위해 어떤 앱, 웹 데이터를 로깅해야할까 새로운 기능을 AB Test 하려고 할 경우, 어떤 방법으로 설계할 수 있을까?
- (Product) 새로운 기능이 출시된 이후에 성공적인지 확인하기 위해 대시보드는 어떻게 구성해야 할까?
- 더 자세한 내용은 쏘카의 [채용 노션 페이지](https://www.notion.so/socarcorp/d458b6b77a2243fb873d1ac800c321f7)를 참고하시면 좋을 것 같습니다.


### AI RedTeam : 우리 모델은 어디가 취약할까, 어디를 보완해야할까

