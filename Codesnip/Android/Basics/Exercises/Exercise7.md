#### Exercise 7 Skype Login

---

######Exercise 7 Skype Login for learning

![Exercise 7 Skype Login for learning](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise7_Skype_login_page.png?raw=true)

Also, resources used are as follows.

* ![skype_logo.png](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/skype_logo.png.png?raw=true)
* ![custom_button.xml](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/custom_button.xml?raw=true)


```xml
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#00aff0"
    android:paddingTop="@dimen/activity_vertical_margin"
    tools:context="com.sagarrkothari.sampleapp.MainActivity">

    <ImageView
        android:id="@+id/imageViewLogo"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:background="@drawable/skype_logo" />

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_below="@id/imageViewLogo"
        android:orientation="vertical">

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginLeft="25dp"
            android:layout_marginRight="25dp"
            android:background="@android:color/white"
            android:hint="Skype name"
            android:padding="8dp"
            android:textSize="20sp" />

        <EditText
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginLeft="25dp"
            android:layout_marginRight="25dp"
            android:layout_marginTop="10dp"
            android:background="@android:color/white"
            android:hint="Password"
            android:padding="8dp"
            android:textSize="20sp" />

        <Button
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_gravity="center"
            android:layout_margin="20dp"
            android:background="@drawable/custom_button"
            android:text="Sign in"
            android:textAllCaps="false"
            android:textColor="@android:color/white"
            android:textSize="20sp" />

        <TextView
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:text="Problem signing in?"
            android:textAlignment="center"
            android:textAllCaps="false"
            android:textColor="@android:color/white"
            android:textSize="16sp" />

    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:layout_alignParentBottom="true"
        android:orientation="vertical">

        <Button
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginBottom="5dp"
            android:background="#FF0096CE"
            android:textSize="16sp"
            android:text="Sign in with a Microsoft Account"
            android:textAllCaps="false"
            android:textColor="@android:color/white"
            android:textAlignment="textStart"
            android:padding="15dp"/>

        <Button
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:layout_marginBottom="5dp"
            android:background="#FF0096CE"
            android:textSize="16sp"
            android:text="Create a Skype Account"
            android:textAllCaps="false"
            android:textColor="@android:color/white"
            android:textAlignment="textStart"
            android:padding="15dp"/>

    </LinearLayout>

</RelativeLayout>
```