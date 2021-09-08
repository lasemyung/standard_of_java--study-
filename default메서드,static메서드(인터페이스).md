# default 메서드, static 메서드 (인터페이스)

- 인터페이스에 디폴트 메서드, static 추가 가능 (JDK 1.8부터)

- 인터페이스에 새로운 메서드(추상 메서드)를 추가하기 어려움

  ​				해결책 : 디폴트 메서드(default mehtod)

- 디폴트 메서드는 인스턴스 메서드(인터페이스 원칙 위반)

  ```java
  interface MyInterface{
  	void mehtod();
  	void newMethod(); // 추상메서드
  }
  
  interface MyInterface{
  	void mehtod();
  	default void newMethod() {} // 몸통이 생겨서 충돌 문제가 생김
  }
  ```

- 디폴트 메서드가 기존의 메서드와 충돌 할 때의 해결책

  1. 여러 인터페이스와 디폴트 메서드 간의 충돌

     : 인터페이스를 구현한 클래스에서 디폴트 메서드를 오버라이딩 해야 한다

  2. 디폴트 메서드와 조상 클래스의 메서드 간의 충돌

     : 조상 클래스의 메서드가 상속되고, 디폴트 메서드는 무시 된다

