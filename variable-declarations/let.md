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



