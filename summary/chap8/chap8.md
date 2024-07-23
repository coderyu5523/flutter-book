# Chapter 08 쇼핑카드 앱 만들기

### 완성 화면

<img src="https://github.com/user-attachments/assets/c3f177db-41d9-4d3a-9eda-849077b2128c" width="200" height="400">
<img src="https://github.com/user-attachments/assets/dbefc00b-2101-416b-9db2-f039f9d51bf7" width="200" height="400">
<img src="https://github.com/user-attachments/assets/96eb7ec3-c21e-41e9-a265-c2ca601f5813" width="200" height="400">

### 주요 위젯 구성

![alt text](image.png)



## 1. StatefulWidget

### 1.1 StatefulWidget이란?
<aside>
💡 플러터에서 StatefulWidget은 상태(state)를 가지는 위젯이다. 이는 사용자가 상호작용할 때나 시간이 지남에 따라 변할 수 있는 데이터를 포함하는 위젯을 만들 때 사용된다. StatefulWidget은 StatelessWidget과 다르게 상태가 변할 수 있는 동적인 위젯이다.

<br>

StatefulWidget은 두 개의 주요 클래스, 즉 StatefulWidget 자체와 그에 대한 상태(State) 클래스로 구성된다.

1. StatefulWidget 클래스: StatefulWidget은 불변(immutable)이며, 상태가 변할 때마다 새로운 상태 객체를 생성한다.
2. State 클래스: State 클래스는 위젯의 상태를 관리하고, 상태가 변경될 때마다 위젯을 다시 빌드한다.
</aside>
<br>

### 1.2 StatefulWidget vs StatelessWidget 
<aside>
💡 StatelessWidget은 상태가 없는, 불변의 위젯이다. 한 번 빌드되면 내부 데이터가 변경되지 않으며, UI는 동일하게 유지된다. 따라서 텍스트, 아이콘, 이미지 등 상태 변화가 필요 없는 UI에 사용한다.
</aside>
<br>

![alt text](Screenshot_2.png)

stateless 위젯으 사용한다면 화면은 그릴 수 있으나 버튼을 눌렀을 때 페이지가 변하지 않는다.


<aside>
💡 StatefulWidget은 상태를 가지며, 상태가 변경될 때마다 위젯이 다시 빌드되어 UI가 업데이트된다. 따라서 사용자 입력에 따라 UI가 변경되는 경우 텍스트 입력, 체크박스, 슬라이더 등 동적인 UI에 사용한다.
</aside>

![alt text](Screenshot_3.png)

StatefulWidget의 createState 메서드는 State 객체를 생성하고 반환하면서 상태를 관리한다. 버튼의 기본 값을 0으로 지정한다.

<br>

![alt text](image-4-1.png)

화면에 표시될 숫자 리스트를 만든다.

![alt text](image-2.png)

버튼에 id 값을 지정한다. 선택된 버튼의 id 값에 따라 상태를 변경하도록 한다.

하지만 변수의 값을 직접적으로 변경하게 되면 앱이 다시 build 되지 않는다. 플러터에서 그림이 다시 그린다는 의미는 build() 함수가 다시 실행된다는 의미이다. 따라서 build() 함수를 호출하기 위해 변수 변경 시 특정 함수를 호출해야 한다.

### 1.3 setState 함수

<aside>
💡 setState는 State 객체의 상태를 변경하고, 변경된 상태에 따라 UI를 다시 빌드하도록 하는 메서드이다. setState 메서드는 주로 사용자 상호작용이나 비동기 작업의 결과에 따라 UI를 업데이트할 때 사용한다.
</aside>
<br>

![alt text](image-4-2.png)

버튼을 누르면 setState가 호출되면서 id 값이 바뀌고, 버튼의 색도 변경된다.

![alt text](image-5.png)

그리고 상단에 표시될 숫자의 인덱스도 변경한다.

![alt text](Screenshot_4.png)

![alt text](Screenshot_5.png)