## equlas(Object obj)

- 객체 자신과 주어진 객체를 비교한다. 같으면 true 다르면 false.
- object클래스의 equals()는 객체의 주소를 비교(참조변수 값 비교)

![1](https://user-images.githubusercontent.com/86362202/140736705-302e81dc-8c6e-466f-b070-5707de4fdb45.png)

```java
class Ex9_1 {
	public static void main(String[] args) {
		Value v1 = new Value(10);
		Value v2 = new Value(10);

		if (v1.equals(v2))
			System.out.println("v1과 v1는 같습니다.");
		else
			System.out.println("v1과 v2는 다릅니다.");
	} // main
} 

class Value {
	int value;

	Value(int value) {
		this.value = value;
	}
	
	// Object의 euqals()를 오버라이딩해서 주소가 아닌 value를 비교
	public boolean equals(Object obj) {
		// return this==obj; // 주소비교, 서로 다른 객체는 항상 거짓
		// 참조변수의 형변환 전에는 instanceof로 확인해야 함
		if(!(obj instanceof Value)) return false;
		
		Value v = (Value)obj; //obj를 value로 형변환
		
		return this.value == v.value;
	}
}
```



## equlas(Object ojb)의 오버라이딩

- 인스턴수 변수(iv)의 값을 비교하도록 equals()를 오버라이딩 해야 한다.

  ![2](https://user-images.githubusercontent.com/86362202/140739687-121982b2-04e6-400e-8f52-cd3e59ff99b0.png)

 

 ```java
import java.util.Iterator;

class Person {
	long id; //this.id

	public boolean equals(Object obj) {
		if(!(obj instanceof Person))
			return false;
		
		Person p = (Person)obj;
		
			return id == p.id;
	}

	Person(long id) {
		this.id = id;
	}
}

class Ex9_2 {
	public static void main(String[] args) {
		Person p1 = new Person(8011081111222L);
		Person p2 = new Person(8011081111222L);

		if(p1.equals(p2))
			System.out.println("p1과 p2는 같은 사람입니다.");
		else
			System.out.println("p1과 p2는 다른 사람입니다.");
		
		
	}
}
 ```

