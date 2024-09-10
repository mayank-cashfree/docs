---
title: "2. Add Cashfree CardView in your layout XML file"
slug: "2-add-cashfree-cardview-in-your-layout-xml-file"
excerpt: ""
hidden: true
createdAt: "Fri Nov 04 2022 07:51:54 GMT+0000 (Coordinated Universal Time)"
updatedAt: "Tue Dec 05 2023 13:45:29 GMT+0000 (Coordinated Universal Time)"
---
Add  CFCardView onto the layout where the developer wants to use it . 

```xml
<androidx.constraintlayout.widget.ConstraintLayout
   android:id="@+id/container"
   android:layout_width="match_parent"
   android:layout_height="wrap_content"
   android:layout_marginHorizontal="16dp"
   app:layout_constraintStart_toStartOf="parent"
   app:layout_constraintTop_toTopOf="parent">

   <com.cashfree.prepaidcard.card.CFCardView
       android:id="@+id/cf_card_view"
       android:layout_width="match_parent"
       android:layout_height="wrap_content"
       android:layout_marginTop="40dp"
       app:cardBackground="@drawable/ic_launcher_background"
       app:loading="true"
       app:layout_constraintEnd_toEndOf="parent"
       app:layout_constraintStart_toStartOf="parent"
       app:layout_constraintTop_toTopOf="parent" />

   <androidx.appcompat.widget.AppCompatButton
       android:id="@+id/card_reset_pin"
       android:layout_width="0dp"
       android:layout_height="wrap_content"
       android:layout_marginTop="20dp"
       android:text="Reset Pin"
       app:layout_constraintStart_toStartOf="parent"
       app:layout_constraintTop_toBottomOf="@id/cf_card_view" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

1. By-default progress bar loading will be enabled on card. If developers don’t want loading, pass **false** in xml.

2. Developers can set card backgrounds with **cardBackground** params in xml. If they don’t provide a card background, then the default card background will be visible.

3. Developers can also set card backgrounds dynamically with the 

```kotlin
setCardBackground(@DrawableRes drawable: Int? = null)
```
