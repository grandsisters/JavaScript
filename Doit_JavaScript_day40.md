## DOM에서 이벤트 처리하기

***
### addEventListener() 메서드 사용하기

<br>

지금까지 살펴본 이벤트 처리기는 한 요소에 하나의 이벤트 처리기만 연결할 수 있다.

하지만 다음과 같이 addEventListener() 메서드와 event 객체를 사용하면 한 요소에 여러 이벤트 처리기를 연결해 실행할 수 있다.

addEventListener() 메서드는 끝에 세미콜론(;)을 꼭 붙여야 한다.

    - 기본형

    요소.addEventListener(이벤트, 함수, 캡처 여부);

1) 이벤트 : 이벤트 유형을 지정한다. 단, click과 keypress 처럼 on을 붙이지 않고 쓴다.

2) 함수 : 이벤트가 발생하면 실행할 명령이나 함수를 지정한다. 여기에서 함수를 정의할 떄는 event 객체를 인수로 받는다.

3) 캡처 여부 : 이벤트를 캡처하는지 여부를 지정하며 기본값은 false이고 true와 false 중에서 선택할 수 있다. true이면 캡처링, false이면 버블링 한다는 의미이다. 이벤트 캡처링은 DOM의 부모 노드에서 자식 노드로 전달되는 것이고, 이벤트 버블링은 DOM의 자식 노드에서 부모 노드로 전달되는 것이다.

다음은 이미지 위로 마우스 포인터를 올려놓으면 다른 이미지로 바뀌었다가 내려놓으면 다시 원래 이미지로 돌아오는 예제이다.

addEventListener() 메서드를 사용해서 changePic() 함수와 originPic() 함수를 이벤트 처리기로 사용한다.

[마우스 포인터를 올리면 이미지 바꾸기](./Doit_JavaScript_day40-1.html)

이 예제에서는 함수 changePic()과 originPic()을 따로 선언하고 사용했다.

하지만 단순히 이벤트를 처리하는 함수라면, 즉 따로 다른 곳에서 다시 사용하는 함수가 아니라면 다음처럼 메서드 안에서 함수 표현식으로 사용하는 경우가 많다.

<img src='./img/JS19.jpg'>

addEventListener() 메서드에서 changePic() 함수가 있던 자리에 함수 선언 부분을 그대로 옮기면 되는데, 이때 함수명은 제외한다.

마찬가지로 originPic() 함수도 옮긴다.

[메서드 안에서 함수 선언하기](./Doit_JavaScript_day40-2.html)

이렇게 addEventListener() 메서드 안에 함수를 함께 선언하면 특정 이벤트에서 어떤 명령을 실행하는지 한눈에 확인할 수 있어서 더욱 편리하다.

***
### CSS 속성에 접근하기

<br>

자바스크립트를 이용하면 스타일 속성값을 가져와서 그 값을 원하는 대로 수정할 수 있다.

자바스크립트에서는 각 요소의 스타일을 자유롭게 수정할 수 있으므로 웹 문서에서 다양한 효과를 만들 수 있다.

CSS 속성에 접근하려면 해당 스타일이 적용된 HTML 요소 다음에 예약어 style을 쓰고 속성을 적는다.

    - 기본형

    document.요소명.style.속성명

예를 들어 id가 desc인 요소를 사용하는 모든 태그의 글자를 파란색으로 변경하려면 다음과 같이 작성한다.

[id가 desc인 요소의 글자색 바꾸기](./Doit_JavaScript_day40-3.html)

이렇게 color처럼 한 단어인 속성명은 그대로 사용하면 되지만 

background-color, border-radius처럼 중간에 하이픈(-)이 있는 속성은 

backgroundColor나 borderRadius처럼 두 단어를 합쳐서 사용한다.

이때 두 번째 단어의 첫 글자는 Color와 Radius처럼 대문자로 표시한다.

<br>

다음은 사각형 위에 마우스 포인터를 올려놓으면 초록색 원으로 바뀌고, 내려놓으면 원래 도형으로 되돌아가는 예제이다.

자바스크립트에서 이미지의 background-color, border-radius 속성을 다루는 방법을 잘 살펴보자.

[도형의 테두리와 배경색 바꾸기](./Doit_JavaScript_day40-4.html)



