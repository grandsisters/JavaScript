## AJAX Introduction

AJAX는 다음과 같은 이유로 개발자의 꿈입니다.

- 웹 서버에서 데이터 읽기 - 페이지가 로드된 후
- 페이지를 다시 로드하지 않고 웹 페이지 업데이트
- 웹 서버에 데이터 보내기 - 백그라운드에서

---

### AJAX란 무엇입니까?

AJAX = 동기 J avaScript ND X ML.

AJAX는 프로그래밍 언어가 아닙니다.

AJAX는 다음 조합을 사용합니다.

- 브라우저 내장 XMLHttpRequest객체(웹 서버에서 데이터를 요청하기 위해)
- JavaScript 및 HTML DOM(데이터 표시 또는 사용)

AJAX는 오해의 소지가 있는 이름입니다.

    AJAX 애플리케이션은 XML을 사용하여 데이터를 전송할 수 있지만 데이터를 일반 텍스트 또는 JSON 텍스트로 전송하는 것도 마찬가지로 일반적입니다.

AJAX를 사용하면 배후에서 웹 서버와 데이터를 교환하여 웹 페이지를 비동기적으로 업데이트할 수 있습니다. 즉, 전체 페이지를 다시 로드하지 않고도 웹 페이지의 일부를 업데이트할 수 있습니다.

---

## AJAX 작동 방식

<img src='https://www.w3schools.com/js/pic_ajax.gif'>

1. 웹페이지에서 이벤트 발생(페이지 로딩, 버튼 클릭)
2. XMLHttpRequest 객체는 JavaScript에 의해 생성됩니다.
3. XMLHttpRequest 객체는 웹 서버에 요청을 보냅니다.
4. 서버가 요청을 처리합니다.
5. 서버가 웹 페이지에 응답을 보냅니다.
6. JavaScript에서 응답을 읽습니다.
7. 페이지 업데이트와 같은 적절한 조치는 JavaScript에 의해 수행됩니다.
