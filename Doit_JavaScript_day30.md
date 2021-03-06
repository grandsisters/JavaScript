## 자바스크립트의 내장 객체

***
### Date 객체

Date 객체는 날짜와 시간 정보를 나타낼 수 있다.

Date 객체는 현재 날짜와 시간을 출력하거나 달력을 표시할 수도 있고,

특정일까지 얼마나 남았는지 알려 주는 등 사이트에서 여러 가지로 응용할 수 있다.

<br>

### Date 객체 인스턴스 만들기

<br>

자바스크립트에서 Date 객체를 사용하려면 우선 Date 객체의 인스턴스를 만들어야 한다.

현재 날짜로 설정할 경우에는 다음과 같이 예약어 new를 붙여 주면 된다.

[Date 객체로 현재 날짜 나타내기](./Doit_JavaScript_day30-1.html)

그리고 특정한 날짜를 저장한 Date 객체를 만들고 싶다면 Date 다음에 붙이는 괄호 안에 날짜 정보를 입력한다.

예를 들어 '2020 2월 25일'이라는 날짜 정보를 객체에 저장한 후 프로그램에서 사용하려면 다음과 같이 입력한다.

월, 일이 한자리일 때는 앞에 0을 붙이지 않고 2020-2-25처럼 입력해도 된다.

[Date 객체로 특정 날짜 나타내기](./Doit_JavaScript_day30-2.html)

또한 시간 정보까지 Date객체로 나타내려면 날짜 다음에 대문자 'T'를 추가한 후 그 뒤에 시간을 입력한다.

[Date 객체로 특정 날짜와 시간 나타내기](./Doit_JavaScript_day30-3.html)

<br>

### 자바스크립트의 날짜, 시간 입력 방식 알아보기

<br>

Date 객체를 사용하여 날짜와 시간을 지정하려면 자바스크립트가 인식할 수 있는 날짜와 시간 형식으로 써야 한다.

자바스크립트에서 주로 사용하는 날짜와 시간 입력 방식을 알아보자.

다음 형식에서 YYYY는 연도를, MM은 월을, DD는 일을 뜻하고, 

시간 입력 형식에서 HH는 시를, MM은 분을, SS는 초를 의미한다.

<br>

1) YYYY-MM-DD 형식

    다음과 같이 연도만 나타낼 때는 YYYY, 연도와 월을 나타낼 때는 YYYY-MM, 
    
    연도와 월과 일을 나타낼 때는 YYYY-MM-DD 형태로 사용한다.

        new Date('2020')
        new Date('2020-02')
        new Date('2020-02-25')

2) YYYY-MM-DDTHH 형식

    연도, 월, 일 다음에 시간을 표시하는 형식이다.

    시간을 나타낼 때는 날짜 뒤에 'T'를 붙이고 HH:MM:SS의 형태로 사용한다.

    맨 끝에 'Z'를 붙이면 UTC(국제 표준시)로 표시된다.

        new Date('2020-02-25T18:00:00')
        new Date('2020-02-25T18:00:00Z')

3) MM/DD/YYYY 형식

    연도를 마지막에 나타내고 싶다면 다음과 같이 MM/DD/YYY 형태로 사용한다.

        new Date('02/25/2020')

4) 이름 형식

    월은 January처럼 전체를 사용하거나 Jan과 같이 줄여서 사용할 수 있다.

    다음과 같이 맨 앞에 요일(Mon)을 함께 작성할 수도 있다.

        new Date('Mon Jan 20 2020 15:00:41 GMT+0900 (대한민국 표준시)')

<br>

### Date 객체의 메서드

<br>

날짜와 시간 정보를 사용하기 위한 Date 객체를 만들었다면 Date 객체에 정의된 메서드를 사용할 수 있다.

Date 객체의 메서드는 크게 3가지로 구분된다.

날짜/시간 정보를 가져오는 메서드, 사용자가 원하는 날짜/시간으로 설정하는 메서드, 

마지막으로 날짜/시간 형식을 바꿔 주는 메서드가 있다.

함수 이름 앞에 get이나 set이 붙어 있는데, get은 '가져온다'는 의미이고 set은 '두다, 설정하다'를 뜻한다.

||구분|설명|
|----|----|----|
|날짜/시간정보 가져오기|getFullYear()|연도를 4자리 숫자로 표시한다.|
|날짜/시간정보 가져오기|getMonth()|0~11 사이의 숫자로 월을 표시한다. 0부터 1월이 시작되고 11은 12월이다.|
|날짜/시간정보 가져오기|getDate()|1~31 사이의 숫자로 일을 표시한다.|
|날짜/시간정보 가져오기|getDay()|0~6 사이의 숫자로 요일을 표시한다. 0부터 일요일이 시작되고 6은 토요일이다.|
|날짜/시간정보 가져오기|getTime()|1970년 1월 1일 자정 이후의 시간을 밀리 초(1/1000초)로 표시한다.|
|날짜/시간정보 가져오기|getHours()|0~23 사이의 숫자로 시를 표시한다.|
|날짜/시간정보 가져오기|getMinutes()|0~59 사이의 숫자로 분을 표시한다.|
|날짜/시간정보 가져오기|getSeconds()|0~59 사이의 숫자로 초를 표시한다.|
|날짜/시간정보 가져오기|getMilliseconds()|0~999 사이의 숫자로 밀리초를 표시한다.|

<br>

||구분|설명|
|----|----|----|
|날짜/시간정보 설정하기|setFullYear()|연도를 4자리 숫자로 설정한다.|
|날짜/시간정보 설정하기|setMonth()|0~11 사이의 숫자로 월을 설정한다. 0부터 1월이 시작되고 11은 12월이다.|
|날짜/시간정보 설정하기|setDate()|1~31 사이의 숫자로 일을 설정한다.|
|날짜/시간정보 설정하기|setDay()|0~6 사이의 숫자로 요일을 설정한다. 0부터 일요일이 시작되고 6은 토요일이다.|
|날짜/시간정보 설정하기|setTime()|1970년 1월 1일 자정 이후의 시간을 밀리 초(1/1000초)로 설정한다.|
|날짜/시간정보 설정하기|setHours()|0~23 사이의 숫자로 시를 설정한다.|
|날짜/시간정보 설정하기|setMinutes()|0~59 사이의 숫자로 분을 설정한다.|
|날짜/시간정보 설정하기|setSeconds()|0~59 사이의 숫자로 초를 설정한다.|
|날짜/시간정보 설정하기|setMilliseconds()|0~999 사이의 숫자로 밀리초를 설정한다.|

<br>

||구분|설명|
|----|----|----|
|날짜/시간 형식 바꾸기|toLocaleString()|현재 날짜와 시간을 현지 시간(local time)으로 표시한다.|
|날짜/시간 형식 바꾸기|toString()|Date 객체 타입을 문자열로 표시한다.|