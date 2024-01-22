# 좌표 압축
- https://www.acmicpc.net/problem/18870
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
rl.on('line', (line) => {
    input.push(line);
    if (input.length === 2) {
        rl.close();
    }
});

rl.on('close', () => {
    const N = Number(input[0]);
    const sequence = input[1].split(' ').map(Number);

    const sortedUniqueSequence = [...new Set(sequence)].sort((a, b) => a - b);

    const compression = {};
    sortedUniqueSequence.forEach((num, index) => {
        compression[num] = index;
    });

    const compressedSequence = sequence.map((num) => compression[num]);

    console.log(compressedSequence.join(' '));
});       
```
<br>
주어진 수열을 좌표 압축하는 문제입니다. 수열의 각 숫자를 해당 숫자보다 작은 숫자의 개수로 변환하여 새로운 배열을 만듭니다.<br>
수열의 길이 N과 수열을 입력 받고, 정렬하여 중복을 제거하는 Set 자료구조에 저장합니다.<br>
이 중복 제거 된 수열을 기준으로 숫자보다 작은 숫자의 개수로 변환하는 작업인 index를 배열에 저장합니다.<br>
이후 수열을 입력 받은 순서대로 해당 숫자의 index를 출력합니다.