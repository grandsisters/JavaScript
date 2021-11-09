## JavaScript Fetch API

Fetch API 인터페이스를 사용하면 웹 브라우저가 웹 서버에 HTTP 요청을 할 수 있습니다.

더 이상 XMLHttpRequest가 필요하지 않습니다.

---

### Fetch API 예제

아래 예에서는 파일을 가져와서 내용을 표시합니다.

### 예시

    fetch(file)
    .then(x => x.text())
    .then(y => myDisplay(y));

Fetch는 비동기 및 대기를 기반으로 하기 때문에 위의 예는 다음과 같이 이해하기 더 쉬울 수 있습니다.

### 예시

    async function getText(file) {
      let x = await fetch(file);
      let y = await x.text();
      myDisplay(y);
    }

또는 더 나은 방법: x 및 y 대신 이해할 수 있는 이름을 사용하십시오.

### 예시

    async function getText(file) {
      let myObject = await fetch(file);
      let myText = await myObject.text();
      myDisplay(myText);
    }
