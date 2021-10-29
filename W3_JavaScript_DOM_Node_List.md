## JavaScript HTML DOM Node Lists

---

### HTML DOM NodeList 객체

NodeList대상 문서로부터 추출 된 노드의 목록 (회수)이다.

NodeList 객체는 HTMLCollection객체와 거의 동일하다.

일부 (구) 브라우저는 getElementsByClassName()과 같은 메소드에 대해 HTMLCollection 대신 NodeList 개체를 반환합니다.

모든 브라우저는 속성 childNodes에 대한 NodeList 개체를 반환합니다.

대부분의 브라우저는 querySelectorAll() 메서드에 대한 NodeList 개체를 반환합니다.

다음 코드는 \<p>문서의 모든 노드를 선택합니다 .

    예시
    const myNodeList = document.querySelectorAll("p");

NodeList의 요소는 인덱스 번호로 액세스할 수 있습니다.

두 번째 \<p> 노드에 액세스하려면 다음을 작성할 수 있습니다.

    myNodeList[1]

참고: 인덱스는 0에서 시작합니다.

---

### HTML DOM 노드 목록 길이

length속성은 노드 목록에 노드의 수를 정의합니다 :

    예시
    myNodelist.length

이 length속성은 노드 목록의 노드를 반복할 때 유용합니다.

예시- 노드 목록에서 모든 \<p> 요소의 색상을 변경합니다.

    const myNodelist = document.querySelectorAll("p");
    for (let i = 0; i < myNodelist.length; i++) {
    myNodelist[i].style.color = "red";
    }

---

### HTMLCollection과 NodeList의 차이점

HTMLCollection(이전 장) HTML 요소의 모음입니다.

A NodeList는 문서 노드의 모음입니다.

NodeList와 HTML 컬렉션은 거의 같은 것입니다.

HTMLCollection 개체와 NodeList 개체는 모두 배열과 같은 개체 목록(컬렉션)입니다.

둘 다 목록(컬렉션)의 항목 수를 정의하는 길이 속성이 있습니다.

둘 다 배열처럼 각 항목에 액세스하기 위해 인덱스(0, 1, 2, 3, 4, ...)를 제공합니다.

HTMLCollection 항목은 이름, ID 또는 색인 번호로 액세스할 수 있습니다.

NodeList 항목은 인덱스 번호로만 액세스할 수 있습니다.

NodeList 개체만 속성 노드와 텍스트 노드를 포함할 수 있습니다.

노드 목록은 배열이 아닙니다!

노드 목록은 배열처럼 보이지만 그렇지 않습니다.

노드 목록을 반복하고 배열처럼 해당 노드를 참조할 수 있습니다.

그러나 노드 목록에서 valueOf(), push(), pop() 또는 join()과 같은 배열 메서드를 사용할 수 없습니다.
