# hashcode()

- 객체의 해시코드를 반환하는 메서드 ( 해시코드=정숫값,해싱 알고리즘)

- object클래스의 hashcode()는 객체의 주소를 int로 변환해서 반환

  ```java
  pubic class object {
  	...
  	public native int hashcode(); //네이티브메서드 : OS의 메서드(c언어)
  }
  ```

- equals()를 오버라이딩하면, hashcode()도 오버라이딩해야 한다.

  equals()의 결과가 true인 두 객체의 해시코드는 같아야하기 때문이다.

  ```java
  String str1 = new String("abc");
  String str2 = new String("abc");
  Sytem.out.println(str1.equals(str2)); //true
  Sytem.out.println(str1.hashcode()); // 96354
  Sytem.out.println(str22.hashcode()); // 96354
  ```

- System.identityHashCode(Object obj)는 Object클래스의 hashcode()와 동일

  ```java
  System.out.println(System.identityHashcode(str1));  //3526198
  System.out.println(Sytem.identityHashcode(str2));   //7699183
  ```

  

# toString(), toString()의 오버라이딩

- toString() :  객체를 문자열(String)으로 변환하기 위한 메서드

  ```java
  public String toString() {
  	return getClass().getName()+"@"+Integer.tpHextString(hashcode());
  }
  ```

  ![1](https://user-images.githubusercontent.com/86362202/140720904-17b1f70a-81fd-416e-bb39-d1736e8c10ce.png)



### 예제

```java
import java.util.Objects;

class Card {
	String kind;
	int number;

	Card() {
		this("SPADE", 1);
	}

	Card(String kind, int number) {
		this.kind = kind;
		this.number = number;
	}
	
	//euqals()를 오버라이딩하면 hascode()도 오버라이딩 해야한다.
	
	public int hashCode() {
		return Objects.hash(kind, number);
	}
	
	public boolean equals(Object obj) {
		if(!(obj instanceof Card))
			return false;
		
		Card c =(Card)obj;
		return this.kind.equals(c.kind)&& this.number==c.number; 
	}
	
	//object 클래스의 toString()을 오버라이딩
	public String toString() {
		return "kind:" + kind +", number"+number;
	}
}

class Ex9_4 {
	public static void main(String[] args) {
		Card c1 = new Card();
		Card c2 = new Card();

		System.out.println(c1.equals(c2));
		//euqals 결과가 같으면 해쉬코드도 같게 나온다.
		System.out.println(c1.hashCode());
		System.out.println(c2.hashCode());
	}
}
```

