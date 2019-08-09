---
title: Higher order function (고차 함수)
date: 2019-08-09 18:37:52 +900
category: 나 혼자 공부
tag: 고차 함수
---

## 고차함수
고차 함수는 다른 함수를 매개 변수로 사용하여 어떤 데이터를 처리하거나 결과로 함수를 반환하는 함수다. 반복적으로 수행하는 어떤 연산을 추상화 하기 위해 사용된다.  

배열과 함수를 인수로 취하는 map이 전형적인 예이다.  
map은 고차 함수를 사용하여 배열의 각 항목을 변환하고, 변환된 데이터로 새 배열을 반환한다.  
자바스크립트에서 흔히 볼 수 있는 다른 예로는 forEach와 reduce, filter가 있다.  
  
다른 함수에서 함수를 반환하는 많은 사용사례가 있기 때문에 고차 함수는 배열을 조작할 필요가 없다.

### map
배열안의 각 요소를 대문자 문자열로 변환한다고 가정해보자.

```
const foo = ['abc', 'def', 'ghi'];
```

일반적인 방법으로는 다음과 같이 한다.

```
const alphabetToUpper = function(abc) {
  const results = [];
  for (let i = 0; i < abc.length; i++) {
    results.push(abc[i].toUpperCase());
  }
  return results;
};
alphabetToUpper(foo); // ['IRISH', 'DAISY', 'ANNA']
```

map을 사용하면

```
const alphabetToUpper = function(abc){
    return abc.map(name => name.toUpperCase());
}
alphabetToUpper(foo); // ['IRISH', 'DAISY', 'ANNA']
```

더 짧다.