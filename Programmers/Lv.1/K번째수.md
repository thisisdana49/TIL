# K번째수
- https://school.programmers.co.kr/learn/courses/30/lessons/42748
<br>

---
### 풀이
```
function solution(array, commands) {
    const answer = [];

    for (const command of commands) {
        const [start, end, k] = command;
        answer.push(array.slice(start - 1, end).sort((a, b) => a - b)[k - 1]);
    }

    return answer;
}
```
1차원 배열 array에 2차원 배열 commands를 활용한 연산을 적용한 결과를 출력하는 문제입니다.<br>
반복문을 통해 commands의 각 배열에 접근하고, 해당 배열의 요소를 추출하여 이를 통해<br>
array를 슬라이스 연산, 정렬 연산, 인덱스 값을 차례로 수행하여 answer에 저장합니다.<br>