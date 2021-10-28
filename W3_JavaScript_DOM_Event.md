## JavaScript HTML DOM Events

HTML DOM을 사용하면 JavaScript가 HTML 이벤트에 반응할 수 있습니다.

---

### 이벤트에 반응하기

JavaScript는 사용자가 HTML 요소를 클릭할 때와 같이 이벤트가 발생할 때 실행할 수 있습니다.

사용자가 요소를 클릭할 때 코드를 실행하려면 HTML 이벤트 속성에 JavaScript 코드를 추가하십시오.

    onclick=JavaScript

HTML 이벤트의 예:

- 사용자가 마우스를 클릭할 때
- 웹 페이지가 로드되었을 때
- 이미지가 로드되었을 때
- 마우스가 요소 위로 이동할 때
- 입력 필드가 변경된 경우
- HTML 양식을 제출할 때
- 사용자가 키를 치는 경우

<br />

    예시 - 이 예에서 <h1>사용자가 요소를 클릭하면 요소 의 내용 이 변경됩니다.
      <!DOCTYPE html>
      <html>
      <body>

      <h1 onclick="this.innerHTML = 'Ooops!'">Click on this text!</h1>

      </body>
      </html>

<br />

    예시 - 이 예에서 함수는 이벤트 핸들러에서 호출됩니다.
    <!DOCTYPE html>
    <html>
    <body>

    <h1 onclick="changeText(this)">Click on this text!</h1>

    <script>
    function changeText(id) {
      id.innerHTML = "Ooops!";
    }
    </script>

    </body>
    </html>

---

### HTML 이벤트 속성

이벤트 속성을 사용하여 HTML 요소에 이벤트를 할당할 수 있습니다.

    예시
    버튼 요소에 onclick 이벤트 할당:

    <button onclick="displayDate()">Try it</button>

위의 예 displayDate에서 버튼을 클릭하면 이름 이 지정된 함수 가 실행됩니다.

---

### HTML DOM을 사용하여 이벤트 할당

HTML DOM을 사용하면 JavaScript를 사용하여 HTML 요소에 이벤트를 할당할 수 있습니다.

    예시
    버튼 요소에 onclick 이벤트 할당:

    <script>
    document.getElementById("myBtn").onclick = displayDate;
    </script>

위의 예에서 이름 displayDate이 지정된 함수 는 id="myBtn".

버튼을 클릭하면 함수가 실행됩니다.

---

### onload 및 onunload 이벤트

onload와 onunload사용자가 입력하거나 페이지를 떠날 때 이벤트가 트리거됩니다.

이 onload이벤트는 방문자의 브라우저 종류 및 브라우저 버전을 확인하고 정보를 기반으로 웹 페이지의 적절한 버전을 로드하는 데 사용할 수 있습니다.

onload및 onunload이벤트는 쿠키를 처리하는 데 사용할 수 있습니다.

    예시

    <body onload="checkCookies()">

---

### 온체인지 이벤트

onchange이벤트는 종종 입력 필드의 유효성 검사와 함께 사용된다.

다음은 onchange를 사용하는 방법의 예입니다. upperCase() 사용자가 입력 필드의 내용을 변경하는 경우 함수가 호출된다.

    예시
    <input type="text" id="fname" onchange="upperCase()">

---

### 더 많은 예

[onmousedown 및 onmouseup](https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onmousedown)
사용자가 마우스 버튼을 누르고 있을 때 이미지를 변경합니다.

[onload](https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onload)
페이지 로드가 완료되면 경고 상자를 표시합니다.

[onfocus](https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onfocus)
포커스를 받았을 때 입력 필드의 배경색을 변경합니다.

[마우스 이벤트](https://www.w3schools.com/js/tryit.asp?filename=tryjs_event_onmouse)
커서가 요소 위로 이동할 때 요소의 색상을 변경합니다.
