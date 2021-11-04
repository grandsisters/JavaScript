## JavaScript Window Navigator

window.navigator객체는 방문자의 브라우저에 대한 정보가 포함되어 있습니다.

---

### Window Navigator

window.navigator객체는 윈도우 접두사없이 작성 할 수 있습니다.

몇 가지 예:

- navigator.appName
- navigator.appCodeName
- navigator.platform

---

### Browser Cookies

cookieEnabled속성은, 그렇지 않은 경우는 false 쿠키를 사용하는 경우 true를 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML =
    "cookiesEnabled is " + navigator.cookieEnabled;
    </script>

---

### Browser Application Name

appName속성은 브라우저 응용 프로그램 이름을 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML =
    "navigator.appName is " + navigator.appName;
    </script>

이상하게도 "Netscape"는 IE11, Chrome, Firefox 및 Safari의 응용 프로그램 이름입니다.

---

### Browser Application Code Name

appCodeName속성은 브라우저의 응용 프로그램 코드의 이름을 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML =
    "navigator.appCodeName is " + navigator.appCodeName;
    </script>

"Mozilla"는 Chrome, Firefox, IE, Safari 및 Opera의 애플리케이션 코드 이름입니다.

---

### The Browser Engine

product속성은 브라우저 엔진의 제품 이름을 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML =
    "navigator.product is " + navigator.product;
    </script>

이것에 의존하지 마십시오. 대부분의 브라우저는 제품 이름으로 "Gecko"를 반환합니다!!

---

### The Browser Version

appVersion속성은 브라우저에 대한 버전 정보를 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = navigator.appVersion;
    </script>

---

### The Browser Agent

userAgent속성은 서버에 브라우저가 보낸 사용자 에이전트 헤더를 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = navigator.userAgent;
    </script>

---

### Warning!!

navigator 객체의 정보는 종종 오해의 소지가 있으며 다음과 같은 이유로 브라우저 버전을 감지하는 데 사용해서는 안 됩니다.

- 다른 브라우저에서 동일한 이름을 사용할 수 있습니다.
- 탐색기 데이터는 브라우저 소유자가 변경할 수 있습니다.
- 일부 브라우저는 사이트 테스트를 우회하기 위해 자신을 잘못 식별합니다.
- 브라우저는 브라우저보다 늦게 출시된 새 운영 체제를 보고할 수 없습니다.

---

### The Browser Platform

platform속성은 브라우저 플랫폼 (운영 체제)를 반환합니다 :

    예시

    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = navigator.platform;
    </script>

---

### The Browser Language

language속성은 브라우저의 언어를 반환합니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = navigator.language;
    </script>

---

### Is The Browser Online?

onLine브라우저가 온라인 인 경우 속성은 true 반환

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = navigator.onLine;
    </script>

---

### Is Java Enabled?

javaEnabled()경우 메소드는 true를 돌려줍니다 자바를 사용할 수 있습니다 :

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = navigator.javaEnabled();
    </script>
