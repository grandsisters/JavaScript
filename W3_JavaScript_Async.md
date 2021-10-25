## JavaScript Async

"async 및 await를 사용하면 promise 더 쉽게 작성할 수 있습니다."

async 는 함수가 Promise를 반환하도록 합니다.

await 는 함수가 Promise를 기다리게 합니다.

---

### 비동기 구문

async함수 앞 의 키워드 는 함수가 약속을 반환하도록 합니다.

    예시
    async function myFunction() {
    return "Hello";
    }

    아래와 같다:

    async function myFunction() {
    return Promise.resolve("Hello");
    }

Promise를 사용하는 방법은 다음과 같습니다.

    myFunction().then(
    function(value) { /_ code if successful _/ },
    function(error) { /_ code if some error _/ }
    );

<br />

    예시
    async function myFunction() {
    return "Hello";
    }
    myFunction().then(
    function(value) {myDisplayer(value);},
    function(error) {myDisplayer(error);}
    );

또는 정상적인 값을 기대하기 때문에 더 간단합니다(오류가 아닌 정상적인 응답).

    예시
    async function myFunction() {
    return "Hello";
    }
    myFunction().then(
    function(value) {myDisplayer(value);}
    );

---

### 구문 대기

await함수 앞 의 키워드 는 함수가 약속을 기다리게 합니다.

    let value = await promise;

await키워드는 단지 내에서 사용할 수있는 async기능.

---

### 예시

    기본 구문
    async function myDisplay() {
    let myPromise = new Promise(function(resolve, reject) {
    resolve("I love You !!");
    });
    document.getElementById("demo").innerHTML = await myPromise;
    }

    myDisplay();

두 개의 인수(resolve 및 reject)는 JavaScript에 의해 미리 정의됩니다.

우리는 그것들을 생성하지 않을 것이지만, 실행기 기능이 준비되면 그것들 중 하나를 호출합니다.

매우 자주 거부 기능이 필요하지 않습니다.

### 거부가 없는 예

    async function myDisplay() {
    let myPromise = new Promise(function(resolve) {
    resolve("I love You !!");
    });
    document.getElementById("demo").innerHTML = await myPromise;
    }

    myDisplay();

### 시간 초과를 기다리는 중

    async function myDisplay() {
    let myPromise = new Promise(function(resolve) {
    setTimeout(function() {resolve("I love You !!");}, 3000);
    });
    document.getElementById("demo").innerHTML = await myPromise;
    }

    myDisplay();

### 파일을 기다리는 중

    async function getFile() {
    let myPromise = new Promise(function(resolve) {
    let req = new XMLHttpRequest();
    req.open('GET', "mycar.html");
    req.onload = function() {
    if (req.status == 200) {
    resolve(req.response);
    } else {
    resolve("File not Found");
    }
    };
    req.send();
    });
    document.getElementById("demo").innerHTML = await myPromise;
    }

    getFile();
