## Web Storage API

Web Storage API는 브라우저에서 데이터를 저장하고 검색하기 위한 간단한 구문입니다. 사용하기 매우 쉽습니다.

    예시
    localStorage.setItem("name", "John Doe");
    localStorage.getItem("name");

---

### localStorage 객체

localStorage 개체는 특정 웹 사이트의 로컬 저장소에 대한 액세스를 제공합니다.

이를 통해 해당 도메인의 데이터 항목을 저장, 읽기, 추가, 수정 및 삭제할 수 있습니다.

데이터는 만료일 없이 저장되며 브라우저를 닫아도 삭제되지 않습니다.

데이터는 일, 주, 연도 동안 사용할 수 있습니다.

---

### setItem() 메서드

localStorage.setItem() 메서드는 저장소에 데이터 항목을 저장합니다.

이름과 값을 매개변수로 사용합니다.

    예시
    localStorage.setItem("name", "John Doe");

---

### getItem() 메서드

localStorage.getItem() 메서드는 저장소에서 데이터 항목을 검색합니다.

매개변수로 이름을 사용합니다.

    예시
    localStorage.getItem("name");

---

### sessionStorage 객체

sessionStorage 객체는 localStorage 객체와 동일합니다.

차이점은 sessionStorage 객체가 하나의 세션에 대한 데이터를 저장한다는 것입니다.

브라우저를 닫으면 데이터가 삭제됩니다.

    예시
    sessionStorage.getItem("name");

---

### setItem() 메서드

sessionStorage.setItem() 메서드는 저장소에 데이터 항목을 저장합니다.

이름과 값을 매개변수로 사용합니다.

    예시
    sessionStorage.setItem("name", "John Doe");

---

### getItem() 메서드

sessionStorage.getItem() 메서드는 저장소에서 데이터 항목을 검색합니다.

매개변수로 이름을 사용합니다.

    예시
    sessionStorage.getItem("name");

---

### 저장소 개체 속성 및 메서드

| Property/Method         | Description                                                                   |
| ----------------------- | ----------------------------------------------------------------------------- |
| key(n)                  | Returns the name of the nth key in the storage                                |
| length                  | Returns the number of data items stored in the Storage object                 |
| getItem(keyname)        | Returns the value of the specified key name                                   |
| setItem(keyname, value) | Adds that key to the storage, or update that key's value if it already exists |
| removeItem(keyname)     | Removes that key from the storage                                             |
| clear()                 | Empty all key out of the storage                                              |

---

### Web Storage API 관련 페이지

| Property              | Description                                                                              |
| --------------------- | ---------------------------------------------------------------------------------------- |
| window.localStorage   | Allows to save key/value pairs in a web browser. Stores the data with no expiration date |
| window.sessionStorage | Allows to save key/value pairs in a web browser. Stores the data for one session         |
