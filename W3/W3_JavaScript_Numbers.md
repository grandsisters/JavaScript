## JavaScript Numbers

JavaScript에는 한 가지 유형의 숫자만 있습니다. 숫자는 소수를 포함하거나 포함하지 않고 쓸 수 있습니다.

    예시
    let x = 3.14; // A number with decimals
    let y = 3; // A number without decimals

매우 크거나 작은 숫자는 과학적(지수) 표기법으로 작성할 수 있습니다.

예시
let x = 123e5; // 12300000
let y = 123e-5; // 0.00123

---

### JavaScript 숫자는 항상 64비트 부동 소수점입니다.

다른 많은 프로그래밍 언어와 달리 JavaScript는 정수, short, long, 부동 소수점 등과 같은 다양한 유형의 숫자를 정의하지 않습니다.

JavaScript 숫자는 국제 IEEE 754 표준에 따라 항상 배정밀도 부동 소수점 숫자로 저장됩니다.

이 형식은 64비트로 숫자를 저장합니다. 여기서 숫자(분수)는 비트 0~51, 지수는 비트 52~62, 부호는 비트 63에 저장됩니다.

| Value (aka Fraction/Mantissa) | Exponent          | Sign       |
| ----------------------------- | ----------------- | ---------- |
| 52 bits (0 - 51)              | 11 bits (52 - 62) | 1 bit (63) |

---

### 정도

정수(마침표 또는 지수 표기법이 없는 숫자)는 최대 15자리까지 정확합니다.

    예시
    let x = 999999999999999; // x will be 999999999999999
    let y = 9999999999999999; // y will be 10000000000000000

최대 소수 자릿수는 17이지만 부동 소수점 산술이 항상 100% 정확한 것은 아닙니다.

    예시
    let x = 0.2 + 0.1; // x will be 0.30000000000000004

위의 문제를 해결하려면 곱셈과 나눗셈이 도움이 됩니다.

    예시
    let x = (0.2 _ 10 + 0.1 _ 10) / 10; // x will be 0.3

---

### 숫자와 문자열 추가하기

경고 !!

JavaScript는 더하기와 연결 모두에 + 연산자를 사용합니다.

숫자가 추가됩니다. 문자열이 연결됩니다.

두 개의 숫자를 더하면 결과는 숫자가 됩니다.

    예시
    let x = 10;
    let y = 20;
    let z = x + y; // z will be 30 (a number)

두 개의 문자열을 추가하면 결과는 문자열 연결이 됩니다.

    예시
    let x = "10";
    let y = "20";
    let z = x + y; // z will be 1020 (a string)

숫자와 문자열을 추가하면 결과는 문자열 연결이 됩니다.

    예시
    let x = 10;
    let y = "20";
    let z = x + y; // z will be 1020 (a string)

문자열과 숫자를 추가하면 결과는 문자열 연결이 됩니다.

    예시
    let x = "10";
    let y = 20;
    let z = x + y; // z will be 1020 (a string)

일반적인 실수는 이 결과가 30일 것으로 예상하는 것입니다.

    예시
    let x = 10;
    let y = 20;
    let z = "The result is: " + x + y;

일반적인 실수는 이 결과가 102030일 것으로 예상하는 것입니다.

    예시
    let x = 10;
    let y = 20;
    let z = "30";
    let result = x + y + z;

JavaScript 인터프리터는 왼쪽에서 오른쪽으로 작동합니다.

x와 y가 모두 숫자이기 때문에 처음 10 + 20이 추가됩니다.

그런 다음 z가 문자열이기 때문에 30 + "30"이 연결됩니다.

---

### 숫자 문자열

JavaScript 문자열에는 숫자 내용이 포함될 수 있습니다.

    let x = 100; // x is a number

    let y = "100"; // y is a string

JavaScript는 모든 숫자 연산에서 문자열을 숫자로 변환하려고 시도합니다.

이것은 작동합니다:

    let x = "100";
    let y = "10";
    let z = x / y; // z will be 10

이것은 또한 작동합니다:

    let x = "100";
    let y = "10";
    let z = x \* y; // z will be 1000

그리고 이것은 작동합니다:

    let x = "100";
    let y = "10";
    let z = x - y; // z will be 90

