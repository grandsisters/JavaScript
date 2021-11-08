## JavaScript Validation API

---

### 제약 조건 유효성 검사 DOM 메서드

| Property            | Description                                              |
| ------------------- | -------------------------------------------------------- |
| checkValidity()     | Returns true if an input element contains valid data.    |
| setCustomValidity() | Sets the validationMessage property of an input element. |

입력 필드에 잘못된 데이터가 포함된 경우 다음 메시지를 표시합니다.

    checkValidity() 메서드

    <input id="id1" type="number" min="100" max="300" required>
    <button onclick="myFunction()">OK</button>

    <p id="demo"></p>

    <script>
    function myFunction() {
      const inpObj = document.getElementById("id1");
      if (!inpObj.checkValidity()) {
        document.getElementById("demo").innerHTML = inpObj.validationMessage;
      }
    }
    </script>

---

### 제약 조건 유효성 검사 DOM 속성

| Property          | Description                                                              |
| ----------------- | ------------------------------------------------------------------------ |
| validity          | Contains boolean properties related to the validity of an input element. |
| validationMessage | Contains the message a browser will display when the validity is false.  |
| willValidate      | Indicates if an input element will be validated.                         |

---

### 유효성 속성

입력 요소 의 유효성 속성 에는 데이터 유효성과 관련된 여러 속성이 포함됩니다.

| Property        | Description                                                              |
| --------------- | ------------------------------------------------------------------------ |
| customError     | Set to true, if a custom validity message is set.                        |
| patternMismatch | Set to true, if an element's value does not match its pattern attribute. |
| rangeOverflow   | Set to true, if an element's value is greater than its max attribute.    |
| rangeUnderflow  | Set to true, if an element's value is less than its min attribute.       |
| stepMismatch    | Set to true, if an element's value is invalid per its step attribute.    |
| tooLong         | Set to true, if an element's value exceeds its maxLength attribute.      |
| typeMismatch    | Set to true, if an element's value is invalid per its type attribute.    |
| valueMissing    | Set to true, if an element (with a required attribute) has no value.     |
| valid           | Set to true, if an element's value is valid.                             |

---

### 예시

    입력 필드의 숫자가 100(입력의 max 속성) 보다 크면 메시지를 표시합니다.

    rangeOverflow 속성

    <input id="id1" type="number" max="100">
    <button onclick="myFunction()">OK</button>

    <p id="demo"></p>

    <script>
    function myFunction() {
      let text = "Value OK";
      if (document.getElementById("id1").validity.rangeOverflow) {
        text = "Value too large";
      }
    }
    </script>

입력 필드의 숫자가 100(입력의 min속성) 보다 작은 경우 다음 메시지를 표시합니다.

    rangeUnderflow 속성

    <input id="id1" type="number" min="100">
    <button onclick="myFunction()">OK</button>

    <p id="demo"></p>

    <script>
    function myFunction() {
      let text = = "Value OK";
      if (document.getElementById("id1").validity.rangeUnderflow) {
        text = "Value too small";
      }
    }
    </script>
