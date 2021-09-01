# 참조변수 super / super() - 조상의 생성자

- 객체 자신을 가리키는 참조변수 , 인스턴스 메서드 (생성자) 내에서만 존재

- 조상의 멤버를 자신의 멤버와 구별할 때 사용

  ```java
  class SuperTest {
  	public static void main(String args[]) {
  		Child c = new Child();
  		c.method();
  	}
  }
  
  class Parent {
  	int x=10;  //부모 클래스의 x는 10  / super. x
  } // 만약 child 클래스에 x 변수가 없으면 super.x , this.x 둘다 가능
  
  class Child extends Parent {
  	int x = 20;  // 자식 클래스의 x는 20
  	void method() {
  		System.out.println("x=" + x);  // x = 20 나옴
  		System.out.println("this.x=" + this.x); // x = 20 나옴
  		System.out.println("super.x="+ super.x); // x는 10나옴
  	}
  }
  ```

  

# super() - 조상의 생성자 ( super랑 상관x)

- 조상의 생성자를 호출 할 때 사용  ( 상속에서 생성자, 초기화블럭은 상속안되기 때문)

- 조상의 멤버는 조상의 생성자를 호출해서 초기화

  ```java
  class Point P {
      int x,y;
      
      point(int x, int y) {
          this.x = x;  // iv 초기화
          this.y = y;
      }
  }
  	
  class point3D extends point {
      int z;
      
      point3D ( int x, int y, int z) {
          this.x = x;  // 조상의 멤버를 초기화 , 이렇게 하는거 비추천, 에러는 안남
          this.y = y;  // 조상의 멤버를 초기화
          this.z = z;  // --> 이것만 초기화 하는게 좋음
          
          // 수정 코드
          // super(x,y); Point(int x, int y) 조상 클래스의 생성자를 호출
          // this.z = z;
      }
  }
  ```

  

- 생성자의 첫 줄에 반드시 생성자를 호출해야 한다 ( 중요 ) 

​       그렇지 않으면 컴파일러가 생성자의 첫 줄에  super(); 삽입

```java
class Point P  {  // ojbect가 조상님
	 int x;
    int y;
}
	point() {
        this(0,0); // 첫 줄에 생성자 호출
    }

	point ( int x, int y)   // 컴파일러가 밑줄에 super(); 조상의 기본 생성자 호출
        //super();  
        this.x = x;
        this.y = y;
    }
```

