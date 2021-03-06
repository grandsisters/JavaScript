## 자바스크립트의 내장 객체

<br>

자바스크립트 내장 객체에는 웹 문서의 계층 구조와 상관없이 나타낼 수 있는 객체가 있다.

Array 객체와 Date 객체가 대표적이다.

이러한 내장 객체의 주요 프로퍼티와 메서드를 살펴보자.

***
### Array 객체

<br>

Array 객체는 자바스크립트의 여러 가지 객체 중에서 배열을 다룬다.

배열은 자바스크립트에서 자주 사용하는 자료형이므로 Array 객체의 주요 프로퍼티와 메서드를 잘 알고 사용하는 것이 중요하다.

<br>

### Array 객체로 배열 만들기

<br>

객체의 인스턴스를 만드는 방법으로 배열을 만들어 보자.

자바스크립트에는 배열을 쉽게 만들고 다룰 수 있는 Array 객체가 내장 되어 있다.

Array 객체를 사용하려면 먼저 인스턴스를 만들어야 한다.

먼저 초깃값이 없는 상태에서단순히 객체의 인스턴스만 만든다면 new d예약어를 사용해 변수에 할당하면 된다.

이때 다음과 같이 배열의 크기를 지정하지 않을 수도 있고,

몇개의 요소가 있는지 크기를 지정할 수도 있다.

[Array 객체 인스턴스 만들기 = 초깃값이 없는 경우](./Doit_JavaScript_day27-1.html)

또한 초깃값이 있는 배열이라면 당므과 같이 인스턴스 선언과 요솟값을 한번에 할당해 작성 할 수 있다.

[Array 객체 인스턴스 만들기 - 초깃값이 있는 경우](./Doit_JavaScript_day27-1.html)

<br>

### Array 객체의 length 프로퍼티 사용하기

<br>

배열 요소는 프로그램 안에서 얼마든지 추가하거나 삭제할 수 있으므로 요소의 개수를 알고 사용하는 것이 좋다.

그렇다면 배열 요소의 개수는 어떻게 알 수 있을까?

바로 Array 객체에 있는 length 프로퍼티를 사용하면 된다.

이 프로퍼티에는 배열 요소의 개수가 저장되어 있다.

다음과 같이 마침표를 사용해 length 프로퍼티를 작성한다.

그리고 for 문을 이용하여 전체 배열의 요솟값을 나열한다.

[배열을 만들고 요소 표시하기](./Doit_JavaScript_day27-3.html)