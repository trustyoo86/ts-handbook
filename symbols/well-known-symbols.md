# Well-known Symbols

* User-defined symbols 외에도 well-known built-in symbols가 있습니다. Built-in symbols는 내부 언어 동작을 나타내는 데 사용됩니다.

`well-known symbols` 목록:

### Symbol.hasInstance
* 생성자 객체가 객체를 생성자의 인스턴스 중 하나로 인식하는지 여부를 결정하는 메소드입니다. `instanceof` 연산자에 의해 호출됩니다.

### Symbol.isConcatSpreadable
* `Array.prototype.concat`에 의해 객체가 배열 요소로 병합되어야 함을 나타내는 Boolean 값입니다.

### Symbol.iterator
* 객체의 기본 반복자를 반환하는 메서드입니다. `for-of`에 의해 호출됩니다.

### Symbol.match
* 정규식을 문자열과 비교하는 정규식 메소드입니다. `String.prototype.match` 메소드에 의해 호출됩니다.

### Symbol.replace
* 일치하는 하위 문자열을 대체하는 정규식 메소드입니다. `String.prototype.replace` 메소드에 의해 호출됩니다.

### Symbol.search
* 정규식과 일치하는 문자열 내에서 인덱스를 반환하는 정규식 메서드입니다. `String.prototype.search` 메소드에 의해 호출됩니다.

### Symbol.species
* 파생 개체를 만드는 데 사용되는 생성자 함수 인 `function-valued` 속성입니다.

### Symbol.split
* 정규식과 일치하는 인덱스에서 문자열을 분할하는 정규식 메서드입니다. `String.prototype.split` 메소드에 의해 호출됩니다.

### Symbol.toPrimitive
* 객체를 해당 primitive 값으로 변환하는 메서드입니다. `ToPrimitive` 추상 연산에 의해 호출됩니다.

### Symbol.toStringTag
* 객체의 기본 문자열 설명 작성에 사용되는 문자열 값입니다. 내장 메소드 `Object.prototype.toString`에 의해 호출됩니다.

### Symbol.unscopables
* 고유 한 속성 이름이 연결된 개체의 'with' 환경 바인딩에서 제외 된 속성 이름 인 개체입니다.
