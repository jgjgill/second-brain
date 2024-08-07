- string literal type이 따로 존재하지 않음
- ex) `'primary' | 'secondary' | string` 인 타입이 존재
	- 예상과 달리 `string`으로 자동완성
	- string literal type이 필요

### string & {}
- 잡기술? 예상대로 타입이 좁혀짐
- TS팀에서도 인지하고 있는 상황 (테스트 코드 존재?)
- 따로 string literal type이 제공되기 전까지는 사용해도 무관
