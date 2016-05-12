#### Exercise 6 Relative Layout and Linear Layout

---

######Exercise 6 Relative Layout + Linear Layout Output with code

![Exercise 6 Relative Layout + Linear Layout](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise6_LinearAndRelativeLayouts.png?raw=true)
![Exercise 6 Relative Layout + Linear Layout 2](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise6_LinearAndRelativeLayouts2.png?raw=true)

Also, resources used are as follows.

* ![applications_icon](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/applications_icon.jpg?raw=true)
* ![google_logo](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/google_logo.png?raw=true)
* ![notifications_icon](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/notifications_icon.png?raw=true)
* ![profile_picture](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/profile_picture.png?raw=true)

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.sagarrkothari.sampleapp.MainActivity">

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:gravity="center_vertical|right"
        android:orientation="horizontal">

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dp"
            android:paddingRight="5dp"
            android:text="Gmail"
            android:textSize="18sp" />

        <TextView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:paddingLeft="5dp"
            android:paddingRight="5dp"
            android:text="Images"
            android:textSize="18sp" />

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/applications_icon"
            android:paddingLeft="5dp"
            android:paddingRight="5dp" />

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/notifications_icon"
            android:paddingLeft="5dp"
            android:paddingRight="5dp" />

        <ImageView
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:background="@drawable/profile_picture"
            android:paddingLeft="5dp"
            android:paddingRight="5dp" />

    </LinearLayout>

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_weight="1"
        android:gravity="center">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:gravity="center"
            android:orientation="vertical">

            <ImageView
                android:id="@+id/imageViewLogo"
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:background="@drawable/google_logo" />
            <EditText
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:hint="Enter text to search."
                android:textAlignment="center"/>

            <LinearLayout
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:orientation="horizontal">
                <Button
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:text="Google Search"/>
                <Button
                    android:layout_width="wrap_content"
                    android:layout_height="wrap_content"
                    android:text="I'm feeling lucky."/>
            </LinearLayout>
        </LinearLayout>

    </RelativeLayout>


    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="60dp">

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentTop="true"
            android:layout_alignParentLeft="true">
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Advertising"
                android:textSize="10sp"
                android:minHeight="0dp"/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Business"
                android:textSize="10sp"
                android:minHeight="0dp"/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="About"
                android:textSize="10sp"
                android:minHeight="0dp"/>
        </LinearLayout>

        <LinearLayout
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:layout_alignParentRight="true"
            android:layout_alignParentBottom="true">
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Privacy"
                android:textSize="10sp"
                android:minHeight="0dp"/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Terms"
                android:textSize="10sp"
                android:minHeight="0dp"/>
            <Button
                android:layout_width="wrap_content"
                android:layout_height="wrap_content"
                android:text="Settings"
                android:textSize="10sp"
                android:minHeight="0dp"/>
        </LinearLayout>

    </RelativeLayout>
</LinearLayout>
```