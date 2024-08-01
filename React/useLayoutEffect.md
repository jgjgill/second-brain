Tags: #React 
브라우저가 화면을 그리기 전에 레이아웃 측정 수행

예시
- `Tooltip`

## 목적
컴포넌트가 렌더링에 레이아웃 정보를 사용하도록 하는 것
- 초기 컨텐츠 렌더링
- 브라우저가 화면을 다시 그리기 전에 레이아웃 측정
- 읽은 레이아웃 정보를 사용하여 최종 컨텐츠 렌더링

## 트러블 슈팅
### “`useLayoutEffect` does nothing on the server”
- `useEffect`를 활용
- `isMounted`로 분기
	- `export const useIsomorphicLayoutEffect = typeof window !== 'undefined' ? useLayoutEffect : useEffect`
- [[useSyncExternalStore]] 활용

## 참고자료
- [useLayoutEffect](https://react.dev/reference/react/useLayoutEffect)
