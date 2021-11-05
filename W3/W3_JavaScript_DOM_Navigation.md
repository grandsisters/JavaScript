## JavaScript HTML DOM Navigation

HTML DOM을 사용하면 노드 관계를 사용하여 노드 트리를 탐색할 수 있습니다.

---

### DOM 노드

W3C HTML DOM 표준에 따르면 HTML 문서의 모든 것은 노드입니다.

- 전체 문서는 문서 노드입니다.
- 모든 HTML 요소는 요소 노드입니다.
- HTML 요소 내부의 텍스트는 텍스트 노드입니다.
- 모든 HTML 속성은 속성 노드입니다(더 이상 사용되지 않음).
- 모든 주석은 주석 노드입니다.

<img src='https://www.w3schools.com/js/pic_htmltree.gif'>

HTML DOM을 사용하면 노드 트리의 모든 노드에 JavaScript로 액세스할 수 있습니다.

새 노드를 생성할 수 있으며 모든 노드를 수정하거나 삭제할 수 있습니다.

---

### 노드 관계

노드 트리의 노드는 서로 계층적 관계를 갖습니다.

부모, 자식 및 형제라는 용어는 관계를 설명하는 데 사용됩니다.

- 노드 트리에서 최상위 노드를 루트(또는 루트 노드)라고 합니다.
- 모든 노드에는 루트(부모가 없음)를 제외하고 정확히 하나의 부모가 있습니다.
- 노드는 여러 자식을 가질 수 있습니다.
- 형제자매(형제자매)는 부모가 같은 노드입니다.

      <html>
        <head>
          <title>DOM Tutorial</title>
        </head>

        <body>
          <h1>DOM Lesson one</h1>
          <p>Hello world!</p>
        </body>

      </html>

위의 HTML에서 다음을 읽을 수 있습니다.

    <html> 루트 노드입니다
    <html> 부모가 없다
    <html>의 부모 <head>이며<body>
    <head> 의 첫 번째 자녀입니다. <html>
    <body> 의 마지막 아이입니다 <html>

그리고:

    <head> 자녀가 한 명 있습니다: <title>
    <title> 자식이 하나 있습니다(텍스트 노드): "DOM Tutorial"
    <body>두 아이가 있습니다 <h1>및<p>
    <h1> 자녀가 하나 있습니다: "DOM Lesson 1"
    <p> 자녀가 한 명 있습니다. "Hello world!"
    <h1>그리고 <p>형제다

---

### 노드 간 탐색

다음 노드 속성을 사용하여 JavaScript로 노드 간을 탐색할 수 있습니다.

- parentNode
- childNodes[nodenumber]
- firstChild
- lastChild
- nextSibling
- previousSibling

---

### 자식 노드 및 노드 값

DOM 처리의 일반적인 오류는 요소 노드에 텍스트가 포함될 것으로 예상하는 것입니다.

    예시:
    <title id="demo">DOM Tutorial</title>

요소 노드 \<title>(위의 예에서) 에는 텍스트 가 포함되어 있지 않습니다 .

여기에는 값이 "DOM Tutorial"인 텍스트 노드 가 포함 됩니다.

텍스트 노드의 값은 노드의 innerHTML속성 으로 액세스할 수 있습니다 .

    myTitle = document.getElementById("demo").innerHTML;

innerHTML 속성에 액세스하는 nodeValue 것은 첫 번째 자식에 액세스하는 것과 동일합니다 .

    myTitle = document.getElementById("demo").firstChild.nodeValue;

첫 번째 자식에 액세스하는 것도 다음과 같이 수행할 수 있습니다.

    myTitle = document.getElementById("demo").childNodes[0].nodeValue;

다음의 모든 (3) 예는 \<h1>요소 의 텍스트를 검색하여 요소에 복사합니다 \<p>.

    예시 1
    <html>
    <body>

    <h1 id="id01">My First Page</h1>
    <p id="id02"></p>

    <script>
    document.getElementById("id02").innerHTML = document.getElementById("id01").innerHTML;
    </script>

    </body>
    </html>

<br />

    예시 2
    <html>
    <body>

    <h1 id="id01">My First Page</h1>
    <p id="id02"></p>

    <script>
    document.getElementById("id02").innerHTML = document.getElementById("id01").firstChild.nodeValue;
    </script>

    </body>
    </html>

<br />

    예시 3
    <html>
    <body>

    <h1 id="id01">My First Page</h1>
    <p id="id02">Hello!</p>

    <script>
    document.getElementById("id02").innerHTML = document.getElementById("id01").childNodes[0].nodeValue;
    </script>

    </body>
    </html>

---

### 내부HTML

이 자습서에서는 innerHTML 속성을 사용하여 HTML 요소의 내용을 검색합니다.

그러나 위의 다른 방법을 배우는 것은 트리 구조와 DOM 탐색을 이해하는 데 유용합니다.

---

### DOM 루트 노드

전체 문서에 대한 액세스를 허용하는 두 가지 특수 속성이 있습니다.

- document.body - 문서의 본문
- document.documentElement - 전체 문서

  <br />

        예시

        <html>
        <body>

        <h2>JavaScript HTMLDOM</h2>
        <p>Displaying document.body</p>

        <p id="demo"></p>

        <script>
        document.getElementById("demo").innerHTML = document.body.innerHTML;
        </script>

        </body>
        </html>

<br />

    예시

    <html>
    <body>

    <h2>JavaScript HTMLDOM</h2>
    <p>Displaying document.documentElement</p>

    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = document.documentElement.innerHTML;
    </script>

    </body>
    </html>

---

### nodeName 속성

nodeName속성은 노드의 이름을 지정합니다.

- nodeName은 읽기 전용입니다.
- 요소 노드의 nodeName은 태그 이름과 동일합니다.
- 속성 노드의 nodeName은 속성 이름입니다.
- 텍스트 노드의 nodeName은 항상 #text입니다.
- 문서 노드의 nodeName은 항상 #document입니다.

      예시

        <h1 id="id01">My First Page</h1>
        <p id="id02"></p>

        <script>
        document.getElementById("id02").innerHTML = document.getElementById("id01").nodeName;
        </script>

참고: nodeName 항상 HTML 요소의 대문자 태그 이름을 포함합니다.

---

### nodeValue 속성

nodeValue속성은 노드의 값을 지정한다.

- 요소 노드의 nodeValue는 null
- 텍스트 노드의 nodeValue는 텍스트 자체입니다.
- 속성 노드의 nodeValue는 속성 값입니다.

---

### nodeType 속성

nodeType속성은 읽기 전용입니다. 노드의 유형을 반환합니다.

    예시

    <h1 id="id01">My First Page</h1>
    <p id="id02"></p>

    <script>
    document.getElementById("id02").innerHTML = document.getElementById("id01").nodeType;
    </script>

가장 중요한 nodeType 속성은 다음과 같습니다.

| Node               | Type | Example                                          |
| ------------------ | ---- | ------------------------------------------------ |
| ELEMENT_NODE       | 1    | \<h1 class="heading">W3Schools\</h1>             |
| ATTRIBUTE_NODE     | 2    | class = "heading" (deprecated)                   |
| TEXT_NODE          | 3    | W3Schools                                        |
| COMMENT_NODE       | 8    | \<!-- This is a comment -->                      |
| DOCUMENT_NODE      | 9    | The HTML document itself (the parent of \<html>) |
| DOCUMENT_TYPE_NODE | 10   | \<!Doctype html>                                 |

유형 2는 HTML DOM에서 더 이상 사용되지 않지만 작동합니다. XML DOM에서는 더 이상 사용되지 않습니다.
