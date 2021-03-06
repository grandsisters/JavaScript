## 웹 브라우저가 자바스크립트를 만났을때

웹 브라우저에는 자바스크립트 소스를 읽고 처리하는 해석기(JavaScript interpreter)가 있다.

따라서 자바스크립트 소스는 웹 문서에서 script태그를 이용해 작성할 수 있다.

또는 자바 스크립트 소스만 별도 스크립트 파일로 작성한 후 웹 문서와 연결해서 사용할 수도 있다.

***
### 웹 문서 안에 script 태그로 자바스크립트 작성하기

<br>

자바스크립트 소스 코드가 짧을 경우 웹 문서에서 자바스크립트를 실행할 위치에 바로 코드를 작성할 수 있다.

웹 문서에서 script태그 사이에 실행할 자바스크립트 소스를 작성하는 것이다.

script 태그는 웹 문서 안의 어디든 위치할 수 있고 삽입된 위치 그 자리에서 바로 스크립트가 실행된다.

또한 script 태그는 하나의 문서에서 여러 개 사용할 수도 있다.

자바스크립트는 웹 문서에서 이미지나 텍스트 등의 요소를 제어하는 경우가 많으므로 되도록이면 이미지나 텍스트 등을 다 표시한 후에 실행하는 것이 좋다.

그래서 body태그 직전에 자바스크립트 소스를 삽입한다.

HTML, CSS와 달리 자바스크립트에서는 영어 대소 문자를 구별하므로 소스를 작성할 때 주의해야 한다.

변수 이름이나 함수를 지정할 때에는 영문 대소 문자를 정확하게 구별해야 한다.

이렇게 HTML 문서 안에 자바스크립트 소스를 작성하면 웹 문서에서 바로 확인할 수 있는 장점도 있지만 단점이 더 많다.

- 우선 HTML 태그와 자바스크립트 소스가 함께 섞여 있어서 웹 문서가 복자해 보인다.

- 여러 웹 문서에서 같은 자바스크립트 소스를 사용하는 경우에 똑같은 소스를 반복해서 삽입해야 한다. 이때 자바스크립트 소스를 수정해야 한다면 이 소스가 포함된 모든 웹 문서를 찾아다니며 수정해야 한다.

그래서 자바스크립트 소스를 작성할 때 외부 스크립트 파일로 저장해서 웹 문서와 연결하는 방법을 많이 사용한다.

***
### 외부 스크립트 파일로 연결해서 자바스크립트 작성하기

<br>

CSS와 마찬가지로 자바스크립트 소스도 따로 파일로 저장한 후 웹 문서에 연결해서 사용할 수 있다.

이렇게 하면 웹 문서 안에는 직접 자바스크립트 소스가 드러나지 않고 HTML 태그와 CSS만 유지할 수 있어서 소스가 한결 깔끔하다.

외부 자바스크립트 파일은 script 태그 없이 자바스크립트 소스만 작성하고 확장자는 *.js 파일로 저장한다.

그리고 HTML 문서에서 script 태그의 src 속성을 이용해서 자바스크립트 파일을 연결하면 된다.

이때 연결한 자바스크립트 파일은 마치 웹 문서에서 직접 작성한 자바스크립트 소스처럼 사용할 수 있다.

이 방법을 이용하면 간단히 JS 파일만 수정해도 연결된 모든 HTML 문서에 바로 적용된다.

이렇게 자바스크립트 소스를 따로 작성하여 HTML 문서에 연결하는 것을 '외부 스크립트 파일을 연결한다'고 말한다.

    기본형 <script src='외부 스크립트 파일 경로'></script>

***
### 웹 브라우저에서 스크립트를 해석하는 과정

<br>

웹 문서에 자바스크립트 소스가 포함되어 있으면 웹 브라우저는 어떤 과정으로 해석하고 그 결과를 보여줄지 확인해보자.

    HTML 분석기
    
    <!DOCTYPE html>
    <html lang="ko">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>글자색 바꾸기</title>

--- 
    CSS 분석기

        <style>
            body { text-align:center; }
            #heading { color:blue; }
            #text { 
                color:gray;
                font-size:15px;
            }
        </style>	
    </head>
    <body>
        <h1 id="heading">자바스크립트</h1>
        <p id="text">위 텍스트를 클릭해 보세요</p>

---
    자바스크립트 해석기

        <script>
            var heading = document.querySelector('#heading');
            heading.onclick = function() {
                heading.style.color = 'red';
            }
        </script>
    </body>
    </html>

1) 웹 브라우저는 !DOCTYPE html를 보고 이 문서가 웹 문서라는 것을 알게된다. 그리고 html태그 사이의 내용을 HTML 표준에 맞춰 읽기 시작한다.

2) 웹 문서에서 HTML 태그의 순서와 포함 관계를 확인한다. head태그와 body태그 사이에 각각 어떤 태그가 있는지 확인하고 태그 간의 관계는 어떻게 되어 있는지 등을 분석한다.

3) 태그 분석이 끝나면 스타일 정보를 분석한다.

4) script 태그를 만나면 웹 브라우저 안에 포함된 자바스크립트 해석기에게 스크립트 소스를 넘긴다. 자바스크립트 해석기는 script 사이의 소스를 해석한다.

5) 2에서 분석한 HTML과 3에서 분석한 CSS 정보에 따라 웹 브라우저 화면에 표시한다.

6) 웹 브라우저에서 '자바스크립트' 텍스트를 클릭하면 분석해 놓은 자바스크립트를 실행해서 그 결과를 화면에 표시한다.