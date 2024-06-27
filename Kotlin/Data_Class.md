# Data Class

- `data` 키워드로 선언한다.
- 자주 사용하는 데이터를 객체로 묶어주는 클래스이다.
- 다양한 메소드들도 자동으로 생성해준다.
  <br>

## Data Class 생성 시 같이 만들어지는 녀석들

- `hashcode()`
- `copy()`
- `equals()`
- `toString()`
- `componentsN()`
  <br><br>

## 다양한 특징들

- 기본 생성자에 1개 이상의 파라미터가 있어야 한다.
- 기본 생성자의 파라미터가 `val` 또는 `var`로 선언해야 한다.
- 다른 클래스를 상속 받을 수 없다. (슈퍼 클래스를 가질 수 없다.) <br>
  - 하지만 `sealed` 클래스는 상속받을 수 있다.<br>
  - 인터페이스는 구현할 수 있다.(버전 1.1 이후 기준)
- `abstract`, `open`, `sealed`, `inner`등의 키워드를 붙일 수 있다.
- 자동으로 생성한 메소드를 오버라이딩 할 경우, 오버라이드 된 메소드를 사용한다.<br><br>

## Data Class 사용법

아래처럼 데이터 클래스를 만들고,

```Kotiln
data class Example (
    val name: String,
    val age: Int
)
```

<br>

아래처럼 데이터 클래스 객체를 생성하여 사용하면 된다.

```Kotiln
fun main() {
    val human = People("QusTmdYou107", 18)
    val human2 = People("BSG", 18)
}
```

<br>

## 다양한 기능들

### toString() 메소드

```Kotlin
println(human)

// 출력 결과 : human(name=QmdTmdYou107, age=18)
```

위처럼 생성한 객체를 출력할 시 가지고 있는 프로퍼티의 값들이 알아서 출력된다. <br>
-> `toString()`이 구현 되어있기 때문이다.

- 디버깅 시 로그캣을 통해 매우 편리하게 사용할 수 있다.
- 이 메소드를 자동으로 생성해주는 것이 가장 좋은 장점이다. <br><br>

---

### copy() 메소드

- 특정 필드값만 바꿔서 복사하기 간편하다.
  <br><br>

---

### hashCode() 메소드

프로퍼티 값이 완전히 같은 두 Data Class 객체를 만들고,<br> `hashCode()`를 출력하면 두 객체의 `hashCode()`가 같은 값을 출력한다. <br> -> 일반 클래스라면 다른 값을 갖는다. <br>

---

### equals() 메소드

- '==' 연산자로 두 객체가 동일한 값을 담고 있는지 쉽게 검사할 수 있다.
- '===' 연산자로 두 객체가 있을 때 두 객체가 메모리 상 같은 객체인지 <br>다른 객체인지 확인 할 수 있다.
  <br><br>

---

### componentN() 메소드

- Data Classs는 기본적으로 `componentN()`메소드가 생성이 되어서, <br>각 프로퍼티에 번호가 붙어 구조 분해가 가능한 형태가 된다.
