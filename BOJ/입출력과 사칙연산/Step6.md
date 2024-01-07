# A-B
- https://www.acmicpc.net/problem/10869
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
    const [A, B] = input.split(' ').map(Number);
    console.log(A + B);
    console.log(A - B);
    console.log(A * B);
    console.log(Math.floor(A / B));
    console.log(A % B);
    rl.close();
});
```
두 자연수 A와 B를 입력받아 입력된 두 숫자를 덧셈, 뺄셈, 곱셈, 몫 그리고 나머지 값을 출력하는 문제입니다. 
<br>
사용자로부터 입력을 받기 위해 readline 모듈을 사용하고, 입력값을 처리하여 각 값을 출력하고 프로그램을 종료합니다.