#### Exercise 4 Relative Layout and Linear Layout

---

######Exercise 4 Relative Layout + Linear Layout Output with code

![Exercise 4 Relative Layout + Linear Layout](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise4_Relative_Linear_layout_combination.png?raw=true)

```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:paddingBottom="@dimen/activity_vertical_margin"
    android:paddingLeft="@dimen/activity_horizontal_margin"
    android:paddingRight="@dimen/activity_horizontal_margin"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.sagarrkothari.sampleapp.MainActivity">

    <ImageView
        android:layout_width="100dp"
        android:layout_height="100dp"
        android:background="@android:color/darker_gray"
        android:id="@+id/imageView"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="100dp"
        android:layout_toRightOf="@id/imageView"
        android:orientation="vertical"
        android:padding="5dp">

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Sagar"
            android:id="@+id/txtSagar"
            android:layout_weight="1"
            android:textSize="22sp" />
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Rajeshbhai"
            android:layout_toRightOf="@id/imageView"
            android:layout_below="@id/txtSagar"
            android:id="@+id/txtRajeshbhai"
            android:layout_weight="1"
            android:gravity="center_vertical"
            android:textSize="22sp"/>
        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Kothari"
            android:layout_toRightOf="@id/imageView"
            android:layout_below="@id/txtRajeshbhai"
            android:layout_weight="1"
            android:id="@+id/txtKothari"
            android:gravity="bottom"
            android:textSize="22sp"/>

    </LinearLayout>

</RelativeLayout>
```