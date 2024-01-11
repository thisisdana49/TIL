# 카드2
- https://www.acmicpc.net/problem/2164
<br>

---
### 풀이
```
let fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString().trim();

const N = parseInt(input);

let front = 0;
let rear = N - 1;
const queue = new Array(N);

for (let i = 0; i < N; i++) {
    queue[i] = i + 1;
}

while (front < rear) {
    front++;
    rear++;
    queue[rear] = queue[front];
    front++;
}

console.log(queue[front]);
```
큐 자료구조를 활용하는 문제입니다. 맨 앞과 맨 뒤의 인덱스를 변수로 저장하고, 1부터 N까지의 원소를 가진 배열을 생성합니다.
이후 front가 rear보다 작은 경우를 조건으로 하는 while문을 돌려, 큐의 앞에 있는 원소를 삭제하고 그 다음 원소를 마지막 인덱스 뒤에 저장합니다.
다음 루프의 시작을 위해 front++를 해주고, while문이 끝나면 front번째에 있는 원소를 출력합니다.