# 변수선언

* `let` `const` 는 javascript에서도 새롭게 나온 개념입니다. \(es2015부터\)
* `const` 의 경우 변수 재할당이 안된다는 점에서 `let` 의 기능을 강화한 것입니다.
* typescript는 javascript의 상위 집합으로써, `let` 과 `const` 를 지원합니다.

#### var 변수 선언

* javascript에서는 전통적으로 변수 선언을 위해 `var` 키워드를 사용했습니다.

```typescript
var a = 10;
```

* function 내에서 변수선언이 가능합니다.

```typescript
function f() {
    var message = "Hello, world!";

    return message;
}
```

* 다른 함수 내에서 동일한 변수에 엑세스 할 수 있습니다.

```typescript
function f() {
    var a = 10;
    return function g() {
        var b = a + 1;
        return b;
    }
}

var g = f();
g(); // returns '11'
```

*  `g` 는 `f` 함수내의 `a` 에 접근할 수 있습니다. `g` 함수가 호출되면,  `f` 의 함수가 한번 실행되면 `a` 변수는 `f` 함수내에 묶이게 됩니다. 이를 통해 `a` 변수에 접근 및 수정이 가능해 집니다.

```typescript
function f() {
    var a = 1;

    a = 2;
    var b = g();
    a = 3;

    return b;

    function g() {
        return a;
    }
}

f(); // returns '2'
```
