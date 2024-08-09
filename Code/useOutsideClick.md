## Code

```ts
const useOutsideClick = (callback: () => void) => {
	const ref = useRef<HTMLDivElement>(null);
	
	useEffect(() => {
		const handleClickOutside = (event: MouseEvent) => {
			if (ref.current && !ref.current.contains(event.target as Node)) {
				callback();
			}
		};
	
		document.addEventListener('mousedown', handleClickOutside);
	
		return () => {
			document.removeEventListener('mousedown', handleClickOutside);
		};
	}, [ref, callback]);

	return ref;

};

export default useOutsideClick;
```

### Example

```tsx
import React, { useState } from 'react';
import useOutsideClick from './useOutsideClick';

const ExampleComponent = () => {
	const [isOpen, setIsOpen] = useState(false);
	const ref = useOutsideClick(() => {
		setIsOpen(false);
	});
	
	return (
		<div>
			<button onClick={() => setIsOpen(!isOpen)}>Toggle</button>
			{isOpen && (
				<div ref={ref}>
					Click outside this box to close it.
				</div>
			)}
		</div>
	);
};

export default ExampleComponent;
```