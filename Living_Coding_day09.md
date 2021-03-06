***
## 유효 범위
***
### 전역변수와 지역변수
***
<b>유효범위(Scope)는 변수의 수명을 의미한다.</b>

아래의 예제를 보자. 결과는 global이다.

    var vscope = 'global';

    function fscope(){

        alert(vscope);

    }

    fscope();

함수 밖에서 변수를 선언하면 그 변수는 전역변수가 된다. 

전역변수는 에플리케이션 전역에서 접근이 가능한 변수다. 

다시 말해서 어떤 함수 안에서도 그 변수에 접근 할 수 있다. 

그렇기 때문에 함수 fscope 내에서 vscope를 호출 했을 때 함수 밖에서 선언된 vscope의 값 global이 반환된 것이다. 

***

아래 예제를 보자. 결과는 '함수안 local'과 '함수밖 global'이 출력된다.

    var vscope = 'global';

    function fscope(){

        var vscope = 'local';

        alert('함수안 '+vscope);

    }

    fscope();

    alert('함수밖 '+vscope);

즉 함수 안에서 변수 vscope을 조회(4행) 했을 때 함수 내에서 선언한 지역변수 vscope(3행)의 값인 local이 사용되었다. 

하지만 함수 밖에서 vscope를 호출(7행) 했을 때는 전역변수 vscope(1행)의 값인 global이 사용된 것이다. 

즉 지역변수의 유효범위는 함수 안이고, 전역변수의 유효범위는 에플리케이션 전역인데, 

같은 이름의 지역변수와 전역변수가 동시에 정의되어 있다면 지역변수가 우선한다는 것을 알 수 있다. 

***
아래 예제를 보자. 결과는 모두 local이다.

    var vscope = 'global';

    function fscope(){

        vscope = 'local';

        alert('함수안'+vscope);

    }

    fscope();

    alert('함수밖'+vscope);

함수밖에서도 vscope의 값이 local인 이유는 무엇일까? 

그것은 함수 fscope의 지역변수를 선언할 때 var를 사용하지 않았기 때문이다. 

- <b>함수 바깥에서 var을 써서 변수를 만들면 전역변수가 된다.</b>

- <b>함수 안쪽에서 var을 써서 변수를 만들면 지역변수가 된다.</b>

- <b>var를 사용하지 않은 지역변수는 전역변수가 된다.</b> 


따라서 3행은 전역변수의 값을 local로 변경하게 된 것이다. 

var을 쓰는 것과 쓰지 않는 것의 차이를 이해해야 한다.
***

전역변수는 사용하지 않는 것이 좋다. 

여러가지 이유로 그 값이 변경될 수 있기 때문이다. 

함수 안에서 전역변수를 사용하고 있는데, 누군가에 의해서 전역변수의 값이 달라졌다면 어떻게 될까? 

- 함수의 동작도 달라지게 된다. 이것은 버그의 원인이 된다. 

- 또한 함수를 다른 에플리케이션에 이식하는데도 어려움을 초래한다. 

함수의 핵심은 로직의 재활용이라는 점을 상기하자. 

변수를 선언할 때는 꼭 var을 붙이는 것을 습관화해야 한다. 

전역변수를 사용해야 하는 경우라면 그것을 사용하는 이유를 명확히 알고 있을 때 사용하도록 하자.

