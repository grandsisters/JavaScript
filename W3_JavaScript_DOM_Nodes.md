## JavaScript HTML DOM Elements (Nodes)

노드 추가 및 제거(HTML 요소)

---

### 새 HTML 요소 만들기(노드)

HTML DOM에 새 요소를 추가하려면 먼저 요소(요소 노드)를 만든 다음 기존 요소에 추가해야 합니다.

예시

    <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

    <script>
    const para = document.createElement("p");
    const node = document.createTextNode("This is new.");
    para.appendChild(node);

    const element = document.getElementById("div1");
    element.appendChild(para);
    </script>

---

### 예시 설명

이 코드는 새 \<p>요소를 만듭니다 .

    const para = document.createElement("p");

\<p>요소 에 텍스트를 추가하려면 먼저 텍스트 노드를 만들어야 합니다. 이 코드는 텍스트 노드를 생성합니다:

    const node = document.createTextNode("This is a new paragraph.");

그런 다음 \<p>요소에 텍스트 노드를 추가해야 합니다 .

    para.appendChild(node);

마지막으로 새 요소를 기존 요소에 추가해야 합니다.

이 코드는 기존 요소를 찾습니다.

    const element = document.getElementById("div1");

이 코드는 새 요소를 기존 요소에 추가합니다.

    element.appendChild(para);

---

### 새 HTML 요소 만들기 - insertBefore()

appendChild()메서드는 새 요소를 부모의 마지막 자식으로 추가했습니다.

그것을 원하지 않으면 insertBefore() 메소드를 사용할 수 있습니다 .

    예시

    <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

    <script>
    const para = document.createElement("p");
    const node = document.createTextNode("This is new.");
    para.appendChild(node);

    const element = document.getElementById("div1");
    const child = document.getElementById("p1");
    element.insertBefore(para, child);
    </script>

---

### 기존 HTML 요소 제거

HTML 요소를 제거하려면 다음 remove() 방법을 사용하십시오 .

    예시

    <div>
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

    <script>
    const elmnt = document.getElementById("p1"); elmnt.remove();
    </script>

---

### 예시 설명

HTML 문서에는 \<div>2개의 자식 노드(2개의 \<p> 요소) 가 있는 요소가 포함되어 있습니다 .

    <div>
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

제거하려는 요소를 찾습니다.

    const elmnt = document.getElementById("p1");

그런 다음 해당 요소에서 remove() 메서드를 실행합니다.

    elmnt.remove();

이 remove()방법은 이전 브라우저에서는 작동하지 않습니다.

대신 removeChild()을 사용하여 지우는 방법을 이용하세요.

아래 예를 참조하세요 .

---

### 자식 노드 제거

remove()방법을 지원하지 않는 브라우저의 경우 요소를 제거하려면 부모 노드를 찾아야 합니다.

    예시

    <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

    <script>
    const parent = document.getElementById("div1");
    const child = document.getElementById("p1");
    parent.removeChild(child);
    </script>

---

### 예시 설명

이 HTML 문서에는 \<div>2개의 하위 노드(2개의 \<p> 요소) 가 있는 요소가 포함되어 있습니다 .

    <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

다음을 사용하여 요소를 찾으십시오 id="div1".

    const parent = document.getElementById("div1");

다음을 사용하여 \<p>요소를 찾으십시오 id="p1".

    const child = document.getElementById("p1");

부모에서 자식을 제거합니다.

    parent.removeChild(child);

일반적인 해결 방법은 다음과 같습니다. 제거하려는 자식 parentNode을 찾고 해당 속성을 사용 하여 부모를 찾습니다.

    const child = document.getElementById("p1");
    child.parentNode.removeChild(child);

---

### HTML 요소 교체

요소를 HTML DOM으로 바꾸려면 다음 replaceChild()방법을 사용하십시오 .

    예시

    <div id="div1">
      <p id="p1">This is a paragraph.</p>
      <p id="p2">This is another paragraph.</p>
    </div>

    <script>
    const para = document.createElement("p");
    const node = document.createTextNode("This is new.");
    para.appendChild(node);

    const parent = document.getElementById("div1");
    const child = document.getElementById("p1");
    parent.replaceChild(para, child);
    </script>
