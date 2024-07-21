# let

- `it`키워드를 이용하여 객체의 상태를 변경할 수 있다.
- 어떤 타입도 반환타입을 가질 수 있다.
- non-null인 객체에만 사용할 수 있다.

```Kotlin
data class User(var age: Int, var id: String, var email: String)

fun main() {
    val user = User(0, "", "")
	val result = user.let {
    	it.age = 18
        it.id = "QusTmdYou107"
        it.email = "example@gmail.com"
        it // 반환값
	}

    println(result)
    // 출력결과 :
    // ​User(age=18, id=QusTmdYou107, email=example@gmail.com)
}
```
