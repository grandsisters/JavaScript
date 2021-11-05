## JavaScript Forms

자바스크립트 양식 검증
HTML 양식 유효성 검사는 JavaScript로 수행할 수 있습니다.

양식 필드(fname)가 비어 있는 경우 이 함수는 메시지를 경고하고 false를 반환하여 양식이 제출되지 않도록 합니다.

    자바스크립트 예제
    function validateForm() {
    let x = document.forms["myForm"]["fname"].value;
    if (x == "") {
    alert("Name must be filled out");
    return false;
    }
    }

양식이 제출될 때 함수를 호출할 수 있습니다.

    HTML 양식 예

    <form name="myForm" action="/action_page.php" onsubmit="return validateForm()" method="post">
    Name: <input type="text" name="fname">
    <input type="submit" value="Submit">
    </form>

---

### 자동 HTML 양식 유효성 검사

HTML 양식 유효성 검사는 브라우저에서 자동으로 수행할 수 있습니다.

양식 필드(fname)가 비어 있으면 required속성으로 인해 이 양식이 제출되지 않습니다.

    HTML 양식 예

    <form action="/action_page.php" method="post">
      <input type="text" name="fname" required>
      <input type="submit" value="Submit">
    </form>

---

### 데이터 유효성 검사

데이터 유효성 검사는 사용자 입력이 깨끗하고 정확하며 유용한지 확인하는 프로세스입니다.

일반적인 검증 작업은 다음과 같습니다.

- 사용자가 모든 필수 필드를 채웠습니까?
- 사용자가 유효한 날짜를 입력했습니까?
- 사용자가 숫자 필드에 텍스트를 입력했습니까?

대부분의 경우 데이터 유효성 검사의 목적은 올바른 사용자 입력을 확인하는 것입니다.

유효성 검사는 다양한 방법으로 정의할 수 있으며 다양한 방식으로 배포할 수 있습니다.

서버 측 유효성 검사 는 입력이 서버로 전송된 후 웹 서버에서 수행됩니다.

클라이언트 측 유효성 검사 는 입력이 웹 서버로 전송되기 전에 웹 브라우저에서 수행됩니다.

---

### HTML 제약 조건 유효성 검사

HTML5는 제약 조건 유효성 검사 라는 새로운 HTML 유효성 검사 개념을 도입했습니다 .

HTML 제약 조건 유효성 검사는 다음을 기반으로 합니다.

- 제약 조건 유효성 검사 HTML 입력 속성
- 제약 조건 유효성 검사 CSS 의사 선택기
- 제약 조건 유효성 검사 DOM 속성 및 메서드

---

### 제약 조건 유효성 검사 HTML 입력 속성

| Attribute | Description                                         |
| --------- | --------------------------------------------------- |
| disabled  | Specifies that the input element should be disabled |
| max       | Specifies the maximum value of an input element     |
| min       | Specifies the minimum value of an input element     |
| pattern   | Specifies the value pattern of an input element     |
| required  | Specifies that the input field requires an element  |
| type      | Specifies the type of an input element              |

전체 목록을 보려면 [HTML 입력 속성](https://www.w3schools.com/html/html_form_attributes.asp) 으로 이동하십시오 .

---

### 제약 조건 유효성 검사 CSS 의사 선택기

| Selector  | Description                                                    |
| --------- | -------------------------------------------------------------- |
| :disabled | Selects input elements with the "disabled" attribute specified |
| :invalid  | Selects input elements with invalid values                     |
| :optional | Selects input elements with no "required" attribute specified  |
| :required | Selects input elements with the "required" attribute specified |
| :valid    | Selects input elements with valid values                       |

전체 목록을 보려면 [CSS Pseudo Classes](https://www.w3schools.com/css/css_pseudo_classes.asp) 로 이동하십시오 .
