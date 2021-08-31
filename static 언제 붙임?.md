# Static을 붙어야 하는 상황

- 속성 ( 멤버 변수 ) 중에서 공통 속성에 static을 붙인다 

  ```java
  class Card {
  	String kind;  // 카드의 모양과 숫자는 다르기 때문에 인스턴스 변수 
  	int number;
  	
  	static int width = 100; // 카드의 폭과 넓이는 같기 때문에 스태틱 변수
  	static int height = 250;
  }
  ```



- 인스턴스 멤버를 사용하지 않는 메서드에 static을 붙인다

  ```java
  class MyMath2 {
  	long a,b;
  	
  	long add() { return a + b; } // a,b는 인스턴스 변수
      static long add ( long a, long b ) { return a + b; } // a,b는 지역변수
  }
  ```

  

### 포인트는 인스턴스 멤버(iv,im)를 사용하냐 안하냐가 차이

