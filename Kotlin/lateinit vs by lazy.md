# lateinit, lazy

### lateinit

```Kotlin
lateinit var ex: String
```

- `var`키워드로 선언한 변수에만 사용할 수 있다.
- Int, Long, Short, Double, Float, Boolean, Byte 타입에는 사용할 수 없다.
  <br><br>

### 만약 lateinit을 사용하여 늦은 초기화도 하지 않았다면?

```Kotlin
Exception in thread "main" kotlin.UninitializedPropertyAccessException: lateinit property text has not been initialized
```

- 컴파일 단계에서 오류가 발생하여서 잠재적 오류를 방지해준다.

---

### by lazy

```Kotlin
val data : Int by lazy {
    println("example")
    20
}
```

- `by lazy { }` 형식으로 선언한다.
- 변수가 최초로 이용되는 순간 중괄호 안의 코드가 자동으로 실행된다.
- 마지막 줄의 실행결과가 변수의 초기값이 된다.

---

<br>

### lateinit과 by lazy의 차이점

**lateinit**

- `var`사용, 값을 변경할 수 있다. <br>
- `var`을 사용하므로 초기화 이후 값을 변경할 일이 있을 때 사용한다.

**by lazy**

- `val` 사용, 값을 변경하지 못한다.
- `val`을 사용하므로 초기화 이후 값을 변경하지 않을 때(읽기 전용으로 이용할 때) 사용한다.
