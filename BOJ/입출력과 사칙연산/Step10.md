# 곱셈
- https://www.acmicpc.net/problem/2588
<br>

---
### 풀이
```
const fs = require('fs');
const input = fs.readFileSync('/dev/stdin').toString().split('\n');

const num1 = parseInt(input[0]);
const num2 = parseInt(input[1]);

const result1 = num1 * (num2 % 10);
const result2 = num1 * Math.floor((num2 % 100) / 10);
const result3 = num1 * Math.floor(num2 / 100);
const totalResult = num1 * num2;

console.log(result1);
console.log(result2);
console.log(result3);
console.log(totalResult);
```
(세 자리 수) * (세 자리 수) 과정에서의 수 세 가지를 출력하는 문제입니다.
<br>
사용자로부터 입력을 받기 위해 readline 모듈을 사용하고, 입력값을 각각 처리하여 변수에 저장하고, 순서대로 출력한 다음 프로그램을 종료합니다.