## JavaScript Window History

window.history객체는 브라우저의 역사를 포함하고 있습니다.

---

### Window History

window.history객체는 윈도우 접두사없이 작성 할 수 있습니다.

사용자의 개인 정보를 보호하기 위해 JavaScript가 이 개체에 액세스하는 방법에 제한이 있습니다.

몇 가지 방법:

- history.back() - 브라우저에서 다시 클릭하는 것과 동일
- history.forward() - 브라우저에서 앞으로를 클릭하는 것과 동일

---

### Window History Back

이 history.back()메서드는 기록 목록에서 이전 URL을 로드합니다.

이것은 브라우저에서 뒤로 버튼을 클릭하는 것과 같습니다.

    예시 - 페이지에 뒤로 버튼 만들기:

    <html>
    <head>
    <script>
    function goBack() {
      window.history.back()
    }
    </script>
    </head>
    <body>

    <input type="button" value="Back" onclick="goBack()">

    </body>
    </html>

---

### Window History Forward

이 history.forward()메서드는 기록 목록에서 다음 URL을 로드합니다.

이는 브라우저에서 앞으로 버튼을 클릭하는 것과 같습니다.

    예시 - 페이지에 앞으로 버튼 만들기:

    <html>
    <head>
    <script>
    function goForward() {
      window.history.forward()
    }
    </script>
    </head>
    <body>

    <input type="button" value="Forward" onclick="goForward()">

    </body>
    </html>
