## 자바 메모
---
- 패키지 사용 이유: 클래스명의 고유성을 보장하기 위해서. 다른 용도의 라이브러리를 도입할 때 이름이 충돌하는 클래스들이 있을 수 있는데 이럴 때 패키지 기능을 사용하여 클래스의 이름이 충돌하는 것을 방지할 수 있다.
---
### 생성자: 초기화를 위한 특별한 함수
- 객체가 생성되자마자 제일 먼저 실행되어야 한다.
- 생성될 때 단 한 번만 실행되어야 한다.
- new ItemList(); -> new ItemList + (); 객체를 초기화하는 생성자를 호출해라라는 뜻.
- 생성자는 반환하는 목적으로 사용하는 것이 아니다. 객체를 넘겨받기만 하는 애다. 따라서 반환타입을 쓰지 않는다.
- 오버로드(overload) 가능.
- 생성자가 하나도 없을 때는 컴파일러가 기본 생성자를 만들어줌.
- 기본 생성자 없이 오버로드 된 생성자만 있을 경우엔 기본 생성자 호출 불가. 컴파일러가 기본 생성자를 만들어 주지 않음.
```
public ItemList(int size) {
    items = new Item[size];
    current = 0;
}
// new ItemList(); <- 기본 생성자가 없는 상태에서 이렇게 기본 생성자 쓰면 호출 불가
```
- 생성자 중복 제거
```
public ItemList() {
    this(4); // this로 중복 제거
}
public ItemList(int size) {
    items = new Item[size];
    current = 0;
}
```
- 재사용이란 단순히 소스코드를 다시 사용하는 것이 아니라 jar 파일로 해서 사용하는 것이다.
- 클래스 앞에 abstract 쓰면 객체화 되는 것을 막고 뼈대로만 사용 가능함.(추상화)
- 인터페이스(Interface)는 분리되어 있는 객체를 사용할 수 있게 하는 약속이다. 
```
public interface Exam {
    int total(); // 이런 식으로 사용해야함. 왜냐 인터페이스는 데이터를 정의하는 녀석이 아니기 때문
    // int total; 소괄호가 없으면 안됨.
    // public int total(); public같은 접근지정자 사용 안됨.
    // public int total() {} 중괄호 사용 안됨.
}
```
