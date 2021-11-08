# StringBuffer클래스

- String 처럼 문자형 배열(char[])을 내부적으로 가지고 있다

  ```java
  public final class StringBuffer implements java.io.Serializable {
  	private char[] value;
  		...
  }
  ```

- 그러나 String과달리 내용을 변경할 수 있다(mutable)

  ```java
  Stringbuffer sb = new StringBuffer("abc");
  ```

![1](https://user-images.githubusercontent.com/86362202/140754020-d41e08bc-be7b-48a1-8ef0-59125c4ab156.png)

## StringbBuffer의 생성자

- 배열은 길이 변경 불가, 공간이 부족하면 새로운 배열 생성해야 함

![1](https://user-images.githubusercontent.com/86362202/140754336-a292c87a-dd5d-43aa-8e0e-49d632d8ec4b.png)

- StringBuffer는 저장할 문자열의 길이를 고려해서 적절한 크기로 생성해야 함

```java
public StringBuffer(int length) { //적절한 크기를 넣어준다.
	value = new char[length];
	shared = false;
}

public StringBuffer() {
	this(16); // 버퍼의 크기를 지정하지 않으면 버퍼의 크기는 16이 된다.
}

pulbic StringBuffer(String str) {
	this.(str.lenght() + 16); //지정한 문자열의 길이보다 16이 더 크게 버퍼를 생성한다
	append(str); 
}
```



## StringBuffer의 변경

- StringBuffer는 String과달리 내용 변경이 가능하다.

![1](https://user-images.githubusercontent.com/86362202/140755187-3b778025-a62d-4909-ab42-d65fdf03ada8.png)

- append()는 지정된 내용을 Stringbuffer에 추가 후, Stringbuffer의 참조를 반환

  ```java
  StringBuffer sb2 = sb.append("ZZ"); //sb의 내용뒤에 ZZ를 추가한다
  System.out.println(sb); //abc123ZZ
  System.out.println(sb2); //abc123ZZ
  ```

  ![1](https://user-images.githubusercontent.com/86362202/140755562-93a0bae4-5ba6-49e9-b7e8-4a00337d9755.png)

#### 반환타입이 StringBuffer라서 왼쪽 코드를 오른쪽과 같이 변경 가능하다.



## StringBuffer의 비교

- StringBuffer는 equals()가 오버라이딩 되어 있지 않다.(주소비교) (this==obj)

![1](https://user-images.githubusercontent.com/86362202/140755952-438a7133-bda9-4efa-8e4a-1531d1e4aa4a.png)

- StringBuffer을 String으로 변환 후에 equals()로 비교해야 한다.

![1](https://user-images.githubusercontent.com/86362202/140756068-f430e319-c824-4895-8225-cc1dc9c93d7a.png)

