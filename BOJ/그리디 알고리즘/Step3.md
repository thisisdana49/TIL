# ATM
- https://www.acmicpc.net/problem/11399
<br>

---
### 풀이
```
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

let input = [];

rl.on('line', function (line) {
    input.push(line);
}).on('close', function () {
    const N = Number(input[0]);
    const times = input[1].split(' ').map(Number).sort((a, b) => a - b);

    let total = 0;

    for (let i = 0; i < N; i++) {
        total = total + times[i] * (times.length - i);
    }

    console.log(total);
});
```
그리디 알고리즘을 사용하여 푸는 문제로, 주어진 ATM 대기 시간을 최소화하는 방법을 찾아야 합니다.<br>
입력의 첫 번째 줄을 N에 두 번째 줄을 배열 times에 저장하고, 배열 times를 오름차순으로 정렬합니다.<br>
그리고 N만큼 반복하며 해당 시간 * (전체 시간 배열의 길이 - 현재 인덱스)로 계산하여 대기시간을 최소화하는 방법으로 누적 합산합니다<br>
최종적으로 최소화된 시간을 출력합니다.