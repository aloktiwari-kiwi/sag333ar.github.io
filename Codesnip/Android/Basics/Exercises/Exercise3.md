#### Exercise 3 Relative Layout

---

######Exercise 3 Relative Layout

![Exercise 3 Relative Layout](https://github.com/sag333ar/sag333ar.github.io/blob/master/Codesnip/Android/Basics/Exercises/Exercise3_RelativeLayout.png?raw=true)

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

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Lyla"
        android:layout_alignParentBottom="true"
        android:layout_alignParentLeft="true"
        android:textSize="30sp"
        android:id="@+id/txtLyla"
        android:textColor="@android:color/white"
        android:background="@android:color/black"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Jennie"
        android:layout_alignParentBottom="true"
        android:layout_alignParentRight="true"
        android:textSize="30sp"
        android:id="@+id/txtJennie"
        android:textColor="@android:color/white"
        android:background="@android:color/black"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Ben"
        android:layout_alignParentTop="true"
        android:layout_centerHorizontal="true"
        android:textSize="30sp"
        android:textColor="@android:color/white"
        android:background="@android:color/darker_gray"
        android:id="@+id/txtBen"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Kunal"
        android:textSize="30sp"
        android:textColor="@android:color/white"
        android:background="@android:color/black"
        android:layout_toLeftOf="@id/txtBen"
        android:id="@+id/txtKunal"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Kagure"
        android:textSize="30sp"
        android:textColor="@android:color/white"
        android:background="@android:color/black"
        android:layout_toRightOf="@id/txtBen"
        android:id="@+id/txtKagure"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Natalie"
        android:textSize="30sp"
        android:textColor="@android:color/white"
        android:background="@android:color/darker_gray"
        android:layout_above="@id/txtLyla"
        android:id="@+id/txtNatalie"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Omoju"
        android:textSize="30sp"
        android:textColor="@android:color/white"
        android:background="@android:color/darker_gray"
        android:layout_above="@id/txtJennie"
        android:layout_alignRight="@id/txtJennie"
        android:id="@+id/txtOmoju"
        />

    <TextView
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="SagarR"
        android:textSize="30sp"
        android:textColor="@android:color/white"
        android:background="@android:color/darker_gray"
        android:layout_toRightOf="@id/txtLyla"
        android:layout_alignParentBottom="true"
        android:id="@+id/txtSagar"
        />

    </RelativeLayout>
```