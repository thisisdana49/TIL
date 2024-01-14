# 나머지
- https://www.acmicpc.net/problem/3052
<br>

---
### 풀이
```
const input = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');

const remainders = new Set();

for (let i = 0; i < 10; i++) {
    const num = parseInt(input[i]);
    const remainder = num % 42;
    remainders.add(remainder);
}

console.log(remainders.size);
```
수 10개를 입력받은 뒤, 이를 42로 나눈 나머지를 구한 다음 서로 다른 값이 몇 개 있는지 출력하는 문제입니다.<br>
중복을 허용하지 않는 자료구조 Set을 사용한 remainders를 생성합니다.<br>
10번 도는 반복문을 통해, 각 순번을 42로 나누었을 때의 나머지를 구해 remainders에 저장합니다.<br>
최종적으로remainders의 크기를 출력하면, 중복된 값은 제외된 값의 개수가 출력됩니다.