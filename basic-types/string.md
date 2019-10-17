# String

* 큰 따옴표 \("\) 혹은 작은 따옴표 \('\) 로 이루어진 text 를 지칭합니다.

```typescript
let color: string = "blue";
color = 'red';
```

* 템플릿 리터럴을 통해 변수를 삽입하여 문자열로 대치할 수 있습니다. 템플릿 리터럴은 백틱\(\`\) 을 사용하여 만들 수 있습니다.
* 변수를 삽입하는 방법은 `${변수}` 형태로 사용할 수 있습니다.

```typescript
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${fullName}.

I'll be ${age + 1} years old next month.`;
```

* 위와 같은 문자열은 아래로 바꿀 수 있습니다.

```typescript
let sentence: string = "Hello, my name is " + fullName + ".\n\n" +
"I'll be " + (age + 1) + " years old next month.";
```

