1. One
일대일 혹은 일대다 관계이다. 주로 하나의 외래키가 걸린 관계라고 보면 된다.

2. Many
다대다 관계이다. 중계 테이블을 통하여 여러개의 데이터를 바라보고 있을때 사용한다.

3. One (and only one)
위의 조건과 동일하게 일대일 관계이나, 하나의 row끼리만 연결된 데이터이다.

4. Zero or one
일대일 혹은 일대 다 관계를 가지고 있으나, 필수 조건이 아님을 의미한다. 비유를 하자면 개인정보 동의시, 필수값 구분과 선택값 구분이라고 보면 될 것 같다.

5. One or Many
일대일 혹은 다대다 관계를 가지고 있음을 의미한다. 관계를 가지고 있으나, 참조되는 row값들이 불명확함을 의미한다.

6. Zero or Many
참조하는 테이블과의 관계가 불명확한 경우이다. 장바구니처럼 row 생성값이 없을수도, 하나일수도, 여러개일 수도 있는 경우이다.