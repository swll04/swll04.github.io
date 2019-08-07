---
title: .call 과 .apply의 차이
date: 2019-08-07 15:50:22 +900
category: 나 혼자 공부
tag: call apply
---

.call과 .apply는 모두 함수를 호출하는 데 사용되며 첫 번째 매개변수는 함수 내에서 this의 값으로 사용된다. 그러나 .call은 쉼표로 구분된 인수를 두 번째 인수로 취하고 .apply는 인수의 배열을 두 번째 인수로 취한다.

```
function add(a, b) {
	return a + b;
}

console.log(add.call(null, 1, 2)) // 3
console.log(add.apply(null, [1, 2])) // 3
```