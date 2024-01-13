# 괄호
- https://www.acmicpc.net/problem/9012
<br>

---
### 풀이
```
let fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString().trim().split('\n');

const N = parseInt(input[0]);
const output = [];

function isValidParenthesis(str) {
    const stack = [];

    for (let i = 0; i < str.length; i++) {
        const char = str.charAt(i);

        if (char === '(') {
            stack.push(char);
        } else if (char === ')') {
            if (stack.length === 0) {
                return false;
            }
            stack.pop();
        }
    }

    return stack.length === 0;
}

for (let i = 1; i <= N; i++) {
    const str = input[i].trim();
    if (isValidParenthesis(str)) {
        output.push('YES');
    } else {
        output.push('NO');
    }
}

console.log(output.join('\n'));
```
스택을 활용하여 주어진 괄호 문자열이 조건을 만족하는지 판별하는 문제입니다.<br>
사용자에게 입력을 받아 테스트 케이스의 개수인 정수 N과 결과를 저장할 output 배열을 초기화합니다.<br>
이후 테스트 케이스의 개수만큼 반복하여 케이스에 대한 조건을 만족하는지 판별하는 함수를 호출하여 그 결과를 output 배열에 저장합니다.<br>
판별하는 함수 isValidPaerenthesis는 각 케이스의 문자열을 순회하며,<br>
여는 괄호를 만나면 스택에 추가하고 닫는 괄호를 만나면 스택에서 pop하여 제거합니다.<br>
만약 스택이 비어있을 때 닫는 괄호를 만나면 유효하지 않으므로 false를 반환하며, <br>
문자열 순회가 끝난 후에도 여는 괄호가 남아있으면 역시 유효하지 않으므로 false를 반환합니다.<br>
반복문 종료 이후, output 배열에 담긴 모든 테스트 케이스의 결과를 한 줄에 하나씩 차례대로 출력합니다.