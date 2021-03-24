***
## 정규표현식 2
***

### 문자열 메소드 실행

String.match() - RegExp.exec()와 비슷하다

String.replace() - 문자열에서 패턴을 검색해서 이를 변경한 후에 변경된 값을 리턴한다 / 치환

***
### 정규표현식의 옵션

정규표현식 패턴을 만들 때 옵션을 설정할 수 있다. 옵션에 따라서 검출되는 데이터가 달라진다.

i
i를 붙이면 대소문자를 구분하지 않느다.

g
g를 붙이면 검색된 모든 결과를 리턴한다.

***
### 캡쳐

괄호안의 패턴은 마치 변수처럼 재사용할 수 있다. 

이 때 기호 $를 사용하는데 아래 코드는 coding과 everybody의 순서를 역전시킨다.

var pattern = /(\w+)\s(\w+)/;

var str = "coding everybody";

var result = str.replace(pattern, "$2, $1");

console.log(result);

***
### (\w+)\s(\w+) 해석

( )괄호는 그룹

\\w는 문자, a-z, A-Z, 0-9를 의미한다

+는 수량자, 앞에 있는 \\w가(문자가) 하나 이상 이라는 것을 의미

\\s는 띄어쓰기, 공백, white space를 의미한다

결국 /(\w+)\s(\w+)/가 의미하는 것은

#### 여러문자/그룹1 + 띄어쓰기 + 여러문자/그룹2 를 의미한다

***
### String.replace() 의 파라미터

String.replace(A, B)

String을 A로 바꾼다

두번째 파라미터는 법칙, 어떻게 바꿀 것인가를 의미한다
***
### 치환

아래 코드는 본문 중의 URL을 링크 html 태그로 교체한다. 

var urlPattern = /\b(?:https?):\/\/[a-z0-9-+&@#\/%?=~_|!:,.;]*/gim;

var content = '생활코딩 : http://opentutorials.org/course/1 입니다. 네이버 : http://naver.com 입니다. ';

var result = content.replace(urlPattern, function(url){

return '<a href="'+url+'">'+url+'</a>';

});

console.log(result);

***
정규 표현식을 시각화 해서 볼 수 있는 사이트

참고 : https://regexper.com/
