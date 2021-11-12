## JSON Server

JSON의 일반적인 용도는 웹 서버와 데이터를 교환하는 것입니다.

웹 서버에서 데이터를 수신할 때 데이터는 항상 문자열입니다.

로 데이터를 파싱하면 데이터 JSON.parse()가 JavaScript 객체가 됩니다.

---

### 데이터 전송

JavaScript 객체에 데이터가 저장된 경우 객체를 JSON으로 변환하여 서버로 보낼 수 있습니다.

    예시
    const myObj = {name: "John", age: 31, city: "New York"};
    const myJSON = JSON.stringify(myObj);
    window.location = "demo_json.php?x=" + myJSON;

---

### 데이터 수신

JSON 형식의 데이터를 받으면 JavaScript 객체로 쉽게 변환할 수 있습니다.

    예시
    const myJSON = '{"name":"John", "age":31, "city":"New York"}';
    const myObj = JSON.parse(myJSON);
    document.getElementById("demo").innerHTML = myObj.name;

---

### 서버의 JSON

AJAX 요청을 사용하여 서버에서 JSON을 요청할 수 있습니다.

서버의 응답이 JSON 형식으로 작성되어 있으면 문자열을 JavaScript 개체로 구문 분석할 수 있습니다.

    예시
    XMLHttpRequest를 사용하여 서버에서 데이터를 가져옵니다.

    const xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      const myObj = JSON.parse(this.responseText);
      document.getElementById("demo").innerHTML = myObj.name;
    };
    xmlhttp.open("GET", "json_demo.txt");
    xmlhttp.send();

---

### JSON으로 배열

JSON.parse()배열에서 파생된 on JSON을 사용할 때 메서드는 JavaScript 개체 대신 JavaScript 배열을 반환합니다.

    예시
    서버에서 배열로 반환된 JSON:

    const xmlhttp = new XMLHttpRequest();
    xmlhttp.onload = function() {
      const myArr = JSON.parse(this.responseText);
      document.getElementById("demo").innerHTML = myArr[0];
      }
    }
    xmlhttp.open("GET", "json_demo_array.txt", true);
    xmlhttp.send();
