## MVP

**MVC** : Model-View-Controller 패턴.<br>
화면(View)과 로직(Model)을 분리하고 둘 사이를 Controller로 중개 하는 방식.

안드로이드에 MVC를 적용하게 되면 발생하는 문제<br>
-> Activity가 View와 Controller의 역할을 모두 하고 있기 때문에 프로젝트 규모가 커질수록 Activity Class의 코드가 비대해짐.<br>
-> 유지보수 힘듦<br>
->그래서 나온게 MVP<br>


**MVP** : Model-View-Presenter 패턴<br>
Presenter가 MVC의 Controller의 역할을 해줌으로써 Activity가 View의 역할만을 가지게 함. Model은 동일.<br>
-> 뷰와 로직을 분리했기 때문에 Activity Class의 비대가 해결되었고 로직 단위의 테스트가 가능해짐<br>
-> View : Presenter = 1 : 1이기 때문에 파일 수가 많아짐.<br>
-> 프로젝트 규모가 커지면 MVC의 Activity 처럼 Presenter도 비대해짐.<br>
-> 그래서 나온게 MVVM<br>

**MVVM** : Model-View-ViewModel 패턴
ViewModel은 Presenter나 Controller와 달리 View의 존재를 모름. View는 구독(subscribe)을 통해 ViewModel에서 일어나는 데이터의 변화를 반영할 수 있음.
-> MVP보다 더 뷰와 로직의 결합도를 낮출 수 있음
->Data Binding, RxAndroid, Live
<!--stackedit_data:
eyJoaXN0b3J5IjpbMjQxNTIyOTE4LDEyNzA5MzgxLDUxMzQzMD
E4OSw5NTAzNTQyNzMsLTE3OTMzOTEyMDcsMTU3MjI2MjEyOSwx
MjE3MzMyNDE3LDkxMTU4MDA3OF19
-->