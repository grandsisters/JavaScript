## JavaScript Events

HTML 이벤트는 HTML 요소에 발생하는 "사물" 입니다.

JavaScript가 HTML 페이지에서 사용될 때 JavaScript는 이러한 이벤트에 "반응" 할 수 있습니다.

---

### HTML 이벤트

HTML 이벤트는 브라우저가 하거나 사용자가 하는 것일 수 있습니다.

다음은 HTML 이벤트의 몇 가지 예입니다.

- HTML 웹 페이지 로드가 완료되었습니다.
- HTML 입력 필드가 변경되었습니다.
- HTML 버튼을 클릭했습니다

종종 이벤트가 발생하면 무언가를 하고 싶을 수 있습니다.

JavaScript를 사용하면 이벤트가 감지될 때 코드를 실행할 수 있습니다.

HTML을 사용하면 JavaScript 코드와 함께 이벤트 핸들러 속성 을 HTML 요소에 추가할 수 있습니다.

    작은따옴표 사용:

    <element event='some JavaScript'>

    큰따옴표 사용:

    <element event="some JavaScript">

다음 예에서는 onclick속성(코드 포함)이 \<button>요소에 추가됩니다 .

    예시
    <button onclick="document.getElementById('demo').innerHTML = Date()">The time is?</button>

위의 예에서 JavaScript 코드는 id="demo"인 요소의 내용을 변경합니다.

다음 예제에서 코드는 자체 요소의 내용을 변경합니다( this.innerHTML).

    예시
    <button onclick="this.innerHTML = Date()">The time is?</button>

JavaScript 코드는 종종 여러 줄입니다. 함수를 호출하는 이벤트 속성을 보는 것이 더 일반적입니다.

    예시
    <button onclick="displayDate()">The time is?</button>

---

### 일반적인 HTML 이벤트

다음은 몇 가지 일반적인 HTML 이벤트 목록입니다.

| Event       | Description                                        |
| ----------- | -------------------------------------------------- |
| onchange    | An HTML element has been changed                   |
| onclick     | The user clicks an HTML element                    |
| onmouseover | The user moves the mouse over an HTML element      |
| onmouseout  | The user moves the mouse away from an HTML element |
| onkeydown   | The user pushes a keyboard key                     |
| onload      | The browser has finished loading the page          |

---

### JavaScript는 무엇을 할 수 있습니까?

이벤트 처리기를 사용하여 사용자 입력, 사용자 작업 및 브라우저 작업을 처리하고 확인할 수 있습니다.

- 페이지가 로드될 때마다 수행해야 하는 작업
- 페이지를 닫았을 때 해야 할 일
- 사용자가 버튼을 클릭할 때 수행해야 하는 작업
- 사용자가 데이터를 입력할 때 확인해야 하는 내용
- etx ...

JavaScript가 이벤트와 함께 작동하도록 하기 위해 다양한 방법을 사용할 수 있습니다.

- HTML 이벤트 속성은 JavaScript 코드를 직접 실행할 수 있습니다.
- HTML 이벤트 속성은 JavaScript 함수를 호출할 수 있습니다.
- HTML 요소에 고유한 이벤트 핸들러 기능을 할당할 수 있습니다.
- 이벤트가 전송되거나 처리되는 것을 방지할 수 있습니다.
- etc ...
