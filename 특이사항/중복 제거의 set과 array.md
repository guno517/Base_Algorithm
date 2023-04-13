### 중복 제거할 경우 set을 사용할 때 주의점
```js
const fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString().split('\n');

let n = Number(input[0]); // 13
let arr = [];

for(let i = 1; i <= n; i++){
    arr.push(input[i]);
}

arr.sort((a,b) => a.length - b.length || a.localeCompare(b));
// const set = new Set(arr);
// const result = [...set]
const result = Array.from(new Set(arr));
let answer = '';
result.map((str) => answer += `${str} \n`);
console.log(answer);
```
- 중복 제거를 위해 set을 사용할 경우 set은 배열 형태가 아니므로 typeerror가 발생할 수 있다.
- 그러므로 set을 생성할 때, <b>Array.from</b> 으로 감싸서 배열 형태로 만들어서 사용하면 좋다.
