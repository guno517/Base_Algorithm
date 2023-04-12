## sort(compare function)
- 정렬 기준 함수를 사용하지 않으면 각 원소는 문자열로 취급된다.
- 유니코드 값 순서대로 정렬된다.
- 항상 정렬 기준 함수를 명시하는 습관을 들일 필요가 있다.

### 대소문자 정렬 예시
```js
let arr ["melon", "Banana", "durian", "Apple", "carrot"];

function compare(a,b) {
  let upperCaseA = a.toUpperCase();
  let upperCaseB = b.toUpperCase();
  if (upperCaseA < upperCaseB) return -1;
  else if (upperCaseA > upperCaseB) return 1;
  else return 0;
}

arr.sort(compare);"
console.log(arr); // ["Apple", "Banana", "carrot", "durian", "melon"];
```

### 객체 정렬 예시
```js
let arr = [
  {name: '고길동', score: 90},
  {name: '박철수', score: 85},  
  {name: '김영희', score: 95},  
];

function compare(a,b){
  return b.score - a.score;
}

arr.sort(compare);
console.log(arr);
//
[
  {name: '김영희', score: 95},
  {name: '고길동', score: 90},
  {name: '박철수', score: 85}, 
];
```
