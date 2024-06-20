# Fragment

- 독립적일 수 없다.
  - Activity혹은 부모 Fragment에 종속적이다.
- 자체적으로 생명주기(LifeCycle)을 가진다.
- 재사용이 가능하다.
  - 여러 Activity에서 생성 및 사용할 수 있다.
- Activity 내에서 실행 중 추가, 삭제, 교체 등이 가능하다.<br><br>

---

# FragmentManager클래스

- Activity혹은 Fragmnet에서 휘하의 Fragment를 관리하는 클래스이다.
- 이 클래스를 통해 Activity - Fragment 혹은<br>
  자식 Fragment간의 상호 작용이 가능하다.<br><br>

---

# FragmentTransation클래스

### 역할

- 실질적으로 Fragment를 추가, 삭제, 교체 등 여러 작업을 진행한다.
- Fragment의 백스택 관리, Fragment 전환시 애니메이션 설정을 담당한다.
  - 백스택 : 사용자가 뒤로가기 버튼을 눌렀을 때<br> 이전 Fragment화면이 나오게 설정하는걸 말한다.

### 사용하는 메소드들

- **add()** : 새로운 Fragment를 컨테이너에 추가한다.
- **replace()** : 기존 컨테이너에 있는 Fragment를 제거한다.
- **remove()** : 컨테이너에 있는 Fragment를 제거한다.
- **show()** : 컨테이너에 있는 Fragment를 보여준다.
- **hide()** : 컨테이너에 있는 Fragment를 숨긴다.
- **commit()** : 작업을 수행한다.
- **commitNow()** : 백스택이 없을 경우만 사용한다. / 작업을 즉시 수행한다.

### Fragment LifeCycle

- **Fragment는 FragmentView의 생명주기도 가지고 있다.**

---

- onAttach()
  - Fragment가 Activity에 포함되는 순간 호출된다. <br> -> Activity에 종속 되는 과정이다.
- onCreate()
  - fragment가 생성 되었을 때 호출된다.<br> Fragment View는 포함되지 않은 상태이다.
- onCreateView()
  - Fragment의 UI 구성을 위해 호출된다.<br> Fragment View의 생명주기가 생성된다.
- onViewCreated()
  - onCreateView()를 통해 View 객체를 전달 받는다.<br> -> 이 단계에서 View의 초기 세팅을 하면 안정성을 보장받을 수 있다!
- onResume()
  - Fragment가 화면에서 사라지고, Fragment의 생명주기를 없앤다.
- onDestroyView()
  - Fragment가 화면에서 사라지고, Fragment View의 생명주기를 없앤다.
  - 이 시점에서 Fragment View에 대한 모든 참조를 제거해야<br> 가비지 컬렉터가 Fragment View를 수거해간다.
  - 백스택 처리를 했다면 onDestroy()로 가지 않고 이 단계에서 머무른다.
- onDetach()
  - Fragment가 Activity에서 완전히 제거될 때 호출된다.

### launchMode

- **standard** (기본 설정)
  - 기본적으로 설정되어 있는 모드
  - 액티비티가 호출될 때 마다 테스크에 저장 <br>
    → 여러개가 중첩되서 저장될 수 있음
- **singleTop**
  - 액티비티가 이미 Task의 가장 위에 있을 경우 onNewIntent() 메서드를 통해 <br>
    액티비티 인스턴스를 재활용함.
    <br>→ 따라서 가장 위쪽의 액티비티가 다시 생성되지 않음
  - 연속되어 중첩되지는 않지만 테스크에 중복되어 저장 될 수는 있음.
- **singleTask**
  - singleTask로 설정된 액티비티가 실행되는 시점에 새로운 테스크를 생성함
  - 이 액티비티가 호출하는 액티비티들은 새로 생성된 테스크에 쌓임
  - 다시 호출될 경우 onNewIntent() 메서드를 통해 해당 액티비티를 재활용함
- **singleInstance**
  - singleTask와 동일하게 새로운 테스크를 생성함
  - singleTask와는 다르게 해당 테스크에서 다른 액티비티를 허용하지 않음
