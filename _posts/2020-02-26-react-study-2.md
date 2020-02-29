---
title: react 2
tags: react study
---

## 기본 react 2

> **prop-types** 를 이용하여 props의 데이터 유효성을 검증할 수 있다.

`npm i prop-types`

``` js
Animal.propTypes = {
    type: PropTypes.string.isRequired,
    legs: PropTypes.number.isRequired
}
```

자세한 것은 [prop-types](https://www.npmjs.com/package/prop-types)에서 알아보자.

### class component

``` javascript
function Animal({ type, legs }){
    console.log(type) // dog
    console.log(legs) // 4
    return <div>type is {type}</div>
}
```

위는 function component이다. 이를 class component로 바꾸면

``` javascript
class Animal extends React.Component{
    render(){
        return <div>this is a class component</div>
    }
}
```
이 된다.

#### react는 모든 class component 안의 render() 함수를 실행한다.

**class component와 function component의 차이가 쉽게 설명되어있다** : [여기](https://overreacted.io/ko/how-are-function-components-different-from-classes/)

> 핵심은 class component는 function component와 다르게 말 그대로 '클래스'이기 때문에 파라미터를 받지 못한다. 따라서 부모로부터 넘겨지는 데이터를 **this.props**로 받을 수 있는데, 여기서 this가 바뀔 수 있기 때문에 이를 클로저로 감싸줘야 한다는 것이다.

``` javascript
class Animal extends React.Component {
  render() {
    const props = this.props; // 렌더링 될 때의 props
    return <div>props in closure</div>
  }
}
```

React.Component를 확장하면 state를 사용할 수 있다. state는 **데이터를 동적으로 다룰 수 있다.** 즉, component의 data를 바꿀 수 있다.

``` javascript
class Animal extends React.Component {
    state = {
        test: 0
    }
    render() {
        return <div>dynamic data test : {this.state.test}</div>
    }
}
```

react에서 state를 변경할 때에는 state를 직접 변경하지 않고 반드시 setState를 사용해야 한다. why? **state를 직접 변경한다면 rerendering을 하지 않기 때문.** 즉, setState를 사용한다면, react는 state를 변경 후 render 함수를 다시 호출할 것이다. 

render 함수를 매번 호출한다면 성능상의 문제가 생기지 않을까 ? 는 no. **react는 Virtual DOM이 있기 때문에 여기서 변경된 부분만 화면에 표출한다.**

``` javascript
class Animal extends React.Component {
    state = {
        count = 1
    }
    add = () => {
        this.setState(curState => ({ count: curState.count + 1 }))
    }
    render() {
        return <button onClick={this.add}>click</button>
    }
}
```


+) button 태그의 onclick 속성에서 메소드는 다음과 같이 사용한다.

``` javascript
class Animal extends React.Component {
    func = () => {console.log("func")}
    render() {
        /*
            this.func은 클릭할 때마다 실행
            this.func()은 렌더링 되자마자 실행
        */
        return <button onClick={this.func}>click</button>
    }
}
```



### 참고
- [노마드 코더 youtube](https://www.youtube.com/channel/UCUpJs89fSBXNolQGOYKn0YQ)