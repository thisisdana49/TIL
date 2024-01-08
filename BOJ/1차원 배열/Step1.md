# 개수 세기
- https://www.acmicpc.net/problem/2557
<br>

---
### 풀이 1
```
const fs = require('fs');
const input = fs.readFileSync('/dev/stdin').toString().split('\n');

const N = Number(input[0]);
const arr = input[1].split(' ').map(Number);
const v = Number(input[2]);

let cnt = 0;
for (i = 0; i < N; i++) {
  if (arr[i] === v) {
    cnt++;
  }
}
console.log(cnt);

```
총 N개의 정수가 주어졌을 때, 정수 v가 몇 개인지 구하는 문제입니다. <br>
N번만큼 arr 배열을 돌고, 정수 v와 같은 배열의 요소를 만나면 cnt++를 하여 최종 cnt를 출력합니다.<br>
<br>
### 풀이 2
```
const fs = require('fs');
const input = fs.readFileSync('/dev/stdin').toString().split('\n');

const [N, S, V] = input;

const cnt = S.split(' ').filter((el) => el == V).length;

console.log(cnt);

```
filter 함수를 사용하여 풀 수도 있습니다.