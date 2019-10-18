# null and undefined

* null 및 undefined는 자체적인 null, undefined 타입을 갖고 있습니다.

```typescript
let u: undefined = undefined;
let n: null = null;
```

* 기본적으로 `null` 및 `undefined`는 다른 데이터타입의 서브타입입니다.
* 이는 즉, null 및 undefined는 number 형태로 지정이 가능하다는 것을 의미합니다.

#### 예외

* `--strictNullChecks` flag를 사용하면, `null` 및 `undefined` 타입은 `any` 타입으로 할당이 가능합니다. \(`undefined` 는 예외로 `void` 형에 할당 가능합니다.\)
* 만약 `string`, `null`, `undefined` 유형을 허용하고 싶다면, union type을 이용하여 `string | null | undefined` 를 명시해주면 됩니다.

> 가능하면 `--strictNullChecks` 를 사용하는 것이 권장됩니다.







