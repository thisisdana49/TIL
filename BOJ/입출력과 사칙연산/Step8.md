# 1998년생인 내가 태국에서는 2541년생?!
- https://www.acmicpc.net/problem/18108
<br>

---
### 풀이
```
const fs = require('fs');
const input = fs.readFileSync('/dev/stdin').toString().trim();

const thaiYear = parseInt(input) - 543;

console.log(thaiYear);
```
사용자로부터 서기 연도를 입력받아, 태국 연도로 변환한 결과를 출력하는 문제입니다.
<br>
사용자로부터 입력을 받기 위해 readline 모듈을 사용하고, 입력값에 543을 더하여 결과를 출력하고 프로그램을 종료합니다.