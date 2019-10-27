# introduction

Typescript의 핵심 원칙 중 하나는 타입 검사가 값의 형태에 중점을 둔다는 것입니다. 이것을 `duck typing` 또는 `구조적 서브 타이핑` 이라고도 합니다.

Typescript에서 `인터페이스(interface)`는 이러한 타입의 이름을 지정하는 역할을 하며, 프로젝트 외부의 코드와 계약 뿐만 아니라 이를 정의하는 강력한 방법중 하나입니다.

## Our First interface

가장 심플한 방법은 어떻게 예시에서 인터페이스가 시작되는지를 알아보는 것입니다.

```typescript
function printLabel(labeledObj: { label: string }) {
    console.log(labeledObj.label);
}

let myObj = {size: 10, label: "Size 10 Object"};
printLabel(myObj);
```

유형 검사기는 `printLabel` function이 호출될때 타입을 체크합니다. `printLabel`함수에는 참조변수중 오브젝트에 `string` 유형의 `lbael`이라는 특성이 있어야 하는 단일 매개변수가 있습니다. 참조 객체는 실제로 이것보다 더 많은 속성을 가지고 있으나, 컴파일러는 최소한 필요한 값이 존재하고 필요한 유형과 일치하는지 확인합니다.
몇몇의 케이스에는 Typescript가 관대하지 않은 경우가 있습니다.

동일한 예제를 다시 작성해 보겠습니다. 이번에는 인터페이스를 사용하여 `string` 속성인 `label` 속성이 있어야 한다는 요구사항을 설명합니다.

```typescript
interface LabeledValue {
    label: string;
}

function printLabel(labeledObj: LabeledValue) {
    console.log(labeledObj.label);
}

let myObj = {size: 10, label: "Size 10 Object"};
printLabel(myObj);
```

`LabeledValue` 인터페이스는 이전 예제의 요구사항을 설명하는데 사용할 수 있는 이름입니다. 여전히 문자열 유형인 `label` 이라는 단일 속성이 존재함을 나타냅니다.
`printLabel`에 전달하는 객체가 다른 언어에서와 같이 이 인터페이스를 구현한다고 명시적으로 말할 필요는 없습니다. 여기서 중요한것은 값의 형태입니다. 함수에 전달한 객체가 나열된 요구사항을 충족하면 허용됩니다.

유형 검사기는 이러한 속성이 어떤 종류의 순서대로 나올 필요가 없으며, 인터페이스에 필요한 속성만 있고 필요한 유형이 있어야 합니다.
