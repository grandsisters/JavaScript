## JavaScript Function Parameters

JavaScript function는 매개변수 값(인수)에 대한 검사를 수행하지 않습니다.

---

### 함수 매개변수 및 인수

    function functionName(parameter1, parameter2, parameter3) {
    // code to be executed
    }

함수 매개변수 는 함수 정의에 나열된 이름 입니다.

함수 인수 는 함수에 전달되고 함수에 의해 수신되는 실제 값 입니다.

---

### 매개변수 규칙

JavaScript 함수 정의는 매개변수에 대한 데이터 유형을 지정하지 않습니다.

JavaScript 함수는 전달된 인수에 대해 유형 검사를 수행하지 않습니다.

JavaScript 함수는 수신된 인수의 수를 확인하지 않습니다.

---

### 기본 매개변수

함수가 누락된 인수 (선언된 것보다 작음) 로 호출 되면 누락된 값이 undefined로 설정됩니다 .

때로는 이것이 허용되지만 때로는 매개변수에 기본값을 할당하는 것이 더 좋습니다.

    예시
    function myFunction(x, y) {
    if (y === undefined) {
    y = 2;
    }
    }

ECMAScript 2015 는 함수 선언에서 기본 매개변수 값을 허용합니다.

    function (x, y = 2) {
    // function code
    }

---

### 인수 객체

JavaScript 함수에는 arguments 객체라는 내장 객체가 있습니다.

인수 객체는 함수가 호출(호출)될 때 사용된 인수의 배열을 포함합니다.

이런 식으로 함수를 사용하여 숫자 목록에서 가장 높은 값을 (예를 들어) 찾을 수 있습니다.

    예시
    x = findMax(1, 123, 500, 115, 44, 88);

    function findMax() {
    let max = -Infinity;
    for (let i = 0; i < arguments.length; i++) {
    if (arguments[i] > max) {
    max = arguments[i];
    }
    }
    return max;
    }

또는 모든 입력 값을 합산하는 함수를 만듭니다.

    예시
    x = sumAll(1, 123, 500, 115, 44, 88);

    function sumAll() {
    let sum = 0;
    for (let i = 0; i < arguments.length; i++) {
    sum += arguments[i];
    }
    return sum;
    }

함수가 너무 많은 인수 (선언된 것보다 많음 )로 호출 되면 arguments 객체를 사용하여 이러한 인수에 도달할 수 있습니다 .

---

### 인수는 값으로 전달됩니다.

함수 호출에서 매개변수는 함수의 인수입니다.

JavaScript 인수는 값 으로 전달됩니다 . 함수는 인수의 위치가 아닌 값만 알게 됩니다.

함수가 인수의 값을 변경하더라도 매개변수의 원래 값은 변경하지 않습니다.

인수에 대한 변경 사항은 함수 외부에서 표시(반사)되지 않습니다.

---

### 개체는 참조로 전달됩니다.

JavaScript에서 객체 참조는 값입니다.

이 때문에 객체는 참조 로 전달된 것처럼 동작합니다 .

함수가 객체 속성을 변경하면 원래 값이 변경됩니다.

객체 속성의 변경 사항은 함수 외부에서 볼 수 있습니다(반사됨).
