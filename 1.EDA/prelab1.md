# Data 전처리 요건 근거 보고서

Data & Digital Squad  
한태승 선임 (09708)

![](temp/req.PNG)

## 결측치 처리

oldbalanceOrig, newbalanceOrig 각 컬럼에 Missing Value가 존재하며 처리가 필요함.

![missings1](temp/missing_old.PNG)

![missings2](temp/missing_new.PNG)

## 불필요 데이터 삭제 1: 컬럼

각 행을 unique에 가까운 수준으로 식별 가능한 무의미한 범주형 변수들인 다음 두 컬럼의 삭제가 필요함.
  - nameOrig
  - nameDest

![unique1](temp/unique1.PNG)

![unique2](temp/unique2.PNG)

## 불필요 데이터 삭제 2: 로우

Type in (1, 3, 4)의 조건을 만족하는 경우 Fraud의 비율이 0

![nofraud](temp/nofraud.PNG)

## 가변수 처리

논리적으로 범주형 변수지만 Int Type으로 로드된 상태이므로, Factorize가 필요함.

![](temp/factorize.PNG)

## 아웃라이어 처리

![](temp/outlier.PNG)

다음 범위에 속하지 않는 데이터 포인트가 존재하며,  
해당 값은 Outlier/Leverage에 속할 확률이 높으므로 확인 및 관리가 필요함.

- 다음: $\mu\pm3\sigma$ = [858325-3*2932855, 858325+3*2932855] = [-7940240, 9656890]
