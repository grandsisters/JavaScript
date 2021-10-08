## JavaScript Template Literals

    동의어:

    - 템플릿 리터럴
    - 템플릿 문자열
    - 문자열 템플릿
    - 백틱 구문

---

### 백틱 구문

템플릿 리터럴 은 따옴표("") 대신 역따옴표(``)를 사용하여 문자열을 정의합니다.

    예시
    let text = `Hello World!`;

---

### 문자열 안의 따옴표

함께 템플릿 리터럴 , 당신은 문자열 내부의 단일 및 이중 따옴표를 사용할 수 있습니다 :

    예시
    let text = `He's often called "Johnny"`;

---

### 여러 줄 문자열

템플릿 리터럴 은 여러 줄 문자열을 허용합니다.

    let text =
    `The quick
    brown fox
    jumps over
    the lazy dog`;

---

### 보간

템플릿 리터럴 은 변수와 표현식을 문자열로 보간하는 쉬운 방법을 제공합니다.

이 방법을 문자열 보간이라고 합니다.

구문은 다음과 같습니다.

    ${...}

---

### 변수 대체

템플릿 리터럴 은 문자열에 변수를 허용합니다.

    예시
    let firstName = "John";
    let lastName = "Doe";

    let text = `Welcome ${firstName}, ${lastName}!`;

변수를 실제 값으로 자동 교체하는 것을 문자열 보간 이라고 합니다 .

---

### 표현식 대체

템플릿 리터럴 은 문자열에서 표현식을 허용합니다.

    예시
    let price = 10;
    let VAT = 0.25;

    let total = `Total: ${(price * (1 + VAT)).toFixed(2)}`;

표현식을 실제 값으로 자동 교체하는 것을 문자열 보간 이라고 합니다 .

---

### HTML 템플릿

    예시
    let header = "Templates Literals";
    let tags = ["template literals", "javascript", "es6"];
    let html = `<h2>${header}</h2><ul>`;

    for (const x of tags) {
    html += `<li>${x}</li>`;
    }

    html += `</ul>`;
