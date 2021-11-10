## JSON Data Types

---

### 유효한 데이터 유형

JSON에서 값은 다음 데이터 유형 중 하나여야 합니다.

- 문자열
- 숫자
- 객체(JSON 객체)
- 배열
- 참이나 거짓
- null

JSON 값 은 다음 데이터 유형 중 하나일 수 없습니다 .

- function
- date
- undefined

---

### JSON 문자열

JSON의 문자열은 큰따옴표로 묶어야 합니다.

    예시
    {"name":"John"}

---

### JSON 숫자

JSON의 숫자는 정수 또는 부동 소수점이어야 합니다.

    예시
    {"age":30}

---

### JSON 객체

JSON의 값은 객체가 될 수 있습니다.

    예시
    {
    "employee":{"name":"John", "age":30, "city":"New York"}
    }

JSON의 값인 객체는 JSON 구문을 따라야 합니다.

---

### JSON 배열

JSON의 값은 배열일 수 있습니다.

    예시
    {
    "employees":["John", "Anna", "Peter"]
    }

---

### JSON boolean

JSON의 값은 참/거짓일 수 있습니다.

    예시
    {"sale":true}

---

### JSON null

JSON의 값은 null일 수 있습니다.

    예시
    {"middlename":null}
