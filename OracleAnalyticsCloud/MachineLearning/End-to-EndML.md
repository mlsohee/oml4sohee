## 오라클 분석 클라우드(Oracle Analytics Cloud - OAC)를 이용한 ML 활용하기 

OAC는 ML을 활용한 자동화된 인사이트를 제공하는 증강분석 솔루션으로 플랫폼에서 손쉽게 머신러닝 알고리즘을 활용할 수 있으며, 강력한 시각화 기능을 제공합니다.

 스마트 기능을 계속 추가하여 **AI/ML 알고리즘**을 앱에 내장할 수 있읍니다.
강력한 GUI기반의 ML알고리즘을 제공함으로써 기존 알고리즘을 Drag & Drop을 사용하여 코드 작성이 필요 없이 실행할 수 있습니다.
***해당 강좌는 [Ravi Panga의 블로그](https://medium.com/@prvtej/end-to-end-machine-learning-workflow-on-oracle-analytics-cloud-oac-1045a6296637)를 한글로 번역해 놓은 강좌입니다.

### 데모 시나리오 
이 데이터는 포르투칼 은행 기관의 직접 마케팅 캠페인과 관련된 데이터입니다.
마케팅 캠페인은 전화를 기반으로 했으며, 목표는 은행 정기예금을 수락할지 여부를 고객이 예측하는 것입니다.
모든 사람보다 제안을 수락할 가능성이 큰 고객에게 캠페인 킴이 연락하는 데 도움을 주는 분석 입니다.
데이터와 함께 오라클 분석 클라우드로 만들어놓은 프로젝트 파일(.dva)를 사용할 수 있습니다.
**예제 다운로드 파일**

 1. 스마트한 기능 : 자동 설명(Explain), 권장 사항(Recommendations), 이상치(Outliers) 및 군집(Clusters) 등
	 
	 자동 설명(Explain) — 칼럼에 대한 기본 측정값 기준의 설명, 다른 속성값의 분석, 세그먼트 분석 및 이상치 등
	 
	 권장 사항(Recommendations) — 데이터 준비 단계에서 데이터를 강화, 정제, 추출 기능 제공
	 
	 이상치(Outliers) — 선택된 데이터의 이상치를 표시
	 
	 군집(Clusters) — 데이터의 군집을 식별함.
	 
	 **자동설명** 기능에 대해 알아보자
	 
	 **예금가입여부**칼럼을 선택하고 마우스 우클릭을 하면 다음과 같은 메뉴가 나타난다. 
	  <img src=https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/explain_1.JPG width=500px height=450px>
	  
	   "예금가입여부 설명"을 클릭한다.
	   화면과 같이 자동 설명 기능이 나타나며, 기본사항 분석은 전체 Bank라는 데이터 집합에 들어있는 데이터 건수를 기준으로 **예금가입여부 칼럼별로 자동 분석한 기본 값**과 **고객접촉일수, 나이, 상담회수 등의 측정값을 기준**으로 예금가입여부에 대해 분석해 준다.!
	   ![Explain](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/explain_y.JPG)
	   
	   **핵심동인** 분석은 해당 분석항목을 기준으로 가장 상관관계가 있는 속성들을 분석해 준다. **세크먼트**분석은 해당 분석항목의 데이터 속성에 가장 일치할 다른 항목들의 데이터 속성을 분석하는 부분이며, **이상치**의 경우 데이터의 이상치를 내타내준다.

 2. GUI기반의 ML 알고리즘
오라클 분석 클라우드는 회귀분석, 분류, 군집 및 연관어 분석으로부터 ML 알고리즘을 사용할 수 있다. 우리는 비즈니스 문제를 해결하기 위해 '고객의 정기예금가입여부를 예측'하는 알고리즘을 실행해 볼 것이다.
통상적으로 데이터 과학자들이 접근하는 방법을 따라 우리도 ML 알고리즘을 실행해보자.

### 데이터 사이언스 파이프라인
데이터 확인 및 적재, 탐색적 분석, 데이터 준비, 모델링, 모델 평가의 순서로 이루어진다. 

 - 데이터 적재
데이터 적재를 위해 햄버거메뉴 ⇒ 데이터 ⇒ 데이터 집합으로 이동한다.
또는 홈화면으로 이동하면, 생성버튼이 나타난다. **생성 ⇒ 데이터 집합** 을 클릭한다.
![Explain](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/newdataset.JPG)

상단에서 다운받은 bank_sample.xlsx 파일을 "여기에 데이터 파일을 놓거나 눌러서 찾아보기"에 끌어다 놓으면 해당 데이터를 자동으로 읽어 OAC에서 분석할 수 있는 형태로 보여준다.

![AddDataSet](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/prep_dataset.JPG)

추가버튼을 클릭하여 새로운 데이터 집합을 만들면, 증강분석의 **권장사항** 기능을 확인할 수 있다.
![Recommendation](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/recommendation.JPG)

어떤 요일에 가입캠페인의 실행 성공이 많았는지 확인하기 위해 **실행일자에서 주 단위 일**을 클릭하면 다음과 같은 **실행일자 요일 1** 칼럼이 생성된다. 칼럼 우상단에 마우스를 클릭하면 햄버커버튼이 나오고, 해당 메뉴를 클릭하여 이름 바꾸기를 클릭한다.
![rename](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/newcolumn.JPG)

해당 이름을 **실행요일**로 변경하고 마우스를 다른 곳으로 클릭하면 **단계추가**버튼이 활성화되고, 해당 버튼을 클릭한다.
![add](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/rename.JPG)

왼쪽의 준비스크립트를 보면 변경된 항목들이 아직 적용되지 않아 파란색 동그라미로 나오고 **스크립트 적용**버튼을 클릭하면, 분석할 준비가 된 상태가 된다.
![Explain](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/applyscript.JPG)

화면 우상단의 **프로젝트 생성** 버튼을 눌러 증강분석을 실행해보자

- 탐색적 분석
자동 설명 기능을 통한 데이터의 탐색적 분석을 실시할 수 있다.    
**핵심동인** 분석은 예금가입여부를 기준으로 가장 상관관계가 있는 속성들을 분석해 준다.
다음 예시의 경우를 보면 실행결과와 자가여부가 상관관계가 있는 것을 알 수 있다. 즉, 예금가입여부를 위한 캠페인을 실행한 결과가 성공인 고객과 자가를 가지고 있지 않은 고객이 예금가입을 더 많이 하는 결과를 자동으로 알 수 있다.	   ![Explain](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/explain_d.JPG)

**세크먼트**분석은 해당 분석항목의 데이터 속성에 가장 일치할 다른 항목들의 데이터 속성을 분석하는 부분이며, **이상치**의 경우 one-class SVM을 이용한 데이터의 이상치를 내타내준다.
![Explain](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/explain_s.JPG)

다음은 시각화를 살펴보자

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTExMTcwNjE3NDMsODk1NTMyMjU3LDQ2NT
gxMjE4LC0yMDUzMzE4MjE2LDY2OTkyNDc0M119
-->