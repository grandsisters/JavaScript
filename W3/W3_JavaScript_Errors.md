## JavaScript Errors - Throw and Try to Catch

try명령문을 사용하면 코드 블록에 오류가 있는지 테스트할 수 있습니다.

catch문을 사용하면 오류를 처리 할 수 있습니다.

throw문은 사용자 정의 오류를 만들 수 있습니다.

이 finally명령문을 사용하면 결과에 관계없이 try 및 catch 후에 코드를 실행할 수 있습니다.

---

### 오류가 발생합니다!

JavaScript 코드를 실행할 때 다른 오류가 발생할 수 있습니다.

오류는 프로그래머의 코딩 오류, 잘못된 입력으로 인한 오류, 기타 예측할 수 없는 일이 될 수 있습니다.

    예시
    이 예에서 우리는 의도적으로 오류를 생성하기 위해 "alert"를 "adddlert"로 잘못 입력했습니다.

    <p id="demo"></p>

    <script>
    try {
      adddlert("Welcome guest!");
    }
    catch(err) {
      document.getElementById("demo").innerHTML = err.message;
    }
    </script>

JavaScript는 adddlert 를 오류로 catch하고 catch 코드를 실행하여 처리합니다.

---

### 자바스크립트 시도 및 잡기

try문을 사용하면이 실행되는 동안 오류를 테스트 할 코드 블록을 정의 할 수 있습니다.

이 catch명령문을 사용하면 try 블록에서 오류가 발생할 경우 실행할 코드 블록을 정의할 수 있습니다.

    자바 스크립트 구문 try과는 catch 쌍으로 :

    try {
    Block of code to try
    }
    catch(err) {
    Block of code to handle errors
    }

---

### JavaScript에서 오류 발생

오류가 발생하면 JavaScript는 일반적으로 중지되고 오류 메시지를 생성합니다.

이에 대한 기술 용어는 JavaScript 에서 예외가 발생합니다(오류 발생) .

JavaScript는 실제로 name 과 message 의 두 가지 속성을 가진 Error 객체 를 생성 합니다 .

---

### throw 문

throw문을 사용하면 사용자 지정 오류를 만들 수 있습니다.

기술적 으로 예외 를 던질 수 있습니다 (오류 던짐) .

예외는 JavaScript String, a Number, a Boolean또는 an Object일 수 있습니다 .

    throw "Too big"; // throw a text
    throw 500; // throw a number

try및 catch와 throw를 함께 사용 하면 프로그램 흐름을 제어하고 사용자 지정 오류 메시지를 생성할 수 있습니다.

---

### 입력 검증 예

이 예에서는 입력을 검사합니다. 값이 잘못된 경우 예외(오류)가 발생합니다.

예외(err)가 catch 문에 의해 catch되고 사용자 지정 오류 메시지가 표시됩니다.

    <!DOCTYPE html>
    <html>
    <body>

    <p>Please input a number between 5 and 10:</p>

    <input id="demo" type="text">
    <button type="button" onclick="myFunction()">Test Input</button>
    <p id="p01"></p>

    <script>
    function myFunction() {
      const message = document.getElementById("p01");
      message.innerHTML = "";
      let x = document.getElementById("demo").value;
      try {
        if(x == "") throw "empty";
        if(isNaN(x)) throw "not a number";
        x = Number(x);
        if(x < 5) throw "too low";
        if(x > 10) throw "too high";
      }
      catch(err) {
        message.innerHTML = "Input is " + err;
      }
    }
    </script>

    </body>
    </html>

---

### HTML 유효성 검사

위의 코드는 예시일 뿐입니다.

최신 브라우저는 HTML 속성에 정의된 미리 정의된 유효성 검사 규칙을 사용하여 JavaScript와 기본 제공 HTML 유효성 검사의 조합을 사용하는 경우가 많습니다.

    <input id="demo" type="number" min="5" max="10" step="1">

---

### finally 문

이 finally명령문을 사용하면 결과에 관계없이 try 및 catch 후에 코드를 실행할 수 있습니다.

    sytax:
    try {
    Block of code to try
    }
    catch(err) {
    Block of code to handle errors
    }
    finally {
    Block of code to be executed regardless of the try / catch result
    }

