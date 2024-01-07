# 꼬마 정민
- https://www.acmicpc.net/problem/11382
<br>

---
### 풀이
```
const readline = require('readline');
const rl = readline.createInterface({
    input: process.stdin,
    output: process.stdout
});

rl.question('', (input) => {
    const [A, B, C] = input.split(' ').map(Number);
    const result = A + B + C;
    console.log(result);
    rl.close();
});
```
세 정수 A와 B 그리고 C를 입력받아 모두 더한 결과를 출력하는 문제입니다. 
<br>
사용자로부터 입력을 받기 위해 readline 모듈을 사용하고, 입력값을 덧셈하여 결과를 출력하고 프로그램을 종료합니다.