# ??!
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
    const readline = require('readline');
    const rl = readline.createInterface({
        input: process.stdin,
        output: process.stdout
    });

    rl.question('', (input) => {
        const result = input + '??!';
        console.log(result);
        rl.close();
    });    
});
```
사용자로부터 문자열을 입력받아, 입력된 문자열 뒤에 "??!"를 추가한 결과를 출력하는 문제입니다. 
<br>
입력된 문자열과 "??!"를 문자열 연산을 통해 합쳐서 출력히고 프로그램을 종룍합니다.