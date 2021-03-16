***
***
### IDE = 통합 개발 환경(Integrated Development Environmen)
생코 아저씨가 추천하는 Sublime Text - 유료
***

***
### 콘솔 사용법

크롬 브라우저
- 브라우저가 켜져있는 상태에서 F12키를 누른다
- 오른쪽 상단의 'show console' 버튼을 클릭
- 이곳에는 html 전체를 작성할 필요가 없고 script부분만 작성을 해줘도 즉석 실행이 된다 / 짧은 코드를 실행해볼때는 유용하다
***

***
- ## 변수의 선언

var a = 1;

var은 생략이 가능한데 왠만하면 써주자

var a = 1, b = 2;

이렇게도 선언이 가능하다
***

***
- ## 자바스크립트의 주석

자바스크립트에선 //로 한줄 주석 처리가 가능하다

여러줄 주석은 시작할때 /*를 써주고 끝날때는 */ 로 한다
***

***
- ## 줄바꿈

\<br />
***

***
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
***


***
# 조건문
### 들어가기전에 

- 조건문이란 주어진 조건에 따라서 에플리케이션을 다르게 동작하도록 하는 것이다

- 조건문에서는 boolean값이 핵심적인 역할을 담당한다

if, else if, else 를 잘 활용하자
***

***
### 논리연산자
- && = and

&&는 좌항과 우항이 모두 참(true)일 때 참이된다

- || = or

'||'는 '||'의 좌우항 중에 하나라도 true라면 true가 되는 논리 연산자다
***

***
### boolean의 대체제

조건문에 사용될 수 있는 데이터 형이 꼭 불린만 되는 것은 아니다.

관습적인 이유로 0는 false 0이 아닌 값은 true로 간주된다

그밖에 false와 0 외에 false로 간주되는 데이터형은 아래와 같다

- !''  빈 문자열

- !undefined

- !a 값이 할당되지 않은 변수 

- !null

- !NaN
***
***