# SimpleDateFormat(1/2)

- 날짜와 시간을 다양한 형식으로 출력 가능하게 해준다.

  ```java
  Date today = new Date();
  SimpleDateFormat df = new SimpleDateFormat("yyyy-MM-dd");
  
  // 오늘 날짜를 yyyy-mm-dd형태로 변환
  String result = df.format(today);
  ```

  ![22](https://user-images.githubusercontent.com/86362202/141687891-ac0d7420-5049-467c-a588-9ac7bd2136bf.png)



- 특정 형식으로 되어 있는 문자열에서 날짜와 시간을 뽑아 낼 수도 있다

  ```java
  DateFormat df = new SimpleDateFormat("yyyy년 MM월 dd일");
  DateFormat df2 = new SimpleDateFormat("yyyy/MM/dd");
  
  Date d = df.parse("2015년 11월 23일");
  String  result = df2.format(d);
  ```

  ![33](https://user-images.githubusercontent.com/86362202/141687991-5d550506-27d2-4dcb-8e14-ea40d27c09d7.png)



## 예제

```java
import java.util.*;
import java.text.*;

class Ex10_8 {
	public static void main(String[] args) {
		Date today = new Date(); //현재의 시간의 날짜

		SimpleDateFormat sdf1, sdf2, sdf3, sdf4;
		SimpleDateFormat sdf5, sdf6, sdf7, sdf8, sdf9;

		sdf1 = new SimpleDateFormat("yyyy-MM-dd");
		sdf2 = new SimpleDateFormat("''yy년 MMM dd일 E요일");
		sdf3 = new SimpleDateFormat("yyyy-MM-dd HH:mm:ss.SSS");
		sdf4 = new SimpleDateFormat("yyyy-MM-dd hh:mm:ss a");

		sdf5 = new SimpleDateFormat("오늘은 올 해의 D번째 날입니다.");
		sdf6 = new SimpleDateFormat("오늘은 이 달의 d번째 날입니다.");
		sdf7 = new SimpleDateFormat("오늘은 올 해의 w번째 주입니다.");
		sdf8 = new SimpleDateFormat("오늘은 이 달의 W번째 주입니다.");
		sdf9 = new SimpleDateFormat("오늘은 이 달의 F번째 E요일 입니다.");

		System.out.println(sdf1.format(today));	// format(Date d)
		System.out.println(sdf2.format(today));
		System.out.println(sdf3.format(today));
		System.out.println(sdf4.format(today));
		System.out.println();
		System.out.println(sdf5.format(today));
		System.out.println(sdf6.format(today));
		System.out.println(sdf7.format(today));
		System.out.println(sdf8.format(today));
		System.out.println(sdf9.format(today));
	}
}
```

![44](https://user-images.githubusercontent.com/86362202/141688198-1d72e0b8-e1c2-43bc-8ae2-17d3cd49c25a.png)

