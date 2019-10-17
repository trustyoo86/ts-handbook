# Any

* 변수등의 타입을 지정하기 어려울때 선언해줍니다.
* 타입 변경이 가능한 콘텐츠 \(예를들면, 3rd party 라이브러리와 같은\) 를 선언할때 사용합니다.
* 이러한 경우 변수의 타입체킹을 opt-out 하고, 컴파일 단계에서 해당 변수의 타입 체킹을 생략합니다.

```typescript
let notSure: any = 4;
notSure = 'maybe a string instead';
notSure = false; // any 타입 선언 변수이므로 해당 내용은 통과됩니다.
```

* `any` 타입은 기존에 작성된 javascript 와 마이그레이션 할때에도 유용하게 쓰일 수 있습니다.

```typescript
let notSure: any = 4;
notSure.ifItExists(); // ifItExists는 runtime 환경에서 실행될 것입니다.
notSure.toFixed(); // toFixed는 number 타입이므로 컴파일됩니다.

let prettySure: Object = 4;
prettySure.toFixed(); // Object타입에서 toFixed는 존재하지 않기 때문에 에러가 발생합니다.
```

* array내 요소들의 타입이 여러가지 일때에도 사용 가능합니다.

```typescript
let list: any[] = [1, true, 'free'];
list[1] = 100;
```



