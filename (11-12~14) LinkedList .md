# LinkedList - 배열의 장단점

- 장점 :  배열은 구조가 간단하고 데이터를 읽는 데 걸리는 시간 

  ​			(접근시간, access time)이 짧다.

- 단점1 : 크기를 변경할 수 없다.

  - 크기를 변경해야 하는 경우 새로운 배열을 생성 후 데이터를 복사
  - 크기 변경을 피하기 위해 충분히  큰 배열을 생성하면, 메모리가 낭비됨

- 단점 2 : 비순차적인 데이터의 추가, 삭제에 시간이 많이 걸린다

  -  데이터를 추가하거나 삭제하기 위해, 다른 데이터를 옮겨야 함
  - 그러나 순차적인 데이터 추가( 끝에 추가) 와 삭제(끝부터 삭제)는 빠르다.



# LinkedList - 배열의 단점을 보완

- 배열과 달리 LinkedList는 불연속적으로 존재하는 데이터를 연결(link)

  ![33](https://user-images.githubusercontent.com/86362202/141787172-3385d038-d483-4723-abab-7d873db4590a.png)

- 데이터의 삭제 : 단 한 번의 참조변경만으로 가능
- 데이터의 추가 : 한번의 node객체생성과 두번의 참조변경만으로 가능



# LinkedList - 이중 연결 리스트

- Linked List - 연결리스트, 데이터 접근성이 나쁨

  ![344](https://user-images.githubusercontent.com/86362202/141788894-b7e6174d-e159-4d42-b617-e4acbe096f55.png)

(한번에1번에서 5번으로 못감, 자기 뒤에 친구밖에 모름)

- 이중 연결 리스트 -  접근성 향상

  ![153](https://user-images.githubusercontent.com/86362202/141789333-66b5161d-1a3e-4503-b767-c7d7e6f85086.png)

### dobuly circular linked list - 이중 원형 연결 리스트

![2534](https://user-images.githubusercontent.com/86362202/141789783-fc376dbf-09ab-4c2b-970f-de29e278e8da.png)



# ArrayList vs LinkedList 성능 비교

![435](https://user-images.githubusercontent.com/86362202/141789979-d37c26cf-6652-43f2-b304-385adf91e675.png)

- 순차적으로 데이터를 추가-삭제 : ArrayList가 빠름

- 비 순차적으로 데이터를 추가-삭제 : LinkedList가 빠름

- 접근시간 : ArrayList가 빠름

  ```java
  인덱스가 n인 데이터의 주소 = 배열의 주소  + n + 데이터 타입의 크기
  ```

  

