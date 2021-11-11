## JSON.stringify()

JSON의 일반적인 용도는 웹 서버와 데이터를 교환하는 것입니다.

웹 서버에 데이터를 보낼 때 데이터는 문자열이어야 합니다.

JSON.stringify()를 사용하여 JavaScript 개체를 문자열로 변환합니다 .

---

### JavaScript 객체 문자열화

JavaScript에 이 객체가 있다고 상상해보십시오.

    const obj = {name: "John", age: 30, city: "New York"};

JavaScript 함수 JSON.stringify()를 사용하여 문자열로 변환합니다.

    const myJSON = JSON.stringify(obj);

결과는 JSON 표기법을 따르는 문자열입니다.

myJSON 이제 문자열이며 서버로 보낼 준비가 되었습니다.

    예시
    const obj = {name: "John", age: 30, city: "New York"};
    const myJSON = JSON.stringify(obj);

---

### JavaScript 배열 문자열화

JavaScript 배열을 문자열화하는 것도 가능합니다:

JavaScript에 다음 배열이 있다고 상상해보십시오.

    const arr = ["John", "Peter", "Sally", "Jane"];

JavaScript 함수 JSON.stringify()를 사용하여 문자열로 변환합니다.

    const myJSON = JSON.stringify(arr);

결과는 JSON 표기법을 따르는 문자열입니다.

myJSON 이제 문자열이며 서버로 보낼 준비가 되었습니다.

    예시
    const arr = ["John", "Peter", "Sally", "Jane"];
    const myJSON = JSON.stringify(arr);

---

### 데이터 저장

데이터를 저장할 때 데이터는 특정 형식이어야 하며 저장 위치에 관계없이 텍스트 는 항상 합법적인 형식 중 하나입니다.

JSON을 사용하면 JavaScript 객체를 텍스트로 저장할 수 있습니다.

    예시
    로컬 저장소에 데이터 저장

    // Storing data:
    const myObj = {name: "John", age: 31, city: "New York"};
    const myJSON = JSON.stringify(myObj);
    localStorage.setItem("testJSON", myJSON);

    // Retrieving data:
    let text = localStorage.getItem("testJSON");
    let obj = JSON.parse(text);
    document.getElementById("demo").innerHTML = obj.name;

---

### 예외

### 날짜 문자열화

JSON에서는 날짜 개체가 허용되지 않습니다. 이 JSON.stringify()함수는 모든 날짜를 문자열로 변환합니다.

    예시
    const obj = {name: "John", today: new Date(), city : "New York"};
    const myJSON = JSON.stringify(obj);

수신기에서 문자열을 다시 날짜 개체로 변환할 수 있습니다.

### 문자열화 함수

JSON에서 함수는 객체 값으로 허용되지 않습니다.

이 JSON.stringify()함수는 키와 값 모두 JavaScript 객체에서 모든 기능을 제거합니다.

    예시
    const obj = {name: "John", age: function () {return 30;}, city: "New York"};
    const myJSON = JSON.stringify(obj);

함수를 실행하기 전에 함수를 문자열로 변환하는 경우 생략할 수 있습니다 JSON.stringify().

    예시
    const obj = {name: "John", age: function () {return 30;}, city: "New York"};
    obj.age = obj.age.toString();
    const myJSON = JSON.stringify(obj);

JSON을 사용하여 함수를 보내는 경우 함수는 범위를 잃고 수신자는 eval()을 사용하여 함수로 다시 변환해야 합니다.
