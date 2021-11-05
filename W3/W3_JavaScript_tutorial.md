## JavaScript Tutorial

---

### 자바 스크립트 소개

### JavaScript는 HTML 콘텐츠를 변경할 수 있습니다

getElementById()는 많은 JavaScript HTML 메소드 중 하나입니다.

아래 예는 HTML 요소(id="demo" 포함)를 "찾고" 요소 콘텐츠(innerHTML)를 "Hello JavaScript"로 변경합니다.

    예시
    document.getElementById("demo").innerHTML = "Hello JavaScript";

JavaScript는 큰따옴표와 작은따옴표를 모두 허용합니다.

    예시
    document.getElementById('demo').innerHTML = 'Hello JavaScript';

<br />

### JavaScript는 HTML 속성 값을 변경할 수 있습니다

이 예제에서 JavaScript src는 /<img>태그 의 (source) 속성 값을 변경합니다 .

[전구](w3schools.com/js/tryit.asp?filename=tryjs_intro_lightbulb)

<br />

### JavaScript는 HTML 스타일(CSS)을 변경할 수 있습니다.

HTML 요소의 스타일 변경은 HTML 속성 변경의 변형입니다.

    예시
    document.getElementById("demo").style.fontSize = "35px";

<br />

### JavaScript는 HTML 요소를 숨길 수 있습니다

display스타일 을 변경하여 HTML 요소를 숨길 수 있습니다 .

    예시
    document.getElementById("demo").style.display = "none";

<br />

### JavaScript는 HTML 요소를 표시할 수 있습니다

display스타일 을 변경하여 숨겨진 HTML 요소를 표시할 수도 있습니다 .

    예시
    document.getElementById("demo").style.display = "block";
