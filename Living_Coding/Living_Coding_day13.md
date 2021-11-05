***
## arguments
***

함수에는 arguments라는 변수에 담긴 숨겨진 유사 배열이 있다. 

이 배열에는 함수를 호출할 때 입력한 인자가 담겨있다. 

아래 예제를 보자. 결과는 10이다.


    function sum(){
        var i, _sum = 0;    
        for(i = 0; i < arguments.length; i++){
            document.write(i+' : '+arguments[i]+'<br />');
            _sum += arguments[i];
        }   
        return _sum;
    }
    document.write('result : ' + sum(1,2,3,4));


함수 sum은 인자로 전달된 값을 모두 더해서 리턴하는 함수다. 

그런데 첫째행처럼 함수 sum은 인자에 대한 정의가 없다. 

하지만 마지막 라인에서는 4개의 인자를 함수 sum으로 전달하고 있다. 

함수의 정의부분에서 인자에 대한 구현이 없음에도 인자를 전달 할 수 있는 것은 왜 그럴까? 

그것은 arguments라는 특수한 배열이 있기 때문이다.

arguments는 함수안에서 사용할 수 있도록 그 이름이나 특성이 약속되어 있는 일종의 배열이다. 

arguments[0]은 함수로 전달된 첫번째 인자를 알아낼 수 있다. 

또 arguments.length를 이용해서 함수로 전달된 인자의 개수를 알아낼 수도 있다.

이러한 특성에 반복문을 결합하면 함수로 전달된 인자의 값을 순차적으로 가져올 수 있다. 

그 값을 더해서 리턴하면 인자로 전달된 값에 대한 총합을 구하는 함수를 만들 수 있다.

    arguments는 사실 배열은 아니다. 실제로는 arguments 객체의 인스턴스다.

***
## 매개변수의 수
***

매개변수와 관련된 두가지 수가 있다. 

하나는 함수.length, 다른 하나는 arguments.length이다. 

arguments.length는 함수로 전달된 실제 인자의 수를 의미하고, 함수.length는 함수에 정의된 인자의 수를 의미한다. 

아래의 코드를 보자.

    function zero(){
        console.log(
            'zero.length', zero.length,
            'arguments', arguments.length
        );
    }
    function one(arg1){
        console.log(
            'one.length', one.length,
            'arguments', arguments.length
        );
    }
    function two(arg1, arg2){
        console.log(
            'two.length', two.length,
            'arguments', arguments.length
        );
    }
    zero(); // zero.length 0 arguments 0 
    one('val1', 'val2');  // one.length 1 arguments 2 
    two('val1');  // two.length 2 arguments 1


***
***
## 함수의 호출
***
### apply 소개
***
함수에 대한 기본 수업에서 함수를 호출하는 방법을 알아봤다. 아래는 함수를 호출하는 가장 기본적인 방법이다.


    function func(){
    }
    func();


JavaScript는 함수를 호출하는 특별한 방법을 제공한다. 

본 토픽의 시작에서 함수를 객체라고 했다. 

위의 예제에서 함수 func는 Function이라는 객체의 인스턴스다. 

따라서 func는 객체 Function이 가지고 있는 메소드들을 상속하고 있다. 

지금 이야기하려는 메소드는 Function.apply과 Function.call이다. 

이 메소드들을 이용해서 함수를 호출해보자. 

결과는 3이다.


    function sum(arg1, arg2){
        return arg1+arg2;
    }
    alert(sum.apply(null, [1,2]))


함수 sum은 Function 객체의 인스턴스다. 

그렇기 때문에 객체 Function 의 메소드 apply를 호출 할 수 있다. 

apply 메소드는 두개의 인자를 가질 수 있는데, 첫번째 인자는 함수(sum)가 실행될 맥락이다. 

맥락의 의미는 다음 예제를 통해서 살펴보자. 

두번째 인자는 배열인데, 이 배열의 담겨있는 원소가 함수(sum)의 인자로 순차적으로 대입된다. 

Function.call은 사용법이 거의 비슷하다 여기서는 언급하지 않는다.

좀 더 흥미로운 예제를 살펴보자. 결과는 6과 185이다.

***
### apply의 사용
***


    o1 = {val1:1, val2:2, val3:3}
    o2 = {v1:10, v2:50, v3:100, v4:25}
    function sum(){
        var _sum = 0;
        for(name in this){
            _sum += this[name];
        }
        return _sum;
    }
    alert(sum.apply(o1)) // 6
    alert(sum.apply(o2)) // 185


예제가 복잡해보이지만 한나씩 분해해서 생각해보면 어렵지 않다.

우선 두개의 객체를 만들었다. o1는 3개의 속성을 가지고 있다. 

각각의 이름은 val1, val2,val3이다. 

o2는 4개의 속성을 가지고 있고 o1과는 다른 속성 이름을 가지고 있고 속성의 수도 다르다.

그 다음엔 함수 sum을 만들었다. 

이 함수는 객체의 속성을 열거할 때 사용하는 for in 문을 이용해서 

객체 자신(this)의 값을 열거한 후에 각 속성의 값을 지역변수 _sum에 저장한 후에 이를 리턴하고 있다.

객체 Function의 메소드 apply의 첫번째 인자는 함수가 실행될 맥락이다. 

이렇게 생각하자. sum.apply(o1)은 함수 sum을 객체 o1의 메소드로 만들고 sum을 호출한 후에 sum을 삭제한다. 

아래와 비슷하다. 
(실행결과가 조금 다를 것이다. 그것은 함수 for in문으로 객체 o1의 값을 열거할 때 함수 sum도 포함되기 때문이다.)


    o1.sum = sum;
    alert(o1.sum());
    delete o1.sum();


sum의 o1 소속의 메소드가 된다는 것은 이렇게 바꿔 말할 수 있다. 

함수 sum에서 this의 값이 전역객체가 아니라 o1이 된다는 의미다. 

일반적인 객체지향 언어에서는 하나의 객체에 소속된 함수는 그 객체의 소유물이 된다. 

하지만 JavaScript에서 함수는 독립적인 객체로서 존재하고, apply나 call 메소드를 통해서 

다른 객체의 소유물인 것처럼 실행할 수 있다. 흥미롭다.

만약 apply의 첫번째 인자로 null을 전달하면 apply가 실행된 함수 인스턴스는 전역객체(브라우저에서는 window)를 맥락으로 실행되게 된다.

***