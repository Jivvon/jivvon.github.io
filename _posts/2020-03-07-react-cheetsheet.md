---
title: react 메모장
tags: react
---

루트 리듀서에 등록하기 : src/modules/index.ts
투두리스트 컴포넌트 준비하기
  필요한 컴포넌트 미리 정하기 - 각 컴포넌트는 하나의 동작만 하도록.

modules/
  action
    1. 액션의 타입을 정하고 // vue.js의 mutation-type
    2. 액션 생성 함수를 선언한다. - { createStandardAction } from 'typesafe-actions' 이용
  types
    1. action에서 정한 액션 타입을 하나로 묶어 타입을 정의한다. - export type TodosAction = ActionType<typeof actions>;
    2. 데이터 타입 정의한다.
  reducer
    1. 초기값을 설정하고
    2. action에서 정한 액션 타입별로 실행되는 리듀서를 선언한다. - { createReducer<state, action> } from 'typesafe-actions' 이용, vue.js의 mutation처럼 [ADD_TOTO]: (state, {payload: text}) =>{...}


