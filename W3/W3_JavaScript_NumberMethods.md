## JavaScript Number Methods

---

### 숫자 메서드 및 속성

기본 값(예: 3.14 또는 2014)은 속성과 메서드를 가질 수 없습니다(객체가 아니기 때문에).

그러나 JavaScript에서는 메서드와 속성을 실행할 때 JavaScript가 기본 값을 객체로 취급하기 때문에 메서드와 속성을 기본 값에도 사용할 수 있습니다.

---

### toString() 메서드

이 toString()메서드는 숫자를 문자열로 반환합니다.

모든 숫자 방법은 모든 유형의 숫자(리터럴, 변수 또는 표현식)에 사용할 수 있습니다.

    예시
    let x = 123;
    x.toString(); // returns 123 from variable x
    (123).toString(); // returns 123 from literal 123
    (100 + 23).toString(); // returns 123 from expression 100 + 23

---

### toExponential() 메서드

toExponential() 숫자가 반올림되고 지수 표기법을 사용하여 작성된 문자열을 반환합니다.

매개변수는 소수점 뒤의 문자 수를 정의합니다.

    예시
    let x = 9.656;
    x.toExponential(2); // returns 9.66e+0
    x.toExponential(4); // returns 9.6560e+0
    x.toExponential(6); // returns 9.656000e+0

매개변수는 선택 사항입니다. 지정하지 않으면 JavaScript가 숫자를 반올림하지 않습니다.

---

### toFixed() 메서드

toFixed() 지정된 소수 자릿수로 작성된 숫자와 함께 문자열을 반환합니다.

    예시
    let x = 9.656;
    x.toFixed(0); // returns 10
    x.toFixed(2); // returns 9.66
    x.toFixed(4); // returns 9.6560
    x.toFixed(6); // returns 9.656000

---

### toPrecision() 메서드

toPrecision() 지정된 길이로 작성된 숫자와 함께 문자열을 반환합니다.

    예시
    let x = 9.656;
    x.toPrecision(); // returns 9.656
    x.toPrecision(2); // returns 9.7
    x.toPrecision(4); // returns 9.656
    x.toPrecision(6); // returns 9.65600

---

### valueOf() 메서드

valueOf() 숫자를 숫자로 반환합니다.

    예시
    let x = 123;
    x.valueOf(); // returns 123 from variable x
    (123).valueOf(); // returns 123 from literal 123
    (100 + 23).valueOf(); // returns 123 from expression 100 + 23

JavaScript에서 숫자는 기본 값(typeof = number) 또는 객체(typeof = 객체)일 수 있습니다.

이 valueOf()메서드는 JavaScript에서 내부적으로 Number 객체를 기본 값으로 변환하는 데 사용됩니다.

코드에서 사용할 이유가 없습니다.

모든 JavaScript 데이터 유형에는 valueOf()및 toString()메소드가 있습니다.

---

### 변수를 숫자로 변환

변수를 숫자로 변환하는 데 사용할 수 있는 3가지 JavaScript 메서드가 있습니다.

- Number()방법
- parseInt()방법
- parseFloat()방법

이러한 메서드는 숫자 메서드가 아니라 전역 JavaScript 메서드입니다.

---

### 전역 JavaScript 메서드

JavaScript 전역 메서드는 모든 JavaScript 데이터 유형에 사용할 수 있습니다.

숫자로 작업할 때 가장 관련성이 높은 방법은 다음과 같습니다.

| Method       | Description                                             |
| ------------ | ------------------------------------------------------- |
| Number()     | Returns a number, converted from its argument.          |
| parseFloat() | Parses its argument and returns a floating point number |
| parseInt()   | Parses its argument and returns an integer              |

---

### Number() 메서드

Number() JavaScript 변수를 숫자로 변환하는 데 사용할 수 있습니다.

    예시
    Number(true); // returns 1
    Number(false); // returns 0
    Number("10"); // returns 10
    Number(" 10"); // returns 10
    Number("10 "); // returns 10
    Number(" 10 "); // returns 10
    Number("10.33"); // returns 10.33
    Number("10,33"); // returns NaN
    Number("10 33"); // returns NaN
    Number("John"); // returns NaN

