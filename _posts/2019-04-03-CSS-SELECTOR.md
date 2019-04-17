---
title: CSS SELECTOR
date: 2019-04-03 18:43:22 +900
category: CSS
tag: CSS
---
# CSS SELECTOR
CSS에서 element를 선택하는 규칙이다. 
앞에서 모든 동일한 h1에 동일한 컬러를 부여했다면, 이번에는 예외를 두고 몇개의 h1에는 다른 색을 주고싶을 경우 사용할 수 있는 방법이다.
1. id 부여
2. class 부여

1번 id부여를 먼저 보면,
```
    <h1>나는 1번</h1>
    <h1>나는 2번</h1>
    <h1>나는 3번</h1>
```
여기서 2번만 다른 색을 주고싶을 경우
```
    <h1>나는 1번</h1>
    <h1 id="color2">나는 2번</h1>
    <h1>나는 3번</h1>
```
라고 2번에 id를 부여한다. 그런 다음 main.css에 들어가서 다음과 같이 작성해주면
```
h1{
    color:blue;
  }
#color2{
  color:green;
}
```
실행결과 

![아이디](https://images.velog.io/post-images/swll04/9b2faaa0-51df-11e9-b536-7503904d0047/-2019-03-29-14.00.00.jpg)

2번이 바뀐것을 볼 수 있다.
다음 두번째 방법인 class는 id와 똑같다. 
```
    <h1>나는 1번</h1>
    <h1 id="color2">나는 2번</h1>
    <h1 class="color3">나는 3번</h1>
```
이렇게 작성해주며 main.css에서는 #이 아닌 .을 이용한다.
```
.color3{
  color:red;
}
```
실행결과

![클래스](https://images.velog.io/post-images/swll04/397e8d70-51e0-11e9-b536-7503904d0047/-2019-03-29-14.05.01.jpg)
이렇게 나타난다.

## 그렇다면 id와 class의 차이는 무엇인가?
id는 이름을 짓는 것이다. 각각의 element에다가 고유한 id를 부여하는 것이다. 한번 사용되면 다른 곳에 동일한 id를 지정하면 안된다.
class는 여러곳에 같은 class를 지정할 수 있다.

![차이점](https://images.velog.io/post-images/swll04/2e71a490-52a2-11e9-bb9d-7b852077c439/-2019-03-30-13.11.44.jpg)


id와 class의 우선순위를 확인하는 방법은 같이 써보면 된다.
```
<h1 id="color1" class="color2">어떤 값이 나타날까??</h1>
```
```
#color1{
  color:green;
}
.color2{
  color:red;
}
```
실행결과

![우선순위](https://user-images.githubusercontent.com/46247666/55268714-c0ed5d00-52cf-11e9-8a00-71b6b3d8c85e.jpg)

이렇게 id값이 우선적으로 나타나게 된다. 