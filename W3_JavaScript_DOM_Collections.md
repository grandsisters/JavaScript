## JavaScript HTML DOM Collections

---

### HTMLCollection 객체

getElementsByTagName()메서드는 HTMLCollection객체를 반환.

HTMLCollection객체는 HTML 요소의 배열과 같은리스트 (콜렉션)이다.

다음 코드는 \<p>문서의 모든 요소를 선택합니다 .

    예시
    const myCollection = document.getElementsByTagName("p");

컬렉션의 요소는 인덱스 번호로 액세스할 수 있습니다.

두 번째 \<p> 요소에 액세스하려면 다음과 같이 작성할 수 있습니다.

    myCollection[1]

참고: 인덱스는 0에서 시작합니다.

---

### HTML HTML컬렉션 길이

length속성은 요소의 수를 정의합니다 HTMLCollection:

    예시
    myCollection.length

이 length속성은 컬렉션의 요소를 반복할 때 유용합니다.

    예시
    모든 <p> 요소의 텍스트 색상 변경:

    const myCollection = document.getElementsByTagName("p");
    for (let i = 0; i < myCollection.length; i++) {
    myCollection[i].style.color = "red";
    }

HTMLCollection은 배열이 아닙니다!

HTMLCollection은 배열처럼 보이지만 그렇지 않습니다.

목록을 반복하고 배열과 마찬가지로 숫자가 있는 요소를 참조할 수 있습니다.

그러나 HTMLCollection에서는 valueOf(), pop(), push() 또는 join()과 같은 배열 메서드를 사용할 수 없습니다.
