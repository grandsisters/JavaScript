***
## UI와 API 그리고 문서보는 법
***

## UI란?
User Interface의 약자로 사람과 사물 또는 시스템, 특히 기계, 컴퓨터 프로그램 등 사이에서 의사소통을 할 수 있도록 일시적 또는 영구적인 접근을 목적으로 만들어진 물리적, 가상적 매개체를 뜻한다. 사용자 인터페이스는 사람들이 컴퓨터와 상호 작용하는 시스템이다.


## API란?

Application Programming Interface의 약자로 프로그램이 동작하는 환경을 제어하기 위해서 환경에서 제공되는 조작 장치이다. 이 조작 장치는 프로그래밍 언어를 통해서 조작할 수 있다

***
***
## 정규 표현식
***

정규표현식(regular expression)은 문자열을 처리하는 방법 중의 하나로 특정한 
조건의 문자를 '검색'하거나 '치환'하는 과정을 매우 간편하게 처리 할 수 있도록 
하는 수단이다. 이 도구를 이용하면 수십줄이 필요한 작업을 한줄로 끝낼 수 
있다. 

***
## 정규표현식 생성
***
정규표현식은 두가지 단계로 이루어진다. 하나는 컴파일(compile) 다른 하나는 실행(execution)이다. 우선 컴파일부터 알아보자.

### 컴파일
***
컴파일은 검출하고자 하는 패턴을 만드는 일이다. 우선 정규표현식 객체를 만들어야 한다.

객체를 만드는 방법에는 두가지가 있는데
<ul>
<li>정규표현식 리터럴</li>
var pattern = /a/

<li>정규표현식 객체 생성자</li>
var pattern = new RegExp('a');
</ul>
두가지 모두 같은 결과를 만들지만 각자가 장단점이 있다. 

정규표현식을 컴파일해서 객체를 만들었다면 이제 문자열에서 원하는 문자를 찾아내야 한다. 

RegExp.exec()

console.log(pattern.exec('abcdef')); // ["a"]
실행결과는 문자열 a를 값으로 하는 배열을 리턴한다.


console.log(pattern.exec('bcdefg')); // null
인자 'bcdef'에는 a가 없기 때문에 null을 리턴한다.

RegExp.test()
test는 인자 안에 패턴에 해당되는 문자열이 있으면 true, 없으면 false를 리턴한다.

console.log(pattern.test('abcdef')); // true

cnosole.log(pattern.test('bcdefg')); // false