---
title: [React] babel 알아보기
tags: react study babel es6 es7
---

babel은 **컴파일러**다. ES6(ECMAScript 2015), ES7와 같은 최신 문법이 호환되지 않는 브라우저가 있기 때문에 브라우저가 이를 이해할 수 있도록 컴파일 해주는 도구이다.

### babel-polyfill

babel-polyfill이 없다면 babel은 브라우저에서 실행되지 않는다. polyfill은 브라우저에 따라 호환되지 않는 문법을 사용한 객체에 prototype을 설정해준다.

### .babelrc

.babelrc는 프로젝트의 최상단에 위치해야 한다. plugins는 문법들이라 보면 되고, preset은 여러 개가 묶여있는 개념이다. 대표적으로 ES6 문법을 모아놓은 es2015 preset과 react 문법을 모아놓은 react preset이 있다.

### babel-cli

babel을 직접 빌드할 때 사용하는 babel-cli. 보통은 webpack을 사용한다.