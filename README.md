# 키친포스

## 퀵 스타트

```sh
cd docker
docker compose -p kitchenpos up -d
```

## 요구사항


### 메뉴그룹
#### 메뉴그룹 등록
- [ ] 메뉴그룹 이름은 필수로 부여되야한다.
#### 메뉴그룹 조회
- [ ] 전체 메뉴그룹을 조회할 수 있다.

----

### 메뉴
#### 메뉴 등록
- [ ] 가격은 0원보다 커야하며 메뉴를 구성하는 메뉴상품에 총 가격(상품가격 * 갯수)보다 클 수 없다.
- [ ] 메뉴상품들에 각 상품에 수량은 0보다 커야한다.
- [ ] 이름에 욕설이 포함된 메뉴명은 불가능하다.
- [ ] 메뉴그룹에 소속된다.
#### 메뉴 가격 변경
- [ ] 변경되는 메뉴 가격이 메뉴상품들에 총 가격보다 클 수 없다.
#### 메뉴 표출
- [ ] 메뉴가격이 메뉴상품들에 총 가격(상품가격 * 갯수)보다 크지 않을경우 메뉴를 표출할 수 있다.
- [ ] 메뉴는 임의로 비노출 할 수 있다.        
#### 메뉴 조회
- [ ] 전체 메뉴를 조회할 수 있다.

----

### 주문
#### 주문 생성
- [ ] 주문은 주문 유형, 상태, 주문 시간, 주문 품목들, 배송 주소, 주문 테이블 정보를 가진다.
  - [ ] 주문 유형은 총 세 가지다.
      - 배달
      - 포장
      - 매장 식사
  - [ ] 주문 상태는 총 여섯 가지다.
      - 대기 중
      - 접수 완료
      - 서빙 중
      - 배달 중
      - 배달 완료
      - 완료됨
- [ ] 주문시 주문 품목 값은 필수 이다.
- [ ] 등록되어 있는 메뉴의 갯수와 주문한 메뉴의 갯수가 같아야 한다.
- [ ] 주문시 매장식사가 아닐경우 주문정보에 수량이 0보다 커야 한다.
- [ ] 주문된 메뉴가 표출되지 않는 상태 일 수 없다.
- [ ] 주문된 메뉴의 가격이 매장 메뉴의 가격과 다를 수 없다.
- [ ] 주문시 주문상태는 대기중으로 된다.
- [ ] 주문시 주문일시를 현재시간으로 한다.
- [ ] 주문시 주문타입이 배달일 경우 배달 주소는 필수 값이다.
- [ ] 매장에서 식사 시 테이블이 사용 중이면 주문을 할 수 없다.
#### 주문 승인
- [ ] 주문이 대기중일 경우 주문을 승인할 수 있다.
- [ ] 주문수락 시 주문타입이 배달일 경우 주문번호, 가격, 주문주소로 배달을 요청한다.
#### 주문 메뉴 제공
- [ ] 주문이 승인된 경우 주문메뉴를 제공할 수 있다.
#### 주문 배달 시작
- [ ] 주문 타입이 배달이고 주문 메뉴가 제공 되었을 경우 배달중으로 상태를 변경할 수 있다.
#### 주문 배달 완료
- [ ] 주문 상태가 배달중일 경우 배달완료로 상태를 변경할 수 있다.
#### 주문 완료
- [ ] 배달주문인 경우 배달완료 상태일경우 주문완료 상태로 변경할 수 있다.
- [ ] 포장주문인 경우 주문 메뉴가 제공 상태일경우 주문완료 상태로 변경할 수 있다.
- [ ] 매장주문인 경우 주문 메뉴가 제공 상태일경우 주문완료 상태로 변경할 수 있으며 사용한 테이블을 사용가능하도록 변경한다.


### 주문(수정)
#### 공통
- [ ] 주문은 주문 유형, 상태, 주문 시간, 주문 품목들, 배송 주소, 주문 테이블 정보를 가진다.
    - [ ] 주문 유형은 총 세 가지다.
        - 배달
        - 포장
        - 매장 식사
    - [ ] 주문 상태는 총 여섯 가지다.
        - 대기 중
        - 접수 완료
        - 서빙 중
        - 배달 중
        - 배달 완료
        - 완료됨
- [ ] 주문시 주문 품목 값은 필수 이다.
- [ ] 등록되어 있는 메뉴의 갯수와 주문한 메뉴의 갯수가 같아야 한다.
- [ ] 주문된 메뉴가 표출되지 않는 상태 일 수 없다.
- [ ] 주문된 메뉴의 가격이 매장 메뉴의 가격과 다를 수 없다.
- [ ] 주문시 주문상태는 대기중으로 된다.
- [ ] 주문시 주문일시를 현재시간으로 한다.
- [ ] 주문이 대기중일 경우 주문을 승인할 수 있다.
- [ ] 주문이 승인된 경우 주문메뉴를 제공할 수 있다.
#### 배달 주문
- [ ] 주문시 주문품목의 수량이 0보다 작을 수 없다.
- [ ] 주문시 배달주소는 필수 값이다. 
- [ ] 주문수락 시 주문번호, 가격, 주문주소로 배달을 요청한다.
- [ ] 주문 메뉴가 제공 되었을 경우 배달중으로 상태를 변경할 수 있다.
- [ ] 주문 상태가 배달중일 경우 배달완료로 상태를 변경할 수 있다.
- [ ] 배달완료 상태일경우 주문완료 상태로 변경할 수 있다.
#### 포장 주문
- [ ] 주문시 주문품목의 수량이 0보다 작을 수 없다.
- [ ] 주문 메뉴가 제공 상태일경우 주문완료 상태로 변경할 수 있다.
#### 매장 주문
- [ ] 테이블이 사용 중이면 주문을 할 수 없다.
- [ ] 주문 메뉴가 제공 상태일경우 주문완료 상태로 변경할 수 있으며 사용한 테이블을 사용가능하도록 변경한다.

----

### 테이블
#### 테이블 생성
- [ ] 이름은 필수로 부여되야한다.
#### 테이블 착석
- [ ] 테이블에 착석 할 경우 테이블의 사용여부 상태가 착석으로 변경된다.
#### 테이블 청소    
- [ ] 테이블을 청소 할 경우 고객 수는 0으로 변경되며 사용여부 사용가능으로 변경된다.
- [ ] 테이블에 착석 한 고객의 주문이 처리된 경우 테이블을 청소 할 수 있다.
#### 테이블 고객 정보 제공
- [ ] 착석한 고객은 몇명인지 얘기할 수 있으나 음수를 얘기할 수 없다.
- [ ] 착석하지 않은 고객은 몇명인지 얘기할 수 없다.
#### 테이블 조회
- [ ] 전체 테이블에 정보를 조회할 수 있다.

----

### 상품
#### 상품 등록
- [ ] 상품 가격은 0원보다 큰 금액이 할당되야 하는 필수 값이다.
- [ ] 상품 이름은 필수로 부여되야하며 욕설이 포함된 상품명은 불가능하다.
#### 상품 가격 변경
- [ ] 상품 가격은 필수 값이다.
- [ ] 상품에 가격정보가 변경될 경우 해당 상품으로 구성된 메뉴가격이 메뉴상품 총 가격보다 클경우 메뉴표출을 비활성화 해야한다.
#### 상품 조회
- [ ] 전체 상품을 조회할 수 있다.

----

## 용어 사전

| 한글명 | 영문명 | 설명 |
| --- | --- | --- |
|  |  |  |

## 모델링


