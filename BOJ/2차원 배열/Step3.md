# 세로 읽기
- https://www.acmicpc.net/problem/10798
<br>

---
### 풀이
```
const words = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');

const maxLength = Math.max(...words.map(word => word.length));

let result = '';

for (let i = 0; i < maxLength; i++) {
    for (let j = 0; j < words.length; j++) {
        if (i < words[j].length) {
            result += words[j][i];
        }
    }
}

console.log(result);

```
주어진 다섯 줄의 단어들을 세로로 읽어 공백 없이 연속해서 출력하는 문제입니다.<br>
먼저 입력받은 단어의 길이가 다를 수 있기 때문에 maxLength에 단어 중 가장 긴 길이를 구합니다.<br>
그리고 이중 for문을 돌려서, 각 단어의 [i]번째를 결과 문자열 result에 추가합니다.<br>
이때 현재 단어의 길이가 i보다 작으면 해당 단어의 i번째는 존재하지 않으므로 무시됩니다.<br>
최종적으로 결과 문자열 result을 출력합니다.