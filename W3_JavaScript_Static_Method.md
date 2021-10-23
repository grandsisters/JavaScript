## JavaScript Static Methods

정적 클래스 메서드는 클래스 자체에 정의됩니다.

static개체에서 메서드를 호출할 수 없으며 개체 클래스에서만 호출할 수 있습니다 .

    예시
    class Car {
      constructor(name) {
        this.name = name;
      }
      static hello() {
        return "Hello!!";
      }
    }

    let myCar = new Car("Ford");

    // You can calll 'hello()' on the Car Class:
    document.getElementById("demo").innerHTML = Car.hello();

    // But NOT on a Car Object:
    // document.getElementById("demo").innerHTML = myCar.hello();
    // this will raise an error.

메소드 내에서 my C ar 객체 를 사용하려면 static이를 매개변수로 보낼 수 있습니다.

    예시
    class Car {
      constructor(name) {
        this.name = name;
      }
      static hello(x) {
        return "Hello " + x.name;
      }
    }
    let myCar = new Car("Ford");
    document.getElementById("demo").innerHTML = Car.hello(myCar);
