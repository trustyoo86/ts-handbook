# Object

* `object` 는 non-premitive 타입으로써, `number`, `string`, `boolean`, `symbol` , `null`, `undefined` 에 해당하지 않는 타입을 의미합니다.
* `object` 타입을 선언하게 되면, API 내에서 `Object.create` 와 같은 내용을 출력합니다.

```typescript
declare function create(o: object | null): void;

create({ prop: 0 }); // OK
create(null); // OK

create(42); // Error
create("string"); // Error
create(false); // Error
create(undefined); // Error
```
