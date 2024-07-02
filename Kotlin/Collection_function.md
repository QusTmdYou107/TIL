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
