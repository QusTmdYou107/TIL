# layout

## 부모 컴포넌트와 자식 컴포넌트

- 부모 컴포넌트 : 화면에 나오지 않고, 보통 화면의 구성(배치)을 정하는 역할을 한다.
- 자식 컴포넌트 : 화면에 나온다, 하지만 배치를 정할 수는 없다.
  <br><br>

## gravity 속성

- TextView가 갖고 있는 content를 어디로 보낼지 정한다.

```Kotlin
     <TextView
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:gravity = "right"
        android:text="gravity"/>
```

<br>

- gravity 속성을 두가지 이상 적용하고 싶을때는 아래와 같이 하면 된다.

```Kotlin
     <TextView
        android:layout_width="200dp"
        android:layout_height="200dp"
        android:gravity = "right|center" // | 기호를 사용한다.
        android:text="gravity"/>
```

<br>

## match_parent / wrap_content 속성

- match_parent : 부모가 차지하고 있는 영역만큼 내 가로 크기를 맞추겠다.
- wrap_content : 내 내용물을 감쌀 수 있는 크기만큼을 내 크기로 하겠다.

```Kotlin
    <TextView
        android:layout_width="match_parent"
        android:layout_height="wrap_content"/>
```

<br><br>

# Linearlayout

- 내가 포함하고 있는 뷰들을 수평 또는 수직으로 배치하는 layout이다.

## orientation 속성

- vertical : 자식 컴포넌트를 수직으로 배열한다.
- horizontal : 자식 컴포넌트를 왼쪽에서 오른쪽으로 나열한다.

```Kotlin
    android:orientation="vertical"
```

## weight 속성

- view의 크기를 비율로 정하고 싶을 때 사옹한다.
- 0dp인 부분에 적용된다.

```Kotlin
    <TextView
        android:layout_weight="1"
        android:layout_width="0dp" // width에 적용
        android:layout_height="wrap_content"
        android:background="#A458FA"
        android:text="300"
        android:textSize="20dp" />


    <TextView
        android:layout_weight="1"
        android:layout_width="wrap_content"
        android:layout_height="0dp" // height에 적용
        android:background="#5869FA"
        android:text="100"
        android:textSize="20dp" />
```
