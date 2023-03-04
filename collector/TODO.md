# 설계

## 수집기 기능
* 원클릭 수집
    * 형태 (캔들 or 주문)
    * 거래소
    * 시간 스케일
    * 기간 (언제까지?)
* 다중 수집
    * 멀티 스레딩 or 프로세싱
* DB 현황 확인 기능
    * 테이블 삭제 및 쿼리 UI
* 시각화 기능

---

## TODO
* 데이터 스키마 3 개 정의
    * candle
    * order
    * trade
* binance 과거 데이터 옮기기
    * 데이터 형식 파악하기
    * 사이트의 모든 데이터 다운로드 자동화
    * zip 파일 풀어서 저장하지 않고 바로 정의된 테이블 형태 DB 에 집어넣기 자동화
    * + 멀티 스레딩 / 프로세싱
* binance wss 모듈 개발
    * DB 에 즉시 집어넣기
* 기타 거래소
    * 대량의 과거 데이터 저장하는 작업 먼저 자동화
* 거래소 모듈 개발
    * rest 모듈화, 정형화
* DB 모듈 개발
    * DB 접근 및 쿼리 모듈화
    * 테이블 정의대로 raw data -> table 변환
* 거래소 모듈, DB 모듈 통합 테스트
* UI 틀 생성


---

## db 계층
> db 갯수, table 갯수 적당 사이즈가 되게 계층 구조 구성

* DB
    * 네이밍 - type_scale (ex. candle_1m, candle_1h, order_15m, trade_30h, ...)
* table
    * 네이밍 - 거래소_종목_날짜 (ex. binance_btc_20230218)
    * 통화는 알아서 맞추기. 분석 시 구분



## candle
* time
* o
* h
* l
* c
* v

## order
* time
* bid_1
* bid_1_amt
* ask_1
* ask_1_amt


## trade
* time
* price
* amt