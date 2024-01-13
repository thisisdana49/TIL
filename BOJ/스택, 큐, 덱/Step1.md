# 스택2
- https://www.acmicpc.net/problem/28278
<br>

---
### 풀이
```
let fs = require('fs');
let input = fs.readFileSync('/dev/stdin').toString().trim().split('\n');

const N = parseInt(input[0]);
const stack = [];
const output = [];

for (let i = 1; i <= N; i++) {
  const cmd = input[i].split(' ');

  switch (cmd[0]) {
    case '1':
      stack.push(parseInt(cmd[1]));
      break;
    case '2':
      if (stack.length > 0) {
        output.push(stack.pop());
      } else {
        output.push(-1);
      }
      break;
    case '3':
      output.push(stack.length);
      break;
    case '4':
      output.push(stack.length > 0 ? 0 : 1);
      break;
    case '5':
      if (stack.length > 0) {
        output.push(stack[stack.length - 1]);
      } else {
        output.push(-1);
      }
      break;
  }
}

console.log(output.join('\n'));

```
문제에서 설명하는 것과 같이 정수를 저장하는 스택을 구현하는 문제입니다.<br>
사용자에게 입력을 받고, 스택으로 사용할 stack과 출력 결과를 저장할 output 2개의 배열을 생성합니다.<br>
그리고 주어진 명령의 수 N만큼 반복문을 돌리며, switch문을 사용하여 명령에 따라 다른 방식으로 처리합니다.<br>
각 명령을 모두 처리한 다음 최종적으로 output 배열을 개행 문자로 구분하여 출력합니다.