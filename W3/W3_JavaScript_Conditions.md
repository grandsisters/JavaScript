## JavaScript if else and else if

조건문은 다른 조건에 따라 다른 작업을 수행하는 데 사용됩니다.

---

### 조건문

코드를 작성할 때 다양한 결정에 대해 다른 작업을 수행하려는 경우가 많습니다.

이를 수행하기 위해 코드에서 조건문을 사용할 수 있습니다.

JavaScript에는 다음과 같은 조건문이 있습니다.

- if를 사용하여지정된 조건에 해당하면 코드 블록을 지정할 수는 실행되는
- else를 사용하여 같은 조건이 거짓 인 경우 코드 블록을 지정할 수는 실행되는
- else if사용은 첫 번째 조건이 false 인 경우, 시험에 새로운 조건을 지정합니다
- switch실행할 많은 대체 코드 블록을 지정하는 데 사용

switch문은 다음 장에 설명되어 있습니다.

---

### if 문

if조건이 true인 경우 실행할 JavaScript 코드 블록을 지정 하려면 명령문을 사용하십시오 .

    통사론
    if (condition) {
      //  block of code to be executed if the condition is true
    }

if소문자로 되어 있으니 참고 하세요. 대문자(If 또는 IF)는 JavaScript 오류를 생성합니다.

    예시
    시간이 18:00 미만인 경우 "좋은 하루" 인사를 합니다.

    if (hour < 18) {
      greeting = "Good day";
    }

---

### else 문

else조건이 false인 경우 실행할 코드 블록을 지정 하려면 명령문을 사용하십시오 .

    if (condition) {
    // block of code to be executed if the condition is true
    } else {
    // block of code to be executed if the condition is false
    }


    예시
    시간이 18시 미만이면 "좋은 하루" 인사말을 만들고, 그렇지 않으면 "안녕히 가세요"를 만듭니다.

    if (hour < 18) {
    greeting = "Good day";
    } else {
    greeting = "Good evening";
    }

---

### else if 문

사용 else if첫 번째 조건이 false 인 경우 새 조건을 지정 문을.

    통사론
    if (condition1) {
    // block of code to be executed if condition1 is true
    } else if (condition2) {
    // block of code to be executed if the condition1 is false and condition2 is true
    } else {
    // block of code to be executed if the condition1 is false and condition2 is false
    }


    예시
    시간이 10:00 미만이면 "Good morning" 인사말을 만들고,
    그렇지 않으면 시간이 20:00 미만이면 "Good day" 인사말을 만들고,
    그렇지 않으면 "Good morning"을 만듭니다.

    if (time < 10) {
    greeting = "Good morning";
    } else if (time < 20) {
    greeting = "Good day";
    } else {
    greeting = "Good evening";
    }
