## Web APIs - Introduction

Web API는 개발자의 꿈입니다.

- 브라우저의 기능을 확장할 수 있습니다.
- 복잡한 기능을 크게 단순화할 수 있습니다.
- 복잡한 코드에 쉬운 구문을 제공할 수 있습니다.

### What is Web API ??

API는 Application Programming Interface의 약자 입니다.

Web API는 웹용 응용 프로그래밍 인터페이스입니다.

브라우저 API는 웹 브라우저의 기능을 확장할 수 있습니다.

서버 API는 웹 서버의 기능을 확장할 수 있습니다.

---

### 브라우저 API

모든 브라우저에는 복잡한 작업을 지원하고 데이터 액세스를 지원하는 내장 웹 API 세트가 있습니다.

예를 들어 Geolocation API는 브라우저가 있는 위치의 좌표를 반환할 수 있습니다.

    예시 - 사용자 위치의 위도와 경도를 가져옵니다.

    const myElement = document.getElementById("demo");

    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition);
      } else {
        myElement.innerHTML = "Geolocation is not supported by this browser.";
      }
    }

    function showPosition(position) {
      myElement.innerHTML = "Latitude: " + position.coords.latitude +
      "<br>Longitude: " + position.coords.longitude;
    }

---

### 타사 API

타사 API는 브라우저에 내장되어 있지 않습니다.

이러한 API를 사용하려면 웹에서 코드를 다운로드해야 합니다.

    예:

    YouTube API - 웹 사이트에 비디오를 표시할 수 있습니다.
    Twitter API - 웹사이트에 트윗을 표시할 수 있습니다.
    Facebook API - 웹 사이트에 Facebook 정보를 표시할 수 있습니다.
