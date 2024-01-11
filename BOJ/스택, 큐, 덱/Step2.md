# 제로
- https://www.acmicpc.net/problem/10773
<br>

---
### 풀이
```
let fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString().split('\n');

const caseCount = Number(input[0]);
const stack =  [];

for (let i = 1; i <= caseCount; i += 1) {
  const value = Number(input[i]);

  if (value === 0) {
    stack.pop();
  } else {
    stack.push(value);
  }
}

let result = 0;

for (let i = 0; i < stack.length; i += 1) {
  result += stack[i];
}

console.log(result);
```
스택 자료구조를 활용하는 문제입니다. 주어진 숫자들을 스택에 넣고, 0이 나올 때마다 스택에서 값을 빼고 최종 결과값을 출력합니다.