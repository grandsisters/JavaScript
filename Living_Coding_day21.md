***
## Object
***

Object 객체는 객체의 가장 기본적인 형태를 가지고 있는 객체이다. 

다시 말해서 아무것도 상속받지 않는 순수한 객체다. 자바스크립트에서는 값을 저장하는 기본적인 단위로 Object를 사용한다. 

    var grades = {'egoing': 10, 'k8805': 6, 'sorialgi': 80};

동시에 자바스크립트의 모든 객체는 Object 객체를 상속 받는데, 그런 이유로 모든 객체는 Object 객체의 프로퍼티를 가지고 있다. 

또한 Object 객체를 확장하면 모든 객체가 접근할 수 있는 API를 만들 수 있다. 

Object API 사용법 : https://www.youtube.com/watch?v=5OFbsj-UuIc

***
### Object 확장

아래는 Object 객체를 확장한 사례다.


    Object.prototype.contain = function(neddle) {
        for(var name in this){
            if(this[name] === neddle){
                return true;
            }
        }
        return false;
    }
    var o = {'name':'egoing', 'city':'seoul'}
    console.log(o.contain('egoing'));
    var a = ['egoing','leezche','grapittie'];
    console.log(a.contain('leezche'));


***
### 확장의 위험성


그런데 Object 객체는 확장하지 않는 것이 바람직하다. 왜냐하면 모든 객체에 영향을 주기 때문이다. 

확장 후에 아래 코드를 실행해보자.

    for(var name in o){
        console.log(name);  
    }

결과는

    name
    contain


확장한 프로퍼티인 contain이 포함되어 있다. 

객체가 기본적으로 가지고 있을 것으로 예상하고 있는 객체 외에 다른 객체를 가지고 있는 것은 개발자들에게 혼란을 준다. 

이 문제를 회피하기 위해서는 프로퍼티의 해당 객체의 소속인지를 체크해볼 수 있는 hasOwnProperty를 사용하면 된다. 

    for(var name in o){
        if(o.hasOwnProperty(name))
            console.log(name);  
    }


hasOwnProperty는 인자로 전달된 속성의 이름이 객체의 속성인지 여부를 판단한다. 

만약 prototype으로 상속 받은 객체라면 false가 된다. 

***