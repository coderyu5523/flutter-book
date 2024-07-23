# Chapter 07 로그인 앱 만들기

### 완성 화면

<img src="https://github.com/user-attachments/assets/4d9aee6b-757f-4982-8475-7fae805eaebf" width="350" height="600">


### 주요 위젯 구성

![alt text](image.png)

## 1. Route 만들기
<aside>
💡 Route는 앱 내에서 페이지 전환을 관리하는 객체를 의미한다. Route는 새로운 화면을 표시할 때 사용되며, Navigator를 통해 관리된다. 이를 통해 애니메이션, 상태 관리 및 사용자 경험을 제어할 수 있다.

<br>
이름은 규칙에 따라 경로와 유사한 구조를 사용한다. 이런 방식을 네이게이터 경로 사용법이라고 한다.
</aside>
<br>

![alt text](image-1.png)

경로의 이름을 설정한다. initialRoute 를 사용하면 기본 경로를 설정할 수 있다.

## 2. SVG 파일 넣기
<aside>
💡 SVG(Scalable Vector Graphics)는 XML 기반의 파일 포맷으로, 벡터 그래픽을 표현하는 데 사용된다. 벡터 그래픽은 픽셀 단위가 아닌 수학적 좌표와 기하학적 도형으로 이미지나 그래픽을 정의하기 때문에, 크기 조절을 하더라도 해상도 저하 없이 선명하게 유지된다.

<br>
플러터에서 SVG 파일을 사용하기 위해 flutter_svg 라이브러리 설치가 필요하다.

<br>
flutter_svg 라이브러리의 SvgPicture 위젯을 사용하여 SVG 파일을 화면에 표시할 수 있다. SvgPicture는 여러 가지 생성자를 제공하지만, 주로 asset과 network 생성자가 많이 사용된다.

1. asset: 로컬 자산에서 SVG 파일을 로드한다.
2. network: 네트워크에서 SVG 파일을 로드한다.
3. file: 파일 시스템에서 SVG 파일을 로드한다.
4. string: 문자열 형식의 SVG 데이터를 로드한다.
5. width, height: SVG 이미지의 너비와 높이를 설정한다.
6. color: SVG 이미지의 색상을 변경한다.
7. fit: BoxFit 속성을 사용하여 SVG 이미지의 크기와 위치를 조정한다.
</aside>
<br>

https://pub.dev/packages/flutter_svg

![alt text](image-2.png)

![alt text](image-3.png)

pubspec.yaml 에서 라이브러리를 등록 후 pub get 을 한다.


![alt text](image-4.png)

assets 폴더에 있는 logo.svg 파일을 출력한다.

![alt text](image-5.png)

## 3. TextFormField 위젯
<aside>
💡 TextFormField는 Flutter에서 폼(Form) 위젯을 만들기 위한 텍스트 입력 필드이다. validator 속성을 사용하여 입력값을 검증할 수 있다.

<br>
주요 속성은 다음과 같다.

1. controller: TextEditingController를 통해 텍스트 필드의 값을 제어하고 접근할 수 있다.
2. initialValue: 필드의 초기값을 설정한다.
3. decoration: InputDecoration을 사용하여 입력 필드의 외형을 꾸밀 수 있다.
4. validator: 입력값을 검증하는 함수
5. onSaved: 폼이 저장될 때 호출되는 함수
6. keyboardType: 입력할 때 사용하는 키보드 타입을 설정한다.
7. obscureText: 비밀번호 입력 필드와 같이 텍스트를 숨긴다.
</aside>
<br>



![alt text](image-8.png)


![alt text](image-9.png)

UnderlineInputBorder 를 사용하면 밑줄만 표시할 수 있다.

![alt text](image-10.png)

![alt text](image-7.png)

OutlineInputBorder 를 사용하면 전체 테두리가 표시된다.

![alt text](image-6.png)

이벤트 발생시의 디자인을 설정할 수도 있다.

## 4. Form 위젯
<aside>
💡 Form 위젯은 사용자가 입력한 데이터를 검증하고 저장하는 기능을 제공하는 위젯이다. 주로 여러 개의 입력 필드(TextFormField)를 그룹화하고, 폼 검증과 제출을 관리하는 데 사용된다.
</aside>
<br>
