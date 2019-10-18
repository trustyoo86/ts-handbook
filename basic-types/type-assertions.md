# Type assertions

* 때때로, typescript에서 컴파일 하는 내용보다 더 많은 변수에 대한 타입을 예상할 수 있는 경우가 있을 수 있습니다. 일반적으로는 구성한 변수의 타입이 더 구체적으로 정의될 수 있을때입니다.
* `type assertion` 은 컴파일러에게 "내가 어떤것을 할지 에 대한걸 안다는걸 믿어줘" 라고 명시해 주는 것과 같습니다. 다른 언어에서 타입 캐스팅 하는 것과 같은 의미지만, 데이터에 대한 특별한 체킹이나 구조를 조정하지는 않습니다.
* 런타임에 영향을 미치지 않으며, 순수하게 컴파일러가 사용되는 문법입니다.
* 개발자가 특별히 해당 data에 대한 타입을 체킹해야 하는 경우 유용합니다.

```typescript
let someValue: any = "this is a string";

let strLength: number = (<string>someValue).length;
```

* 다른 방법으로 `as` 키워드를 사용할 수 있습니다.

```typescript
let someValue: any = "this is a string";

let strLength: number = (someValue as string).length;
```

* `jsx` 문법을 사용하는 경우 `as` syntax만 사용 가능합니다.

