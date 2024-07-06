# sort()

- Collection을 정렬해주는 역할을 한다.

---

<br>

### 오름차순 정렬

- `sort()`를 사용한다.

```Kotlin
val list = mutableListOf(3, 2, 1)
list.sort()
println(list) // [1, 2, 3]
```

---

  <br>

### 내림차순 정렬

- `sortedByDescending()`을 사용한다.
- 정렬된 새로운 객체를 반환한다.

```Kotlin
val list = mutableListOf(1, 2, 3)
val sortedList = list.sortedByDescending()
println(sortedList) // [3, 2, 1]
```

---

<br>

### 특정 프로퍼티를 기준으로 정렬

- `sortBy()`를 이용하며, 오름차순으로 정렬된다.
- `sortBy()`는 고차함수이다.

```Kotlin
val list = mutableListOf(10 to "a", 2 to "b", 30 to "c")
list.sortBy { it.first } // 객체의 first 값을 기준으로 정렬한다.
pritnln(list) // [(2, b), (10, a), (30, c)]
```

<br>

# map()

- Collection을 구성하는 각 요소들을 특정 표현식에 의해 변형시킨 뒤 새로운 Collection을 반환한다.
- 고차함수이다.

```Kotlin
val list = List<Int> = listOf(10, 20, 30)
val listToMap = list.map { it + 10 }
// list의 각 요소들에 10을 더한 값을 가진 새로운 Collection을 반환하게 된다.
println(listToMap) // [20, 30, 40]
```

<br>

# forEach

- collection을 하나씩 순회할 수 있게 해주는 함수이다.

```Kotlin
fun main() {
  val list: List<String> = listOf("item1", "item2", "item3")

  list.forEach {
    println(it)
  }
  // 출력 결과 :
  // item1
  // item2
  // item3
}
```

### forEachIndexed

- 요소들의 인덱스도 함께 사용할 수 있도록 해주는 함수이며, 고차함수이다.

```Kotlin
fun main() {
  val list: List<String> = listOf("item1", "item2", "item3")

  list.forEachIndexed { index, item ->
    println("${index} : ${item}")
  }
  // 출력 결과 :
  // 0 : item1
  // 1 : item2
  // 2 : item3
}
```
