## Web Geolocation API

---

### 사용자의 위치 찾기

HTML Geolocation API는 사용자의 지리적 위치를 얻는 데 사용됩니다.

이는 개인정보를 침해할 수 있으므로 사용자가 승인하지 않는 한 해당 위치를 사용할 수 없습니다.

참고: 지리적 위치는 스마트폰과 같이 GPS가 있는 장치에서 가장 정확합니다.

---

### 지리적 위치 API 사용

이 getCurrentPosition()메서드는 사용자의 위치를 ​​반환하는 데 사용됩니다.

아래 예는 사용자 위치의 위도와 경도를 반환합니다.

    예시
    <script>
    const x = document.getElementById("demo");
    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.getCurrentPosition(showPosition);
      } else {
        x.innerHTML = "Geolocation is not supported by this browser.";
      }
    }

    function showPosition(position) {
      x.innerHTML = "Latitude: " + position.coords.latitude +
      "<br>Longitude: " + position.coords.longitude;
    }
    </script>

예시 설명:

- 지리적 위치가 지원되는지 확인
- 지원되는 경우 getCurrentPosition() 메서드를 실행합니다. 그렇지 않은 경우 사용자에게 메시지 표시
- getCurrentPosition() 메서드가 성공하면 매개변수(showPosition)에 지정된 함수에 좌표 객체를 반환합니다.
- showPosition() 함수는 위도와 경도를 출력합니다.

위의 예는 오류 처리가 없는 매우 기본적인 Geolocation 스크립트입니다.

---

### 오류 및 거부 처리

getCurrentPosition()메소드 의 두 번째 매개변수는 오류를 처리하는 데 사용됩니다. 사용자의 위치를 ​​가져오지 못하는 경우 실행할 함수를 지정합니다.

    예시
    function showError(error) {
      switch(error.code) {
        case error.PERMISSION_DENIED:
          x.innerHTML = "User denied the request for Geolocation."
          break;
        case error.POSITION_UNAVAILABLE:
          x.innerHTML = "Location information is unavailable."
          break;
        case error.TIMEOUT:
          x.innerHTML = "The request to get user location timed out."
          break;
        case error.UNKNOWN_ERROR:
          x.innerHTML = "An unknown error occurred."
          break;
      }
    }

---

### 지도에 결과 표시

결과를 지도에 표시하려면 Google 지도와 같은 지도 서비스에 액세스해야 합니다.

아래 예에서 반환된 위도와 경도는 Google 지도에 위치를 표시하는 데 사용됩니다(정적 이미지 사용).

    예시
    function showPosition(position) {
      let latlon = position.coords.latitude + "," + position.coords.longitude;

      let img_url = "https://maps.googleapis.com/maps/api/staticmap?center=
      "+latlon+"&zoom=14&size=400x300&sensor=false&key=YOUR_KEY";

      document.getElementById("mapholder").innerHTML = "<img src='"+img_url+"'>";
    }

---

### 위치별 정보

이 페이지에서는 지도에서 사용자의 위치를 ​​표시하는 방법을 보여주었습니다.

지리적 위치는 다음과 같은 위치별 정보에도 매우 유용합니다.

- 최신 지역 정보
- 사용자 주변의 관심 지점 표시
- 턴 바이 턴 내비게이션(GPS)

---

### getCurrentPosition() 메서드 - 데이터 반환

getCurrentPosition()방법은 성공에 대한 개체를 반환합니다. 위도, 경도 및 정확도 속성은 항상 반환됩니다. 사용 가능한 경우 다른 속성이 반환됩니다.

| Property                | Returns                                                                 |
| ----------------------- | ----------------------------------------------------------------------- |
| coords.latitude         | The latitude as a decimal number (always returned)                      |
| coords.longitude        | The longitude as a decimal number (always returned)                     |
| coords.accuracy         | The accuracy of position (always returned)                              |
| coords.altitude         | The altitude in meters above the mean sea level (returned if available) |
| coords.altitudeAccuracy | The altitude accuracy of position (returned if available)               |
| coords.heading          | The heading as degrees clockwise from North (returned if available)     |
| coords.speed            | The speed in meters per second (returned if available)                  |
| timestamp               | The date/time of the response (returned if available)                   |

---

### Geolocation 개체 - 기타 흥미로운 방법

Geolocation 객체에는 다른 흥미로운 방법도 있습니다.

- watchPosition() - 사용자의 현재 위치를 반환하고 사용자가 이동함에 따라 업데이트된 위치를 계속 반환합니다(예: 자동차의 GPS).
- clearWatch()- watchPosition()메서드를 중지합니다 .

아래 예는 watchPosition()방법을 보여줍니다 . 이를 테스트하려면 정확한 GPS 장치(예: 스마트폰)가 필요합니다.

    예시
    <script>
    const x = document.getElementById("demo");
    function getLocation() {
      if (navigator.geolocation) {
        navigator.geolocation.watchPosition(showPosition);
      } else {
        x.innerHTML = "Geolocation is not supported by this browser.";
      }
    }
    function showPosition(position) {
      x.innerHTML = "Latitude: " + position.coords.latitude +
      "<br>Longitude: " + position.coords.longitude;
    }
    </script>