숫자를 변환할 수 없는 경우 NaN(Not a Number)가 반환됩니다.

---

### 날짜에 사용되는 Number() 메서드

Number() 날짜를 숫자로 변환할 수도 있습니다.

    예시
    // This returns 0:
    Number(new Date("1970-01-01"))

이 Number()메서드는 1.1.1970 이후의 밀리초 수를 반환합니다.

1970-01-02와 1970-01-01 사이의 밀리초 수는 86400000입니다.

    예시1
    // This returns 86400000
    Number(new Date("1970-01-02"))

    예시2
    // This returns 1506729600000
    Number(new Date("2017-09-30"))

---

### parseInt() 메서드

parseInt()문자열을 구문 분석하고 정수를 반환합니다. 공백이 허용되지만 첫 번째 숫자만 반환됩니다.

    예시
    parseInt("-10"); // returns -10
    parseInt("-10.33"); // returns -10
    parseInt("10"); // returns 10
    parseInt("10.33"); // returns 10
    parseInt("10 20 30"); // returns 10
    parseInt("10 years"); // returns 10
    parseInt("years 10"); // returns NaN

숫자를 변환할 수 없는 경우 NaN(Not a Number)가 반환됩니다.

---

### parseFloat() 메서드

parseFloat()문자열을 구문 분석하고 숫자를 반환합니다. 공백이 허용되지만 첫 번째 숫자만 반환됩니다.

    예시
    parseFloat("10"); // returns 10
    parseFloat("10.33"); // returns 10.33
    parseFloat("10 20 30"); // returns 10
    parseFloat("10 years"); // returns 10
    parseFloat("years 10"); // returns NaN

숫자를 변환할 수 없는 경우 NaN(Not a Number)가 반환됩니다.

---

### 숫자 속성

| Property          | Description                                         |
| ----------------- | --------------------------------------------------- |
| MAX_VALUE Returns | the largest number possible in JavaScript           |
| MIN_VALUE Returns | the smallest number possible in JavaScript          |
| POSITIVE_INFINITY | Represents infinity (returned on overflow)          |
| NEGATIVE_INFINITY | Represents negative infinity (returned on overflow) |
| NaN               | Represents a "Not-a-Number" value                   |

---

### 자바스크립트 MIN_VALUE 및 MAX_VALUE

MAX_VALUE JavaScript에서 가능한 가장 큰 수를 반환합니다.

    예시
    let x = Number.MAX_VALUE;

MIN_VALUE JavaScript에서 가능한 가장 낮은 숫자를 반환합니다.

    예시
    let x = Number.MIN_VALUE;

---

### 자바스크립트 POSITIVE_INFINITY

    예시
    let x = Number.POSITIVE_INFINITY;

POSITIVE_INFINITY 오버플로 시 반환됩니다.

    예시
    let x = 1 / 0;

---

### 자바스크립트 NEGATIVE_INFINITY

    예시
    let x = Number.NEGATIVE_INFINITY;

NEGATIVE_INFINITY 오버플로 시 반환됩니다.

    예시
    let x = -1 / 0;

---

### JavaScript NaN - Not a Number

    예시
    let x = Number.NaN;

NaN 숫자가 법적 숫자가 아님을 나타내는 JavaScript 예약어입니다.

숫자가 아닌 문자열로 산술을 수행하려고 하면 (숫자가 NaN아님)이 발생합니다.

    예시
    let x = 100 / "Apple"; // x will be NaN (Not a Number)

---

### 숫자 속성은 변수에 사용할 수 없습니다.

숫자 속성은 자바스크립트의 숫자 개체 래퍼인 Number에 속합니다.

이러한 속성은 Number.MAX_VALUE로만 액세스할 수 있습니다 .

myNumber 가 변수, 표현식 또는 값인 myNumber.MAX_VALUE를 사용하면 undefined을 반환합니다 .

    예시
    let x = 6;
    x.MAX_VALUE // returns undefined
