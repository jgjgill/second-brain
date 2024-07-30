## 핵심
- `e.target`: 이벤트가 발생한 실제 요소
	- 이벤트가 트리거된 가장 깊은 요소
	- 이벤트가 버블링되면서 상위 요소로 전파될 때, `e.target`은 변하지 않고 이벤트가 발생한 원래 요소 지정
- `e.currentTarget` : 이벤트 핸들러가붙어 있는 요소
	- 이벤트가 처리되고 있는 요소
	- 이벤트가 버블링될 때 이벤트가 도달하는 각 요소 지정

### 예제 코드

```html
<div id="parent"> <button id="child">Click me</button> </div>
```

```javascript
document.getElementById('parent').addEventListener('click', function(e) { console.log('target:', e.target); console.log('currentTarget:', e.currentTarget); }); document.getElementById('child').addEventListener('click', function(e) { console.log('target:', e.target); console.log('currentTarget:', e.currentTarget); });
```

- `#child`의 이벤트 핸들러 출력
	- `target`: `<button id="child">Click me</button>`
	- `currentTarget`: `<button id="child">Click me</button>`
- `#parent`의 이벤트 핸들러 출력 (이벤트 버블링으로 인해 실행됨)
    - `target`: `<button id="child">Click me</button>`
    - `currentTarget`: `<div id="parent"></div>`

