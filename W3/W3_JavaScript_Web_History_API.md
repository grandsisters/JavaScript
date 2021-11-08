## Web History API

Web History API는 windows.history 개체에 액세스하는 쉬운 방법을 제공합니다.

window.history 객체는 사용자가 방문한 URL(웹 사이트)을 포함합니다.

---

### History back() 메서드

back() 메서드는 windows.history 목록의 이전 URL을 로드합니다.

브라우저에서 "뒤로 화살표"를 클릭하는 것과 같습니다.

    예시
    <button onclick="myFunction()">Go Back</button>

    <script>
    function myFunction() {
      window.history.back();
    }
    </script>

---

### 히스토리 go() 메서드

go() 메서드는 기록 목록에서 특정 URL을 로드합니다.

    예시
    <button onclick="myFunction()">Go Back 2 Pages</button>

    <script>
    function myFunction() {
      window.history.go(-2);
    }
    </script>

---

### 기록 개체 속성

| Property | Description                                    |
| -------- | ---------------------------------------------- |
| length   | Returns the number of URLs in the history list |

<br />

### 기록 개체 메서드

| Method    | Description                                |
| --------- | ------------------------------------------ |
| back()    | Loads the previous URL in the history list |
| forward() | Loads the next URL in the history list     |
| go()      | Loads a specific URL from the history list |
