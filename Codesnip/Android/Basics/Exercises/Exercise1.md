#### Exercise1 Linear Layout With Weight

---

####### Exercise output

![Exercise1 Linear Layout With Weight](https://github.com/sag333ar/sag333ar.github.io/blob/master/Cdesnip/Android/Basics/Exercises/Exercise1_LinearLayoutWithWeight.png?raw=true)

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.sagarrkothari.sampleapp.MainActivity">

    <TextView
        android:layout_height="wrap_content"
        android:layout_width="match_parent"
        android:text="Hey! Happy Birthday"
        android:textStyle="bold|italic"
        android:textColor="@android:color/holo_green_dark"
        android:textSize="30sp"
        />

    <TextView
        android:layout_height="0dp"
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:text="Guest List"
        android:textStyle="bold"
        android:textColor="@android:color/holo_orange_dark"
        android:textSize="25sp"
        />

    <TextView
        android:layout_height="0dp"
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:text="Sagar R. Kothari"
        android:textColor="@android:color/secondary_text_dark_nodisable"
        android:textSize="20sp"
        />

    <TextView
        android:layout_height="0dp"
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:text="Sameer Shah"
        android:textColor="@android:color/secondary_text_dark_nodisable"
        android:textSize="20sp"
        />

    <TextView
        android:layout_height="0dp"
        android:layout_weight="1"
        android:layout_width="match_parent"
        android:text="Sima Kothari"
        android:textColor="@android:color/secondary_text_dark_nodisable"
        android:textSize="20sp"
        />

</LinearLayout>
```