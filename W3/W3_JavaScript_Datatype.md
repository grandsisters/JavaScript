## JavaScript Data Types

    JavaScript 변수는 숫자, 문자열, 개체 등 다양한 데이터 유형을 보유할 수 있습니다.

    let length = 16;                               // Number
    let lastName = "Johnson";                      // String
    let x = {firstName:"John", lastName:"Doe"};    // Object

---

### 데이터 유형의 개념

프로그래밍에서 데이터 유형은 중요한 개념입니다.

변수에 대해 연산을 수행하려면 유형에 대해 아는 것이 중요합니다.

데이터 유형이 없으면 컴퓨터는 다음을 안전하게 해결할 수 없습니다.

    let x = 16 + "Volvo";

16에 "볼보"를 추가하는 것이 의미가 있습니까? 오류가 발생합니까 아니면 결과가 발생합니까?

JavaScript는 위의 예를 다음과 같이 처리합니다.

    let x = "16" + "Volvo";

숫자와 문자열을 추가할 때 JavaScript는 숫자를 문자열로 처리합니다.

<br />

JavaScript는 표현식을 왼쪽에서 오른쪽으로 평가합니다. 다른 시퀀스는 다른 결과를 생성할 수 있습니다.

    예시1
    자바스크립트:
    let x = 16 + 4 + "Volvo";

    결과:
    20Volvo


    예시2
    자바스크립트:
    let x = "Volvo" + 16 + 4;

    결과:
    Volvo164

첫 번째 예에서 JavaScript는 "Volvo"에 도달할 때까지 16과 4를 숫자로 취급합니다.

두 번째 예에서는 첫 번째 피연산자가 문자열이므로 모든 피연산자가 문자열로 처리됩니다.

---

### JavaScript 유형은 동적입니다.

JavaScript에는 동적 유형이 있습니다. 이는 동일한 변수를 사용하여 다른 데이터 유형을 보유할 수 있음을 의미합니다.

    예시
    let x; // Now x is undefined
    x = 5; // Now x is a Number
    x = "John"; // Now x is a String

---

### 자바스크립트 문자열

문자열(또는 텍스트 문자열)은 "John Doe"와 같은 일련의 문자입니다.

문자열은 따옴표로 작성됩니다. 작은따옴표나 큰따옴표를 사용할 수 있습니다.

    예시
    let carName1 = "Volvo XC60"; // Using double quotes
    let carName2 = 'Volvo XC60'; // Using single quotes

문자열을 둘러싼 따옴표와 일치하지 않는 한 문자열 안에 따옴표를 사용할 수 있습니다.

    예시
    let answer1 = "It's alright"; // Single quote inside double quotes
    let answer2 = "He is called 'Johnny'"; // Single quotes inside double quotes
    let answer3 = 'He is called "Johnny"'; // Double quotes inside single quotes

---

### 자바스크립트 숫자

JavaScript에는 한 가지 유형의 숫자만 있습니다.

숫자는 소수를 포함하거나 포함하지 않고 쓸 수 있습니다.

    예시
    let x1 = 34.00; // Written with decimals
    let x2 = 34; // Written without decimals

매우 크거나 작은 숫자는 과학적(지수) 표기법으로 작성할 수 있습니다.

    예시
    let y = 123e5; // 12300000
    let z = 123e-5; // 0.00123

---

### 자바스크립트 불린

불린 값은 true또는 false 2개만 가질 수 있습니다 .

    예시
    let x = 5;
    let y = 5;
    let z = 6;
    (x == y) // Returns true
    (x == z) // Returns false

불린은 종종 조건부 테스트에 사용됩니다.

---

### 자바스크립트 배열

JavaScript 배열은 대괄호로 작성됩니다.

배열 항목은 쉼표로 구분됩니다.

다음 코드는 cars3개의 항목(자동차 이름)을 포함하는 이라는 배열을 선언(생성)합니다 .

    예시
    const cars = ["Saab", "Volvo", "BMW"];

배열 인덱스는 0부터 시작하므로 첫 번째 항목은 [0], 두 번째 항목은 [1] 입니다.

---

### 자바스크립트 객체

JavaScript 객체는 중괄호로 작성됩니다 {}.

개체 속성은 쉼표로 구분된 이름:값 쌍으로 작성됩니다.

    예시
    const person = {firstName:"John", lastName:"Doe", age:50, eyeColor:"blue"};

위의 예에서 객체(사람)에는 4가지 속성이 있습니다: firstName, lastName, age 및 eyeColor.

---

### typeof 연산자

JavaScript typeof연산자를 사용하여 JavaScript 변수의 유형을 찾을 수 있습니다 .

typeof연산자 변수 또는 표현식의 타입을 반환

    예시
    typeof "" // Returns "string"
    typeof "John" // Returns "string"
    typeof "John Doe" // Returns "string"

    예시
    typeof 0 // Returns "number"
    typeof 314 // Returns "number"
    typeof 3.14 // Returns "number"
    typeof (3) // Returns "number"
    typeof (3 + 4) // Returns "number"

---

### Undefined

JavaScript에서 값이 없는 변수에는 값이 undefined있습니다. 유형도 undefined입니다.

    예시
    let car; // Value is undefined, type is undefined

값을 undefined로 설정하여 모든 변수를 비울 수 있습니다 undefined. 유형도 입니다.

    예시
    car = undefined; // Value is undefined, type is undefined

---

### Empty Values

빈 값은 undefined와 관련이 없습니다 .

빈 문자열에는 유효한 값과 유형이 모두 있습니다.

    예시
    let car = ""; // The value is "", the typeof is "string"
