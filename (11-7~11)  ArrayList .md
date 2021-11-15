#  ArrayList

- ArrayList는 기존의 vector를 개선한 것으로 구현원리와 기능적으로 동일
- vector 동기화 X , ArrayList 동기화 O
- List 인터페이스를 구현하므로 저장순서가 유지되고, 중복 허용
- 데이터의 저장공간으로 배열을 사용한다.

```java
public class Vector extends AbstractList
	implements List, RandomAccess, Cloneable, java.io.Serlializble
	{
		...		 
		protected Object[]  elementData; // 객체를 담기 위한 배열
	}			// 다형성으로 모든 종류의 객체 저장 가능
```

# Arraylist 메서드

#### 생성자

| ArrayList()                    | 기본 생성자      |
| ------------------------------ | ---------------- |
| ArrayList(Collection c)        | 배열             |
| ArrayList(int initialCapacity) | 배열의 길이 설정 |

#### 추가

| boolean add(Object o)                   | 객체를 넣어서 성공하면 true, 실패하면 false |
| --------------------------------------- | ------------------------------------------- |
| void add(int index, Object element)     | index(저장 위치) 를 정해서 추가             |
| boolean addAll(Collection c)            | 컬렉션을 주면 컬렉션 요소를 그대로 저장     |
| boolean addAll(int index, Collection c) | 위치를 정해서 추가                          |

#### 삭제

| boolean remove(Object o)        | 삭제                 |
| ------------------------------- | -------------------- |
| Object remove(int index)        | 위치를 지정해서 삭제 |
| boolean removeAll(Collection c) | 컬렉션을 삭제        |
| void clear()                    | 모든 객체 삭제       |

#### 검색

| int indexOf(Object o)                 | 인덱스를 검색해서 찾음 못찾으면 -1 반환 |
| ------------------------------------- | --------------------------------------- |
| int lastIndexOf(Object o)             | 오른쪽부터 왼쪽으로 찾아줌              |
| boolean contains(Object o)            | 객체가 존재하는지 찾아줌                |
| Object get(int idex)                  | 특정 위치의 객체 반환                   |
| Object set(int index, Object element) | 특정 위치의 객체를 다른걸로 바꿔줌      |



| List subList(int fromindex, int toindex) | from~to 사이의 객체들을 뽑아서 새로운 list를 만들어줌 |
| ---------------------------------------- | ----------------------------------------------------- |
| Object[] toArray()                       | Array리스트가 가지고 있는 객체 배열 반환              |
| Object[] toArray(Object[] a)             |                                                       |
| boolean isEmpty()                        | 비어있는지 확인                                       |
| void trimToSize()                        | 빈공간 제거                                           |
| int size()                               | 저장된 객체의 갯수                                    |



## 예제

```java
import java.util.*;

class Ex11_1 {
	public static void main(String[] args) {
		// 기본 길이(용량, capacity)가 10인 ArrayList를 생성
		ArrayList list1 = new ArrayList(10);
//		list1.add(new Integer(5)); 자동 오토박싱
		list1.add(5);
		list1.add(new Integer(4));
		list1.add(new Integer(2));
		list1.add(new Integer(0));
		list1.add(new Integer(1));
		list1.add(new Integer(3));
		
		//sublist는 일부분을 뽑아서 새로운 list를 만들어 줌
		ArrayList list2 = new ArrayList(list1.subList(1,4)); 
		print(list1, list2);				  // 1~3까지 불러옴 4는 포함 X
		
		// 정렬해서 배열 출력 ( 오름 차순 )
		// Collection은 인터페이스 Collections는 유틸 클래스
		Collections.sort(list1);	
		Collections.sort(list2);	
		print(list1, list2);
		
		// list1이 list2의 모든 요소를 포함하는가? -> true / false
		System.out.println("list1.containsAll(list2):"
                                               + list1.containsAll(list2));

		list2.add("B");
		list2.add("C");
		list2.add(3, "A"); // 3은 추가할 위치, 중간에 넣을 경우 기존 요소가 오른쪽으로 이동
		print(list1, list2);
		
		//set은 변경 추가가 아니라 아예 바꿈
		list2.set(3, "AA");
		print(list1, list2);

		// list1에서 list2와 겹치는 부분만 남기고 나머지는 삭제한다.
		System.out.println("list1.retainAll(list2):" + list1.retainAll(list2));
		print(list1, list2);

		//  list2에서 list1에 포함된 객체들을 삭제한다.
		for(int i= list2.size()-1; i >= 0; i--) {
			if(list1.contains(list2.get(i)))
				list2.remove(i);
		}
		print(list1, list2);
	}

	static void print(ArrayList list1, ArrayList list2) {
		System.out.println("list1:"+list1);
		System.out.println("list2:"+list2);
		System.out.println();		
	}
} // class
```

![123](https://user-images.githubusercontent.com/86362202/141711260-3d711143-57a0-4bcd-adcc-6342bc74e2a1.png)



# ArrayList에 저장된 객체의 삭제 과정

- ArrayList에 저장된 세 번째 데이터(data[2])를 삭제하는 과정. list.remove(2);를 호출

삭제할 데이터 아래의 데이터를 한 칸씩 위로 복사해서 삭제할 데이터를 덮어 쓴다

```java
System.arraycopy(data, 3, data, 2, 2)
	data[3]에서 data[2]로 2개의 데이터를 복사하라는 의미이다.
```

데이터가 모두 한 칸씩 이동했으므로 마지막 데이터는 null로 변경한다

```java
data[size-1] = null;
```

데이터가 삭제되어 데이터의 개수가 줄었으므로 size의 값을 감소 시킨다.

```java
size--;	
```

마지막 데이터를 삭제하는 경우 1의 과정은 필요 없다



ArrayList에 저장된 첫 번째 객체부터 삭제하는 경우(배열 복사 발생)

```java
for(int i=0; i<list.size(); i+)
	list.remove();
```

![11](https://user-images.githubusercontent.com/86362202/141784869-7e0abc32-7968-4fdc-b9f0-77b30528f03d.png)

ArrayList에 저장된 마지막 객체부터 삭제하는 경우 ( 배열 복사 발생 안함)

![22](https://user-images.githubusercontent.com/86362202/141785014-2b260312-c2dc-471c-b49a-2ef816cf4c57.png)

# java API 소스 보기 - /jdk설치경로/src.zip



