Tags: #React 
Created at : 2024-07-31
Updated at: 방법 찾기

- `mutable`한 객체 ([[state]]와 가장 큰 차이점)
- `escape hatch` (탈출구) 역할
- `DOM`에 직접 가능
- `ref.current`로 접근
- React에서 제공하는 명령형(imperative) API
	- `ref`를 `props`로 넘기는 경우 충돌하는 상황 발생
	- `forwardRef` 활용
- 코드를 클린하게 구성하는 방법
	- [[useimperativehandle]] 활용 (외부에서 DOM을 노출시키고 싶지 않음)
- **ref callback** 방식
	- `ref` 가 여러 개 사용하는 경우 활용 가능

`ref` 의 내부 코드는 `useState` 에서 `setter` 를 사용하지 않은 것과 유사

```jsx
function useRef(initialValue) {
	const [ref, unUsed] = useState({ current: initialValue })
	
	return ref
}
```


...ing
https://react.dev/learn/referencing-values-with-refs


## Reference

- [useRef](https://react.dev/reference/react/useRef#avoiding-recreating-the-ref-contents)
- [Referencing Values with Refs](https://react.dev/learn/referencing-values-with-refs)