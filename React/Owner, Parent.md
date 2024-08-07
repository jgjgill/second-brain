Tags: #React 
created at : 2024-08-01
updated at: 

## Owner

- `Child` 컴포넌트에게 렌더링을 유발한다.
- `Child` 에게 `Props` 를 전달할 수 있다.

## Parent

- `Parent`는 `Child` 컴포넌트에게 렌더링을 유발하지 않는다.
- `Child` 에게 `Props` 을 전달할 수 없다.

### Example

```jsx
function Owner() {
	return (
		<Parent>
			<Child />
		<Parent/>
	)
}
```

### Use Case

- 서버 컴포넌트에서 `Provider` 패턴 형태로 활용