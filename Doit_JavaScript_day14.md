## 반복문 알아보기

***
### while문과 do~while문 사용하기

<br>

while문은 조건이 true인 동안 명령을 반복한다.

for문과 마찬가지로 while문도 조건을 체크하고 true일 때만 명령을 반복하여 실행한다.

결국 조건이 false라면 명령은 한 번도 실행하지 않을 수 있다.

{ }으로 블록을 만들어 여러 명령을 반복할 수 있다.

    - 기본형
    while(조건) {
        실행할 명령
    }

while문과 달리 do~while문은 조건이 맨 뒤에 붙는다.

그리고 do문은 일단 명령을 한번 실행한 후 while문에서 조건을 체크한다.

그러므로 조건이 false라 할더라도 일단 명령을 최소한 한 번은 실행한다.

<br>

while문은 조건부터 체크하지만 do~while문은 일단 명령을 실행한 후 조건을 체크한다는 점에서 다르다.

while문과 do~while문 중에서 어떤 것을 사용할지는 상황에 따라 달라진다.

프로그래머의 개인 취향이나 프로그램 처리 속도, 환경에 따라 다르게 사용할 수 있다.

다음 예제는 while문을 사용하여 팩토리얼을 계산하는 프로그램이다.

팩토리얼은 반복문을 연습하기 좋은 예제라서 프로그래밍을 공부할 때 자주 등장하는데,

1부터 주어진 어떤 숫자(n)까지 곱한 결과이다.

예를 들어 3의 팩토리얼은 '1 x 2 x 3'의 계산 결과인 6을 의미하며 '3팩토리얼', '3!' 이라고 쓴다.

[while문으로 팩토리얼 만들기](./Doit_JavaScript_day14-1.html)

여기에서 입력값은 변수 n이며 1부터 n까지 곱한 결과를 보여준다.

***
### 어떤 반복문을 사용해야 할까?

<br>

지금까지 살펴본 for문, while문, do~while문은 특정 명령을 여러 번 반복해서 실행할 수 있다는 공통점이 있다.

그렇다면 어떤 상황일 때 어떤 반복문을 골라서 사용해야 할까?

- for문은 초깃값과 반복 크기가 일정할 경우에 주로 사용한다. 예를 들어 숫자 0~9를 차례로 반복해서 사용하려면 
    for(i = 0; i < 10; i++)을 쓰는게 편리하다.

- while문과 do~while문은 초깃값이나 반복 크기 없이 조건만 주어졌을 때 많이 사용한다.
    어떤 조건을 만족하는 동안만 반복하게 만드는 것이다.
    그리고 while문과 do~while문은 조건을 체크하기 전에 명령 실행 여부에 따라 달라지는데, 실제로 코드를 작성할 때는
    프로그램 환경에 따라 선택해서 사용하면 된다.

***
### break문과 continue문 사용하기

<br>

반복문은 지정한 횟수만큼 명령을 반복할 때 사용한다.

하지만 특정 조건에서 반복문을 멈추어야 하거나, 반복문 중간에서 앞으로 되돌아가야 할 경우가 있다.

이럴 때 break문과 continue문이 필요하다.

<br>

### 멈추는 braek문

반복문에서 조건의 역할은 명령이 조건에 맞는지 체크하고 명령을 반복한다.

또한 조건 안에는 종료 조건도 포함되어 있다.

예를 들어 다음 반복문 2개를 살펴보자

for문에서는 i값이 10이되면 반복이 끝나고, while문에서는 i값이 20이 되면 반복을 끝낸다.

    for(i = 0; i < 10; i++) { 실행할 명령 }

    while(i < 20) { 실행할 명령 }

하지만 종료 조건이 되기 전에 반복문을 빠져나와야 할 경우도 있다.

이럴 때 break문을 사용한다.

break문의 기본 형식은 다음과 같다.

    - 기본형
    break

break문은 단독으로 사용할 수도 있고 반복문을 끝낼 조건과 함께 사용할 수도 있다.

예를 들어 앞에서 작성한 구구단 프로그램은 9단까지 모두 표시했는데,

이 소스 코드를 변형해 3단까지만 표시해 보자.

즉, 카운터 변숫값(i)이 3이면 종료하는 프로그램이다.

[break문으로 구구단을 3단까지만 표시하기](./Doit_JavaScript_day14-2.html)

<br>

### 건너뛰는 continue문

continue문은 주어진 조건에 해당하는 값을 만나면 해당 반복문을 건너뛴다.

그리고 반복문의 맨 앞으로 되돌아가 다음 과정으로 넘어가도록 한다.

쉽게 말해 반복 과정을 한 차례 건너뛰게 하는 것이다.

    - 기본형
    continue

다음은 숫자 1부터 10까지 중에서 짝수만 더하는 예제이다. 

i % 2는 짝수인지 홀수인지를 체크한다.

i를 2로 나누어 나머지가 1이라면 i는 홀수이므로 i값을 계속 증가시키고, 

i % 2가 0이라면 짝수이므로 sum 변수에 i값을 더한다.

[1부터 10까지 짝수만 더하기](./Doit_JavaScript_day14-3.html)
