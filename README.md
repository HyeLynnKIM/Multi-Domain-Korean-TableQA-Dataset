# 다중 도메인 Table QA 데이터셋

<br/>

|데이터셋|표 도메인|데이터 양|특징
:--:|:--:| :--:| :--:
|Spec Table QA|제품 스펙 관련 표|3,055|복잡한 제품 용어
|Office Table QA|공문서 관련 표|10,500|복잡한 조건의 질문 유형
|Law Table QA|법령 문서 관련 표|2,005|복잡한 법률 용어, 범위나 수치 관련 질문 강화

<br/>

## 데이터 셋 Description

## 1. 다양한 형태의 표가 포함된 안전 법령 문서 데이터셋<br/>


> 본 데이터셋은 국가법령정보센터(https://www.law.go.kr/LSW/main.html)에 존재하는 안전 법령 문서를 기반으로 구축된 다양한 형태의 표가 포함된 안전 법령 문서 질의응답 시스템을 위한 Train data set 및 Validation data set입니다. 총 2,005개의 QA로 구성되었습니다.

<br/>

### QA 유형


|번호|질문유형|설명|예시
:--:|:--:| :--:| :--:
|1|어휘에 관련된 질문|테이블에 있는 어휘가 포함되는 유형|(예) Q: 계량 특수단위에서 천문단위는?<br/>A: AU
|2|어휘 변경|테이블에 있는 어휘가 변형되어 질문에 나타나는 유형|(예) Q: 자동차용 석유대체연료의 성능평가를 하는 품질검사기관에서 원동기동력계의 필요개수는?<br/>A: 1식
|3|숫자 범위 질문|숫자 범위를 인식하여 정답을 도출하는 유형|(예) Q: 계량기 중 오일미터 내구성시험기의 호칭구경이 60mm일 때 최대통과유량은?<br/>A: 최대통과유량 40m^3/h 이상
|4|개수 질문|원하는 정보의 개수를 파악하는 유형|(예) Q: 정량표시상품의 종류의 개수는?<br/>A: 27
|5|행정처분기준 표에 관한질문|행위에 대한 결과를 추론하는 유형|(예) Q: 석유정제업을 1회 폐업한 경우 행정처분기준은?<br/>A: 등록취소 또는 영업장 폐쇄

<br/>

### 데이터셋 형식


-	엑셀 형태로 수집한 데이터에 대해 표형태로 나타나지 않은 경우 텍스트를 줄바꿈 기준으로 분리하여 표 형태로 표현하였습니다.
-	데이터셋은 **(문장 | 답변 | QA가 추출된 문서이름 | 문서 안에서 sheet 이름 | 정답 셀 위치)** 로 구성되었습니다.
-	복잡한 법률 용어와 범위나 수치 관련 질문이 강화되어 질문이 생성되었습니다.

<br/>

___

<br/>

## 2. 한국어 공문서 표 형태 데이터셋

> 본 데이터셋은 공공데이터포털(https://www.data.go.kr/), 나무위키(https://namu.wiki) 2개의 도메인에서 Web Crawling으로 표 데이터를 수집하고, 정부24(https://www.gov.kr/portal/main), 다나와(https://www.danawa.com), 위키피디아(https://ko.wikipedia.org/wiki) 3개의 도메인에서 문서를 직접 수집하여 제작된 공문서 관련 데이터셋입니다. 총 10,500개의 QA셋으로 구성되어 있습니다.

<br/>

### QA유형
|번호|질문유형|설명
:--:|:--:| :--:
|1|어휘 탐색 유형|테이블에 정답 어휘가 포함되는 유형
|2|비교 유형|테이블 내의 셀 간 내용을 비교하여 답변하는 유형
|3|어휘 다양성|내포하는 의미가 유사한 어휘를 사용하는 유형
|4|순서 유형|데이터 내의 셀의 개수 및 내용 상의 횟수 등을 세어 답변하는 유형

<br/>

### 대상 문서 및 데이터셋 형식


- 계획표와 같이 의미가 부족한 테이블을 수집하는 것은 지양하였습니다.
-	유의미하고 적절한 크기의 데이터 선별을 위해 4행 4열 미만의 표 데이터는 선별 대상에서 제외하였습니다.
-	표 데이터 내용의 70-80% 이상이 숫자로만 구성된 경우에는 선별 대상에서 제외하였습니다.
-	PDF 형태로 수집한 데이터의 경우엔 HTML 파일로 변환하여 주석, 첨자, 링크 등 불필요한 태그의 내용을 제거하여 데이터셋을 구성하였습니다.
-	데이터 셀에 값이 들어있지 않은 경우 빈 문자열(‘’)로 처리하였습니다.
-	셀이 병합된 경우, 행과 열 모두 분리하여 사용하였습니다.
-	데이터셋은 **(번호 | QA가 추출된 대상 파일명 | 질문 | 정답 | 정답셀 행 위치 | 정답셀 열 )** 로 구성되었습니다.
