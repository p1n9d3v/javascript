# Descriptor

- 프로퍼티의 속성 이름과 속성 값을 정의
- data, access 타입인 디스크립터는 같이 사용할 수 없다.(common은 같이 사용 가능)

## Data

- value : 값 설정
- writable : 값 변경 가능 여부

## Access

- getter : 값을 가져오는 기능, value가 없으면 getter 함수를 호출
- setter : 값을 설정하는 기능, 값을 설정할 때 setter를 호출

## Common

- enumerable : for-in, Object.keys()로 열거 가능 여부
- configurable : 속성 삭제 가능 여부