<br />

    예시
    function myFunction() {
    const message = document.getElementById("p01");
    message.innerHTML = "";
    let x = document.getElementById("demo").value;
    try {
    if(x == "") throw "is empty";
    if(isNaN(x)) throw "is not a number";
    x = Number(x);
    if(x > 10) throw "is too high";
    if(x < 5) throw "is too low";
    }
    catch(err) {
    message.innerHTML = "Error: " + err + ".";
    }
    finally {
    document.getElementById("demo").value = "";
    }
    }

---

### 오류 개체

JavaScript에는 오류가 발생할 때 오류 정보를 제공하는 내장 오류 객체가 있습니다.

error 객체는 name과 message라는 두 가지 유용한 속성을 제공합니다.

---

### 오류 개체 속성

| Property | Description                                  |
| -------- | -------------------------------------------- |
| 이름     | 오류 이름을 설정하거나 반환합니다.           |
| 메세지   | 오류 메시지(문자열)를 설정하거나 반환합니다. |

---

### 오류 이름 값

error name 속성은 6가지 다른 값을 반환할 수 있습니다.

| 오류 이름      | 설명                                 |
| -------------- | ------------------------------------ |
| EvalError      | eval() 함수에서 오류가 발생했습니다. |
| RangeError     | "범위를 벗어난" 숫자가 발생했습니다. |
| ReferenceError | 잘못된 참조가 발생했습니다.          |
| SyntaxError    | 구문 오류가 발생했습니다             |
| TypeError      | 유형 오류가 발생했습니다.            |
| URIError       | encodeURI()에서 오류가 발생했습니다  |

6가지 다른 값이 아래에 설명되어 있습니다.

---

### 평가 오류

An EvalError은 eval() 함수의 오류를 나타냅니다.

    최신 버전의 JavaScript에서는 EvalError가 발생하지 않습니다. 대신 SyntaxError를 사용하십시오.

---

### 범위 오류

RangeError유효한 값 범위를 벗어난 숫자를 사용하면 A 가 발생합니다.

예: 숫자의 유효 자릿수를 500으로 설정할 수 없습니다.

    예시
    let num = 1;
    try {
    num.toPrecision(500); // A number cannot have 500 significant digits
    }
    catch(err) {
    document.getElementById("demo").innerHTML = err.name;
    }

---

### 참조 오류

ReferenceError선언되지 않은 변수를 사용(참조)하면 A 가 발생합니다.

    예시
    let x = 5;
    try {
    x = y + 1; // y cannot be used (referenced)
    }
    catch(err) {
    document.getElementById("demo").innerHTML = err.name;
    }

---

### 구문 오류

SyntaxError구문 오류가 있는 코드를 평가하려고 하면 A 가 발생합니다.

    예시
    try {
    eval("alert('Hello)"); // Missing ' will produce an error
    }
    catch(err) {
    document.getElementById("demo").innerHTML = err.name;
    }

---

### 유형 오류

TypeError예상 유형 범위를 벗어난 값을 사용하면 A 가 발생합니다.

    예시
    let num = 1;
    try {
    num.toUpperCase(); // You cannot convert a number to upper case
    }
    catch(err) {
    document.getElementById("demo").innerHTML = err.name;
    }

---

### URI(Uniform Resource Identifier) ​​오류

URIErrorURI 함수에서 잘못된 문자를 사용하면 A 가 발생합니다.

    예시
    try {
    decodeURI("%%%"); // You cannot URI decode percent signs
    }
    catch(err) {
    document.getElementById("demo").innerHTML = err.name;
    }

---

### 비표준 오류 개체 속성

Mozilla와 Microsoft는 일부 비표준 오류 개체 속성을 정의합니다.

    fileName(Mozilla)
    lineNumber(Mozilla)
    columnNumber(Mozilla)
    스택(Mozilla)
    설명(Microsoft)
    번호(Microsoft)

공개 웹 사이트에서 이러한 속성을 사용하지 마십시오. 모든 브라우저에서 작동하지 않습니다.
