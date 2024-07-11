# Clip() 모디파이어

- 컴포저블을 특정한 형태로 랜더링 해주는 모디파이어이다.
- 컴포저블의 형태를 전달할 때는 `clip()` 모디파이어를 전달하고 **Shape**값을 전달해주면 된다.

---

아래 예제에서는 Box 컴포넌트를 이용하였지만 꼭 Box에만 지정할 수 있는것은 아니다.

```Kotlin
Box(Modifier.size(200.dp).clip(CircleShape).background(Color.Black))
```

<img src="../../image/Clip.png" width="" height="100"/>
