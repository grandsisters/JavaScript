## JavaScript Cookies

쿠키를 사용하면 웹 페이지에 사용자 정보를 저장할 수 있습니다.

---

### 쿠키란?

쿠키는 귀하의 컴퓨터에 작은 텍스트 파일로 저장되는 데이터입니다.

웹 서버가 웹 페이지를 브라우저로 보내면 연결이 종료되고 서버는 사용자에 대한 모든 정보를 잊어버립니다.

쿠키는 "사용자에 대한 정보를 기억하는 방법" 문제를 해결하기 위해 발명되었습니다.

사용자가 웹 페이지를 방문할 때 그의 이름이 쿠키에 저장될 수 있습니다.
다음에 사용자가 페이지를 방문할 때 쿠키는 사용자의 이름을 "기억"합니다.
쿠키는 다음과 같은 이름-값 쌍으로 저장됩니다.

    username = John Doe

브라우저가 서버에 웹 페이지를 요청하면 해당 페이지에 속한 쿠키가 요청에 추가됩니다. 이런 식으로 서버는 사용자에 대한 정보를 "기억"하는 데 필요한 데이터를 얻습니다.

브라우저에 로컬 쿠키 지원이 꺼져 있으면 아래 예 중 어느 것도 작동하지 않습니다.

---

### JavaScript로 쿠키 만들기

JavaScript는 document.cookie 속성을 사용하여 쿠키를 만들고 읽고 삭제할 수 있습니다 .

JavaScript를 사용하면 다음과 같이 쿠키를 만들 수 있습니다.

    document.cookie = "username=John Doe";

만료 날짜(UTC 시간)를 추가할 수도 있습니다. 기본적으로 쿠키는 브라우저가 닫힐 때 삭제됩니다.

    document.cookie = "username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 UTC";

경로 매개변수를 사용하면 쿠키가 속한 경로를 브라우저에 알릴 수 있습니다. 기본적으로 쿠키는 현재 페이지에 속합니다.

    document.cookie = "username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/";

---

### JavaScript로 쿠키 읽기

JavaScript를 사용하면 쿠키를 다음과 같이 읽을 수 있습니다.

    let x = document.cookie;

document.cookie다음과 같이 모든 쿠키를 하나의 문자열로 반환합니다.

    cookie1=value; 쿠키2=값; 쿠키3=값;

---

### JavaScript로 쿠키 변경

JavaScript를 사용하면 쿠키를 만들 때와 같은 방식으로 쿠키를 변경할 수 있습니다.

    document.cookie = "username=John Smith; expires=Thu, 18 Dec 2013 12:00:00 UTC; path=/";

이전 쿠키를 덮어씁니다.

---

### JavaScript로 쿠키 삭제

쿠키를 삭제하는 것은 매우 간단합니다.

쿠키를 삭제할 때 쿠키 값을 지정할 필요가 없습니다.

만료 매개변수를 과거 날짜로 설정하기만 하면 됩니다.

    document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 UTC; path=/;";

올바른 쿠키를 삭제하려면 쿠키 경로를 정의해야 합니다.

일부 브라우저에서는 경로를 지정하지 않으면 쿠키를 삭제할 수 없습니다.

---

### 쿠키 문자열

document.cookie속성은 일반 텍스트 문자열처럼 보인다. 하지만 그렇지 않습니다.

document.cookie에 전체 쿠키 문자열을 작성하더라도 다시 읽을 때 이름-값 쌍만 볼 수 있습니다.

새 쿠키를 설정하면 이전 쿠키를 덮어쓰지 않습니다.

새 쿠키가 document.cookie에 추가되었으므로 document.cookie를 다시 읽으면 다음과 같은 결과를 얻게 됩니다.

지정된 쿠키 하나의 값을 찾으려면 쿠키 문자열에서 쿠키 값을 검색하는 JavaScript 함수를 작성해야 합니다.

---

### 자바스크립트 쿠키 예

다음 예에서는 방문자의 이름을 저장하는 쿠키를 만듭니다.

방문자가 웹 페이지에 처음 도착하면 이름을 입력해야 합니다. 그런 다음 이름이 쿠키에 저장됩니다.

방문자가 다음에 같은 페이지에 도착하면 환영 메시지를 받게 됩니다.

예를 들어 3개의 JavaScript 함수를 만들 것입니다.

1. 쿠키 값을 설정하는 함수
2. 쿠키 값을 가져오는 함수
3. 쿠키 값을 확인하는 함수

---

### 쿠키를 설정하는 기능

먼저 function방문자의 이름을 쿠키 변수에 저장 하는 함수를 만듭니다 .

    예시
    function setCookie(cname, cvalue, exdays) {
    const d = new Date();
    d.setTime(d.getTime() + (exdays*24*60*60*1000));
    let expires = "expires="+ d.toUTCString();
    document.cookie = cname + "=" + cvalue + ";" + expires + ";path=/";
    }

설명된 예:

위 함수의 매개변수는 쿠키의 이름(cname), 쿠키의 값(cvalue), 쿠키가 만료될 때까지 남은 일수(exdays)입니다.

이 함수는 쿠키 이름, 쿠키 값 및 만료 문자열을 함께 추가하여 쿠키를 설정합니다.

---

### 쿠키를 가져오는 함수

그런 다음 function지정된 쿠키의 값을 반환하는 다음을 생성합니다 .

    예시
    function getCookie(cname) {
      let name = cname + "=";
      let decodedCookie = decodeURIComponent(document.cookie);
      let ca = decodedCookie.split(';');
      for(let i = 0; i <ca.length; i++) {
        let c = ca[i];
        while (c.charAt(0) == ' ') {
          c = c.substring(1);
        }
        if (c.indexOf(name) == 0) {
          return c.substring(name.length, c.length);
        }
      }
      return "";
    }

기능 설명:

쿠키 이름을 매개변수(cname)로 사용합니다.

검색할 텍스트(cname + "=")로 변수(이름)를 만듭니다.

쿠키 문자열을 디코딩하여 특수 문자가 있는 쿠키를 처리합니다(예: '$').

세미콜론에 있는 document.cookie를 ca라는 배열로 분할합니다(ca = decodedCookie.split(';')).

ca 배열(i = 0; i < ca.length; i++)을 순환하고 각 값 c = ca[i])를 읽습니다.

쿠키가 발견되면(c.indexOf(name) == 0) 쿠키의 값(c.substring(name.length, c.length)을 반환합니다.

쿠키를 찾을 수 없으면 ""를 반환합니다.

---

### 쿠키를 확인하는 기능

마지막으로 쿠키가 설정되었는지 확인하는 함수를 만듭니다.

쿠키가 설정되면 인사말이 표시됩니다.

쿠키가 설정되지 않은 경우 사용자 이름을 묻는 프롬프트 상자가 표시되고 다음 setCookie함수 를 호출하여 사용자 이름 쿠키를 365일 동안 저장합니다 .

    예시
    function checkCookie() {
      let username = getCookie("username");
      if (username != "") {
      alert("Welcome again " + username);
      } else {
        username = prompt("Please enter your name:", "");
        if (username != "" && username != null) {
          setCookie("username", username, 365);
        }
      }
    }

[All Together Now](./W3_JavaScript_BOM_Cookies.html)
