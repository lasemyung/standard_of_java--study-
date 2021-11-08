# join()과 StringJoiner

- join()은여러 문자열 사이에 구분자를 넣어서 결합한다.

  ```java
  String animals = "dog,cat,pear";
  String[] arr = animals.split(","); // 문자열을 ','을 구분자로 나눠서 배열에 저장
  String str = String.join("-", arr); // 배열의 문자열을 '-'로 구분해서 결합
  System.out.println(str); // dog-cat-bear
  ```

  

##  문자열과 기본형 간의 변환

- 숫자를 문자열로 바꾸는 방법

  ```java
  int i = 100;
  String str1 = i + "";  //100을 "100"으로 변환하는 방법1
  String str2 = String.valueof(i); //100을 "100"으로 변환하는 방법2
  //2번이 속도면에서 빠름
  ```

- 문자열을 숫자로 바꾸는 방법

  ```java
  int i = Integer.parseInt("100"); //"100"을 100으로 변한하는 방법1
  int i2 = Integer.valueof("100"); //"100"을 100으로 변환하는 방법2
  Integer i2 = Integer.valueof("100"); // 원래는 반환 타입이 Integer
  ```

  

### 예제

```java
class Ex9_10 {
	public static void main(String[] args) {
		int iVal = 100;
//		String strVal = String.valueOf(iVal); // int를 String으로 변환한다.
		String strVal = iVal+""; // int를 String으로 변환한다
		
		double dVal = 200.0;
		String strVal2 = dVal + "";	// int를 String으로 변환하는 다른 방법

		double sum  = Integer.parseInt("+"+strVal)
                                          + Double.parseDouble(strVal2);
		double sum2 = Integer.valueOf(strVal) + Double.valueOf(strVal2);
		
		System.out.println(String.join("",strVal,"+",strVal2,"=")+sum);
		System.out.println(strVal+"+"+strVal2+"="+sum2);
	}
}
```

