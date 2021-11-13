# Calendar클래스 - 예제 2,3 

- set()으로 날짜와 시간 지정하기

  ```java
  void set ( int field, int value )
  void set ( int year, int month, int date )
  void set ( int year, int month, int date , int hourOfDay, int minute)
  void set ( int year, int month, int date  int hourOfDay, int minute, int second)
  ```

  - 날짜 지정하는 방법, 월(MONTH)이 0부터 시작한다는 점에 주의

    ```java
    Calendar datel = Calendar.getInstance();
    datel.set ( 2017, 7, 15); // 2017년 8월 15일 ( 7월 아님)
    // datal.set (Calendar.YEAR, 2017);
    // datal.set (Calendar.MONTH, 7);
    // datal.set (Calendar.DATE, 15);
    
    // 0부터 시작하는 이유는 배열때문 
    ```

- 시간 지정하는 방법

```java
Calendar time1 = Calendar.getInstance();
time1.set (Calendar.HOUR_OF_DAY, 10); // timel을 10시 20분 30초로 설정
time1.set(Calendar.MINUTE, 20);
time1.set(Calendar.SECOND, 30);
```

## 예제

![3](https://user-images.githubusercontent.com/86362202/141643193-ad39d5c3-6854-4fce-b98d-69be23df8b4c.png)
![4](https://user-images.githubusercontent.com/86362202/141643194-00d1212d-984b-4869-8327-4098c52b374e.png)



- clear()는 Calendar객체의 모든 필드를 초기화 ( 현재시간으로 )

  ```java
  Calendar dt = Calendar.getInstance();
  
  // Tue Aug 29 07:13:03 KST2017
  System.out.println(new Date(dt.getTimeInMillis()));
  
  dt.clear(); //모든 필드를 초기화
  // THU JAN 01 00:00:00 KST 1970 이때가 처음 기준 시간
  System.out.println(new Date(dt.getTimeInMillis()));
  ```

- clear(int field)는 Calendar객체의 특정 필드를 초기화

  ```JAVA
  Calendar dt = Calendar.getInstance();
  System.out.println(new DAte(dt.getTimeInMillis()));
  
  dt.clear(Calendar.SECOND); //초 초기화
  dt.clear(Calendar.MINUTE); // 분 초기화
  dt.clear(Calendar.HOUR_OF_DAY); // 시간 초기화
  dt.clear(Calendar.HOUR); //시간 초기화
  
  System.out.println(new Date(dt.getTimeInMillis()));
  ```

  

