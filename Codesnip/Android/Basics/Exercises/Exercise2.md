#### Exercise2 Linear Layout With Weight

---

######Exercise output

![Exercise2 Linear Layout With Weight](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise2_LinearLayoutWithWeight.png?raw=true)

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.sagarrkothari.sampleapp.MainActivity">

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="From"/>

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="To"/>

    <EditText
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Subject"/>

    <EditText
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1"
        android:gravity="top"
        android:hint="Compose Email"/>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:orientation="horizontal">

        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Call"
            android:textAllCaps="false"/>
        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Save"
            android:textAllCaps="false"/>
        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_weight="1"
            android:text="Website"
            android:textAllCaps="false"/>

    </LinearLayout>

    <LinearLayout
        android:layout_width="match_parent"
        android:layout_height="wrap_content">

        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="right"
            android:layout_weight="1"
            android:text="Cancel"
            android:textAllCaps="false" />

        <Button
            android:layout_width="0dp"
            android:layout_height="wrap_content"
            android:layout_gravity="right"
            android:layout_weight="1"
            android:text="@string/send"
            android:textAllCaps="false" />

    </LinearLayout>

    </LinearLayout>
```