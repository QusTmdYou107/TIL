# Context

- 어플리케이션에 대해서 현재 상태를 나타내는 역할을 한다.<br>
  → 앱이 흘러가는 맥락
- 애플리케이션의 현재 상태를 갖고 있다.
- 시스템이 관리하고 있는 액티비티, 어플리케이션의 정보를 얻기 위해 사용한다.
- 안드로이드 시스템 서비스에서 제공하는 API에 접근하기 위해 사용한다,
- `Activity`, `Application`클래스는 `Context` 클래스를 상속 받은 클래스이다.

> Context의 잘못된 사용은 메모리 릭 문제로 이어질 수 있기 때문에<br>
> 정말 주의해야 한다.

## Application Context

- Activity에서 applicationContext라는 프로퍼티를 통해 얻을 수 있는<br>
  싱글톤 인스턴스이다.
- 어플리케이션 생명주기와 묶여있어, 현재 Context가 종료되고 나서도<br>
  Context가 필요한 작업이나, 액티비티 범위를 벗어난 곳에 Context가<br>
  필요한 작업에 적합하다.
  > 오랫동안 지속되거나 앱 전역에서 사용될 것의 경우에는<br>
  > Application Context를 사용하면 된다.

## Activity Context

- 액티비티 안에서만 사용 가능하다.
- 특정 Activity의 라이프 사이클에 종속되어 있다.
- Activity 스코프 내에서 사용될 때 넘겨주거나,<br>
  Activity와 라이프사이클이 같은 객체를 생성할 때 넘겨준다.<br>
  → 즉 Activity가 소멸되면 해당 Context도 같이 소멸된다.
