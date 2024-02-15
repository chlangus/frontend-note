## typescript
타입스크립트는 변수의 타입을 직접 지정해주기 때문에 실행을 해보아야 에러를 알수있는 자바스크립트와 달리 컴파일 시점에 에러를 잡아낼 수 있다는 장점이 있다.   
기존 자바스크립트는 에러가 나더라도 프로젝트 규모가 크다면 어디서 잘못된지 알기가 어려운데 타입스크립트를 사용하면 쉽게 파악할 수 있다는 장점이 존재한다.   
그리고 변수의 타입이나 어떤 종류의 데이터가 들어가는지 알기 쉬워 코드의 흐름을 파악하기 좋다.   
<br>

## typescript 동작원리
1. 타입스크립트 소스를 타입스크립트 AST(추상 문법 트리)로 변환
2. 타입 검사기가 AST를 확인
3. 타입스크립트 AST를 자바 스크립트 소스로 변환
4. 자바스크립트 소스를 자바스크립트 AST로 변환
5. AST를 바이트코드로 변환
6. 런타임이 바이트코드를 평가
1 ~ 3은 TSC가수행하며, 4~6은 브라우저, NodeJS, 기타 자바스크립트 엔진 등에서 수행한다. 
<br>

## 타입 정하기
- `let size: number = 100` 이처럼 변수의 뒤에 :number처럼 작성하여 타입 지정
- 기본형 타입: `string`, `number`, `boolean`, `undefined`, `null`
- 배열 타입: `string[]`, `string[][]`
- 튜플 타입: `[string, string]`
- 객체 타입: `{ id: string; name: string; ...}`, property 개수를 알 수 없을때 `{ [id: string]: number; }` 이런 방식으로 사용
- `any` 모든 타입에 지정가능하지만 불가피한 상황이 아니면 타입스크립트 사용하는 이유가 없어지지 않게, 사용하지 않아야 함 
- `{ name: 'son' } as { name: string} `처럼 as를 사용하여 타입을 정해주는것도 가능

## 함수 타입 정하기
- `function func(id: string, quantity?: number): string{}` 이처럼 변수 옆에 :string 이렇게 타입 지정 그리고 ?:를 사용해 값이 없을때도 지정해 줌, return값의 타입은 함수이름과 옆에 :string 이렇게 사용
- 함수 안에 있는 메서드의 타입은 `funcInfunc : (id: string, quantity?: number) => boolean;` => 뒤에 반환값 타입을 지정해줌
-  