# ByeBurgerNavigationView
[![](https://jitpack.io/v/githubwing/ByeBurgerNavigationView.svg)](https://jitpack.io/#githubwing/ByeBurgerNavigationView)


Bye Burger~  this is a new android Bottom Navigation like this

[Bye, Bye Burger!
What we learned from implementing the new Android Bottom Navigation](https://medium.com/startup-grind/bye-bye-burger-5bd963806015#.qibuxdc1t)


##[中文文档](https://github.com/githubwing/ByeBurgerNavigationView/blob/master/README_CN.md)

![image](https://github.com/githubwing/ByeBurgerNavigationView/raw/master/img/preview.gif)

> **Hiding on scroll:** We wanted to provide as much content as possible on our user’s screens. Consequently, we decided to make the navigation hide on scroll, thus making more room for the content area. Scrolling up makes the navigation fade back in.

> **Shifting navigation** : The Material Design bottom bar comes with a very slick animation, which is referred to as the Shifting navigation — when navigating between destinations the selected section icon is enlarged, moving the unselected element to the back. Flipping through destinations on the nav bar thus feels a bit like browsing through a carousel. We decided to utilize this effect as it adds a playful note to switching sections, which we hoped would nudge our users into navigating to different areas in the app more often. Further, the animation plays a major part in our next point…


# USAGE

compile the library in your build.gralde

```gradle

allprojects {
    repositories {
        jcenter()
        maven { url "https://jitpack.io" }
    }
}


dependencies {
  compile 'com.github.githubwing:ByeBurgerNavigationView:v1.0'
  compile 'com.android.support:design:25.0.0'
  }
```

layout xml

```xml
<android.support.design.widget.CoordinatorLayout>
  <Viewpager />
  <com.wingsofts.byeburgernavigationview.ByeBurgerNavigationView 
      <--! important --> 
        app:menu="@menu/bottom"
        app:layout_behavior="@string/bye_burger_behavior"  
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        app:itemIconTint="@color/colorPrimary"
        app:itemTextColor="@color/colorPrimary"
   />
      
</android.support.design.widget.CoordinatorLayout>

```


menu xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<menu xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto">
  <item
      android:icon="@drawable/ic_home_black_24dp"
      android:enabled="true"
      app:showAsAction="ifRoom"
      android:title="home"/>

  <item
      android:icon="@drawable/ic_search_black_24dp"
      android:enabled="true"
      app:showAsAction="ifRoom"
      android:title="search"/>
  <item
      android:icon="@drawable/ic_account_circle_black_24dp"
      android:enabled="true"
      app:showAsAction="ifRoom"
      android:title="me"
      />
  <item
      android:icon="@drawable/ic_settings_black_24dp"
      android:enabled="true"
      app:showAsAction="ifRoom"
      android:title="setting"
      />
</menu>
```

addOnSelectedListener
```java
mByeBurger.setOnNavigationItemSelectedListener(
        new BottomNavigationView.OnNavigationItemSelectedListener() {
          @Override public boolean onNavigationItemSelected(@NonNull MenuItem item) {
            if(item.getTitle().equals("home")){
              mViewPager.setCurrentItem(0);
            }else if(item.getTitle().equals("search")){
              mViewPager.setCurrentItem(1);
            }else if(item.getTitle().equals("me")){
              mViewPager.setCurrentItem(2);
            }else if(item.getTitle().equals("setting")){
              mViewPager.setCurrentItem(3);
            }
            return false;
          }
        });
```
# License

    Copyright 2016 androidwing1992

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at
    
        http://www.apache.org/licenses/LICENSE-2.0
    
    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.
