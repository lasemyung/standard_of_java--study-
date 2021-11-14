# Calendar 클래스 예제4,5

- add()는 특정 필드의 값을 증가 또는 감소 ( 다른 필드에 영향O )

  ```java
  Calendar date = Calendar.getInstance();
  date.clear(); // 모든 필드를 초기화
  date.set(2020,7,31);
  
  date.add(Calendar.DATE, +1); //  날짜에 1을 더한다
  date.add(Calendar.MONTH, -8); //  월에서 8을 뺀다
  ```

-  roll()은 특정 필드의 값을 증가 또는 감소 ( 다른 필드에 영향 X )

  ```java
  date.set(2020,7,31);
  
  //add()와 달리 다른 필드에 영향을 X
  date.roll(Calendar.DATE, 1);	// 날짜에 1을 더한다
  date.roll(Calendar.MONTH, -8); // 월에서 8을 뺀다
  ```



## 예제 달력 구하기

```java
import java.util.*; 

class Ex10_5 { 
	public static void main(String[] args) { 
		if(args.length !=2) { 
			System.out.println("Usage : java Ex10_5 2019 9"); 
			return; 
		} 
		int year  = Integer.parseInt(args[0]); 
		int month = Integer.parseInt(args[1]); 
		int START_DAY_OF_WEEK = 0; //1일의 요일
		int END_DAY = 0; 

		Calendar sDay = Calendar.getInstance(); // 시작일 
		Calendar eDay = Calendar.getInstance(); // 끝임 

		// 월의 경우 0부터 11까지의 값을 가지므로 1을 빼준다
  		sDay.set(year, month-1, 1); //month는 0부터 시작     
		eDay.set(year, month, 1); 

		// 다음달의 첫날에서 하루를 빼면 현재 달의 마지막 날이 된다.
		eDay.add(Calendar.DATE, -1);       

		// 첫번째 요일이 무슨 요일인지 알아낸다.
		START_DAY_OF_WEEK = sDay.get(Calendar.DAY_OF_WEEK); 

		// eDay에 지정된 날짜를 얻어온다. 
		END_DAY = eDay.get(Calendar.DATE); 

		System.out.println("      " + args[0] +"년 " + args[1] +"월"); 
		System.out.println(" SU MO TU WE TH FR SA"); 

		// 해당 월의 1일이 어느 요일인지에 다라서 공백을 출력한다.
		// 만일 1일이 수요일이라면 공백을 세번 찍는다.
		for(int i=1; i < START_DAY_OF_WEEK; i++)  
			System.out.print("   "); 
            
		for(int i=1, n=START_DAY_OF_WEEK ; i <= END_DAY; i++, n++) { 
			System.out.print((i < 10)? "  "+i : " "+i ); 
			if(n%7==0) System.out.println(); 
		} 
	} 
}
```



# Date와 Calendar간의 변환

- Date의 메서드는 대부분 deprecated되었지만 여전히 사용

```java
1. Calendar를 Date로 변환
	Calendar cal = Calendar.getInstance();
		...
	Date d = new Date(cal.getTimeInMillis()); // Date(long date)
	
2. Date를 Calendar로 변환
	Date d = new Date();
		..
	Calendar cal = Calendar.getInstance();
	cal.setTime(d);
```

