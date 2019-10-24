# void

* `void` 는 `any` 와 정반대 입니다. 어떤 유형도 존재하지 않으며, 일반적으로 값을 `return` 을 통해 반환하지 않는 function에 쓰입니다.

```typescript
function warnUser(): void {
    console.log('This is my warning message');
}
```

* 변수에 `void` 타입이 지정되는 경우 `null` 만 지정하거나 \(--strictNullChecks가 지정되지 않은 경우에 참조 가능합니다.\) 변수를 정의할 수 없으므로, 유용하게 쓰이지는 않습니다.

```typescript
let unusable: void = undefined;
unusable = null;
```
