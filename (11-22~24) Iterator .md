# Iterator(new), ListIterator, Enumeration (old)

- 컬렉션에 저장된 데이터를 접근하는데 사용되는 인터페이스

- ListIterator는 Iterator의 접근성을 향상시킨 것 ( 단방향 -> 양방향 ) ( next, previous 둘다 있음) ( 잘 쓰이진 않음)

  | 메서드                  | 설명                                                         |
  | ----------------------- | ------------------------------------------------------------ |
  | boolean hashNext() 확인 | 읽어 올 요소가 남아 있는지 확인한다. true / false            |
  | Object next() 읽기      | 다음 요소를 읽어 온다, next()를 호출하기 전에 hashNext()를 호출해서 읽어 올 요소가 있는지 확인하는 것이 안전하다. |
  | void remove()           | next()로 읽어 온 요소를 삭제한다. next()를 호출한 다음에 remove()를 호출해야 한다.(선택적 기능) |



## Iterator을 쓰는 이유

- 컬렉션에 저장된 요소들을 읽어오는 방법을 표준화 한것 ( List, set , map )
- 구조에 상관없이 확인한 뒤 읽어오기 때문에 편리하다
- 컬렉션에 iterator()를 호출해서 Iterator를 구현한 객체를 얻어서 사용

![44](https://user-images.githubusercontent.com/86362202/142006710-30511fba-0912-4597-b62f-f812364c4f20.png)

```java
List list = new ArrayList(); // 다른 컬렉션으로 변경할 때는 이 부분만 고치면 된다.
Iterator it = list.iterator(); //iterator 객체를 it에 반환

while(it.hashNext()) { // boolean hashNext() 읽어올 요소가 있는지 확인
	System.out.println(it.next()); // Object next() 다음 요소를 읽어옴
}
```



### 예제

- iterator을 활용한 ArrayList 내용 출력

```java
import java.util.*;

class Ex11_5 {
	public static void main(String[] args) {
		ArrayList list = new ArrayList(); //Arraylist 생성
		list.add("1");
		list.add("2");
		list.add("3");
		list.add("4");
		list.add("5");

		Iterator it = list.iterator(); 

		while(it.hasNext()) { // 읽어올 요소가 있는지 확인, 없으면 false 반복문 탈출
			Object obj = it.next(); // 다음 요소를 읽어 온다.
			System.out.println(obj); // obj 내용 출력
            
        for(int i=0;)
		}
	} 
}
```



# Map과 Iterator

- Map에는 iterator()가 없다. KeySet(), entrySet(), values()를 호출해야

  ```java
  public interface Collection {
  	...
  	public Iterator iterator();
  }
  ```

  ![22](https://user-images.githubusercontent.com/86362202/142010362-8371e9e4-d354-41b3-a0af-befe4fb0838e.png)

```java
Map map = new HashMap();
	...
Iterator it = map.entrySet().iterator(); //아래 두 문장을 합친 것
// set eSet = map.entrySet();
// Iterator it = eSet.iterator();
```

