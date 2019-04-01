## Data Binding이란?
UI와 데이터/로직을 연결하는 것.

## Android Data Binding Library
xml 파일에서 view와 데이터를 연결해주는 라이브러리.
<br>
이를 통해서 글루코드(UI와 로직을 연결하는 코드)를 줄일 수 있음
<br>
findViewById, OnClickListener 등

## 프로젝트에 추가하기
```
android {
  ....
  dataBinding {
   enabled =  true  
   }  
}
```

## xml 코드
루트가 layout 태그로 시작해야 함
data 태그 안에는 레이아웃에서 사용할 클래스들을 variable로 선언해서 씀
```
<?xml version="1.0" encoding="utf-8"?>  
<layout  xmlns:android="http://schemas.android.com/apk/res/android">

	<data>  
		<variable  name="user"  type="com.example.User"/>
	</data>
	
	<LinearLayout  android:orientation="vertical"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent">
	   
	    <TextView  android:layout_width="wrap_content" 
	     android:layout_height="wrap_content"  
	     android:text="@{user.firstName}"/>  
	    
	     <TextView  
	     android:layout_width="wrap_content"  
	     android:layout_height="wrap_content"  
	     android:text="@{user.lastName}"/>  
	 </LinearLayout>  
</layout>
```

## 코드에서 바인딩된 변수에 값 할당하기

액티비티
```
@Override  
protected  void onCreate(Bundle savedInstanceState)  { 
	super.onCreate(savedInstanceState);  
	MainActivityBinding binding =  DataBindingUtil.setContentView(this, R.layout.main_activity);  
	User user =  new  User("Test",  "User"); 
	binding.setUser(user);  
}
```

<br>

리사이클러뷰 등
```
ListItemBinding binding =  ListItemBinding.inflate(layoutInflater, viewGroup,  false);  
//or  
ListItemBinding binding =  DataBindingUtil._inflate_(layoutInflater, R.layout.list_item, viewGroup,  false);
```


## 이벤트 처리
기존에 사용하던 이벤트 처리용 메소드들을 사용할 필요가 없음
<br>
예 : setOnclickListener, addTextChangedListener 등 수많은 리스너
<br>
대신 메소드를 선언해서 만들고 xml 파일에서 그 메소드를 붙여주면 됨.
<br>
메소드

```
public class Handler {
	public void onButtonClick(View view){
	....
	}
}
```
<br>

xml 파일
```
<TextView  android:layout_width="wrap_content"  
android:layout_height="wrap_content"  
android:text="@{user.firstName}"  
android:onClick="@{handlers::onButtonClick}"/>
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE1ODA5NjQ1NzMsMTI2NDk2MDE4Ml19
-->