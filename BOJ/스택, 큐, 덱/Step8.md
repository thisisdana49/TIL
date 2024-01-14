# 요세푸스 문제 0
- https://www.acmicpc.net/problem/11866
<br>

---
### 풀이
```
const input = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');

const [N, K] = input[0].trim().split(' ').map(Number);

const queue = [];
for (let i = 1; i <= N; i++) {
    queue.push(i);
}

const result = [];
let index = 0;

while (queue.length > 0) {
    index = (index + K - 1) % queue.length;
    result.push(queue.splice(index, 1)[0]);
}

console.log('<' + result.join(', ') + '>');

```
요세푸스 순열을 구현하는 문제입니다.<br>
먼저 1부터 N까지 순번을 의미하는 모든 수를 queueq 배열에 저장합니다.<br>
다음으로, index에 K-1을 더해 그 값을 큐의 길이로 나눈 나머지를 index로 설정합니다.<br>
이때 큐에서 index번째 수를 빼내고 result 배열에 저장합니다. 큐의 길이가 0이 되면 반복문을 종료합니다.<br>
마지막으로 '<'와 '>'를 붙여 result배열의 모든 요소를 출력합니다.<br>