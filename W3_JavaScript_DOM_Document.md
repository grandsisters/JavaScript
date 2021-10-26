## JavaScript HTML DOM Document

HTML DOM 문서 개체는 웹 페이지에 있는 다른 모든 개체의 소유자입니다.

---

### HTML DOM 문서 객체

문서 개체는 웹 페이지를 나타냅니다.

HTML 페이지의 요소에 액세스하려면 항상 문서 개체에 액세스하는 것으로 시작합니다.

다음은 문서 개체를 사용하여 HTML에 액세스하고 조작하는 방법에 대한 몇 가지 예입니다.

---

### HTML 요소 찾기

| Method                                | Description                   |
| ------------------------------------- | ----------------------------- |
| document.getElementById(id)           | Find an element by element id |
| document.getElementsByTagName(name)   | Find elements by tag name     |
| document.getElementsByClassName(name) | Find elements by class name   |

---

### HTML 요소 변경

| Property                               | Description                                   |
| -------------------------------------- | --------------------------------------------- |
| element.innerHTML = new html           | content Change the inner HTML of an element   |
| element.attribute = new value          | Change the attribute value of an HTML element |
| element.style.property = new style     | Change the style of an HTML element           |
| Method                                 | Description                                   |
| element.setAttribute(attribute, value) | Change the attribute value of an HTML element |

---

### 요소 추가 및 삭제

| Method                          | Description                       |
| ------------------------------- | --------------------------------- |
| document.createElement(element) | Create an HTML element            |
| document.removeChild(element)   | Remove an HTML element            |
| document.appendChild(element)   | Add an HTML element               |
| document.replaceChild(new, old) | Replace an HTML element           |
| document.write(text)            | Write into the HTML output stream |

---

### 이벤트 핸들러 추가

| Method                                                 | Description                                   |
| ------------------------------------------------------ | --------------------------------------------- |
| document.getElementById(id).onclick = function(){code} | Adding event handler code to an onclick event |

---

### HTML 개체 찾기

첫 번째 HTML DOM 레벨 1(1998)은 11개의 HTML 개체, 개체 컬렉션 및 속성을 정의했습니다. HTML5에서는 여전히 유효합니다.

나중에 HTML DOM 레벨 3에서 더 많은 개체, 컬렉션 및 속성이 추가되었습니다.

| Property                     | Description                                              | DOM |
| ---------------------------- | -------------------------------------------------------- | --- |
| document.anchors             | Returns all \<a> elements that have a name attribute     | 1   |
| document.applets             | Deprecated                                               | 1   |
| document.baseURI             | Returns the absolute base URI of the document            | 3   |
| document.body                | Returns the \<body> element                              | 1   |
| document.cookie              | Returns the document's cookie                            | 1   |
| document.doctype             | Returns the document's doctype                           | 3   |
| document.documentElement     | Returns the \<html> element                              | 3   |
| document.documentMode        | Returns the mode used by the browser                     | 3   |
| document.documentURI         | Returns the URI of the document                          | 3   |
| document.domain              | Returns the domain name of the document server           | 1   |
| document.domConfig           | Obsolete.                                                | 3   |
| document.embeds              | Returns all \<embed> elements                            | 3   |
| document.forms               | Returns all \<form> elements                             | 1   |
| document.head                | Returns the \<head> element                              | 3   |
| document.images              | Returns all \<img> elements                              | 1   |
| document.implementation      | Returns the DOM implementation                           | 3   |
| document.inputEncoding       | Returns the document's encoding (character set)          | 3   |
| document.lastModified        | Returns the date and time the document was updated       | 3   |
| document.links Returns       | all \<area> and \<a> elements that have a href attribute | 1   |
| document.readyState          | Returns the (loading) status of the document             | 3   |
| document.referrer            | Returns the URI of the referrer (the linking document)   | 1   |
| document.scripts             | Returns all \<script> elements                           | 3   |
| document.strictErrorChecking | Returns if error checking is enforced                    | 3   |
| document.title               | Returns the \<title> element                             | 1   |
| document.URL                 | Returns the complete URL of the document                 | 1   |
