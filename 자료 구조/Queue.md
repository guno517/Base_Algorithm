### 코딩 테스트에 잘 나오는 자료 구조

## 개념
- 큐는 먼저 삽입된 데이터가 먼저 추출되는 자료구조
- ex) 롤에서 큐를 잡는다에서 큐가 자료 구조의 큐이다.

## 연결 리스트로 큐 구현
- 큐를 연결 리스트로 구현하면, 삽입과 삭제에 있어서 O(1)을 보장할 수 있다.
- 연결 리스트로 구현할 때는 머리와 꼬리 두 개의 포인터를 가진다.
- 머리: 남아있는 원소 중 가장 먼저 들어 온 데이터를 가리키는 포인터
- 꼬리: 남아있는 원소 중 가장 마지막에 들어 온 데이터를 가리키는 포인터
- 삽입할 때는 꼬리 위치에 데이터를 넣는다
- 삭제할 때는 머리 위치에서 데이터를 꺼낸다.

## 큐 동작 속도: 배열 vs 연결 리스트
- 단순히 배열 자료형을 이용할 때보다 연결 리스트를 사용할 때 수행 시간 관점에서 효율적이다.
- JS에서는 Dictionary 자료형을 이용하여 큐를 구현하면 간단하다.

## JS 큐 구현
```js
class Queue {
  constructor() {
    this.items = {}; // 전체 원소를 담는items
    this.headIndex = 0;
    this.tailIndex = 0;
  }
  enqueue(item) { // 큐는 삽입할 때 꼬리 위치에 데이터를 넣는다 했다.
    this.items[this.tailIndex] = item;
    this.tailIndex++;
  }
  dequeue() {
    const item = this.items[this.headIndex];
    delete this.items[this.headIndex];
    this.headIndex++;
    return item;
  }
  peek() {
    return this.items[this.headIndex];
  }
  getLength() {
    return this.tailIndex - this.headIndex;
  }
}
```
- queue 사용 코드
```js
queue = new Queue();

queue.enqueue(5);
queue.enqueue(2);
queue.enqueue(3);
queue.enqueue(7);
queue.dequeue();
queue.enqueue(4);
while (queue.getLength() != 0) {
  console.log(queue.dequeue());
}

2
3
7
4
```
