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
```
<?xml version="1.0" encoding="utf-8"?>  
<layout  xmlns:android="http://schemas.android.com/apk/res/android">
	  <data>  
		  <variable  name="user"  type="com.example.User"/>
	  </data>
	  <LinearLayout  android:orientation="vertical"
	    android:layout_width="match_parent"
	    android:layout_height="match_parent">
	        <TextView  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="@{user.firstName}"/>  <TextView  android:layout_width="wrap_content"  android:layout_height="wrap_content"  android:text="@{user.lastName}"/>  </LinearLayout>  
</layout>
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTc5MTE2NDY5NywxMjY0OTYwMTgyXX0=
-->