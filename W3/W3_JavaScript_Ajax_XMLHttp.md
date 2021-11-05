## AJAX - The XMLHttpRequest Object

AJAX의 핵심은 XMLHttpRequest 객체입니다.

1. XMLHttpRequest 객체 생성
2. 콜백 함수 정의
3. XMLHttpRequest 객체 열기
4. 서버에 요청 보내기

---

### XMLHttpRequest 객체

모든 최신 브라우저는 XMLHttpRequest개체를 지원 합니다.

XMLHttpRequest오브젝트는 장면 뒤에 웹 서버와 데이터를 교환 할 수 있습니다. 즉, 전체 페이지를 다시 로드하지 않고도 웹 페이지의 일부를 업데이트할 수 있습니다.

---

### XMLHttpRequest 객체 생성

모든 최신 브라우저(Chrome, Firefox, IE, Edge, Safari, Opera)에는 XMLHttpRequest객체 가 내장되어 있습니다.

XMLHttpRequest객체 생성 구문 :

    variable = new XMLHttpRequest();

---

### 콜백 함수 정의

콜백 함수는 다른 함수에 매개변수로 전달되는 함수입니다.

이 경우 콜백 함수에는 응답이 준비되었을 때 실행할 코드가 포함되어야 합니다.

    xhttp.onload = function() {
    // What to do when the response is ready
    }

---

### 요청 보내기

서버에 요청을 보내려면 XMLHttpRequest객체 의 open() 및 send() 메서드를 사용할 수 있습니다 .

    xhttp.open("GET", "ajax_info.txt");
    xhttp.send();

<br />

    예시
    // Create an XMLHttpRequest object
    const xhttp = new XMLHttpRequest();

    // Define a callback function
    xhttp.onload = function() {
    // Here you can use the Data
    }

    // Send a request
    xhttp.open("GET", "ajax_info.txt");
    xhttp.send();

---

### 도메인 간 액세스

보안상의 이유로 최신 브라우저는 도메인 간 액세스를 허용하지 않습니다.

즉, 웹 페이지와 웹 페이지에서 로드하려는 XML 파일이 모두 동일한 서버에 있어야 합니다.

W3Schools의 예제는 W3Schools 도메인에 있는 모든 열린 XML 파일입니다.

자신의 웹 페이지 중 하나에서 위의 예를 사용하려면 로드하는 XML 파일이 자체 서버에 있어야 합니다.

---

### XMLHttpRequest 객체 메서드

<img src='./img/XMLHttpRequest.png'>

---

### XMLHttpRequest 객체 속성

<img src='./img/XMLHttpRequest2.png'>

---

### onload 속성

XMLHttpRequest객체를 사용하여 요청이 응답을 수신할 때 실행할 콜백 함수를 정의할 수 있습니다.

함수는 XMLHttpRequest객체 의 onload속성에 정의되어 있습니다 .

    예시
    xhttp.onload = function() {
    document.getElementById("demo").innerHTML = this.responseText;
    }
    xhttp.open("GET", "ajax_info.txt");
    xhttp.send();

---

### 다중 콜백 함수

웹 사이트에 둘 이상의 AJAX 작업이 있는 경우 XMLHttpRequest개체 를 실행하기 위한 하나의 함수 와 각 AJAX 작업에 대해 하나의 콜백 함수를 만들어야 합니다.

함수 호출에는 URL과 응답이 준비되었을 때 호출할 함수가 포함되어야 합니다.

    예시
    loadDoc("url-1", myFunction1);

    loadDoc("url-2", myFunction2);

    function loadDoc(url, cFunction) {
    const xhttp = new XMLHttpRequest();
    xhttp.onload = function() {cFunction(this);}
    xhttp.open("GET", url);
    xhttp.send();
    }

    function myFunction1(xhttp) {
    // action goes here
    }
    function myFunction2(xhttp) {
    // action goes here
    }

---

### onreadystatechange 속성

readyState속성은 XMLHttpRequest의 상태를 보유하고 있습니다.

onreadystatechange속성은 readyState가 변경될 때 실행할 콜백 함수를 정의합니다.

status속성과 statusText속성은 XMLHttpRequest의 객체의 상태를 보유하고 있습니다.

<img src='./img/XMLHttpRequest3.png'>

이 onreadystatechange함수는 readyState가 변경될 때마다 호출됩니다.

때 readyState4와 상태가 200 응답이 준비

    예시
    function loadDoc() {
    const xhttp = new XMLHttpRequest();
    xhttp.onreadystatechange = function() {
    if (this.readyState == 4 && this.status == 200) {
    document.getElementById("demo").innerHTML =
    this.responseText;
    }
    };
    xhttp.open("GET", "ajax_info.txt");
    xhttp.send();
    }

onreadystatechange이벤트는 네 번 (1-4)의 readyState가 변경 될 때마다 하나의 시간이 시작됩니다.
