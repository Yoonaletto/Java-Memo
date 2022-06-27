## 자바 메모
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
