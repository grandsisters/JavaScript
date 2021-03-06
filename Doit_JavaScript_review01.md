## 한눈에 정리하기

***
### 변수

<br>

변수(variable)란? 프로그램을 실행하는 동안 값이 여러 번 달라질 수 있는 데이터를 말한다.
- 변수 작성 규칙
    1) 변수의 이름은 대소 문자를 구별하여 작성한다.
    2) 영문자와 숫자, 언더스코러( _ )만 사용하며 숫자로 시작할 수 없다.

***
### 자료형

<br>

|유형|종류|설명|
|----|----|----|
|기본유형|숫자형|따옴표 없이 숫자로만 표시한다.|
|기본유형|문자열|작음따옴표('')나 큰따옴표("")로 묶어서 나타낸다.|
|기본유형|논리형|참(true)와 거짓(false)이란 2가지 값만 가진다.|
|복합유형|배열|하나의 변수에 여러 개의 값을 저장한다.|
|복합유형|객체|함수와 속성들이 함께 포함된 자료형이다.|
|특수유형|undefined|데이터 유형이 지정되지 않았을 때의 상태를 나타낸다.|
|특수유형|null|데이터 값이 유효하지 않은 상태를 나타낸다.|

***
### 연산자

<br>

|종류|설명|
|----|----|
|산술 연산자|+ - * / % ++ --|
|할당 연산자|= += -= *= /= %=|
|비교 연산자|== != === !== < <= > >=|
|논리 연산자|! && \|\||
|조건 연산자|(조건) ? true 일 때 실행할 명령 : false일 때 실행할 명령|


***
### 조건문

<br>

if문

    if(조건) {
        조건이 true일 때 실행할 명령
    }

if~else문

    if(조건) {
        조건이 true일 때 실행할 명령
    } else {
        조건이 false일 때 실행할 명령
    }

switch문

    switch(조건)
    {
        case 값1: 문장1
            break
        case 값2: 문장2
            break
        ...
        default: 문장n
    }

***
### 반복문

<br>

for문

    for(초깃값; 조건; 증가식) {
        실행할 명령
    }

while문 

    while(조건) {
        실행할 명령
    }

do~while문

    do {
        실행할 명령
    } while(조건)

break문

    break // 반복문이 끝나기 전에 조건에 따라 반복문을 빠져나옴

continue문

    continue // 반복 과정을 한 차례 건너뛰고 반복문의 맨 앞으로 돌아감