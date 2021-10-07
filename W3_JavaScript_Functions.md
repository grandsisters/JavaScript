## JavaScript Functions

JavaScript 함수는 특정 작업을 수행하도록 설계된 코드 블록입니다.

JavaScript 함수는 "무언가"가 이를 호출(호출)할 때 실행됩니다.

    function myFunction(p1, p2) {
    return p1 * p2;   // The function returns the product of p1 and p2
    }

---

### 자바스크립트 함수 구문

JavaScript 함수는 function키워드, 이름 , 괄호 () 순으로 정의됩니다 .

함수 이름에는 문자, 숫자, 밑줄 및 달러 기호가 포함될 수 있습니다(변수와 동일한 규칙).

괄호에는 쉼표로 구분된 매개변수 이름이 포함될 수 있습니다.
( parameter1, parameter2, ... )

함수에 의해 실행될 코드는 중괄호 {} 안에 배치됩니다.

    function name(parameter1, parameter2, parameter3) {
    // code to be executed
    }

함수 매개변수 는 함수 정의에서 괄호() 안에 나열됩니다.

함수 인수 있는 값 이 호출되면 함수에 의해 수신.

함수 내에서 인수(매개변수)는 지역 변수로 작동합니다.

함수는 다른 프로그래밍 언어에서 프로시저 또는 서브루틴과 거의 동일합니다.

---

### 함수 호출

함수 내부의 코드는 "무언가" 가 함수를 호출 (호출) 할 때 실행됩니다 .

- 이벤트 발생 시(사용자가 버튼을 클릭했을 때)
- JavaScript 코드에서 호출(호출)될 때
- 자동(자체 호출)

---

### 함수 반환

JavaScript가 return명령문에 도달 하면 함수 실행이 중지됩니다.

함수가 명령문에서 호출된 경우 JavaScript는 호출 명령문 다음에 코드를 실행하기 위해 "반환"합니다.

함수는 종종 반환 값을 계산 합니다 . 반환 값은 "호출자"에게 다시 "반환"됩니다.

    예시
    두 숫자의 곱을 계산하고 결과를 반환합니다.

    let x = myFunction(4, 3); // Function is called, return value will end up in x

    function myFunction(a, b) {
    return a * b; // Function returns the product of a and b
    }

x의 결과는 다음과 같습니다.

    12

---

### 왜 함수인가?

코드를 재사용할 수 있습니다. 코드를 한 번 정의하고 여러 번 사용하십시오.

다른 인수와 함께 동일한 코드를 여러 번 사용하여 다른 결과를 생성할 수 있습니다.

    예시
    화씨를 섭씨로 변환:

    function toCelsius(fahrenheit) {
    return (5/9) \* (fahrenheit-32);
    }

    document.getElementById("demo").innerHTML = toCelsius(77);

---

### () 연산자가 함수를 호출합니다.

위의 예를 사용하여 toCelsius함수 개체를 toCelsius()참조하고 함수 결과를 참조합니다.

() 없이 함수에 액세스하면 함수 결과 대신 함수 객체가 반환됩니다.

    예시
    function toCelsius(fahrenheit) {
    return (5/9) \* (fahrenheit-32);
    }

    document.getElementById("demo").innerHTML = toCelsius;

---

### 변수 값으로 사용되는 함수

함수는 모든 유형의 수식, 할당 및 계산에서 변수를 사용하는 것과 동일한 방식으로 사용할 수 있습니다.

    예시
    변수를 사용하여 함수의 반환 값을 저장하는 대신:

    let x = toCelsius(77);
    let text = "The temperature is " + x + " Celsius";

    함수를 변수 값으로 직접 사용할 수 있습니다.

    let text = "The temperature is " + toCelsius(77) + " Celsius";

---

### 지역 변수

JavaScript 함수 내에서 선언된 변수는 함수에 대해 LOCAL 이 됩니다.

지역 변수는 함수 내에서만 액세스할 수 있습니다.

    예시
    // code here can NOT use carName

    function myFunction() {
    let carName = "Volvo";
    // code here CAN use carName
    }

    // code here can NOT use carName

지역 변수는 함수 내에서만 인식되기 때문에 같은 이름의 변수를 다른 함수에서 사용할 수 있습니다.

지역 변수는 함수가 시작될 때 생성되고 함수가 완료되면 삭제됩니다.
