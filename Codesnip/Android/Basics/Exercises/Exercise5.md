#### Exercise 5 Relative Layout and Linear Layout

---

######Exercise 5 Relative Layout + Linear Layout Output with code

![Exercise 5 Relative Layout + Linear Layout](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise5_LinearAndRelativeLayouts.png?raw=true)

```xml
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="vertical"
    tools:context="com.sagarrkothari.sampleapp.MainActivity">

    <RelativeLayout
        android:layout_width="match_parent"
        android:layout_height="0dp"
        android:layout_weight="1">

        <LinearLayout
            android:layout_width="match_parent"
            android:layout_height="wrap_content"
            android:padding="20dp"
            android:layout_gravity="center"
            android:layout_centerVertical="true"
            android:orientation="vertical">

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:id="@+id/txtWelcome"
                android:textSize="25sp"
                android:textStyle="bold"
                android:textAlignment="center"
                android:padding="10dp"
                android:text="Welcome to Chrome" />

            <ImageView
                android:layout_width="200dp"
                android:layout_height="200dp"
                android:layout_gravity="center"
                android:id="@+id/imageChrome"
                android:padding="10dp"
                android:background="@android:color/darker_gray"
                />

            <TextView
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:text="@string/by_using_this_app"
                android:textAlignment="center"
                android:padding="10dp"
                android:id="@+id/txtByUsingThisApp"
                android:textSize="16sp" />

            <RelativeLayout
                android:layout_width="match_parent"
                android:layout_height="wrap_content"
                android:orientation="horizontal"
                android:padding="20dp">

                <ImageView
                    android:id="@+id/imageCheck"
                    android:layout_width="20dp"
                    android:layout_height="20dp"
                    android:layout_centerVertical="true"
                    android:background="@android:color/darker_gray"
                    />

                <TextView
                    android:id="@+id/txtHelp"
                    android:layout_width="match_parent"
                    android:layout_height="wrap_content"
                    android:layout_gravity="center"
                    android:padding="10dp"
                    android:text="Help make Chrome better by sending usage statistics and crash reports to Google."
                    android:textSize="16sp"
                    android:layout_toRightOf="@id/imageCheck"/>

            </RelativeLayout>

        </LinearLayout>

    </RelativeLayout>

    <Button
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="@string/accept_and_continue"
        android:background="#ffffff" />

    </LinearLayout>
```