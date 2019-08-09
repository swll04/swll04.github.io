---
title: 함수 선언식 표현식
date: 2019=08-09 18:30:13 +900
category: 나 혼자 공부
tag: 함수 선언 표현
---

## 함수 선언식

함수 바디가 호이스트 된다

## 함수 표현식

함수 바디는 호이스트 되지 않는다.
함수 표현식을 정의하기 전에 호출하려고 하면 Uncaught TypeError : XXX is not function 에러가 발생한다.

### 함수 선언식

```
abc(); // 'qwerty'
function abc(){
    console.log('qwerty');
}
```

### 함수 표현식

```
def(); // Uncaught TypeError : def is not function
var def = function(){
    console.log('asdfgh');
}
```