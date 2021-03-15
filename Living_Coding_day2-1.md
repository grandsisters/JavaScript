- ## 변수의 선언

var a = 1;

var은 생략이 가능한데 왠만하면 써주자

var a = 1, b = 2;

이렇게도 선언이 가능하다

- ## 자바스크립트의 주석

자바스크립트에선 //로 한줄 주석 처리가 가능하다

여러줄 주석은 시작할때 /*를 써주고 끝날때는 */ 로 한다

- ## 연산자

= 대입연산자

== 비교연산자

<

#### >

!=

=!

#### >=

<=

등등
비교연산자의 결과는 boolean값이 나온다

주의 해야할 것으로 === 가 있는데 양변이 '정확히' 일치해야만 true가 나온다

예를 들면

1 == '1' 은 자바스크립트에선 true 이지만
1 === '1' 은 false 가 나온다

비슷한 예로

alert(null == undefined);       //true

alert(null === undefined);      //false

alert(true == 1);               //true

alert(true === 1);              //false

alert(true == '1');             //true

alert(true === '1');            //false
 
alert(0 === -0);                //true

alert(NaN === NaN);             //false

null과 undefined는 값이 없다는 의미의 데이터 형이다. 

null은 값이 없음을 명시적으로 표시한 것이고, undefined는 그냥 값이 없는 상태라고 생각하자.

NaN은 0/0과 같은 연산의 결과로 만들어지는 특수한 데이터 형인데 숫자가 아니라는 뜻이다.

아래의 참고는 == 와 === 의 차이점을 표로 정리해놓은 곳이다

참고:https://dorey.github.io/JavaScript-Equality-Table/