## JavaScript Random

---

### Math.random()

Math.random() 0(포함)과 1(제외) 사이의 난수를 반환합니다.

    예시
    // Returns a random number:
    Math.random();

Math.random()은 항상 1보다 작은 숫자를 반환합니다.

---

### JavaScript 임의의 정수

Math.random()와 함께 Math.floor()사용하여 임의의 정수를 반환할 수 있습니다.

JavaScript 정수 같은 것은 없습니다.

여기서는 소수가 없는 숫자에 대해 이야기하고 있습니다.

    예시
    // Returns a random integer from 0 to 9:
    Math.floor(Math.random() * 10);

    예시
    // Returns a random integer from 0 to 10:
    Math.floor(Math.random() * 11);

    예시
    // Returns a random integer from 0 to 99:
    Math.floor(Math.random() * 100);

    예시
    // Returns a random integer from 0 to 100:
    Math.floor(Math.random() * 101);

    예시
    // Returns a random integer from 1 to 10:
    Math.floor(Math.random() * 10) + 1;

    예시
    // Returns a random integer from 1 to 100:
    Math.floor(Math.random() * 100) + 1;

---

### 적절한 랜덤 함수

위의 예에서 볼 수 있듯이 모든 임의의 정수 목적에 사용할 적절한 임의 함수를 만드는 것이 좋습니다.

이 JavaScript 함수는 항상 최소(포함)와 최대(제외) 사이의 난수를 반환합니다.

    예시
    function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min) ) + min;
    }

이 JavaScript 함수는 항상 최소값과 최대값(둘 다 포함) 사이의 난수를 반환합니다.

    예시
    function getRndInteger(min, max) {
    return Math.floor(Math.random() * (max - min + 1) ) + min;
    }
