# Array

* javascript에서와 같이 배열로 사용할 수 있습니다.
* Array 타입의 선언은 두가지 방법중 하나를 택해서 사용 가능합니다.
* 첫번째 방법: Array안의 요소들의 타입을 이용하여 선언 가능합니다.

```typescript
let list: number[] = [1, 2, 3];
```

* 두번째 방법: generic 타입을 이용하여 Array 타입을 선언해줄 수 있습니다.

```typescript
let list: Array<number> = [1, 2, 3];
```
