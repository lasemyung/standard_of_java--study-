# import문

- 클래스를 사용할 때 패키지 이름을 생략 할 수 있다

- 컴파일러에게 클래스가 속한 패키지를 알려 준다

- java.lang패키지의 클래스는 import 하지 않고도 사용 할수 있다

  (String, Object, System, Thread ...)

  ```java
  class ImportTest {
  	Java.util.Datetoday = new java.util.Date();
  	//...
  }
  	//아래는 import문을 사용하여 객체 생성 생략	ctrl+shift+O (단축키)
  import java.util.Date;
  
  class ImportTest {
      Date.today = new Date();
  }
  
  
  import java.lang *; //(모든 클래스, 생략 가능)
  	
  	class ImportTest2 {
          public static void main(STring{} args) {
              System.out.println("Hello World!");
          }
      }
  ```



### import문 선언

- import 문을 선언하는 방법은 다음과 같다

  ```java
  import  패키지명.클래스명; // ctrl+shift+O
                 or
  import 패키지명.*;  // 모든 클래스 
  ```

  - import문은 패키지문과클래스 선언 사이에 선언한다

  - import문은 컴파일 시에 처리되므로 프로그램의 성능에 영향 없음

    ```java
    import java.util.Calendar  
    import java.util.Date              ->  import java.util.*;
    import java.util.ArrayList             
    ```

    

  ### static import문

  - static멤버를 사용할 때 클래스 이름을 생략 할 수 있게 된다

    ```java
    import static java.lang.Integer.*;  // Integer클래스의 모든 static 메서드
    import static java.lang.Math.random.*; // Math.random()만. 괄호 안붙임
    import static java.lang.System.out.*; //System.out.을 out만으로 참조 가능
    
    ```

    
