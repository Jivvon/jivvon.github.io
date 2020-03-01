---
title: [React] life cycle 라이프사이클
tags: React study life-cycle lifecycle 라이프사이클
---

React의 component는 Life cycle은 가지는데, 특정 시점에 호출되는 메서드가 있다. 이를 **라이프 사이클 이벤트**라고 한다.

라이프사이클마다 주로 사용되는 메소드만 정리하였다. 각 메소드는 반드시 
**<span style="color:red">순서대로 실행</span>**된다.

#### mounting
    1. constructor()
    2. render()
    3. componentDidMount()

componentDidMount : AJAX, Timer를 주로 작성한다.

#### updating
    1. render()
    2. componentDidUpdate()

#### unmounting
    1. componentWillUnmount()

componentWillUnmount : Timer, async API를 제거한다.
