# String 클래스

- String 클래스 = 데이터(char[]) + 메서드(문자열 관련)

  ```java
  public final class String implements java.io.Serializable, Comparable {
  	private char[] value;
      	...
  }
  ```

- 내용을 변경할 수 없는 불변(immutable) 클래스

  

![3](https://user-images.githubusercontent.com/86362202/140742653-479a7a94-db64-46c2-a378-dfb90694a43b.png)

-   덧셈 연산자를 이용한 문자열 결합은 성능이 떨어짐

  문자열 결합이나 변경이 잦다면 내용 변경 가능한 StringBuffer을 사용



## 문자열 비교

- String str = "abc";와 String str = new String("abc");의 비교

![4](https://user-images.githubusercontent.com/86362202/140743167-2b749398-5185-4fd4-ba44-4b7057b1114c.png)



## 문자열 리터럴

- 문자열 리터럴은 프로그램 실행시 자동으로 생성된다. (constant pool에 저장)

![5](https://user-images.githubusercontent.com/86362202/140743930-4fbfee4c-04ee-4a12-be89-c633d20016c8.png)

String  클래스는 불변 클래스 이므로 내용이 변경 불가하다.



## 빈 문자열 ("", empty string)

- 내용이 없는 문자열. 크기가 0인 char형 배열을 저장하는 문자열

  ```java
  String str =""; //str을 빈 문자열로 초기화
  ```

- 크기가 0인 배열을 생성하는 것은 어느 타입이나 가능

  ```java
  char[] chArr = new char[0]; //길이가 0인 char 배열
  int[] iArr = {}; //길이가 0인 int 배열
  ```

- 문자(char)와 문자열(String)의 초기화

  ![6](https://user-images.githubusercontent.com/86362202/140744616-d04fb56e-0a2a-4bee-aa32-bcd227f09954.png)

