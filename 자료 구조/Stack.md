## 개념
- 스택: 먼저 들어온 데이터가 나중에 나가는 자료구조 (FILO)
- 새로운 원소를 삽입할 때는 마지막 위치에 삽입, 삭제할 때는 마지막 원소가 삭제

## 연산 시간 복잡도
||연산|시간 복잡도|설명|
|---|---|---|---|
|1|삽입(Push)|O(1)|스택에 원소를 삽입하는 연산|
|2|추출(Pop)|O(1)|스택에서 원소를 추출하는 연산|
|3|최상위 원소(Top)|O(1)|스택의 취상위 원소(마지막에 들어온 원소)를 확인하는 연산|
|4|Empty|O(1)|스택이 비어 있는지 확인하는 연산|

## JS에서 스택 구현
- push() 메서드
- pop() 메서드

## 연결 리스트로 스택 구현
- 스택을 연결 리스트로 구현하면, 삽입과 삭제에 있어서 O(1)을 보장할 수 있다.
- 연결 리스트로 구현할 때는 머리를 가리키는 한 개의 포인터만 가진다.
> 머리(head): 남아있는 원소 중 가장 마지막에 들어온 데이터를 가리키는 포인터

- 삼입할 때는 머리 위치에 데이터를 넣는다
- 삭제할 때는 머리 위치에서 데이터를 꺼낸다.
