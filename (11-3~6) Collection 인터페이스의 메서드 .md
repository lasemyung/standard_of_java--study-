# Collection 인터페이스의 메서드

- List ( 중복O, 순서O )
- Set ( 중복, 순서 X)
- Map (중복 X , 순서 : 키X / 값 O )
- collection ( List,set의 공통부분 )

![22](https://user-images.githubusercontent.com/86362202/141706735-5b0f58da-853b-49a6-9167-75f6939c9b56.png)



# List 인터페이스  - 순서, 중복 O

![33](https://user-images.githubusercontent.com/86362202/141706886-6072f875-7059-4478-bedc-2461ee0d39a1.png)

![44](https://user-images.githubusercontent.com/86362202/141707088-480d7d72-f1c4-4a83-a979-03c48af47566.png)

- List,set은 Collection 클래스의 자손이므로 조상의 클래스를 사용 할 수 있다.



# Set 인터페이스 - 순서X, 중복 X (집합)

![55](https://user-images.githubusercontent.com/86362202/141707198-ee84bdb6-3e36-4175-87bd-a5c91cac2665.png)

![66](https://user-images.githubusercontent.com/86362202/141707258-528ab69d-1371-4d8b-9ec9-eb4ed7cc3e48.png)



# Map 인터페이스 - 순서X,중복(키X, 값O)

![77](https://user-images.githubusercontent.com/86362202/141707359-7c7c2b4d-4924-4f8b-a0a1-7f4f99320bac.png)

- hashtable( 예전 것 ) = hashmap( 최신 )

- hashtable (동기화 o ) , hashmap ( 동기화 x )

  ![1](https://user-images.githubusercontent.com/86362202/141708078-8eaaaa3d-6c11-4c7f-93d8-da1f91a8d77b.png)

-  키 + 값 = entry
- collection -> 순서, 중복 모두 O,X 허용

