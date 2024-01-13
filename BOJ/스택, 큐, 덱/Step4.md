# 균형잡힌 세상
- https://www.acmicpc.net/problem/4949
<br>

---
### 풀이
```
let fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString().trim().split('\n');

const open = ['(', '['];
const close = [')', ']'];
const output = [];

input.slice(0, input.length - 1).forEach((v) => {
    let isBalanced = true;
    let stack = [];
    for (let i = 0; i < v.length; i++) {
        if (open.includes(v[i])) {
            stack.push(v[i]);
        } else if (close.includes(v[i])) {
            if (stack.length === 0) {
                isBalanced = false;
                break;
            }
            const last = stack[stack.length - 1];
            if (open.indexOf(last) === close.indexOf(v[i])) {
                stack.pop();
            } else {
                isBalanced = false;
                break;
            }
        }
    }
    if (isBalanced && stack.length === 0) {
        output.push('yes');
    } else {
        output.push('no');
    }
});

console.log(output.join('\n'));

```
스택을 활용하여 주어진 문자열의 괄호들이 균형과 조건을 만족하는지 판별하는 문제입니다.<br>
사용자에게 입력을 받은 케이스들을 각각 forEach로 처리합니다.<br>
케이스마다 주어진 문자열의 괄호 유효성을 스택을 활용하여 검사합니다. <br>
검사 방식은 열린 괄호는 스택에 추가하고, 닫힌 괄호는 스택에서 pop하여 짝을 확인합니다.<br>
만약 스택이 비어있지 않거나 균형이 맞지 않는 경우 isBalanced를 false를 설정하며, <br>
스택이 비어있고 isBalanced가 true인 경우 yes를 출력합니다.<br>
반복문 종료 이후, output 배열에 담긴 모든 테스트 케이스의 결과를 개행 문자로 구분하여 출력합니다.