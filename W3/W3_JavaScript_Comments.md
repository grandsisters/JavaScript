### 자바스크립트 주석

JavaScript 주석은 JavaScript 코드를 설명하고 더 읽기 쉽게 만드는 데 사용할 수 있습니다.

JavaScript 주석은 대체 코드를 테스트할 때 실행을 방지하는 데 사용할 수도 있습니다.

---

### 한 줄 주석

한 줄 주석은 로 시작합니다 //.

//행의 끝과 사이의 모든 텍스트는 JavaScript에서 무시됩니다(실행되지 않음).

이 예에서는 각 코드 줄 앞에 한 줄 주석을 사용합니다.

    예시
    // Change heading:
    document.getElementById("myH").innerHTML = "My First Page";

    // Change paragraph:
    document.getElementById("myP").innerHTML = "My first paragraph.";

이 예에서는 각 줄 끝에 한 줄 주석을 사용하여 코드를 설명합니다.

    예시
    let x = 5; // Declare x, give it the value of 5
    let y = x + 2; // Declare y, give it the value of x + 2

---

### 여러 줄 주석

여러 줄 주석은 로 시작 /_하고 로 끝납니다 _/.

/_와 사이의 모든 텍스트는 _/JavaScript에서 무시됩니다.

이 예에서는 여러 줄 주석(주석 블록)을 사용하여 코드를 설명합니다.

    예시
    /_
    The code below will change
    the heading with id = "myH"
    and the paragraph with id = "myP"
    in my web page:
    _/
    document.getElementById("myH").innerHTML = "My First Page";
    document.getElementById("myP").innerHTML = "My first paragraph.";

한 줄 주석을 사용하는 것이 가장 일반적입니다.
블록 주석은 종종 공식 문서에 사용됩니다.

---

### 주석을 사용하여 실행 방지

코드 실행을 방지하기 위해 주석을 사용하는 것은 코드 테스트에 적합합니다.

//코드 라인 앞에 추가 하면 코드 라인이 실행 가능한 라인에서 주석으로 변경됩니다.

이 예제에서는 //를 사용하여 코드 라인 중 하나의 실행을 방지합니다.

    예시
    //document.getElementById("myH").innerHTML = "My First Page";
    document.getElementById("myP").innerHTML = "My first paragraph.";
    이 예에서는 주석 블록을 사용하여 여러 줄의 실행을 방지합니다.

    예시
    /_
    document.getElementById("myH").innerHTML = "My First Page";
    document.getElementById("myP").innerHTML = "My first paragraph.";
    _/
