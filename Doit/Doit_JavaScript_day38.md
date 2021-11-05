## DOM 요소에 접근하고 속성 가져오기

<br>

웹 문서에서 사용한 여러 이미지 가운데 하나만 골라서 크기를 바꾸려면 콕 집어 지정할 수 있어야 한다.

이렇게 웹 문서에서 원하는 요소를 찾아가는 것을 '접근한다'고 한다.

여기에서는 자바스크립트를 사용해 DOM에 접근하는 몇 가지 방법을 알아보자.

***
### DOM에 접근하기

<br>

CSS에서는 class, id, 태그 등의 스타일을 각각 구별해서 정의해야 한다.

이때 class, id, 태그 등을 선택자(selector)라고 하는데,

이 선택자를 사용해서 DOM에 접근하는 방법을 알아보자.

HTML 요소란 img태그를 사용한 이미지나 p태그를 사용한 텍스트 등 HTML 태그로 웹 문서에 삽입한 모든 대상을 가리킨다.

<br>

### id 선택자로 접근하는 getElementById() 메서드

HTML 태그의 id 속성은 HTML 요소가 문서 안에서 중복되지 않도록 사용하는 CSS 선택자이다.

다음과 같이 getElementById() 메서드를 이용하면 특정한 id가 포함된 DOM 요소에 접근할 수 있다.

    - 기본형

    요소명.getElementById('id명')

예를 들어 id값이 heading인 요소에 접근하려면 다음과 같이 사용한다.

[id 선택자로 DOM 요소에 접근하기](./Doit_JavaScript_day38-1.html)

<br>

### class 값으로 접근하는 getElementsByClassName() 메서드

getElementsByClassName() 메서드는 지정한 class 선택자 이름이 들어 있는 DOM 요소에 접근한다.

    - 기본형

    요소명.getElementsByClassName('class명')

class 선택자는 웹 문서 안의 여러 요소에서 사용할 수 있으므로 getElementsByClassName() 메서드를 사용하면 반환하는 요소가 2개 이상일 수 있다.

그래서 이 메서드 이름에는 반환 요소가 여러 개라는 뜻에서 Element에 s를 붙인것이다.

예를 들어 웹 문서에서 class = 'bright' 속성이 있는 요소를 모두 찾으려면 다음과 같이 사용한다.

[class 선택자로 DOM 요소에 접근하기](./Doit_JavaScript_day38-2.html)

getElementsByClassName() 메서드를 사용하게 되면 클래스 이름이 같은 DOM 요소들이 HTMLCollection 객체로 저장된다.

HTMLCollection 객체는 배열과 비슷하고 배열처럼 사용할 수 있다.

하지만 배열은 아니다.

<br>

### 태그 이름으로 접근하는 getElementsByTagName() 메서드

class나 id를 지정하지 않은 DOM 요소에 접근하려면 태그를 이용한다.

getElementsByTagName() 메서드는 다음과 같이 지정한 태그명을 사용한 DOM 요소에 접근할 수 있다.

여기에서도 메서드 이름이 Elements로 복수형을 사용한 점을 잘 알아두자.

    - 기본형

    요소명.getElementsByTagName('태그명')


웹 문서 안에서 같은 태그를 사용하는 요소가 2개 이상일 수 있으므로 getElementsByTagName() 메서드가 반환하는 값도 HTMLCollection 형태로 저장된다.

예를 들어 웹 문서에서 p태그를 사용한 모든 요소에 접근하려면 다음과 같이 사용한다.

[태그로 DOM 요소에 접근하기](./Doit_JavaScript_day38-3.html)

<br>

### 다양한 방법으로 접근하는 querySelector(), querySelectorAll() 메서드

앞에서 살펴본 getElementById(), getElementsByClassName(), getElementsByTagName() 메서드의 반환값은 HTMLCollection 객체이다.

여기에는 HTML 요소(p나 a같은 형태)만 저장된다.

