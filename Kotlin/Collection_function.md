이글을 보며 작성하였습니다. <br>
https://velog.io/@haero_kim/Kotlin-Collection-%EB%82%A0%EB%A8%B9%ED%95%98%EB%8A%94-%ED%95%A8%EC%88%98%EB%93%A4

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

- 요소들의 인덱스도 함께 사용할 수 있도록 해주는 고차함수이다.

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

<br>

# filter()

- 특정 조건에 부합하는 요소만 걸렁내서 새로운 Collection을 반환해주는 고차함수이다.

```Kotlin
fun main() {
  val list: List<Int> listOf(1, 2, 3, 4, 5, 6)

  val listToFilter {
    it % 2 == 0
  }
  println(listToFilter)
  // 출력 결과 : [2, 4, 6]
}
```

<br>

# find()

- 최초로 조건에 부합하는 요소를 반환해주는 함수이다.
- 조건에 부합하는 요소가 발견되지 않는다면 null을 반환한다.

```Kotlin
fun main() {
  val list: List<Int> = listOf(1, 2, 3, 4, 5, 6)

  val listToFind = list.find {
      it % 2 == 0
  }
  println(listToFind)
  //출력 결과 : 2
}
```

### findLast()

- 조건에 부합하는 마지막 요소를 반환해주는 함수이다.

```Kotlin
fun main() {
  val list: List<Int> = listOf(1, 2, 3, 4, 5, 6)

  val listToFindLast = a.findLast {
        it % 2 == 0
  }
  println(listToFindLast)
  //출력 결과 : 6
}
```

<br>

# any, all(), none()

- Collection의 요소들을 하나씩 검사해보며 Boolean을 반환하는 함수들이다.

### any()

- Collection의 요소들 중 조건에 만족하는게 하나라도 있다면
  true를 반환한다.

```Kotlin
fun main() {
  val list: List<Int> = listOf(1, 2, 3, 4)

  if(list.any { it % 2 == 0} ) {
    println("true 입니다.")
  }
  // 출력결과 : true 입니다.

}
```

<br>

### all()

- Collection의 요소들이 모두 조건에 만족하면 true를 반환한다.

```Kotlin
fun main() {
  val list: List<Int> = listOf(2, 4, 6, 8)

  if(list.all { it % 2 == 0} ) {
    println("true 입니다.")
  }
  // 출력결과 : true 입니다.

}
```

<br>

### none()

- Collection의 요소들이 모두 조건에 만족하지 않으면 true를 반환한다.

```Kotlin
fun main() {
  val list: List<Int> = listOf(1, 2, 3, 4)

  if(list.none { it >= 10} ) {
    println("true 입니다.")
  }
  // 출력결과 : true 입니다.
}
```

<br><br>

# partition()

- 배열 요소의 조건을 걸어서 pair 형태로 분리되어 <br>
  조건에 부합하 요소는 `first`, 부합하지 않는 요소는 `second`로 가게 된다.

  ```Kotlin
  fun main() {

  val list: List<Int> = listOf(1, 2, 3, 4, 5, 6)

    val listToPartition = list.partition{ it % 2 == 0 }

    println(listToPartition.first)
    println(listToPartition.second)

  }
  출력 결과 : [2, 4, 6]
             [1, 3, 5]
  ```

  <br>

# flatMap()

- **Collection**을 구성하는 요소들 각각마다 원하는 형태로 <br> 새로운 **Collection**을 만들고, <br> 이 **Collection**들을 하나의 **Collection**으로 **Flatten**하여 반환한다.

```Kotlin
fun main() {
    val list: List<Int> = listOf(1, 2, 3)

    val listToFlatMap = a.flatMap {
        listOf(it * 3, it * 4)
    }

    println(flatA)
    // 출력 결과 : [3, 4, 6, 8, 9, 12]
}
```

각 원소마다 `listOf(it * 3, it * 4)` 형태로 새로운 **Collection**을 만든뒤, <br> 그 **Collection**들을 하나로 **Flatten** 하기 때문에 저런 결과가 나오게 된다.
