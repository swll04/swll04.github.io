---
title: forEach와 map 사용
date: 2019-08-07 15:55:22 +900
category: 나 혼자 공부
tag: forEach map
---

forEach

\- 배열의 요소를 반복

\- 각 요소에 대해 콜백을 실행

\- 값을 반환하지 않음

```
const a = [1,2,3]
const doubled = a.forEach((num, index) => {
	// null이나 index 이용
})
//doubled = undefined
```

map

\- 배열의 요소를 반복

\- 각 요소에서 함수를 호출하여 결과로 새 배열을 작성하여 각 요소를 새 요소애 맵핑한다.

```
const a = [1, 2, 3]
const doubled = a.map(num => {
	return num * 2
})

// doubled = [2, 4, 6]
```

forEach와 map의 가장 큰 차이점은 map이 새로운 배열을 반환한다는 것이다. 결과가 필요하지만 원본 배열을 변경하고싶지 않으면 map 아니면 forEach를 선택