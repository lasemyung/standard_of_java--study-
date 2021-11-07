# 메서드에 예외 선언하기

- 예외 처리 방법 : try-catch문, 예외 선언하기 ( 예외 떠넘기기 )

- 메서드가 호출 시 발생가능한 예외를 호출하는 쪽에 알리는 것

  예외를 발생시키는 키워드 throw와 예외를 메서드에 선언할 때 쓰이는 trhows를 잘 구별하자

  ```java
  void mehtod() throws exception1, Exception2, ... ExceptionN { // 메서드 예외 선언
      //메서드 내용
  }
  ```

  ```java
  void mehtod() throws Exception {  //모든 종류의 예외가 발생가능
  	//메서드의 내용
  }
  ```

  ```java
  static vod startINstall() throws SpaceExceptoin, MemoeryException {
  	if(!enoughSpace())
  	throw new SpaceException("설치할 공간이 부족합니다");
  	if(!enoughMemory())
  	throw new MemoryException("메모리가 부족합니다")
  }
  ```

  

### 메서드가 호출시 발생가능한 예외를 호출하는 쪽에 알리는 것



![2](https://user-images.githubusercontent.com/86362202/140646870-e010eba9-106a-49c0-bb68-fff2c79f596d.png)

### 예제 살펴보기



![3](https://user-images.githubusercontent.com/86362202/140646987-27b500eb-69c8-4b4c-a051-728f7ff0c343.png)

main 메소드가 mehtod1을 호출하고 mehtod1이 method2를 호출한 상태에서 예외가 발생

하지만 method2에는 try-catch문이 없고 mehtod1에게 떠넘김, mehtod1도 마찬가지로 main메소드에게 떠넘김

main도 try-catch문도 없기 때문에 jvm에게 떠넘김 () -> 비정상 종료



### 예제 살펴보기 2

![4](https://user-images.githubusercontent.com/86362202/140647211-395906ea-27da-49a4-8e3e-b32613df9adb.png)

main메소드가 실행되면서 file f 함수 시작, 입력된 값이 정상적이면 "파일이 성공적으로 생성되었습니다."

만약 빈값이면 예외처리를 메인메소드로 던진다 ( try-catch가 없으니까)

메인메소드에는 예외처리에 해당하는 try-catch문이 있으므로 "파일이름이 있습니다, 다시 입력해주세요"가 나옴


### finally 블럭

- 예외 발생 여부와 관계없이 수행되어야 하는 코드를 넣는다

```java
try {
//예외가 발생할 가능성이 있는 문장
} catch (Exception1 e1) {
	// 예외처리를 위한 문장을 적는다
} finally {
	//예외의 발생여부에 관계없이 항상 수행되어야 하는 문장들을 넣는다
	// finally 블럭은 try-catch문의 맨 마지막에 위치해야 한다
}
```

- try 블럭 안에 return 문이 있어서 try 블럭을 벗어나도 finally 블럭이 실행된다

  ```java
  try {
  	startInstall();
  	copyFiles();
  	deleteTempFiles();
  } catch (Exception e) {
  	e.printStackTrace();
  	deleteTempFiles();
  } //try-catct 의 끝
  ```

  


