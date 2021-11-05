## 조건문 알아보기

***
### AND 연산자

<br>

AND 연산자 기호는 '&&'를 사용하며, 피연산자 2개 중에서 false가 하나라도 있으면 결괏값이 false가 된다.

|op 1|op 2|op 1 && op 2|
|----|----|------------|
|false|false|false|
|false|true|false|
|true|false|false|
|true|true|true|

<br>

AND 연산자를 사용해 입력한 2개의 숫자가 50보다 작은지를 체크하는 예제를 보자.

    <script>
        var numberOne = prompt('50 미만인 숫자를 입력하세요.')
        var numberTwe = prompt('50 미만인 숫자를 입력하세요.')

        if(numberOne < 50 && numberTwo < 50)
            alert('숫자 2개 모두 50 미만이군요.');
        else
            alert('조건에 맞지 않는 숫자가 있습니다.')
    </script>

<img src='./img/JS06.jpg'>
<img src='./img/JS07.jpg'>
<img src='./img/JS08.jpg'>

***
### NOT 연산자

<br>

NOT 연산자 기호는 '!'를 사용하며 true나 false를 반대로 뒤집는다.

|op|!op|
|--|---|
|false|true|
|true|false|

앞에서 살펴본 '3의 배수 확인하기 2' 예제를 떠올려 보자.

다음과 같이 변수 userNumber의 입력값이 null이 아닌지를 체크했다.

이때 NOT 연산자 !를 사용하여 작성한다.

    if(userNumber !== null) { 실행할 명령 } // 입력값이 null이 아니면 if 문을 실행


***
### 조건 계산을 빠르게 하는 방법이 있나요?

<br>

조건이 2가지 이상일 경우 동시에 함께 체크하는 조건식을 만들 때는 첫 번째 조건을 보고 빠르게 판단할 수 있도록 해야한다.

예를 들어 다음과 같은 조건식을 체크할 경우를 생각해 보자

    ((x === 10) && (y === 20))

AND 연산자(&&)는 조건식이 둘 이상일 경우에 하나만 false여도 최종 결괏값이 false가 된다.

그러므로 첫 번째 조건식 (x === 10)이 false이면, 두 번째 조건식 (y === 20)은 체크하지 않고 바로 false가 된다.

이와 같이 AND 연산자(&&)를 사용한다면 'false가 될 확률이 높은 조건을 첫 번째 조건식으로 사용'하는 게 좋다.

반대로 OR 연산자(||)는 조건식이 둘 이상일 경우에 하나만 true여도 최종 결괏값이 true가 된다.

따라서 OR 연산자를 사용한다면 'true가 될 확률이 높은 조건식을 첫 번째 조건식으로 사용'하는 것이 좋다.

이렇게 연산하는 방법을 단축 평가(short circuit evaluation)라고 한다.

***
## switch 문

<br>

자바스크립트에서 조건을 체크할 때는 if~else 문을 사용하지만, 처리할 명령이 많다면 if~else 문을 여러 개 사용하는 것보다 switch 문이 더 편리하다.

switch 문에서 조건을 체크한 후 case 문을 사용하여 명령을 처리할 수 있다.

switch 문의 기본 형식은 다음과 같다.

    - 기본형
    switch(조건)
    {
        case 값1: 명령1
            break
        case 값2: 명령2
            break
        ...
        default: 명령n
    }

switch 문의 조건은 아래에 있는 case 문의 값과 일대일로 일치해야 한다.

조건과 일치하는 case 문의 명령을 실행한 후에는 switch 문을 완전히 빠져나온다.

switch의 조건이 case의 '값1'과 일치하면 '명령1'을 실행하고, 다음에 있는 break 문을 만나 switch 문을 빠져나간다.

만약 조건이 case의 '값2'와 일치하면 '명령2'를 실행한다.

이런식으로 조건에 따라 다른 명령을 실행할 수 있다.

하지만 조건과 일치하는 case 문이 없다면 어떻게 해야 할까?

이럴 때는 마지막에 있는 default 문을 실행한다.

default 문은 switch 문의 마지막에 작성하며 여기에는 break 문을 쓰지 않는다.

다음 예제는 사용자에게 1,2,3 중에서 값을 하나만 입력 받아 session 변수에 저장하고, switch 문을 이용해 session 값을 체크한다.

이때 case 문에서는 값만 사용하고 '식을 사용할 수 없다'는 점에 주의하자.

[switch 문으로 조건 체크하기](./Doit_JavaScript_day11.html)