## 한눈에 정리하기

***
### DOM 트리의 노드

- 요소 노드 : 모든 HTML 태그를 의미한다.
- 텍스트 노드 : 태그의 텍스트 내용이다.
- 속성 노드 : 태그의 속성이다.
- 주석 노드 : 주석이다.

***
### DOM에 접근하기

- getElementById(id) : id명으로 접근한다.
- getElementsByClassName(class) : 클래스명으로 접근하면 여러 요소가 배열 형태로 저장된다. 
- getElementsByTagName(tag) : 태그명으로 접근하며 여러 요소가 배열 형태로 저장된다.
- querySelector() : id명이나 선택자를 사용해 접근한다.
- querySelectorAll() : 클래스명이나 태그명의 선택자를 사용해 접근한다. 여러 노드가 노드 리스트 형태로 저장된다.

<br>

- 속성 가져오기 및 수정하기

    - getAttribute(속성) : 태그에서 사용한 속성값을 가져옴
    
    - setAttribute(속성, 값) : 태그의 속성을 특정한 값으로 지정함

- 이벤트 처리하기

    - 요소.addEventListener(이벤트, 함수, 캡쳐 여부)

- CSS 속성에 접근하기

    - document.요소명.style.속성명

***
### 텍스트 노드를 사용하는 새로운 요소 추가하기

|순서|메서드|설명|
|-|-|-|
|1|createElement()|새로운 요소 노드를 만든다.|
|2|createTextNode()|새로운 텍스트 노드를 만든다.|
|3|appendChild()|텍스트 노드를 요소 노드의 자식으로 연결한다.|
|4|appendChild()|요소 노드를 DOM에 연결한다.|

***
### 속성값이 있는 새로운 요소 추가하기

|순서|메서드|설명|
|-|-|-|
|1|createElement()|새로운 요소 노드를 추가한다.|
|2|createAttribute()|새로운 속성 노드를 추가한다.|
|3|속성값 지정하기|속성값을 프로퍼티로 지정한다.|
|4|setAttributeNode()|속성 노드를 요소 노드의 자식으로 연결한다.|
|5|appendChild()|요소 노드를 DOM에 연결한다.|

***
### 노드 삭제

parentNode 프로퍼티로 부모 노드를 찾아서 부모 노드에서 삭제한다.

    부모노드.removeChild(자식 노드)


