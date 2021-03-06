## 자료형 이해하기

<br>

자료형이란 프로그램에서 처리할 자료(data)의 형태를 뜻한다.

예를 들어 '3'을 숫자로 처리하는지, 문자열로 처리하는지에 따라 프로그램의 결과는 달라진다.

***
### 자료형이란

<br>

우리는 '10'이나 '-15'가 숫자인 것을 알 수 있고, '안녕하세요'가 문자라는 걸 바로 알 수 있다.

하지만 컴퓨터에게 일을 시킬 때는 '10'은 숫자이고, '안녕하세요'는 문자라는 것을 따로 알려 줘야 처리할 수 있다.

이렇게 컴퓨터가 처리할 수 있는 자료의 형태를 자료형(data type)이라고 한다.

데이터 유형, 데이터 타입, 데이터형 이라고도 한다.

<br>

자바 스크립트의 자료형은 숫자, 문자열, 논리형과 같은 기본 유형과

배열, 객체를 다루는 복합 유형,

그리고 undefined, null 같은 특수 유형이 있다.

자바스크립트의 자료형은 다음과 같이 정리할 수 있다.

|유형|종류|설명|예시|
|----|----|----|----|
|기본 유형|숫자형|따옴표 없이 숫자로만 표기한다.|var birthday = 2000;|
|기본 유형|문자열|작은 따옴표('')나 큰따옴표("")로 묶어서 나타낸다. 숫자를 따옴표로 묶으면 문자로 인식한다.|var greeting = 'Hello!'; , var birthday = '2000';|
|기본 유형|논리형|참(true)과 거짓(false)이라는 2가지 값만 있는 유형이다. 이때 true와 false는 소문자로만 표시한다.|var isEmpty = true;|
|복합 유형|배열|하나의 변수에 여러 개의 값을 저장한다.|var seasons = ['봄','여름','가을','겨울'];|
|복합 유형|객체|함수와 속성을 함께 포함한다.|var date = new Date();|
|특수 유형|undefined|자료형이 지정되지 않았을 때의 상태이다. 예를 들어 변수 선언만 하고 값을 할당하지 않는 변수는 undefined 상태이다.|-|
|특수 유형|null|값이 유효하지 않을 때의 상태이다.|-|

***
### 숫자형

<br>

자바스크립트에서 숫자형(number)은 정수와 실수로 나누어 구분한다.

2가지 숫자형을 알아보자.

<br>

- 정수
    
    정수는 소수점 없는 숫자이다.

    표현 방법에 따라 10진수, 8진수, 16진수의 3가지 유형으로 나누기도 한다.

    8진수와 16진수는 익숙하지 않고 조금 이해하기 어렵지만 프로그래머가 되려면 반드시 알아 두어야 하는 개념이다.

        - 10진수 : 0~9로 표현할 수 있는 수이다. 
                    예) 2000, 17

        - 8진수 : 0~7로 표현할 수 있는 수이다. 이때 10진수와 구분하기 위해 숫자 0을 맨 앞에 붙인다. 
                    예) 012, 013, 0200

        - 16진수 : 숫자 0~9와 알파벳 A~F로 표현할 수 있는 수이다. 
                    16진수는 프로그래밍을 할 때 가장 많이 사용한다. 
                    10진수와 구분하기 위하여 0x 또는 0X를 맨 앞에 붙인다. 이때 알파벳 A~F는 대문자와 소문자를 모두 사용할 수 있다. 
                    예) 0xfff, 0xFFF, 0XFFF

- 실수

    실수는 소수점이 있는 숫자를 가리킨다.
    
    예를 들어 자바스크립트에서 4.13은 정수와 마찬가지로 숫자형이다. 
    
    C나 자바와 같은 프로그래밍 언어에서는 정수와 실수를 명확히 구별하고 처리 방법도 다르지만, 자바스크립트에서는 정수와 실수를 함께 묶어 숫자형이라고 한다.

    하지만 자바스크립트에서는 실수를 정밀하게 계산하는 것은 적합하지 않다.

    예상하지 못한 계산 결괏값이 나올 때가 있기때문이다.

    예를 들어 계산식 0.1 + 0.2의 결괏값은 0.3이 나올 것이라 생각하지만 실제로 자바스크립트에서는 0.30000000000000004를 표시한다.

    자바스크립트에서는 0.1이나 0.2를 2진수로 변환해서 계산하는데 이때 자릿수가 많은 소수로 변환되고, 그 상태에서 0.1과 0.2를 더하기 때문이다.

    따라서 자바스크립트에서 정밀하게 숫자를 계산하는 프로그램을 만들 때는 주의해야 한다.

