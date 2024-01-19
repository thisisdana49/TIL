# 단어 정렬
- https://www.acmicpc.net/problem/1181
<br>

---
### 풀이
```
const input = require('fs').readFileSync('/dev/stdin').toString().trim().split('\n');****

const words = new Set();
const sortedWords = new Map();****

for (let i = 1; i <= input[0]; i++) {
    words.add(input[i]);
}

words.forEach(word => {
    if (!sortedWords.has(word.length)) {
        sortedWords.set(word.length, []);
    }
    sortedWords.get(word.length).push(word);
});

const sortedKeys = Array.from(sortedWords.keys()).sort((a, b) => a - b);

sortedKeys.forEach(key => {
    const sortedWordsByLength = sortedWords.get(key).sort();
    sortedWordsByLength.forEach(word => console.log(word));
});        
```
입력받은 N개의 단어를 짧은 것부터, 길이가 같다면 사전 순으로 정렬하는 프로그램입니다. 또한 같은 단어가 있다면 하나만 남기고 제거합니다.<br>
먼저 중복을 제거하고 시작하기 위해 단어들은 Set인 words에 추가합니다.<br>
그 다음 단어들의 길이를 기준으로 정렬하기 위해 길이가 같은 단어들을 하나의 배열로 묶어 Map인 sortedWords에 추가합니다.<br>
단어들을 길이별로 sortedWords에 모두 정렬했다면, 다음으로는 key값을 짧은 순으로 나열하여 sortedKeys에 담아줍니다.
마지막으로, 짧은 길이의 단어들부터 접근하여 각 배열의 단어들을 사전 순으로 정렬하고 출력합니다.