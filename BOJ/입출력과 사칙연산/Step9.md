# 나머지
- https://www.acmicpc.net/problem/10430
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
    console.log(((A + B) % C));
    console.log((((A % C) + (B % C)) % C));
    console.log(((A * B) % C));
    console.log((((A % C) * (B % C)) % C));
    rl.close();
});
```
A, B, C를 입력받아 주어진 셈의 결과를 출력하는 문제입니다. 
<br>
사용자로부터 입력을 받기 위해 readline 모듈을 사용하고, 입력값을 각각 처리한 결과를 출력하고 프로그램을 종료합니다.