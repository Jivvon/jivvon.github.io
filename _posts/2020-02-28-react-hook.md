---
title: [React] Hooks 리액트 훅
tags: react study hooks react-hooks
---

React Hook 리액트 훅을 사용하면 함수형 컴포넌트로도 state를 다룰 수 있다. (클래스 컴포넌트보다 더 편하게 !)

### useState

``` javascript
const App = () => {
  const [count, setCount] = useState(0); // 배열 [value, value를 변경하는 함수] 를 반환
  const [email, setEmail] = useState("");
  const updateEmail = e => {
    const {
      target: { value }
    } = e;
    setEmail(value);
  };
  return (
    <>
      <div>{count}</div>
      <div>{email}</div>
      <button onClick={() => setCount(count + 1)}>Increment</button>
      <input placeholder="Email" value={email} onChange={updateEmail} />
    </>
  );
};
```
**useState는 배열 [value, value를 변경하는 함수] 를 반환한다.**

### useEffect

``` javascript
useEffect(func, [dependency])
```

**useEffect는 dependency가 바뀔 때마다 func을 호출한다**

### useRef

``` javascript
const inputTag = useRef()
setTimeout(() => inputTag.current.focus(), 5000)
<input ref={inputTag} placeholder="Type here..." />
```

**모든 react component는 reference 속성을 가지고 있다. useRef는 해당 element를 사용할 수 있게 해준다. (getElementById 처럼 !)**




---

### Note


input 태그 안의 value={name.value} onChange={name.onChange}는 {...name}과 같은 의미이다.

``` javascript
<input value={name.value} onChange={name.onChange} placeholder="Type here" />>
```
``` javascript
<input {...name} placeholder="Type here" />>
```

다음과 같이 쓸 수 있다 (in JSX only)

``` javascript
flag = false
{flag && <span>this is true</span>}
{!flag && <span>this is false</span>}
```

**modal (popup) 만들기**
``` javascript
function clickOutside(f){
    const ref = createRef();
    const handleClick = e => {
        if(!ref.current.contains(e.target)){
            f();
        }
    }
    useEffect(()=>{
        document.addEventListener("click", handleClick);
    }, []) // componentDidMount 후 rerender 안 함
    return ref;
}


function App() {
    const testFunction = () => {
        console.log("test")
    }
    const ref = clickOutside(testFunction);
    return (
        <div className="App">
            <div ref={ref}>
                <h2>popup</h2>
            </div>
        </div>
    )
}

```



### 참고
- [노마드 코더 youtube](https://www.youtube.com/channel/UCUpJs89fSBXNolQGOYKn0YQ)