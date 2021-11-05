## JavaScript Statements

    예시
    let x, y, z; // Statement 1
    x = 5; // Statement 2
    y = 6; // Statement 3
    z = x + y; // Statement 4

---

### JavaScript Programs

컴퓨터 프로그램은 컴퓨터에서 "실행"할 명령의 목록입니다.

프로그래밍 언어에서는 이러한 프로그래밍 명령을 문이라고 합니다.

자바스크립트 프로그램은 프로그래밍 문의 목록입니다.

    HTML에서 JavaScript 프로그램은 웹 브라우저에서 실행됩니다.

---

### JavaScript Statements

JavaScript 문은 다음으로 구성됩니다.

값, 연산자, 표현식, 키워드 및 주석.

id="demo"인 innerHTML 문은 브라우저에 "Hello Dolly"를 쓰도록 지시합니다.

    예시
    document.getElementById("demo").innerHTML = "Hello Dolly.";

대부분의 JavaScript 프로그램에는 많은 JavaScript 문이 포함되어 있습니다.

명령문은 작성된 순서대로 하나씩 실행됩니다.

JavaScript 프로그램(및 JavaScript 문)은 종종 JavaScript 코드라고 합니다.

---

### 세미콜론 ;

세미콜론은 JavaScript 문을 구분합니다.

각 실행 문 끝에 세미콜론을 추가합니다.

    예
    let a, b, c; // Declare 3 variables
    a = 5; // Assign the value 5 to a
    b = 6; // Assign the value 6 to b
    c = a + b; // Assign the sum of a and b to c

세미콜론으로 구분하면 한 줄에 여러 문이 허용됩니다.

    a = 5; b = 6; c = a + b;

웹에서 세미콜론이 없는 예제를 볼 수 있습니다.
세미콜론으로 끝나는 문장은 필수는 아니지만 적극 권장합니다.

---

### 자바스크립트 공백

JavaScript는 여러 공백을 무시합니다. 스크립트에 공백을 추가하여 가독성을 높일 수 있습니다.

다음 줄은 동일합니다.

    let person = "Hege";
    let person="Hege";

좋은 방법은 연산자( = + - \* / ) 주위에 공백을 넣는 것입니다.

    let x = y + z;

---

### JavaScript 줄 길이 및 줄 바꿈

최고의 가독성을 위해 프로그래머는 종종 80자보다 긴 코드 라인을 피하고 싶어합니다.

JavaScript 문이 한 줄에 맞지 않는 경우 가장 좋은 위치는 연산자 다음입니다.

    예시
    document.getElementById("demo").innerHTML =
    "Hello Dolly!";

---

### 자바스크립트 코드 블록

JavaScript 문은 중괄호 {...} 안에 있는 코드 블록으로 그룹화할 수 있습니다.

코드 블록의 목적은 함께 실행할 명령문을 정의하는 것입니다.

블록으로 함께 그룹화된 명령문을 찾을 수 있는 곳은 JavaScript 함수입니다.

    예시
    function myFunction() {
    document.getElementById("demo1").innerHTML = "Hello Dolly!";
    document.getElementById("demo2").innerHTML = "How are you?";
    }
