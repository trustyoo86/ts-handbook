# Enum

* 열거형 데이터 타입입니다.
* 데이터 타입을 custom 하게 부여하여 타입을 지정해 줄 수 있습니다.

```typescript
enum Color {Red, Green, Blue}
let c: Color = Color.Green;
```

* 기본적으로 enum은 0부터 시작하여 멤버의 번호를 매기기 시작합니다.
* 멤버중의 하나의 값을 수동으로 설정할 수 있습니다.
* 아래 예제는 0대신 1을 할당하여 변경한 예제입니다.

```typescript
enum Color {Red = 1, Green, Blue}
let c: Color = Color.Green;
```

* 또는, 모든 값을 수동으로 설정해 줄 수 있습니다.

```typescript
enum Color {Red = 1, Green = 2, Blue = 4}
let c: Color = Color.Green;
```

* enum 타입의 또다른 특징은 해당 value를 숫자값에서 다른 데이터 타입으로 변경이 가능하다는 점입니다.

```typescript
enum Color {Red = 1, Green, Blue}
let colorName: string = Color[2];

console.log(colorName); // e
```

