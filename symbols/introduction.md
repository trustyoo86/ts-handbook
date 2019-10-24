# Introduction

ECMAScript 2015 부터 Symbol은 숫자 및 문자열과 마찬가지로 기본 데이터 유형입니다.

* Symbol 값은 Symbol constructor를 호출하여 생성됩니다.

```typescript
let sym1 = Symbol();

let sym2 = Symbol("key"); // optional string key
```

* Symbol은 불변이고 고유합니다.

```typescript
let sym2 = Symbol("key");
let sym3 = Symbol("key");

sym2 === sym3; // false, symbols are unique
```

* 문자열처럼 Symbol을 객체 속성의 key로 사용할 수 있습니다.

```typescript
const sym = Symbol();

let obj = {
    [sym]: "value"
};

console.log(obj[sym]); // "value"
```

* Symbol을 계산된 속성 선언과 결합하여 객체 속성과 클래스 멤버를 선언할 수도 있습니다.

```typescript
const getClassNameSymbol = Symbol();

class C {
    [getClassNameSymbol](){
       return "C";
    }
}

let c = new C();
let className = c[getClassNameSymbol](); // "C"
```
