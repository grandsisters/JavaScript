## JavaScript Arrow Function

화살표 함수는 ES6에 도입되었습니다.

화살표 함수를 사용하면 더 짧은 함수 구문을 작성할 수 있습니다.

    before:
    hello = function() {
      return "Hello World!";
    }

    after:
    hello = () => {
      return "Hello World!";
    }

함수에 하나의 문이 있고 그 문이 값을 반환하는 것일 경우 및 return 키워드일에는 괄호를 제거 할 수 있습니다 :

    기본적인 화살표 함수 반환 값:
    hello = () => "Hello World!";

참고: 이는 함수에 명령문이 하나만 있는 경우에만 작동합니다.

매개변수가 있는 경우 괄호 안에 전달합니다.

    매개변수가 있는 화살표 기능:
    hello = (val) => "Hello " + val;

실제로 매개변수가 하나만 있는 경우 괄호도 건너뛸 수 있습니다.

    괄호가 없는 화살표 함수:
    hello = val => "Hello " + val;

---

### 화살표 함수 안에서 this는 어떻게 작동할까?

this의 처리도 일반 함수와 비교하여 화살표 함수에서 다릅니다.

요컨대, 화살표 기능에는 this의 바인딩이 없습니다.

일반 함수에서 this키워드는 함수 를 호출한 객체를 나타냅니다. window, 문서, button 또는 그 밖의 무엇이든 될 수 있습니다.

화살표 기능을 사용하면 this키워드는 항상 화살표 기능 을 정의한 객체를 나타냅니다.

차이점을 이해하기 위해 두 가지 예를 살펴보겠습니다.

두 예제 모두 페이지가 로드될 때 먼저 메서드를 호출하고 사용자가 버튼을 클릭할 때 다시 한 번 메서드를 호출해 총 두 번 호출합니다.

첫 번째 예제는 일반 함수를 사용하고 두 번째 예제는 화살표 함수를 사용합니다.

결과는 window 객체가 함수의 "소유자"이기 때문에 첫 번째 예는 두 개의 다른 개체(window 및 button)를 반환하고 두 번째 예는 window 객체를 두 번 반환함을 보여줍니다.

    예시
    일반 함수 this는 함수 를 호출 하는 객체를 나타냅니다 .

    // Regular Function:
    hello = function() {
    document.getElementById("demo").innerHTML += this;
    }

    // The window object calls the function:
    window.addEventListener("load", hello);

    // A button object calls the function:
    document.getElementById("btn").addEventListener("click", hello);

<br />

    예시
    화살표가 있는 함수 this는 함수 의 소유자 를 나타냅니다 .

    // Arrow Function:
    hello = () => {
    document.getElementById("demo").innerHTML += this;
    }

    // The window object calls the function:
    window.addEventListener("load", hello);

    // A button object calls the function:
    document.getElementById("btn").addEventListener("click", hello);

함수로 작업할 때 이러한 차이점을 기억하십시오. 때로는 일반 함수의 동작이 원하는 것이지만 그렇지 않은 경우 화살표 함수를 사용합니다.
