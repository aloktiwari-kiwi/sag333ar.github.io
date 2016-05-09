#### Android Common attributes for layouts with explanation & sample values

---

######1. `android:layout_width`

**Description:** To specify the width of the control

**Values:**

* `wrap_content` : fit to the content size
* `match_parent` : fit to the parent container

***Sample for attributes***

```
<TextView
	android:layout_width="wrap_content"
/>
```

```
<TextView
	android:layout_width="match_parent"
/>
```

---

######2. `android:layout_height`

**Description:** To specify the height of the control

**Values:**

* `wrap_content` : fit to the content size
* `match_parent` : fit to the parent container

***Sample for attributes***

```
<TextView
	android:layout_height="wrap_content"
/>
```

```
<TextView
	android:layout_height="match_parent"
/>
```

---

######3. Align Android control to parent container

1. `android:layout_alignParentTop="true"` attribute is used to align your control to the ***TOP*** of parent container.
2. `android:layout_alignParentRight="true"` attribute is used to align your control to the ***RIGHT*** of parent container.
3. `android:layout_alignParentEnd="true"` attribute is used to align your control to the ***BOTTOM*** of parent container.
4. `android:layout_alignParentLeft="true"`  attribute is used to align your control to the ***LEFT*** of parent container.

---

######4. Apply MARGIN Android control

* `android:layout_margin="20dp"` will apply margin to all corners of Android control.
* `android:layout_marginBottom="10dp"` will apply margin to **BOTTOM** corners of Android control.
* `android:layout_marginLeft="10dp"` will apply margin to **LEFT** corners of Android control.
* `android:layout_marginRight="10dp"` will apply margin to **RIGHT** corners of Android control.
* `android:layout_marginTop="10dp"` will apply margin to **TOP** corners of Android control.

Supported by API 17 or above

* `android:layout_marginStart="10dp"` will apply margin to **Start** corners of Android control. ( I believe, Left & Top )
* `android:layout_marginEnd="10dp"` will apply margin to **End** corners of Android control. ( I believe, Right & Bottom )

######5. Apply text size

* `android:textSize="20dp"` is not recommended at all. Always use SP for fonts.
* `android:textSize="20sp"` is always recommended. Based on user's font display settings font-size will be adjusted.

Using system defined font sizes/styles

* `android:textSize="?android:textAppearanceLarge"`
* `android:textSize="?android:textAppearanceButton"`
* `android:textSize="?android:textAppearanceListItem"`
* `android:textSize="?android:textAppearanceListItemSeconday"`
* `android:textSize="?android:textAppearanceListItemSmall"`
* `android:textSize="?android:textAppearanceMedium"` etc.