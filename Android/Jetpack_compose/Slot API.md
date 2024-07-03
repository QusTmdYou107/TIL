# Slot API

- 어떠한 컴포저블 함수가 다른 컴포저블 함수나 컴포넌트를 포함하는 것을 말한다.
- 하나의 slot API는 하나 이상의 요소가 비어있는 UI템플릿 이라고 생각하면 된다.

---

### Slot API 선언하기

```Kotlin
// Slot API 선언
@Composable
fun SlotDemo(middleContent: @Composable () -> Unit) {
    Column {
	Text("Top Text")
        middleContent()
        Text("Bottom Text")
    }
}

@Composable
fun ButtonDemo() {
    Button(onClick = {}) {
        Text("Click Me")
    }
}
```

- `SlotDemo` 컴포저블을 호출할 때는 하나의 컴포저블 함수를 전달해야 한다.
- 파라미터 `middleContent`라는 라벨로 할당되고, <br>함수 본체 안에서 이를 참조해 슬롯을 참조할 수 있다.
- 마지막으로 `middleContent` 컴포넌트를 `Column` 선언 안에 추가한다.
  <br><br>

### 선언한 Slot API 컴포저블 호출하기

```Kotlin
SlotDemo {
    ButtonDemo()
}
```
