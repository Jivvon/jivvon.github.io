---
title: Redux 정리
tags: react redux 상태관리
---

### 액션 (Action)

액션 객체는 **반드시 `type` 필드를 가져야 한다.**

### 액션 생성함수 (Action Creator)

**액션 객체를 만드는 함수**이다. 파라미터를 *payload*로 통일하기도 한다.

### Reducer

리듀서는 **변화를 일으키는 함수**이다. 파라미터는 **(state, action)** 두 개이다.

### Store

스토어 안에는 현재의 앱 상태와, 리듀서와, 몇가지 내장 함수들이 있다.

### dispatch

스토어의 내장 함수 중 하나이며, **액션을 발생**시킨다. dispatch에는 액션을 파라미터로 전달한다. 

스토어는 reducer 함수를 실행시켜 해당 액션을 통해 새로운 상태를 만든다.

### subscribe

함수 형태의 값을 파라미터로 받아와, 액션이 디스패치 되었을 때마다 전달된 함수가 호출된다. (react와 함께 사용하면 react-redux가 알아서 처리해주기 때문에 대부분 쓸 일이 없다.)

---

vue 의 vuex와 굉장히 유사하다. 
> vuex에는 state, mutation, actions가 있고, <br />redux에는 state, action, reducer이 있다.