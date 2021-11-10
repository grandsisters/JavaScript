## JSON - Introduction

JSON은 JavaScript Object Notation의 약자 입니다.

JSON은 데이터 저장 및 전송을 위한 텍스트 형식 입니다.

JSON은 "자체 설명"이며 이해하기 쉽습니다.

### JSON 예제

이 예는 JSON 문자열입니다.

    '{"name":"John", "age":30, "car":null}'

3가지 속성을 가진 객체를 정의합니다.

- 이름
- 나이
- 자동차

각 속성에는 값이 있습니다.

JavaScript 프로그램으로 JSON 문자열을 구문 분석하면 데이터에 객체로 액세스할 수 있습니다.

    let personName = obj.name;
    let personAge = obj.age;

---

### JSON이란 무엇입니까?

- JSON은 경량 데이터 교환 형식입니다.
- JSON은 JavaScript 객체 표기법으로 작성된 일반 텍스트입니다.
- JSON은 컴퓨터 간에 데이터를 전송하는 데 사용됩니다.
- JSON은 언어에 독립적입니다

JSON 구문은 JavaScript 객체 표기법에서 파생되지만 JSON 형식은 텍스트 전용입니다.

JSON을 읽고 생성하기 위한 코드는 많은 프로그래밍 언어에 존재합니다.

---

### JSON을 사용하는 이유

JSON 형식은 JavaScript 객체를 생성하기 위한 코드와 구문적으로 유사합니다.

이 때문에 JavaScript 프로그램은 JSON 데이터를 JavaScript 객체로 쉽게 변환할 수 있습니다.

형식이 텍스트 전용이므로 JSON 데이터를 컴퓨터 간에 쉽게 전송할 수 있으며 모든 프로그래밍 언어에서 사용할 수 있습니다.

JavaScript에는 JSON 문자열을 JavaScript 객체로 변환하는 내장 함수가 있습니다.

    JSON.parse()

JavaScript에는 객체를 JSON 문자열로 변환하는 내장 함수도 있습니다.

    JSON.stringify()

서버에서 순수 텍스트를 받아 JavaScript 객체로 사용할 수 있습니다.

JavaScript 개체를 순수 텍스트 형식으로 서버에 보낼 수 있습니다.

복잡한 구문 분석 및 번역 없이 데이터를 JavaScript 개체로 사용할 수 있습니다.

---

### 데이터 저장

데이터를 저장할 때 데이터는 특정 형식이어야 하며 저장 위치에 관계없이 텍스트 는 항상 합법적인 형식 중 하나입니다.

JSON을 사용하면 JavaScript 객체를 텍스트로 저장할 수 있습니다.
