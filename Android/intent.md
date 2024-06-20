# intent

- 앱 컴포넌트가 무엇을 할 것인지 담는 메시지 객체이다.
- 다른 Activity, Service, BroadCast Receiver, Content Provider <br>등을 실행하는 것이 메시지의 목적이다.
- 그들 사이에 데이터를 주고 받기 위한 용도로 쓰인다.

---

- 액티비티를 띄우기 위해 사용되는 메소드는 <br> `startActivity()`와 `startActivityForResult` 가 있다.
- `String`, `Int`, `Array`, `List` 같은 형태도 전달 가능하다.
- `putExtra` : 데이터를 보내는 메서드
- `getExtra` : 전 페이지에서 보낸 값을 받아올 때 사용하는 메서드
