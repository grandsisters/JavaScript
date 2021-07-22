## Dom을 이용한 이벤트 처리기

HTML 요소에 이벤트 처리기를 지정하면 태그 속성과 자바스크립트 소스가 섞인다.

그래서 자바스크립트를 수정하려면 HTML의 태그와 속성을 하나씩 찾아봐야 한다.

하지만 DOM을 이용하여 이벤트 처리기를 지정하면 태그와 자바스크립트 소스를 분리해서 보기 좋게 사용할 수 있다.

<br>

지금까지 이벤트 처리기를 지정하는 방법은 HTML이 주인이 되어 자바스크립트의 함수를 불러와서 사용했다.

하지만 DOM을 사용하면 자바스크립트가 주인이 되어 HTML의 요소를 가져와서 이벤트 처리기를 연결한다.

HTML과 자바스크립트 중에서 어느 쪽을 중심으로 잡는가에 따라 지정하는 방법이 다르다는 것을 알면 된다.

<br>

예를 들어 웹 요소를 클릭했을 때 실행할 함수를 연결하려면 다음과 같은 기본 형식으로 사용한다.

    - 기본형

    웹 요소.onclick = 함수;

자바스크립트에서는 웹 요소를 여러 방법으로 가져올 수 있는데 그중에서 함수 querySelector()를 사용하여 가죠오는 것이 쉽다.

querySelector의 괄호 안에는 클래스 이름이나 id 이름 또는 다양한 선택자를 넣을 수 있다.

다음은 id='change'인 버튼을 클릭했을 때 글자색을 바꾸는 예제이다.

querySelector()를 사용해 버튼 요소를 가져오고 변수 changeBttn에 저장한다.

그리고 changeBttn에 onclick을 사용해 changeColor() 함수를 연결한다.

이때 주의할 점은 함수의 이름만 사용하고 괄호는 붙이지 않아야 한다는 것이다.

[버튼 클릭해서 글자색 바꾸기](./Doit_JavaScript_day24-1.html)

앞의 스크립트 코드는 조금 다르게 표현할 수도 있다.

웹 요소를 프로그램 안에서 여러번 사용하지 않는다면 다음과 같이 변수에 할당하지 않고 직접 사용해도 된다.

[버튼 클릭해서 글자색 바꾸기2](./Doit_JavaScript_day24-2.html)

또는 함수를 딱 한 번만 사용한다면 위 코드에서 changeColor라는 함수 이름이 들어갔던 자리에 직접 함수를 선언해도 된다.

[버튼 클릭해서 글자색 바꾸기3](./Doit_JavaScript_day24-3.html)

지금부터 이 예제를 DOM을 이용한 이벤트 처리 방식으로 수정해 보자

이렇게 수정하면 자바스크립트 소스와 HTML 마크업을 분리해서 이벤트를 제어할 수 있다.

[버튼 클릭해서 설명 글 열고 닫기 - DOM 이벤트 처리기 연결](./Doit_JavaScript_day24-4.html)