그러나 이것은 작동하지 않습니다:

    let x = "100";
    let y = "10";
    let z = x + y; // z will not be 110 (It will be 10010)

마지막 예제에서 JavaScript는 + 연산자를 사용하여 문자열을 연결합니다.

---

### NaN - Not a Number

NaN 숫자가 법적 숫자가 아님을 나타내는 JavaScript 예약어입니다.

숫자가 아닌 문자열로 산술을 수행하려고 하면 (숫자가 NaN아님)이 발생합니다.

    예시
    let x = 100 / "Apple"; // x will be NaN (Not a Number)

그러나 문자열에 숫자 값이 포함된 경우 결과는 숫자가 됩니다.

    예시
    let x = 100 / "10"; // x will be 10

전역 JavaScript 함수 isNaN() 를 사용하여 값이 숫자가 아닌지 확인할 수 있습니다.

    예시
    let x = 100 / "Apple";
    isNaN(x); // returns true because x is Not a Number

당신이 사용하는 경우 NaN 수학 연산의 결과도있을 것입니다:

    예시
    let x = NaN;
    let y = 5;
    let z = x + y; // z will be NaN

또는 결과가 연결일 수 있습니다.

    예시
    let x = NaN;
    let y = "5";
    let z = x + y; // z will be NaN5

NaN숫자: typeof NaN반환 number:

    예시
    typeof NaN; // returns "number"

---

### 무한대

Infinity(또는 -Infinity)은 가능한 가장 큰 수 이외의 수를 계산할 경우 JavaScript가 반환하는 값입니다.

    예시
    let myNumber = 2;
    while (myNumber != Infinity) { // Execute until Infinity
    myNumber = myNumber \* myNumber;
    }

0(영)으로 나누기는 다음을 생성합니다 Infinity.

    예시
    let x = 2 / 0; // x will be Infinity
    let y = -2 / 0; // y will be -Infinity

Infinity는 숫자입니다: 를 typeof Infinity반환합니다 number.

    예시
    typeof Infinity; // returns "number"

---

### 16진수

JavaScript는 숫자 상수 앞에 0x가 오면 16진수로 해석합니다.

    예시
    let x = 0xFF; // x will be 255

앞에 0이 있는 숫자를 쓰지 마십시오(예: 07).
일부 JavaScript 버전은 선행 0으로 작성된 숫자를 8진수로 해석합니다.

기본적으로 JavaScript는 숫자를 10 진수 로 표시합니다 .

하지만 당신은 사용할 수 있습니다 toString()에서 출력 번호에 방법을 기본 2 에 베이스 (36) .

16진수는 16 진수입니다 . 10진수는 기수 10 입니다. 8진수는 8 진수입니다 . 이진법은 2진법 입니다.

    예시
    let myNumber = 32;
    myNumber.toString(10); // returns 32
    myNumber.toString(32); // returns 10
    myNumber.toString(16); // returns 20
    myNumber.toString(8); // returns 40
    myNumber.toString(2); // returns 100000

---

### 숫자는 객체가 될 수 있습니다

일반적으로 JavaScript 숫자는 리터럴에서 생성된 기본 값입니다.

    let x = 123;

그러나 숫자는 new 키워드를 사용하여 객체로 정의할 수도 있습니다 .

    let y = new Number(123);

    예시
    let x = 123;
    let y = new Number(123);

    // typeof x returns number
    // typeof y returns object

Number 객체를 생성하지 마십시오. 실행 속도가 느려집니다.
이 new키워드는 코드를 복잡하게 만듭니다. 이로 인해 예기치 않은 결과가 발생할 수 있습니다.

==연산자를 사용할 때 동일한 숫자는 동일합니다.

    예시
    let x = 500;
    let y = new Number(500);

    // (x == y) is true because x and y have equal values

===연산자를 사용할 때 ===연산자는 유형과 값 모두에서 평등을 기대 하기 때문에 동일한 숫자는 같지 않습니다 .

    예시
    let x = 500;
    let y = new Number(500);

    // (x === y) is false because x and y have different types

또는 더 나쁜. 개체를 비교할 수 없습니다.

    예시
    let x = new Number(500);
    let y = new Number(500);

    // (x == y) is false because objects cannot be compared

(x==y)와 의 차이점에 유의하십시오 (x===y).
두 JavaScript 객체를 비교하면 항상 false.
