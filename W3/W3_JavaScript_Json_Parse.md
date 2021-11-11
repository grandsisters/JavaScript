## JSON.parse()

JSON의 일반적인 용도는 웹 서버와 데이터를 교환하는 것입니다.

웹 서버에서 데이터를 수신할 때 데이터는 항상 문자열입니다.

JSON.parse()로 데이터를 파싱하면 데이터가 JavaScript 객체가 됩니다.

---

### 예 - JSON 구문 분석

웹 서버에서 다음 텍스트를 받았다고 상상해 보십시오.

    '{"name":"John", "age":30, "city":"New York"}'

JavaScript 함수 JSON.parse()를 사용하여 텍스트를 JavaScript 객체로 변환:

    const obj = JSON.parse('{"name":"John", "age":30, "city":"New York"}');

텍스트가 JSON 형식인지 확인하십시오. 그렇지 않으면 구문 오류가 발생합니다.

페이지에서 JavaScript 개체를 사용합니다.

    예시
    <p id="demo"></p>

    <script>
    document.getElementById("demo").innerHTML = obj.name;
    </script>

---

### JSON으로 배열

JSON.parse()배열에서 파생된 JSON을 사용할 때 메서드는 JavaScript 개체 대신 JavaScript 배열을 반환합니다.

    예시
    const text = '["Ford", "BMW", "Audi", "Fiat"]';
    const myArr = JSON.parse(text);

---

### 예외

### 파싱 ​​날짜

날짜 객체는 JSON에서 허용되지 않습니다.

날짜를 포함해야 하는 경우 문자열로 작성합니다.

나중에 날짜 개체로 다시 변환할 수 있습니다.

    예시
    문자열을 날짜로 변환:

    const text = '{"name":"John", "birth":"1986-12-14", "city":"New York"}';
    const obj = JSON.parse(text);
    obj.birth = new Date(obj.birth);

    document.getElementById("demo").innerHTML = obj.name + ", " + obj.birth;

또는 reviverJSON.parse() 라는 함수 의 두 번째 매개변수를 사용할 수 있습니다 .

염색제의 파라미터 값을 리턴하기 전에, 기능 검사 각 속성이다.

    예시
    reviver 함수를 사용하여 문자열을 날짜로 변환 합니다.

    const text = '{"name":"John", "birth":"1986-12-14", "city":"New York"}';
    const obj = JSON.parse(text, function (key, value) {
      if (key == "birth") {
        return new Date(value);
      } else {
        return value;
      }
    });

    document.getElementById("demo").innerHTML = obj.name + ", " + obj.birth;

### 구문 분석 기능

함수는 JSON에서 허용되지 않습니다.

함수를 포함해야 하는 경우 문자열로 작성하십시오.

나중에 함수로 다시 변환할 수 있습니다.

    예시
    문자열을 함수로 변환:

    const text = '{"name":"John", "age":"function () {return 30;}", "city":"New York"}';
    const obj = JSON.parse(text);
    obj.age = eval("(" + obj.age + ")");

    document.getElementById("demo").innerHTML = obj.name + ", " + obj.age();

JSON에서 함수를 사용하는 것을 피해야 합니다.

함수는 범위를 잃게 eval()되며 함수를 다시 함수로 변환하는 데 사용해야 합니다.
