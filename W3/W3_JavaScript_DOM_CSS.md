## JavaScript HTML DOM - Changing CSS

HTML DOM을 사용하면 JavaScript가 HTML 요소의 스타일을 변경할 수 있습니다.

---

### HTML 스타일 변경

HTML 요소의 스타일을 변경하려면 다음 구문을 사용하십시오.

    document.getElementById(id).style.property = new style

<br />

    예시 - 다음 예에서는 <p>요소 의 스타일을 변경합니다 .

    <html>
    <body>

    <p id="p2">Hello World!</p>

    <script>
    document.getElementById("p2").style.color = "blue";
    </script>

    </body>
    </html>

---

### 이벤트 사용

HTML DOM을 사용하면 이벤트가 발생할 때 코드를 실행할 수 있습니다.

이벤트는 HTML 요소에 "일이 발생"할 때 브라우저에서 생성됩니다.

- 요소가 클릭됨
- 페이지가 로드되었습니다
- 입력 필드가 변경됨

이 자습서의 다음 장에서 이벤트에 대해 자세히 알아볼 것입니다.

    예시 - 이 예제 id="id1"에서는 사용자가 버튼을 클릭할 때 HTML 요소의 스타일을 변경 합니다.

    <!DOCTYPE html>
    <html>
    <body>

    <h1 id="id1">My Heading 1</h1>

    <button type="button"
    onclick="document.getElementById('id1').style.color = 'red'">
    Click Me!</button>

    </body>
    </html>
