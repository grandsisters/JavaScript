***
## 유효범위의 효용
***
아래 두개의 예제는 변수 i를 지역변수로 사용했을 때와 전역변수로 사용했을 때의 차이점을 보여준다. 전역변수는 각기 다른 로직에서 사용하는 같은 이름의 변수값을 변경시켜서 의도하지 않은 문제를 발생시킨다.

### 지역변수의 사용

    function a (){

        var i = 0;

    }

    for(var i = 0; i < 5; i++){

        a();

        document.write(i);

    }

실행결과

01234

***
### 전역변수의 사용

본 예제는 무한반복을 발생시킨다. 

    function a (){

        i = 0;

    }

    for(i = 0; i < 5; i++){

        a();

        document.write(i);

    }

***

a 함수 내에 i 변수가 지역 변수냐 전역 변수냐에 따라서 값이 제대로 출력될 수 있고

무한반복을 발생 시킬 수도 있게된다

***
***
## 전역 변수를 사용하는 법
***
불가피하게 전역변수를 사용해야 하는 경우는 하나의 객체를 전역변수로 만들고 

객체의 속성으로 변수를 관리하는 방법을 사용한다.

    MYAPP = {}
    MYAPP.calculator = {
        'left' : null,
        'right' : null
    }
    MYAPP.coordinate = {
        'left' : null,
        'right' : null
    }
    
    MYAPP.calculator.left = 10;
    MYAPP.calculator.right = 20;
    function sum(){
        return MYAPP.calculator.left + MYAPP.calculator.right;
    }
    document.write(sum());


하지만 만약 어떤 경우에도 난 전역 변수를 사용하고 싶지 않다라고 한다면

아래와 같이 <b>익명함수</b>를 호출함으로서 이러한 목적을 달성할 수 있다.

    
    (function(){
    var MYAPP = {}
    MYAPP.calculator = {
        'left' : null,
        'right' : null
    }
    MYAPP.coordinate = {
        'left' : null,
        'right' : null
    }
    MYAPP.calculator.left = 10;
    MYAPP.calculator.right = 20;
    function sum(){
        return MYAPP.calculator.left + MYAPP.calculator.right;
    }
    document.write(sum());
    }())


위와 같은 방법은 자바스크립트에서 로직을 모듈화하는 일반적인 방법이다. 


***
***
## 유효범위의 대상
***
자바스크립트는 함수에 대한 유효범위만을 제공한다. 많은 언어들이 블록(대체로 {,})에 대한 유효범위를 제공하는 것과 다른 점이다. 아래 예제의 결과는 coding everybody이다.

    for(var i = 0; i < 1; i++){
        var name = 'coding everybody';
    }
    alert(name);

자바에서는 아래의 코드는 허용되지 않는다. name은 지역변수로 for 문 안에서 선언 되었는데 이를 for문 밖에서 호출하고 있기 때문이다.

    for(int i = 0; i < 10; i++){
        String name = "egoing";
    }
    System.out.println(name);
자바스크립트의 지역변수는 함수에서만 유효하다.

***
***
## 정적 유효범위
***

자바스크립트는 함수가 선언된 시점에서의 유효범위를 갖는다. 이러한 유효범위의 방식을 정적 유효범위(static scoping), 혹은 렉시컬(lexical scoping)이라고 한다. 

    var i = 5;
    
    function a(){
        var i = 10;
        b();
    }
    
    function b(){
        document.write(i);
    }
    
    a();
실행 결과는 5이다.
***