# let 변수

* `var` 변수의 `function-coping` 으로 인해서, `let` 키워드를 사용하면, scope 문제를 해결할 수 있습니다.

```typescript
let hello = "hello";
```

#### block-scoping

* `let` 변수할당을 사용하게 되면, 정의 환경에서의 스코핑 \(lexical-scoping\) 또는 block-scoping 을 사용하게 됩니다.
* `var` 변수가 선언되어 function의 스코핑을 가지는 것과 달리, block scoped 변수는 `for` loop 바깥에서 사용할 수 없게 됩니다.

```typescript
function f(input: boolean) {
    let a = 100;

    if (input) {
        // Still okay to reference 'a'
        let b = a + 1;
        return b;
    }

    // Error: 'b' doesn't exist here
    return b;
}
```

* 예제를 보면, `a` 변수와 `b` 변수 두가지가 선언되어 있습니다.
* `a` 변수의 경우 `f` 함수 내로 한정되어 있으나, `b` 함수의 경우 `if` 블록에 갇혀있기 때문에, 사용할 수 없습니다.
* 이러한 변수 선언은 `try-catch` 문에도 동일하게 적용됩니다.

```typescript
try {
    throw "oh no!";
}
catch (e) {
    console.log("Oh well.");
}

// Error: 'e' doesn't exist here
console.log(e);
```

* block-scoped 변수의 또다른 특징은 선언되기 전에 사용이 불가능한 것입니다.
* typescript의 경우 해당 내용을 error로 알려줍니다.

```typescript
a++; // illegal to use 'a' before it's declared;
let a;
```

* block 범위 변수 \(let\)을 선언하기 전 캡쳐링이 가능합니다.
* 선언하기전에 해당 함수를 호출하는것은 문제가 있습니다. es2015를 기준으로 하는 경우 해당 런타임은 오류를 발생시키나, typescript는 이를 허용하며, 오류로 보고하지 않습니다.

```typescript
function foo() {
    // a변수를 캡쳐링 합니다.
    return a;
}

// a가 선언되기 전에 foo를 선언하므로, 해당 내용은 문제가 있습니다.
// 런타임시에 해당 에러를 발생시킬 것입니다.
foo();

let a;
```

#### 변수 재할당

`var` 변수를 사용하는 경우, 이는 몇번이나 재할당을 하더라도 문제가 되지 않습니다.

```typescript
function f(x) {
    var x;
    var x;

    if (true) {
        var x;
    }
}
```

* f 함수에 선언된 `var x` 는 if  block 내의 `var x` 와 동일합니다. 이는 종종 에러를 발생시키는 요인입니다.
* `let` 변수는 이런 경우 에러를 발생시킵니다.

```typescript
let x = 10;
let x = 20; // error: 같은 scope에서 x를 재할당 할 수 없습니다.
```

* block 범위의 변수를 함수 범위의 변수로 선언할 수 없습니다. block 범위의 변수는 다른 block 내에서 선언하면 됩니다.

```typescript
function f(condition, x) {
    if (condition) {
        let x = 100;
        return x;
    }

    return x;
}

f(false, 0); // returns '0'
f(true, 0);  // returns '100'
```



