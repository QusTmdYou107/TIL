# Null safety

- 코틀린의 특징으로, Null에 대해서 안전하다.

### Null vs 0

휴지를 예로 들어 설명해 보겠다.<br>

- 0 : 휴지를 다 쓰고 휴지심만 남은 상태를 말한다.
- Null : 휴지심도 없는 상태를 말한다, 존재 하지 않는 상태, 모르는 상태 라고도 한다.

### Null이 안전하지 않은 이유

- 0 + 10 = 10 <br>
  Null + 10 = ? -> 에러 발생
- button.setOnClickListener<br>
  null.setOnClickListener → 에러 발생<br>
  → NullPointExceptionError가 발생한다.

### 엘비스 연산자

엘비스 연산자가 없던 기존의 코드를 살펴보겠다.

```Kotiln
 if(number != null) {
	 number += 10
 }
 if(button != null) {
	 button.setOnClickListener
 }
```

- 항상 Null인지 아닌지 확인을 해 주어야 하기 때문에 번거롭다.
- 그리고 체크를 하지 못하면 오류가 발생한다.<br><br>
  하지만 코틀린에서는 엘비스 연산자를 사용하여 코드를 줄일 수 있다.<br><br>
- ?

```Kotlin
button?.setOnClickListener
// button이 Null이 아니라면 ? 이하 구문을 실행한다.
```

<br>

- !!

```Kotlin
button?.setOnClickListener
// button이 Null이 아님을 개발자가 보장한다(= !!)
```
