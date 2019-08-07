---
title: 프로토타입 상속 작동 원리
date: 2019-08-07 18:48:22 +900
category: 나 혼자 공부
tag: prototype inheritance 프로토타입
---

모든 javascript 객체는 다른 객체에 대한 참조인 prototype property를 가지고 있다. 객체의 property에 접근할 때 해당 객체에 해당 property가 없으면
javascript엔진은 객체의 prototype과 prototype의 prototype 등을 보고 property 정의가 있을 때 까지 찾고, 
만약 객체의 property에 접근할 때 해당 객체에 해당 property가 없으면 prototype 체인 중 하나에 있거나 prototype 체인의 끝에
도달할 때 까지 찾는다. 이 동작은 고전적인 상속을 흉내내지만, 실제로 상속보다 위임에 더 가깝다.  

