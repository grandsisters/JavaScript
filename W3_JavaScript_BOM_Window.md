## JavaScript Window - The Browser Object Model

BOM(브라우저 개체 모델)을 사용하면 JavaScript가 브라우저와 "대화"할 수 있습니다.

---

### 브라우저 개체 모델(BOM)

에 대한 공식적인 기준이 없습니다 B rowser O bject M ODEL (BOM)를.

최신 브라우저는 JavaScript 상호 작용에 대해 (거의) 동일한 메서드와 속성을 구현했기 때문에 BOM의 메서드 및 속성이라고 하는 경우가 많습니다.

---

### 창 개체

window객체는 모든 브라우저에서 지원됩니다. 브라우저의 창을 나타냅니다.

모든 전역 JavaScript 개체, 함수 및 변수는 자동으로 창 개체의 구성원이 됩니다.

전역 변수는 창 개체의 속성입니다.

전역 함수는 창 개체의 메서드입니다.

(HTML DOM의) 문서 객체조차도 창 객체의 속성입니다.

    window.document.getElementById("header");

아래와 같다:

    document.getElementById("header");

---

### 창 크기

두 가지 속성을 사용하여 브라우저 창의 크기를 결정할 수 있습니다.

두 속성 모두 크기를 픽셀 단위로 반환합니다.

- window.innerHeight - 브라우저 창의 내부 높이(픽셀 단위)
- window.innerWidth - 브라우저 창의 내부 너비(픽셀 단위)

브라우저 창(브라우저 뷰포트)에는 도구 모음과 스크롤바가 포함되어 있지 않습니다.

    예시
    let w = window.innerWidth;
    let h = window.innerHeight;

---

### 다른 창 방법

다른 방법:

- window.open() - 새 창 열기
- window.close() - 현재 창 닫기
- window.moveTo() - 현재 창 이동
- window.resizeTo() - 현재 창 크기 조정
