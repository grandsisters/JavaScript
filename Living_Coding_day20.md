***
## 표준 내장 객체의 확장
***

### 표준 내장 객체??

표준 내장 객체(Standard Built-in Object)는 자바스크립트가 기본적으로 가지고 있는 객체들을 의미한다. 

내장 객체가 중요한 이유는 프로그래밍을 하는데 기본적으로 필요한 도구들이기 때문에다. 

결국 프로그래밍이라는 것은 언어와 호스트 환경에 제공하는 기능들을 통해서 

새로운 소프트웨어를 만들어내는 것이기 때문에 내장 객체에 대한 이해는 프로그래밍의 기본이라고 할 수 있다. 

자바스크립트는 아래와 같은 내장 객체를 가지고 있다. 

    Object
    Function
    Array
    String
    Boolean
    Number
    Math
    Date
    RegExp


이제 우리는 내장객체라는 하늘에서 뚝떨어진 이것들이 무엇인지를 보다 잘 이해할 수 있게 되었다. 

new가 무엇인지, 함수가 객체를 어떻게 만드는지도 알았다. 

또 원한다면 자바스크립트의 내장 객체와 같은 것을 우리도 만들 수 있다는 것도 알았다. 

이러한 지식을 바탕으로 좀 더 멋진 일을 해보자.

***
### 배열의 확장

배열을 확장해보자. 

아래 코드는 배열에서 특정한 값을 랜덤하게 추출하는 코드다. 


    var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
    function getRandomValueFromArray(haystack){
        var index = Math.floor(haystack.length*Math.random());
        return haystack[index]; 
    }
    console.log(getRandomValueFromArray(arr));


이렇게 작성해도 된다! 잘못한 것이 아니다. 

하지만 조금 더 세련된 방법은 이 함수를 배열 객체에 포함시키는 것이다. 

그렇게하면 마치 배열에 내장된 메소드인 것처럼 위의 기능을 사용할 수 있다.
***

### 배열의 확장2

    Array.prototype.rand = function(){
        var index = Math.floor(this.length*Math.random());
        return this[index];
    }
    var arr = new Array('seoul','new york','ladarkh','pusan', 'Tsukuba');
    console.log(arr.rand());

***