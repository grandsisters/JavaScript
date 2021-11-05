## JavaScript Syntax

JavaScript 구문은 JavaScript 프로그램이 구성되는 규칙의 집합입니다.

    // How to create variables:
    var x;
    let y;

    // How to use variables:
    x = 5;
    y = 6;
    let z = x + y;

<br />

### 자바스크립트 값

JavaScript 구문은 두 가지 유형의 값을 정의합니다.

- 고정 값
- 변수 값

고정 값을 리터럴 이라고 합니다.

변수 값을 변수 라고 합니다.

---

### 자바스크립트 리터럴

고정 값에 대한 가장 중요한 두 가지 구문 규칙은 다음과 같습니다.

1. 숫자 는 소수점 이하 자릿수를 포함하거나 포함하지 않고 작성됩니다.

   10.50

   1001

2. 문자열 은 큰따옴표나 작은따옴표로 묶인 텍스트입니다.

   "John Doe"

   'John Doe'

---

### 자바스크립트 변수

프로그래밍 언어에서 변수 는 데이터 값 을 저장 하는 데 사용 됩니다.

자바 스크립트는 키워드를 사용 var, let및 const에 선언 변수.

동일한 기호 로 사용되는 할당 값 변수.

이 예에서 x는 변수로 정의됩니다. 그런 다음 x에 값 6이 할당됩니다.

    let x;
    x = 6;

---

### 자바스크립트 연산자

JavaScript는 산술 연산자 ( + - \* /)를 사용하여 값 을 계산 합니다.

    (5 + 6) \* 10

JavaScript는 할당 연산자 ( =)를 사용하여 변수에 값을 할당 합니다.

    let x, y;
    x = 5;
    y = 6;

---

### 자바스크립트 표현식

표현식은 값을 계산하는 값, 변수 및 연산자의 조합입니다.

계산을 평가라고 합니다.

예를 들어 5 \* 10은 50으로 평가됩니다.

    5 \* 10

표현식에는 변수 값도 포함될 수 있습니다.

    x \* 10

값은 숫자 및 문자열과 같은 다양한 유형일 수 있습니다.

예를 들어 "John" + " " + "Doe"는 "John Doe"로 평가됩니다.

    "John" + " " + "Doe"

---

### 자바스크립트 키워드

JavaScript 키워드 는 수행할 작업을 식별하는 데 사용됩니다.

let 키워드는 브라우저에 변수를 생성하도록 지시합니다.

    let x, y;
    x = 5 + 6;
    y = x \* 10;

var 키워드는 브라우저에 변수를 생성하도록 지시합니다.

    var x, y;
    x = 5 + 6;
    y = x \* 10;

이 예에서 var 또는 let를 사용하면 동일한 결과가 생성됩니다.

---

### 자바스크립트 주석

모든 JavaScript 문이 "실행"되는 것은 아닙니다.

이중 슬래시 //또는 /_및 사이의 코드 _/는 주석으로 처리됩니다 .

주석은 무시되며 실행되지 않습니다.

    let x = 5; // I will be executed

    // x = 6; I will NOT be executed

---

### 자바스크립트 식별자

식별자는 이름입니다.

JavaScript에서 식별자는 변수(및 키워드, 함수, 레이블)의 이름을 지정하는 데 사용됩니다.

법적 이름에 대한 규칙은 대부분의 프로그래밍 언어에서 거의 동일합니다.

JavaScript에서 첫 번째 문자는 문자, 밑줄(\_) 또는 달러 기호($)여야 합니다.

후속 문자는 문자, 숫자, 밑줄 또는 달러 기호일 수 있습니다.

숫자는 첫 번째 문자로 사용할 수 없습니다.

이 방법으로 JavaScript는 식별자와 숫자를 쉽게 구별할 수 있습니다.

---

### JavaScript는 대소문자를 구분합니다

모든 JavaScript 식별자는 대소문자를 구분 합니다.

변수 lastName및 lastname는 서로 다른 두 변수입니다.

    let lastname, lastName;
    lastName = "Doe";
    lastname = "Peterson";

JavaScript는 LET 또는 Let 을 키워드 let 으로 해석하지 않습니다 .

---

### 자바스크립트와 카멜 케이스

역사적으로 프로그래머는 여러 단어를 하나의 변수 이름으로 결합하는 다양한 방법을 사용했습니다.

하이픈:

first-name, last-name, master-card, inter-city.

하이픈은 JavaScript에서 허용되지 않습니다. 뺄셈을 위해 예약되어 있습니다.

밑줄:

first_name, last_name, master_card, inter_city.

Upper Camel Case (Pascal Case):

FirstName, LastName, MasterCard, InterCity.

Lower Camel Case:

JavaScript 프로그래머는 소문자로 시작하는 카멜 케이스를 사용하는 경향이 있습니다.

firstName, lastName, masterCard, interCity.

---

### 자바스크립트 문자 집합

JavaScript는 유니코드 문자 집합을 사용합니다 .

유니코드는 (거의) 세계의 모든 문자, 구두점 및 기호를 다룹니다.
