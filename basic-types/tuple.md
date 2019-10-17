# Tuple

* 튜플 유형의 경우 유형을 먼저 선언 후, 해당 type에 해당하는 변수만 바인딩 할 수 있습니다.

```typescript
// string, number형태의 배열 선언
let x: [string, number];
// 초기화
x = ["hello", 10]; // 정상 작동함
// 에러의 경우
x = [10, "hello"]; // 에러 발
```

* 해당 요소에 접근할때도, 올바른 타입에 대한 function을 사용해야 합니다.

```typescript
console.log(x[0].substring(1)); // 정상 작동
console.log(x[1].substring(1)); // 에러를 반환합니다. number 타입에는 substring이 동작할 수 없습니다.
```

* 위의 예제에 두번째 이후의 원소에 직접할당도 에러를 반환합니다.

```typescript
// 에러를 반환합니다. 3번째 원소는 [string, number] array에 타입이 지정되어 있지 않습니다.
x[3] = "world";
// 에러를 반환합니다. 5번째 원소는 [string, number] array에 포함되어 있지 않습니다.
console.log(x[5].toString());
```

