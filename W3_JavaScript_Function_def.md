## JavaScript Function Definitions

JavaScript 함수는 키워드 function로 정의 됩니다.

함수 선언 또는 함수 표현식을 사용할 수 있습니다 .

---

### 함수 선언

    function functionName(parameters) {
    // code to be executed
    }

선언된 함수는 즉시 실행되지 않습니다. "나중에 사용하기 위해 저장"되며 나중에 호출(호출)될 때 실행됩니다.

    예시
    function myFunction(a, b) {
    return a \* b;
    }

<br />

    세미콜론은 실행 가능한 JavaScript 문을 구분하는 데 사용됩니다.
    함수 선언 은 실행 가능한 문이 아니기 때문에 세미콜론으로 끝나는 것이 일반적이지 않습니다.

---

### 함수 표현식

JavaScript 함수는 표현식을 사용하여 정의할 수도 있습니다 .

함수 표현식은 변수에 저장할 수 있습니다.

    예시
    const x = function (a, b) {return a \* b};

함수 표현식을 변수에 저장한 후 변수를 함수로 사용할 수 있습니다.

    예시
    const x = function (a, b) {return a \* b};
    let z = x(4, 3);

위의 함수는 실제로 익명 함수 (이름이 없는 함수)입니다.

변수에 저장된 함수에는 함수 이름이 필요하지 않습니다. 항상 변수 이름을 사용하여 호출(호출)됩니다.

    위의 함수는 실행 가능한 문의 일부이므로 세미콜론으로 끝납니다.

---

### Function() 생성자

이전 예제에서 보았듯이 JavaScript 함수는 function키워드 로 정의됩니다 .

함수는 라는 내장 JavaScript 함수 생성자를 사용하여 정의할 수도 있습니다 Function().

    예시
    const myFunction = new Function("a", "b", "return a \* b");

    let x = myFunction(4, 3);

실제로 함수 생성자를 사용할 필요가 없습니다. 위의 예는 다음과 같이 작성하는 것과 같습니다.

    예시
    const myFunction = function (a, b) {return a \* b};

    let x = myFunction(4, 3);

대부분의 경우 newJavaScript 에서는 키워드 사용을 피할 수 있습니다 .

---

### 함수 호이스팅

호이스팅은 선언 을 현재 범위의 맨 위로 이동하는 JavaScript의 기본 동작입니다 .

호이스팅은 변수 선언과 함수 선언에 적용됩니다.

이 때문에 JavaScript 함수는 선언되기 전에 호출될 수 있습니다.

    myFunction(5);

    function myFunction(y) {
      return y * y;
    }

표현식을 사용하여 정의된 함수는 호이스팅되지 않습니다.

---

### 자체 호출 함수

함수 표현식은 "자체 호출"로 만들 수 있습니다.

자체 호출 표현식은 호출되지 않고 자동으로 호출(시작)됩니다.

표현식 뒤에 ()가 오면 함수 표현식이 자동으로 실행됩니다.

함수 선언을 자체 호출할 수 없습니다.

함수 표현식임을 나타내려면 함수 주위에 괄호를 추가해야 합니다.

    예시
    (function () {
    let x = "Hello!!"; // I will invoke myself
    })();

위의 함수는 실제로 익명의 자체 호출 함수 (이름 없는 함수)입니다.

---

### 함수를 값으로 사용할 수 있음

JavaScript 함수를 값으로 사용할 수 있습니다.

    예시
    function myFunction(a, b) {
    return a \* b;
    }

    let x = myFunction(4, 3);

JavaScript 함수는 표현식에서 사용할 수 있습니다.

    예시
    function myFunction(a, b) {
    return a \* b;
    }

    let x = myFunction(4, 3) \* 2;

---

### 함수는 객체입니다

JavaScript 의 typeof연산자는 함수에 대해 "함수"를 반환합니다.

그러나 JavaScript 함수는 객체로 가장 잘 설명될 수 있습니다.

JavaScript 함수에는 속성 과 메서드 가 모두 있습니다 .

이 arguments.length속성은 함수가 호출될 때 받은 인수의 수를 반환합니다.

    예시
    function myFunction(a, b) {
    return arguments.length;
    }

이 toString()메서드는 함수를 문자열로 반환합니다.

    예시
    function myFunction(a, b) {
    return a \* b;
    }

    let text = myFunction.toString();

객체의 속성으로 정의된 함수를 객체에 대한 메서드라고 합니다.
새로운 객체를 생성하도록 설계된 함수를 객체 생성자라고 합니다.

---

### 화살표 함수

화살표 함수는 함수 표현식을 작성하기 위한 짧은 구문을 허용합니다.

function키워드, return키워드 및 중괄호 는 필요하지 않습니다 .

    예시
    // ES5
    var x = function(x, y) {
    return x \* y;
    }

    // ES6
    const x = (x, y) => x \* y;

화살표 함수에는 자신의 this가 없습니다 . 그것들은 객체 메소드 를 정의하는 데 적합하지 않습니다 .

화살표 함수는 호이스팅되지 않습니다. 사용 하기 전에 정의해야 합니다 .

함수 표현식은 항상 상수 값이기 때문에 const 를 사용하는 것이 var를 사용하는 것보다 안전 합니다.

함수가 단일 명령문인 경우 return에만 키워드와 중괄호를 생략할 수 있습니다 .

이 때문에 항상 보관하는 것이 좋은 습관일 수 있습니다.

    예시
    const x = (x, y) => { return x \* y };
