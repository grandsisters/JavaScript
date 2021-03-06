## let과 const의 등장

<br>

var 예약어를 사용하는 변수는 함수 영역의 스코프를 가지고, 재할당과 재선언을 할 수 있다.

그래서 var 예약어를 자칫 잘못 사용하면 예상하지 못한 프로그램 오류를 발생시킬 수 있다.

그래서 ES6부터는 var를 보완한 let과 const 예약어가 등장한다.

***
### let을 사용한 변수의 특징

<br>

ES6 이전의 자바스크립트 프로그램에서는 var 예약어만으로 변수를 선언했다.

그런데 var 예약어를 빠뜨리면 의도하지 않게 전역 변수가 되기도 하고, 프로그램 길이가 길어지다 보면 실수로 사용하는 변수를 재선언하거나 값을 재할당해 버리는 경우가 생기기도 한다.

그래서 ES6에서는 변수를 선언하기 위한 예약어로 let과 const가 추가 되었고, 되도록이면 var 예약어는 사용하지 않을 것을 권장한다.

예약어 var와 let, const의 가장 큰 차이는 스코프의 범위이다.

var는 함수 영역(레벨)의 스코프를 가지지만 let과 const는 블록 영역의 스코프를 가진다.

지금부터 let과 const를 사용한 변수의 특징을 하나씩 살펴보자.

<br>

### 블록 안에서만 쓸 수 있는 변수

<br>

let 예약어로 선언한 변수는 변수를 선언한 블록( {}로 묶은 부분 )에서만 유효하고 블록을 벗어나면 사용할 수 없다.

다음 예제를 보면 calcSum() 함수에서 변수 sum은 let 예약어를 사용하여 선언한다.

즉, sum은 함수 calcSum()의 블록( {} )안에서만 사용할 수 있다.

또한 for 문의 카운터 변수 i도 let 예약어를 사용했다.

그렇다면 변수 i는 for문을 벗어나면 사용할 수 없다.

{ } 블록이나 ( ) 블록 안에서만 사용할 수 있는 변수를 '블록 변수'라고 한다.

[블록 변수 선언하기](./Doit_JavaScript_day18-1.html)

만약 전역 변수를 선언하고 싶다면 let 예약어를 쓰지 않고 변수 이름과 초깃값만 할당하면 된다.

다음은 sum 변수를 전역 변수로 선언하고 함수 밖의 consol.log()로 결괏값을 표시 하는 예제이다.

[전역 변수 선언하기](./Doit_JavaScript_day18-2.html)


<br>

### 재할당은 가능하지만 재선언은 할 수 없는 변수

<br>

let 예약어를 사용하여 선언한 변수는 값을 재할당할 수는 있지만 변수를 재선언할 수는 없다.

그러니 예약어 var와 같이 실수로 같은 변수의 이름을 사용할 걱정은 없다.

다음은 for문 실행이 끝나고 이미 계산한 값이 저장되어 있는 sum q변수에 값 100을 재할당한 예제이다.

[블록 변수의 재할당](./Doit_JavaScript_day18-3.html)

블록 변수 sum을 재선언하면 어떻게 될까?

다음은 이미 블록 변수로 선언한 sum을 다시 한번 블록 변수로 선언한 예제이다.

[재선언할 수 없는 let 변수](./Doit_JavaScript_day18-4.html)

이 예제의 실행 결과를 확인하면 변수 sum이 중복으로 선언되었다는 메시지가 나타난다.

<img src='./img/JS11.jpg'>

이렇듯 let 예약어는 같은 변수 이름을 중복해서 사용할 수 없다.

<br>

### 호이스팅이 없는 변수

<br>

var 예약어를 사용한 변수는 선언하기 전에 실행하더라도 아직 할당되지 않은 자료형인 undefined값을 가질 수 있다.

바로 호이스팅 때문이다.

하지만 let 예약어를 사용한 변수는 선언하기 전에 사용할 경우 오류 메시지를 나타낸다.

다음 예제를 웹 브라우저의 콘솔 차에서 확인해 보면 

    Cannot access 'y' before initialization at displayNumber

라고 표시된다. 

함수 displayNumber()에서 변수 y를 초기화하기 전에 사용할 수 없다는 뜻이다.

[호이스팅이 없는 let 변수](./Doit_JavaScript_day18-5.html)