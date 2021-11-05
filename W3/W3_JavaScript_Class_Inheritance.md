## JavaScript Class Inheritance

---

### 클래스 상속

클래스 상속을 생성하려면 extends 키워드를 사용하십시오 .

클래스 상속으로 생성된 클래스는 다른 클래스의 모든 메서드를 상속합니다.

    예시
    "Car" 클래스에서 메서드를 상속할 "Model"이라는 클래스를 만듭니다.

    class Car {
      constructor(brand) {
        this.carname = brand;
      }
      present() {
        return 'I have a ' + this.carname;
      }
    }

    class Model extends Car {
      constructor(brand, mod) {
        super(brand);
        this.model = mod;
      }
      show() {
        return this.present() + ', it is a ' + this.model;
      }
    }

    let myCar = new Model("Ford", "Mustang");
    document.getElementById("demo").innerHTML = myCar.show();

super()메서드는 부모 클래스를 의미합니다.

생성자 메서드로 super()메서드를 호출하는 것으로, 우리는 부모의 생성자 메서드를 호출하고 부모의 메서드와 속성에 대한 액세스를 얻을 수 있습니다.

상속은 코드 재사용성에 유용합니다. 즉, 새 클래스를 만들 때 기존 클래스의 속성과 메서드를 재사용합니다.

---

### getter와 setter

클래스를 사용하면 getter와 setter도 사용할 수 있습니다.

특히 값을 반환하기 전이나 값을 설정하기 전에 값으로 특별한 작업을 수행하려는 경우 속성에 대해 getter 및 setter를 사용하는 것이 현명할 수 있습니다.

클래스에 getter 및 setter를 추가하려면 get및 set키워드를 사용하십시오 .

    예시
    "carname" 속성에 대한 getter 및 setter를 만듭니다.

    class Car {
      constructor(brand) {
        this.carname = brand;
      }
      get cnam() {
        return this.carname;
      }
      set cnam(x) {
        this.carname = x;
      }
    }

    let myCar = new Car("Ford");

    document.getElementById("demo").innerHTML = myCar.cnam;

참고: getter가 메서드인 경우에도 속성 값을 가져올 때 괄호를 사용하지 않습니다.

getter/setter 메서드의 이름은 속성의 이름과 같을 수 없습니다. 위 예시에선 carname의 경우 입니다.

많은 프로그래머 \_ 가 실제 속성과 getter/setter를 구분하기 위해 속성 이름 앞에 밑줄 문자 를 사용합니다 .

    예시
    밑줄 문자를 사용하여 getter/setter를 실제 속성과 구분할 수 있습니다.

    class Car {
    constructor(brand) {
    this.\_carname = brand;
    }
    get carname() {
    return this.\_carname;
    }
    set carname(x) {
    this.\_carname = x;
    }
    }

    let myCar = new Car("Ford");

    document.getElementById("demo").innerHTML = myCar.carname;

setter 를 사용하려면 속성 값을 설정할 때와 동일한 구문을 괄호 없이 사용하세요.

    예시
    setter를 사용하여 carname을 "Volvo"로 변경합니다.

    class Car {
    constructor(brand) {
    this.\_carname = brand;
    }
    get carname() {
    return this.\_carname;
    }
    set carname(x) {
    this.\_carname = x;
    }
    }

    let myCar = new Car("Ford");
    myCar.carname = "Volvo";
    document.getElementById("demo").innerHTML = myCar.carname;

---

### Hoisting

함수 및 기타 JavaScript 선언과 달리 클래스 선언은 호이스트되지 않습니다.

즉, 클래스를 사용하려면 먼저 선언해야 합니다.

    예시
    //You cannot use the class yet.
    //myCar = new Car("Ford")
    //This would raise an error.

    class Car {
    constructor(brand) {
    this.carname = brand;
    }
    }

    //Now you can use the class:
    let myCar = new Car("Ford")

참고: 함수와 같은 다른 선언의 경우 JavaScript 선언의 기본 동작이 호이스팅(선언을 맨 위로 이동)하기 때문에 선언되기 전에 사용하려고 하면 오류가 발생하지 않습니다.