DOM트리의 텍스트, 속성 노드까지 자유롭게 제어하려면 querySelector(), querySelectorAll() 메서드를 사용해야 한다.

id 선택자처럼 반환값이 하나라면 querySelector()메서드를 사용하고,

class 선택자나 태그 이름을 사용하여 여러 값이 한꺼번에 반환될 경우에는 querySelectorAll() 메서드를 사용한다.

    - 기본형

    노드.querySelector(선택자)
    노드.querySelectorAll(선택자 또는 태그)

querySelector(), querySelectorAll() 메서드에서 선택자를 표시할 때 

id 이름 앞에는 해시기호(#)를 붙이고,

class 이름 앞에는 마침표(,)를 붙인다.

태그는 기호 없이 태그명만 쓰면 된다.

querySelector() 메서드에서 class 이름으로 접근할 때는 class 이름을 사용한 여러 요소 중에서 첫 번째 요소만 반환한다.

[다양한 방법으로 DOM 요소에 접근하기](./Doit_JavaScript_day38-4.html)

querySelector(), querySelectorAll() 메서드의 반환값은 노드이거나 노드 리스트(node list)이다.

노드 리스트는 노드를 한꺼번에 여러 개 저장한 것으로 배열과 비슷하다고 생각하면 된다.


***
### 웹 요소의 내용을 수정하는 innerText, innerHTML 프로퍼티

<br>

자바스크립트에서는 웹 요소의 내용도 수정할 수 있다.

가장 쉬운 방법은 innerText 프로퍼티나 innerHTML 프로퍼티를 이용하는 것이다.

이름만 봐도 알 수 있듯이, innerText 프로퍼티는 텍스트 내용을 표시하고 innerHTML 프로퍼티는 HTML 태그까지 반영하여 표시한다.

    - 기본형

    요소명.innerText = 내용
    요소명.innerHTML = 내용

다음은 Date 객체를 사용해서 현재 날짜와 시간을 나타내는 예제이다.

날짜와 시간을 그대로 innerText 프로퍼티로 표시할 떄와 innerHTML 프로퍼티로 em 태그와 같이 표시할 때 어떤 차이가 있는지 살펴보자

[innerText, innerHTML 프로퍼티 사용하기](./Doit_JavaScript_day38-5.html)

***
### 속성을 가져오거나 수정하는 getAttribute(), setAttribute() 메서드

웹 요소를 문서에 삽입할 때 태그 속성을 함께 사용하면 DOM 트리에 속성 노드가 추가되면서 속성값이 저장된다.

이때 속성에 접근하려면 getAttribute() 메서드를 사용하고, 접근한 속성의 값을 바꾸려면 setAttribute() 메서드를 사용한다.

속성을 가져오려면 다음과 같이 getAttribute() 메서드에서 속성명을 지정한다.

    - 기본형

    getAttribute('속성명')

setAtttibute() 메서드를 사용하면 원하는 속성값으로 지정할 수 있다.

속성값이 이미 있다면 새로운 속성값으로 수정하고, 아직 해당 속성이 없다면 속성과 속성값을 새로 추가한다.

    - 기본형

    setAttribute('속성명', '값')

다음은 id='cup'인 이미지의 src 속성값을 가져오는 예제이다.

큰 이미지를 클릭하면 그 이미지의 경로 속성을 가져와 알림 창에 표시한다.

[이미지 속성 가져오기](./Doit_JavaScript_day38-6.html)


다음 예제는 setAttribute() 메서드를 사용해서 작은 이미지를 클릭했을 때 위의 큰 이미지 자리에 표시되도록 만든 예제이다.

이 파일의 소스에는 아직 배우지 않은 내용이 많기 때문에 당장에 setAttribute() 메서드가 이렇게 사용되는구나 하는 정도로 이해하고 넘어가자.

[작은 이미지를 클릭하면 큰 이미지 자리에 표시하기](./Doit_JavaScript_day38-7.html)

