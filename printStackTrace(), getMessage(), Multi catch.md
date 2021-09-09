# printStackTrace() / getMessage()

- printStackTrace() : 예외 발생 당시의 호출스택(Call Stack)에 있었던 메서드의 정보와 

  예외 메시지를 화면에 출력한다

- getMessage() 발생한 예외클래스의 인스턴스에 저장된 메시지를 얻을 수 있다

  ```java
  try {
  	...
  	System.out.println(0/0);  // 예외 발생 , 예외 객체 생성 (ArithmeticException)
      ...
  } catch ( ArithmeticException ae ) {  // 타입 . 참조변수 일치
      ae.printStackTrace();
      System.out.println( ae. getMessage("예외메시지 : " + ae.getMessage());
  } catch ( Exception e ) { 
      ...
  }
  ```

  

## 멀티 catch 블럭

- 내용이 같은 catch 블럭을 하나로 합친 것 ( JDK1.7 부터 가능 )

```java
try {
	...
} catch ( ExceptionA e ) {
	e.printStackTrace();
} catch ( ExceptionB e 2) {
	e2.printStackTrace();
} 
		// 아래는 코드를 하나의 catch 블럭으로 정리
try {
    ...
} catch ( ExceptionA | ExceptionB e ) {
	e.printStackTrace();
}

try {
    ...
// } catch ( ParentException | ChildException e ) { // 부모 자식 관계는 에러남
} catch (  ParentExceptionA e ) { 
	e.printStackTrace();
}
```

