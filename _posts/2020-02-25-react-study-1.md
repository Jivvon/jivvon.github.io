---
title: React 1
tags: react study
---

## 기본 react 1

react는 빈 html 파일을 읽은 후 JSX(html + javascript) 를 렌더링하여 표출한다. 즉, 처음 불러오는 파일은 가볍기 때문에 속도가 빠르다.

**모든 요소는 component이다.**
and component는 반드시 대분자로 시작해야 한다 !

react는 component를 가져와서 브라우저가 이해할 수 있는 형태의 html 코드로 만든다.

**react application은 한번에  하나의 component만 rendering할 수 있다.**

``` javascript
ReactDOM.render(<App />, document.getElementById('root'));
```

처럼 하나만 렌더링 가능 ! 하므로 가장 큰 DOM인 App 안에 다른 것들이 들어가야 한다.

#### **component는 재사용 가능하다** 또한, **component 간에 정보를 주고받을 수 있다**

``` javascript
<Animal type="dog" legs=4 > // Animal 컴포넌트에 type이라는 속성의 값으로 dog를 넘겨준 것.
```

이러한 속성들은 **props**라고 부른다.
props는 여러 개가 될 수 있고, 컴포넌트를 정의하는 곳에서는 **하나의 object로 묶어서 argument로 받는다.**

이는 각각 받을 수 있다 ! (ES6)

``` javascript
function Animal(param){
    console.log(param) // {type = "dog", legs = 4}
    return <div>type is {param.type}</div>
}
```
를 아래와 같이 쓸 수 있다
``` javascript
function Animal({ type, legs }){
    console.log(type) // dog
    console.log(legs) // 4
    return <div>type is {type}</div>
}
```

**javascript는 중괄호'{}'로 묶는다**

**component의 key는 unique해야 한다. -> parameter로 넘겨주지 않아도 component를 사용할 때 key 속성을 주자.**

---

### 참고
- [노마드 코더 youtube](https://www.youtube.com/channel/UCUpJs89fSBXNolQGOYKn0YQ)