## JavaScript Popup Boxes

JavaScript에는 경고 상자, 확인 상자 및 프롬프트 상자의 세 가지 종류의 팝업 상자가 있습니다.

---

### alert box

정보가 사용자에게 전달되었는지 확인하려는 경우 경고 상자가 자주 사용됩니다.

경고 상자가 나타나면 사용자는 "확인"을 클릭하여 계속 진행해야 합니다.

    sytax
    window.alert("sometext");

window.alert()방법은 윈도우 접두사없이 작성 할 수 있습니다.

    예시
    alert("I am an alert box!");

---

### Confirm box

확인 상자는 사용자가 무언가를 확인하거나 수락하도록 하려는 경우에 자주 사용됩니다.

확인 상자가 나타나면 사용자는 "확인" 또는 "취소"를 클릭하여 계속 진행해야 합니다.

사용자가 "확인"을 클릭하면 상자가 true 를 반환 합니다 . 사용자가 "취소"를 클릭하면 상자가 false 를 반환합니다 .

    sytax
    window.confirm("sometext");

window.confirm()방법은 윈도우 접두사없이 작성 할 수 있습니다.

    예시
    if (confirm("Press a button!")) {
      txt = "You pressed OK!";
    } else {
      txt = "You pressed Cancel!";
    }

---

### Prompt Box

사용자가 페이지를 입력하기 전에 값을 입력하도록 하려면 프롬프트 상자가 자주 사용됩니다.

프롬프트 상자가 팝업되면 사용자는 입력 값을 입력한 후 "확인" 또는 "취소"를 클릭하여 계속 진행해야 합니다.

사용자가 "확인"을 클릭하면 상자가 입력 값을 반환합니다. 사용자가 "취소"를 클릭하면 상자가 null을 반환합니다.

    sytax
    window.prompt("sometext","defaultText");

window.prompt()방법은 윈도우 접두사없이 작성 할 수 있습니다.

    예시
    let person = prompt("Please enter your name", "Harry Potter");
    let text;
    if (person == null || person == "") {
      text = "User cancelled the prompt.";
    } else {
      text = "Hello " + person + "! How are you today?";
    }

---

### Line Breaks

팝업 상자 안에 줄 바꿈을 표시하려면 백슬래시 다음에 문자 n을 사용하십시오.

    예시
    alert("Hello\nHow are you?");
