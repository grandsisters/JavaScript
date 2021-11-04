## JavaScript Window Location

window.location개체를 현재 페이지 주소 (URL)를 얻기 위해 새로운 페이지로 브라우저를 리디렉션 할 수 있습니다.

---

### window.location

window.location객체는 윈도우 접두사없이 작성 할 수 있습니다.

몇 가지 예:

- window.location.href 현재 페이지의 href(URL)를 반환합니다.
- window.location.hostname 웹 호스트의 도메인 이름을 반환합니다.
- window.location.pathname 현재 페이지의 경로와 파일 이름을 반환합니다.
- window.location.protocol 사용된 웹 프로토콜을 반환합니다(http: 또는 https:).
- window.location.assign() 새 문서를 로드

---

### window.location Href

window.location.href속성은 현재 페이지의 URL을 반환합니다.

    예시 - 현재 페이지의 href(URL) 표시:

    document.getElementById("demo").innerHTML =
    "Page location is " + window.location.href;

결과는 다음과 같습니다.

    Page location is https://www.w3schools.com/js/js_window_location.asp

---

### window.location Hostname

window.location.hostname property는 인터넷 호스트의 이름(현재 페이지)를 반환한다.

    예시 - 호스트 이름 표시:

    document.getElementById("demo").innerHTML =
    "Page hostname is " + window.location.hostname;

결과는 다음과 같습니다.

    Page hostname is www.w3schools.com

---

### Window Location Pathname

window.location.pathname속성은 현재 페이지의 경로 이름을 반환합니다.

    예시 - 현재 URL의 경로 이름 표시:

    document.getElementById("demo").innerHTML =
    "Page path is " + window.location.pathname;

결과는 다음과 같습니다.

    Page path is /js/js_window_location.asp

---

### Window Location Protocol

window.location.protocol속성은 페이지의 웹 프로토콜을 반환합니다.

    예시 - 웹 프로토콜 표시:

    document.getElementById("demo").innerHTML =
    "Page protocol is " + window.location.protocol;

결과는 다음과 같습니다.

    Page protocol is https:

---

### Window Location Port

window.location.port재산 반환 (현재 페이지) 인터넷 호스트 포트의 수.

    예시 - 호스트 이름 표시:

    document.getElementById("demo").innerHTML =
    "Port number is " + window.location.port;

결과는 다음과 같습니다.

    Port number is

대부분의 브라우저는 기본 포트 번호를 표시하지 않습니다(http의 경우 80, https의 경우 443).

---

### Window Location Assign

이 window.location.assign()메서드는 새 문서를 로드합니다.

    예시 - 새 문서 로드:

    <html>
    <head>
    <script>
    function newDoc() {
      window.location.assign("https://www.w3schools.com")
    }
    </script>
    </head>
    <body>

    <input type="button" value="Load new document" onclick="newDoc()">

    </body>
    </html>
