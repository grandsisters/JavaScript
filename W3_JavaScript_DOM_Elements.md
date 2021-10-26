## JavaScript HTML DOM Elements

이 페이지에서는 HTML 페이지에서 HTML 요소를 찾고 액세스하는 방법을 설명합니다.

---

### HTML 요소 찾기

종종 JavaScript를 사용하여 HTML 요소를 조작하려고 합니다.

그러려면 먼저 요소를 찾아야 합니다. 이를 수행하는 방법에는 여러 가지가 있습니다.

- ID로 HTML 요소 찾기
- 태그 이름으로 HTML 요소 찾기
- 클래스 이름으로 HTML 요소 찾기
- CSS 선택기로 HTML 요소 찾기
- HTML 개체 컬렉션으로 HTML 요소 찾기

---

### ID로 HTML 요소 찾기

DOM에서 HTML 요소를 찾는 가장 쉬운 방법은 요소 ID를 사용하는 것입니다.

이 예에서는 다음을 사용하여 요소를 찾습니다 id="intro".

    예시
    const element = document.getElementById("intro");

요소가 발견되면 메서드는 요소를 객체로 반환합니다(myElement에서).

요소를 찾을 수 없으면 myElement에 가 포함 null됩니다.

---

### 태그 이름으로 HTML 요소 찾기

이 예에서는 모든 <p>요소 를 찾습니다 .

    예시
    const element = document.getElementsByTagName("p");

이 예에서는 id="main"가 있는 요소 \<p>를 찾은 다음 "main" 내부의 모든 요소 를 찾습니다 .

    예시
    const x = document.getElementById("main");
    const y = x.getElementsByTagName("p");

---

### 클래스 이름으로 HTML 요소 찾기

동일한 클래스 이름을 가진 모든 HTML 요소를 찾으려면 getElementsByClassName().
이 예는 가 있는 모든 요소의 목록을 반환합니다 class="intro".

    예시
    const x = document.getElementsByClassName("intro");

---

### CSS 선택기로 HTML 요소 찾기

지정된 CSS 선택자와 일치하는 모든 HTML 요소(id, 클래스 이름, 유형, 속성, 속성 값 등)를 찾으려면 querySelectorAll()메서드를 사용합니다 .
이 예는 가 있는 모든 \<p>요소 의 목록을 반환합니다 class="intro".

    예시
    const x = document.querySelectorAll("p.intro");

---

### HTML 개체 컬렉션으로 HTML 요소 찾기

이 예 id="frm1"에서는 양식 컬렉션에서 가 포함된 양식 요소를 찾고 모든 요소 값을 표시합니다.

    예시
    const x = document.forms["frm1"];
    let text = "";
    for (let i = 0; i < x.length; i++) {
    text += x.elements[i].value + "<br>";
    }
    document.getElementById("demo").innerHTML = text;

다음 HTML 개체(및 개체 컬렉션)에도 액세스할 수 있습니다.

- document.anchors
- document.body
- document.documentElement
- document.embeds
- document.forms
- document.head
- document.images
- document.links
- document.scripts
- document.title
