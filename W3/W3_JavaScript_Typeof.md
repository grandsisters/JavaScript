## JavaScript typeof

- JavaScript에는 값을 포함할 수 있는 5가지 다른 데이터 유형이 있습니다.

  - string
  - number
  - boolean
  - object
  - function

- 6가지 유형의 객체가 있습니다.

  - Object
  - Date
  - Array
  - String
  - Number
  - Boolean

- 값을 포함할 수 없는 2가지 데이터 유형:

  - null
  - undefined

---

### typeof 연산자

typeof연산자를 사용하여 JavaScript 변수의 데이터 유형을 찾을 수 있습니다 .

    예시
    typeof "John" // Returns "string"
    typeof 3.14 // Returns "number"
    typeof NaN // Returns "number"
    typeof false // Returns "boolean"
    typeof [1,2,3,4] // Returns "object"
    typeof {name:'John', age:34} // Returns "object"
    typeof new Date() // Returns "object"
    typeof function () {} // Returns "function"
    typeof myCar // Returns "undefined" *
    typeof null // Returns "object"

다음 사항을 준수하십시오.

- NaN의 데이터 유형은 숫자입니다.
- 배열의 데이터 유형은 객체입니다.
- 날짜의 데이터 유형은 객체입니다.
- null의 데이터 유형은 객체입니다.
- undefined 변수의 데이터 유형이 undefined
- 값이 할당되지 않은 변수의 데이터 유형도 undefined

typeof는 JavaScript 객체가 배열(또는 날짜)인지 확인하는 데 사용할 수 없습니다 .

---

### 원시 데이터

기본 데이터 값은 추가 속성 및 메서드가 없는 단일 단순 데이터 값입니다.

typeof운영자는 이러한 원시적 유형 중 하나를 반환 할 수 있습니다 :

- string
- number
- boolean
- undefined

<br />

    예시
    typeof "John" // Returns "string"
    typeof 3.14 // Returns "number"
    typeof true // Returns "boolean"
    typeof false // Returns "boolean"
    typeof x // Returns "undefined" (if x has no value)

---

### 복잡한 데이터

typeof운영자는이 개 복잡한 유형 중 하나를 반환 할 수 있습니다 :

- function
- object

typeof객체, 배열, 널 (null)에 대한 운영자 반환 "개체".

typeof연산자는 함수에 대해 "개체"를 반환하지 않습니다.

    예시
    typeof {name:'John', age:34} // Returns "object"
    typeof [1,2,3,4] // Returns "object" (not "array", see note below)
    typeof null // Returns "object"
    typeof function myFunc(){} // Returns "function"

typeof운영자 반환 " object때문에 자바 스크립트 배열의 배열은"개체입니다.

---

### typeof의 데이터 유형

typeof연산자 변수 아니다. 운영자입니다. 연산자( + - \* / )에는 데이터 유형이 없습니다.

그러나 typeof연산자는 항상 문자열 (피연산자 유형 포함)을 반환합니다 .

---

### 생성자 속성

constructor속성은 모든 자바 스크립트 변수의 생성자 함수를 반환합니다.

    예시
    "John".constructor // Returns function String() {[native code]}
    (3.14).constructor // Returns function Number() {[native code]}
    false.constructor // Returns function Boolean() {[native code]}
    [1,2,3,4].constructor // Returns function Array() {[native code]}
    {name:'John',age:34}.constructor // Returns function Object() {[native code]}
    new Date().constructor // Returns function Date() {[native code]}
    function () {}.constructor // Returns function Function(){[native code]}

생성자 속성을 확인하여 객체가 Array ("배열"이라는 단어를 포함) 다음과 같은지 확인할 수 있습니다 .

    예시
    function isArray(myArray) {
    return myArray.constructor.toString().indexOf("Array") > -1;
    }

또는 더 간단하게 객체가 Array 함수 인지 확인할 수 있습니다 .

    예시
    function isArray(myArray) {
    return myArray.constructor === Array;
    }

생성자 속성을 확인하여 객체가 a Date("Date"라는 단어 포함) 인지 확인할 수 있습니다 .

    예시
    function isDate(myDate) {
    return myDate.constructor.toString().indexOf("Date") > -1;
    }

또는 더 간단하게 객체가 Date 함수 인지 확인할 수 있습니다 .

    예시
    function isDate(myDate) {
    return myDate.constructor === Date;
    }

---

### Undefined

JavaScript에서 값이 없는 변수에는 값이 undefined있습니다. 유형도 undefined입니다.

    예시
    let car; // Value is undefined, type is undefined

값을 로 설정하여 모든 변수를 비울 수 있습니다 undefined. 유형도 입니다 undefined.

    예시
    car = undefined; // Value is undefined, type is undefined

---

### Empty Values

Empty Values는 undefined와 관련이 없습니다 .

Empty Values 문자열에는 유효한 값과 유형이 모두 있습니다.

    예시
    let car = ""; // The value is "", the typeof is "string"

---

### Null

JavaScript null에서 "아무것도 아닌"입니다. 존재하지 않는 존재라고 봐야 합니다.

불행히도 JavaScript에서 null의 데이터 유형은 객체입니다.

typeof null객체인 JavaScript의 버그라고 생각할 수 있습니다 . 그것은 null이여야 합니다.

다음과 null같이 설정하여 개체를 비울 수 있습니다 .

    예시
    let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
    person = null; // Now value is null, but type is still an object

다음과 undefined같이 설정하여 개체를 비울 수도 있습니다 .

    예시
    let person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};
    person = undefined; // Now both value and type is undefined

---

### Difference Between Undefined and Null

undefined과 null는 값이 동일하지만 타입은 상이하다 :

    typeof undefined           // undefined
    typeof null                // object

    null === undefined         // false
    null == undefined          // true
