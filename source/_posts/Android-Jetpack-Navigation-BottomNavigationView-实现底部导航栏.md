---
title: Android-Jetpack-Navigation-BottomNavigationView-实现底部导航栏
tags: [Jetpack,Navigation,Android,移动端]
categories: Android
date: 2022-01-07
updated:  2022-01-07
description:    基于Jetpack-Navigation-BottomNavigationView-实现底部导航栏
top_img: https://static.runoob.com/images/mix/life-code-typography-hd-wallpaper-1920x1080-7168.jpg
cover: https://static.runoob.com/images/mix/life-code-typography-hd-wallpaper-1920x1080-7168.jpg
connents: 
aside: true
--- 


## 1、效果展示
![在这里插入图片描述](https://img-blog.csdnimg.cn/7ae4047cff1b47c4a30d43510cb54258.gif#pic_center)

## 2、实现步骤
### 1、导入相关依赖

```groovy
dependencies {
    //Navigation
    def nav_version = "2.3.5"
    implementation "androidx.navigation:navigation-fragment:$nav_version"
    implementation "androidx.navigation:navigation-ui:$nav_version"
}
```



### 2、创建Fregment

	FirstFragment.class

```java
public class FirstFragment extends Fragment {
    @Override
    public View onCreateView(LayoutInflater inflater, ViewGroup container,
                             Bundle savedInstanceState) {
        return inflater.inflate(R.layout.fragment_first, container, false);
    }
}
```

    fragment_first.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".Fragment.FirstFragment">

    <TextView
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:gravity="center"
        android:textSize="25pt"
        android:text="First" />

</FrameLayout>
```

SecondFragment、ThirdFragment仅文本显示不同，略过。

### 3、创建导航资源图

![在这里插入图片描述](https://img-blog.csdnimg.cn/f7afa1bbdeb04d31b772f4c458ece2e2.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA546L5bCP5rOl,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)



```xml
<?xml version="1.0" encoding="utf-8"?>
<navigation xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:id="@+id/main_navigation"
    app:startDestination="@id/firstFragment">

    <fragment
        android:id="@+id/firstFragment"
        android:name="com.holloyi.bottomnavdemo.Fragment.FirstFragment"
        android:label="fragment_first"
        tools:layout="@layout/fragment_first" />
    <fragment
        android:id="@+id/secondFragment"
        android:name="com.holloyi.bottomnavdemo.Fragment.SecondFragment"
        android:label="fragment_second"
        tools:layout="@layout/fragment_second" />
    <fragment
        android:id="@+id/thirdFragment"
        android:name="com.holloyi.bottomnavdemo.Fragment.ThirdFragment"
        android:label="fragment_third"
        tools:layout="@layout/fragment_third" />
</navigation>
```



### 4、创建menu资源文件

![在这里插入图片描述](https://img-blog.csdnimg.cn/907a564b091f4e3a85100ce253abdb79.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA546L5bCP5rOl,size_20,color_FFFFFF,t_70,g_se,x_16#pic_center)



```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android">
    <item
        android:id="@+id/firstFragment"
        android:title="First"
        android:icon="@drawable/ic_home_blue"/>
    <item
        android:id="@+id/secondFragment"
        android:title="Second"
        android:icon="@drawable/ic_car"/>

    <item
        android:id="@+id/thirdFragment"
        android:title="Third"
        android:icon="@drawable/ic_calendar"/>
</menu>
```



### 5、MainActivity布局文件

activity_my_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context=".MainActivity">
    <fragment
        android:id="@+id/nav_host"
        android:name="androidx.navigation.fragment.NavHostFragment"
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        app:defaultNavHost="true"
        app:navGraph="@navigation/main_navigation"
        tools:ignore="FragmentTagUsage" />

    <com.google.android.material.bottomnavigation.BottomNavigationView
        android:id="@+id/bottom_nav_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:itemIconTint="@drawable/selector_bottom_nav_icon_color"
        app:itemTextColor="@drawable/selector_bottom_nav_icon_color"
        app:labelVisibilityMode="labeled"
        app:menu="@menu/bottom_nav_menu" />
</LinearLayout>
```

selector_bottom_nav_icon_color.xml,用于区分底部active和inactive状态

```xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:state_checked="true" android:color="@color/activity_toolbarbgd" />
    <item android:state_pressed="true" android:state_enabled="true" android:color="@color/activity_toolbarbgd" />
    <item android:color="@color/InactiveBottomNavIconColor" />
</selector>
```



### 6、MainActivity.class

```java
public class MainActivity extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        NavController navController = Navigation.findNavController(this,R.id.nav_host);
        BottomNavigationView navigationView = findViewById(R.id.bottom_nav_view);
        NavigationUI.setupWithNavController(navigationView,navController);
    }
}
```

## 3、BottomNavigationView使用详情
```xml
 <com.google.android.material.bottomnavigation.BottomNavigationView
        android:id="@+id/bottom_nav_view"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:itemIconTint="@drawable/selector_bottom_nav_icon_color"
        app:itemTextColor="@drawable/selector_bottom_nav_icon_color"
        app:labelVisibilityMode="auto"
        app:menu="@menu/bottom_nav_menu" />
```
### 1、底部menu的item不能超过5个,建议3-5个
### 2、labelVisibilityMode menu-item文本显示模式
    + auto
    item<=3时,为labeled模式
    item>3时,为selected模式
   + selected

    仅选中项显示文本
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/9d5235e965e7463e91a99eda742be933.gif#pic_center)

   + labeled

    所有item显示文本
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/a316200d0a274f4b84da1ffbf3feee70.gif#pic_center)

   + unlabeled

    所有item不显示文本
    ![在这里插入图片描述](https://img-blog.csdnimg.cn/71ab145c25874d7cbbf6bf9226293d7a.gif#pic_center)
### 3、item脚标
```java
//获取角标
        BadgeDrawable badge1 = navigationView.getOrCreateBadge(R.id.firstFragment);
        BadgeDrawable badge2 = navigationView.getOrCreateBadge(R.id.secondFragment);
        BadgeDrawable badge3 = navigationView.getOrCreateBadge(R.id.thirdFragment);
        //角标是否显示
        badge1.setVisible(true);
        //角标位置
        badge1.setBadgeGravity(BadgeDrawable.TOP_START);
        //显示数量
        badge2.setNumber(10);
        badge3.setNumber(99);
        //角标背景
        badge3.setBackgroundColor(R.color.black);
        badge3.setBadgeGravity(BadgeDrawable.TOP_END);
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/2d4d3c85463944728df7a85c78041ad1.png?x-oss-process=image/watermark,type_d3F5LXplbmhlaQ,shadow_50,text_Q1NETiBA546L5bCP5rOl,size_14,color_FFFFFF,t_70,g_se,x_16#pic_center)



## 4、git地址
[https://gitee.com/Holloyi/bottom-nav-demo](https://gitee.com/Holloyi/bottom-nav-demo)