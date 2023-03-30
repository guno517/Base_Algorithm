## 개념
- 선택 정렬은 매 단계에서 가장 작은 원소를 선택해서 앞으로 보내는 정렬 방법
- 매 단계에서 가장 작은 것을 선택하는 데에 약 N번의 연산이 필요 (선형 탐색)
- 앞으로 보내진 원소는 더 이상 위치가 변하지 않음
- 시간 복잡도 : O(N<sup>2</sup>)

## 동작 방식
1. 각 단계에서 가장 작은 원소를 선택
2. 현재까지 처리되지 않은 원소들 중 가장 앞의 원소와 위치를 교체
ps. 전체가 N개 일 때, N - 1번 반복을 한다. (마지막 원소는 이전에 이미 배치되어있다.)

## 소스 코드 
```
function selectionSort(arr) {
    for(let i = 0; i < arr.length; i++){
        let minIndex = i; // 가장 작은 원소의 인덱스
        for(let j = i + 1; j < arr.length; j++){
            if(arr[minIndex] > arr[j]){
                minIndex = j;
            }
        }
      // 위치 교체
      let temp = arr[i];
      arr[i] = arr[minIndex];
      arr[minIndex] = temp;
    }
}
```
