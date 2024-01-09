# 공 넣기
- https://www.acmicpc.net/problem/10810
<br>

---
### 풀이 1
```
const fs = require('fs');
const input = fs.readFileSync('/dev/stdin').toString().split('\n');

<!-- const [N, M] = input[0].split(' ').map(el => +el); -->
const [N, M] = input[0].split(' ').map(Number);
let arr = new Array(N);

for(let i = 1; i <= M; i++ ){
   let [start, end, k] = input[i].split(' ').map(Number);
    for(start; start <= end; start++){
        arr[start-1] = k;
    } 
}

for(let j=0; j<arr.length; j++){
    typeof arr[j] === 'undefined' ? arr[j] = 0 : arr[j]
}

console.log(arr.join(' '));

```
N개의 바구니에 M번 공을 넣어, 각 바구니에 어떤 공이 들어 있는지 구하는 문제입니다. <br>
M번만큼 반복문을 실행하여, 배열의 해당 되는 index만큼의 요소에 k를 할당합니다.<br>
그리고 두 번째 반복문을 통하여 할당되지 않은 요소에는 0을 할당하고, 최종 arr를 출력합니다.<br>