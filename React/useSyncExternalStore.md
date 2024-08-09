Tags: #React 

Reference
- [Build your own React state management library in under 40 lines of code](https://dev.to/paripsky/build-your-own-react-state-management-library-in-under-40-lines-of-code-with-typescript-support-hji)



```tsx
const snapshot = useSyncExternalStore(subscribe, getSnapshot, getServerSnapshot?)
```

- 3개의 props 받음
	- `subscribe`
	- `getSnabshot`
	- `getServerSnapshot?`
- 반환값은 `snabshot`

### store 예제

```tsx
export type Listener = () => void

function createStore<T> = ({initialState}: {initialState: T}) {
	let subscribers: Listener[] = []
	let state = initialState

	const notifyStateChanged = () => {
		subscribers.forEach((fn) => fn())
	}
		
	return {
		subscribe (fn: Listener) {
			subscribers.push(fn)

			return () => {
				subscribers = subscribers.filter((listener) => listener !== fn)
			}
		}

		getSnabshot () {
			return state
		}

		setState(newState: T) {
			state = newState
			notifyStateChanged()
		}
	}
}
```

```tsx
export function createUseStore<T>(initialState: T) {
	const store = createStore({initialState})
	return () => [useSyncExternalStore(store.subscribe, store.getSnapshot), store.setState] as const
}
```

```tsx
export const useCountStore = createUseStore(0)

...

function Counter() {
	const [count, setCount] = useCountStore()
	
	const increment = () => {
		setCount(count + 1)
	}

	const decrement = () => {
		setCount(count - 1)
	}
}
```