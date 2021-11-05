## JavaScript - HTML DOM Methods

HTML DOM 메서드는 HTML 요소에서 수행할 수 있는 작업 입니다.

HTML DOM 속성은 설정하거나 변경할 수 있는 HTML 요소의 값 입니다.

---

### DOM 프로그래밍 인터페이스

HTML DOM은 JavaScript(및 기타 프로그래밍 언어)로 액세스할 수 있습니다.

DOM에서 모든 HTML 요소는 객체 로 정의됩니다 .

프로그래밍 인터페이스는 각 개체의 속성과 메서드입니다.

속성은 당신이 (HTML 요소의 내용을 변경하는 등) 가져 오거나 설정할 수있는 값입니다.

방법은 당신이 (추가 또는 HTML 요소를 삭제 등) 할 수있는 작업입니다.

    예시
    다음 예제는 <p>요소 의 내용(the innerHTML)을 id="demo"을 이용해 변경합니다 .

    예시
    <html>
    <body>

    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = "Hello World!";
    </script>

    </body>
    </html>

위의 예에서 getElementById는 메서드 이고 innerHTML는 속성 입니다.

---

### getElementById 메소드

HTML 요소에 액세스하는 가장 일반적인 방법은 id요소를 사용하는 것 입니다.

위의 예 에서 요소를 찾기위해 getElementById 메소드에 id="demo"을 사용하였습니다.

---

### innerHTML 속성

요소의 내용을 가져오는 가장 쉬운 방법은 innerHTML속성 을 사용하는 것 입니다.

이 innerHTML속성은 HTML 요소의 내용을 가져오거나 바꾸는 데 유용합니다.

innerHTML속성을 얻거나 포함한 모든 HTML 요소를 변경하는 데 사용할 수 있습니다 \<html>및 \<body>.
