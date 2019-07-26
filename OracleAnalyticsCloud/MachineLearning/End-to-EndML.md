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

자동설명 기능에 대해 알아보자
**예금가입여부**칼럼을 선택하고 마우스 우클릭을 하면 다음과 같은 메뉴가 나타난다. 
 <img src=https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/explain_1.JPG width=500px height=450px>
 
 "예금가입여부 설명"을 클릭한다.
 화면과 같이 자동 설명 기능이 나타나며, 기본사항 분석은 전체 Bank라는 데이터 집합에 들어있는 데이터 건수를 기준으로 **예금가입여부 칼럼별로 자동 분석한 기본 값**과 **고객접촉일수, 나이, 상담회수 등의 측정값을 기준**으로 예금가입여부에 대해 분석해 준다.
 ![Explain](https://github.com/mlsohee/oml4sohee/raw/master/OracleAnalyticsCloud/MachineLearning/img/explain_y.JPG)
 
**핵심동인** 분석은 예금가입여부를 기준으로 가장 상관관계가 있는 속성들을 분석해 준다.
다음 예시의 경우를 보면 실행결과와 월이 상관관계가 있는 것을 알 수 있다.
즉, 예금가입여부를 위한 캠페인을 실행한 결과가 성공인 고객이 예금가입을 더 많이 하는 결과를 자동으로 알 수 있다.

**세크먼트**분석은 해당 분석항목의 데이터 속성에 가장 일치할 다른 항목들의 데이터 속성을 분석하는 부분이며, **이상치**의 경우 one-class SVM을 이용한 데이터의 이상치를 내타내준다.

 2. GUI기반의 ML 알고리즘

오라클 분석 클라우드는

### 데이터 사이언스 파이프라인

 - 데이터 적재
데이터 적재를 위해 햄버거메뉴 ⇒ 데이터 ⇒ 데이터 흐름 
또는 생성버튼 ⇒ 데이터흐름 ⇒ 추가


<!--stackedit_data:
eyJoaXN0b3J5IjpbMjExNzY2NTkyNiw0NjU4MTIxOCwtMjA1Mz
MxODIxNiw2Njk5MjQ3NDNdfQ==
-->