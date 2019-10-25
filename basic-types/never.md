# Never

* `never` 타입은 절대로 발생하지 않는 경우에 할당하는 타입입니다.
* 예를들어, 항상 예외를 반환하는 함수식의 경우 절대 다른 변수가 return되지 않습니다.
* `never` 타입의 경우 모든 데이터타입의 서브타입이 될 수 있으나, 모든 유형에 할당하지는 않습니다. 심지어 `any` 타입도 `never` 타입에 할당할 수 없습니다. 오직 `never` 타입 자체에 할당하는것만 가능합니다.

```typescript
// 에러를 발생하는 function의 경우
function error(message: string): never {
    throw new Error(message);
}

// return type이 존재하지 않습니다.
function fail() {
    return error("Something failed");
}

// infinity로 절대 해당 값에 도달하지 않는 경우
function infiniteLoop(): never {
    while (true) {
    }
}
```
