## JavaScript Where To

### \<script> 태그

HTML에서는 \<script>및 \</script>태그 사이에 JavaScript 코드가 삽입 됩니다.

    예시

    <script>
    document.getElementById("demo").innerHTML = "My First JavaScript";
    </script>

이전 JavaScript 예제는 \<script type="text/javascript"> 유형 속성을 사용할 수 있습니다.
유형 속성은 필요하지 않습니다. JavaScript는 HTML의 기본 스크립팅 언어입니다.

---

### JavaScript 함수 및 이벤트

JavaScript function는 "호출"될 때 실행할 수 있는 JavaScript 코드 블록입니다.

예를 들어 사용자가 버튼을 클릭할 때와 같이 이벤트 가 발생할 때 함수를 호출할 수 있습니다 .

---

### \<head> 또는 \<body>의 JavaScript

HTML 문서에 스크립트를 원하는 수만큼 배치할 수 있습니다.

스크립트는 \<body>, 또는 \<head>HTML 페이지 의 섹션 또는 둘 다에 배치할 수 있습니다 .

---

### \<head>의 자바스크립트

이 예에서 JavaScript function는 \<head>HTML 페이지 의 섹션에 배치됩니다 .

버튼을 클릭하면 함수가 호출(호출)됩니다.

    예시
    <!DOCTYPE html>
    <html>
    <head>
    <script>
    function myFunction() {
    document.getElementById("demo").innerHTML = "Paragraph changed.";
    }
    </script>
    </head>
    <body>
    <h2>Demo JavaScript in Head</h2>

    <p id="demo">A Paragraph</p>
    <button type="button" onclick="myFunction()">Try it</button>

    </body>
    </html>

---

### <body>의 자바스크립트

이 예에서 JavaScript function는 \<body>HTML 페이지 의 섹션에 배치됩니다 .

버튼을 클릭하면 함수가 호출(호출)됩니다.

    예시
    <!DOCTYPE html>
    <html>
    <body>

    <h2>Demo JavaScript in Body</h2>

    <p id="demo">A Paragraph</p>

    <button type="button" onclick="myFunction()">Try it</button>

    <script>
    function myFunction() {
    document.getElementById("demo").innerHTML = "Paragraph changed.";
    }
    </script>

    </body>
    </html>

\<body> 요소의 맨 아래에 스크립트를 배치하면 스크립트 해석이 디스플레이 속도를 늦추기 때문에 디스플레이 속도가 향상됩니다.

---

### 외부 자바스크립트

스크립트는 외부 파일에 배치할 수도 있습니다.

    외부 파일: myScript.js
    function myFunction() {
    document.getElementById("demo").innerHTML = "Paragraph changed.";
    }

외부 스크립트는 동일한 코드가 여러 다른 웹 페이지에서 사용될 때 실용적입니다.

JavaScript 파일의 파일 확장자는 .js 입니다.

외부 스크립트를 사용하려면 태그 의 src(source) 속성에 스크립트 파일 이름을 입력합니다 \<script>.

    예시

    <script src="myScript.js"></script>

당신은에서 외부 스크립트 참조를 \<head>또는 \<body> 당신이 좋아하는곳에 배치 할 수 있습니다.

스크립트는 \<script>태그가 있는 위치 에 정확히 있는 것처럼 작동합니다 .

외부 스크립트는 \<script>태그를 포함할 수 없습니다 .

---

### 외부 자바스크립트의 장점

스크립트를 외부 파일에 배치하면 다음과 같은 몇 가지 이점이 있습니다.

- HTML과 코드를 분리합니다.
- HTML 및 JavaScript를 더 쉽게 읽고 유지 관리할 수 있습니다.
- 캐시된 JavaScript 파일은 페이지 로드 속도를 높일 수 있습니다.

한 페이지에 여러 스크립트 파일을 추가하려면 - 여러 스크립트 태그를 사용하십시오.

    예시

    <script src="myScript1.js"></script>
    <script src="myScript2.js"></script>

---

### 외부 참조

외부 스크립트는 3가지 방법으로 참조할 수 있습니다.

- 전체 URL(전체 웹 주소)
- 파일 경로 사용(예: /js/)
- 어떤 길도 없이

이 예에서는 전체 URL 을 사용 하여 myScript.js에 연결합니다.

    예시
    <script src="https://www.w3schools.com/js/myScript.js"></script>

이 예에서는 파일 경로 를 사용 하여 myScript.js에 연결합니다.

    예시
    <script src="/js/myScript.js"></script>

이 예에서는 myScript.js에 연결하기 위해 경로를 사용하지 않습니다.

    예시
    <script src="myScript.js"></script>

파일 경로에 대한 자세한 내용은 [HTML 파일 경로 장](https://www.w3schools.com/html/html_filepaths.asp)에서 읽을 수 있습니다 .
