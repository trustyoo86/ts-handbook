# Scoping rules

* `var` 변수선언시의 scope rule은 다른 언어와 상이합니다. 다음 예제를 보시겠습니다.

```typescript
function f(shouldInitialize: boolean) {
    if (shouldInitialize) {
        var x = 10;
    }

    return x;
}

f(true);  // returns '10'
f(false); // returns 'undefined'
```

* 위의 예제에서, `x` 는 `if` 블록 안에 선언되었지만, 여전히 if block 외에서 엑세스가 가능합니다.
* `var` 변수는 함수단위의 스코프를 가지고 있으므로, block 바깥의 함수, 모듈, 네임스페이스, 전역 스코프 어디서나 참조가 가능하기 때문입니다.
* 이를 `var-scoping` 혹은 `function-scoping` 이라고 불립니다.
* 참조변수도 scope를 가지고 있습니다.

```typescript
function sumMatrix(matrix: number[][]) {
    var sum = 0;
    for (var i = 0; i < matrix.length; i++) {
        var currentRow = matrix[i];
        for (var i = 0; i < currentRow.length; i++) {
            sum += currentRow[i];
        }
    }

    return sum;
}
```

* 위의 예제의 경우, 실수로 변수 `i` 에 대한 스코핑을 덮어쓰는 경우가 발생합니다. `i` 변수는 같은 함수내의 scope를 가지고 있기 때문입니다.

#### 변수 캡쳐링

```typescript
for (var i = 0; i < 10; i++) {
    setTimeout(function () { console.log(i); }, 100 * i);
}
```

* `setTimeout` 은 특정 밀리세컨드 이후에 실행됩니다.
* 결과를 보겠습니다.

```text
10
10
10
10
10
10
10
10
10
10
```

* 기대했던 결과는 다음과 같을 것입니다.

```text
0
1
2
3
4
5
6
7
8
9
```

* `setTimeout` 내에서의 함수 표현식은 `i` 변수와 동일한 함수 스코프를 가지고 있습니다.
* `setTimeout` 함수는 몇 밀리세컨드 후에 실행되나, 이는 `for` loop가 끝난 이후 실행됩니다.
* 이로인해서 `for` loop가 끝난 상태에서, `i` 변수의 value는 10이 됩니다.
* 따라서, 모든 함수에서 `10` 이 출력되는 것입니다.

```typescript
for (var i = 0; i < 10; i++) {
    // capture the current state of 'i'
    // by invoking a function with its current value
    (function(i) {
        setTimeout(function() { console.log(i); }, 100 * i);
    })(i);
}
```

* 자주 사용되는 방법중 하나입니다.
* 즉시 실행 함수를 통해 `i` 변수를 또다른 스코프에 할당하여, 해당 문제를 해결합니다.



