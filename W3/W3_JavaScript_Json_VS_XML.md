## JSON vs XML

JSON과 XML 모두 웹 서버에서 데이터를 수신하는 데 사용할 수 있습니다.

---

다음 JSON 및 XML 예제는 모두 3명의 직원 배열로 직원 개체를 정의합니다.

### JSON 예제

    {"employees":[
      { "firstName":"John", "lastName":"Doe" },
      { "firstName":"Anna", "lastName":"Smith" },
      { "firstName":"Peter", "lastName":"Jones" }
    ]}

### XML 예제

    <employees>
      <employee>
        <firstName>John</firstName> <lastName>Doe</lastName>
      </employee>
      <employee>
        <firstName>Anna</firstName> <lastName>Smith</lastName>
      </employee>
      <employee>
        <firstName>Peter</firstName> <lastName>Jones</lastName>
      </employee>
    </employees>

---

### JSON이 XML과 비슷한 점

- JSON과 XML은 모두 "자체 설명"(사람이 읽을 수 있음)
- JSON과 XML은 모두 계층적입니다(값 내의 값).
- JSON과 XML은 모두 많은 프로그래밍 언어에서 구문 분석되고 사용될 수 있습니다.
- XMLHttpRequest를 사용하여 JSON과 XML을 모두 가져올 수 있습니다.

---

### JSON이 XML과 다른점.

- JSON은 종료 태그를 사용하지 않습니다.
- JSON이 더 짧습니다.
- JSON은 읽고 쓰기가 더 빠릅니다.
- JSON은 배열을 사용할 수 있습니다.

가장 큰 차이점은 다음과 같습니다.

    XML은 XML 파서로 파싱되어야 합니다. JSON은 표준 JavaScript 함수로 구문 분석할 수 있습니다.

---

### JSON이 XML보다 나은 이유

    XML은 JSON보다 구문 분석하기가 훨씬 더 어렵습니다.
    JSON은 바로 사용할 수 있는 JavaScript 객체로 구문 분석됩니다.

AJAX 애플리케이션의 경우 JSON은 XML보다 빠르고 쉽습니다.

XML 사용

- XML 문서 가져오기
- XML DOM을 사용하여 문서 반복
- 값을 추출하고 변수에 저장

JSON 사용

- JSON 문자열 가져오기
- JSON.JSON 문자열 구문 분석
