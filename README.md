# UNIT-3-W-1
# Create a To Do List application using android studio. You can use the different layout, views and controls in android.
## AIM:
To create a To Do List application using android studio. You can use the different layout, views and controls in android.

## EQUIPMENTS REQUIRED:
Android Studio(Min.required Artic Fox)

## ALGORITHM:
Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as studentinfo and click Next.

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout in activity_main.xml.

Step 6: Accept student name and register number,cgpa from the end user and the display information give in MainActivity file.

Step 7: Save and run the application.

## PROGRAM:
### Activity_Main.xml
```python
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="@drawable/blue"
    tools:context=".MainActivity">


    <ListView
        android:id="@+id/simplelistview"
        android:layout_width="0dp"
        android:layout_height="0dp"
        android:layout_marginStart="32dp"
        android:layout_marginTop="32dp"
        android:layout_marginEnd="32dp"
        android:layout_marginBottom="32dp"
        android:textFilterEnabled="false"
        android:divider="#f00"
        android:dividerHeight="2dp"
        android:listSelector="#0f0"
    app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="1.0" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
### MainActivity.java
```python
package com.example.unit3_ws_1;

import android.content.Context;

import android.view.LayoutInflater;
import android.view.View;
import android.view.ViewGroup;
import android.widget.BaseAdapter;
import android.widget.ImageView;
import android.widget.TextView;

public class CustomAdapter extends BaseAdapter {
    Context context;
    String countryList[];
    int flags[];
    LayoutInflater inflater;
    public CustomAdapter(Context applicationContext, String[] countryList, int[] flags) {
        this.context = context;
        this.countryList = countryList;
        this.flags = flags;
        inflater = (LayoutInflater.from(applicationContext));
    }

    @Override
    public int getCount() {
        return countryList.length;
    }

    @Override
    public Object getItem(int i) {
        return null;
    }

    @Override
    public long getItemId(int i) {
        return 0;
    }

    @Override
    public View getView(int i, View view, ViewGroup viewGroup) {
        view = inflater.inflate(R.layout.activity_listview, null);
        TextView country = (TextView) view.findViewById(R.id.textView);
        ImageView icon = (ImageView) view.findViewById(R.id.icon);
        country.setText(countryList[i]);
        icon.setImageResource(flags[i]);
        return view;
    }
}
``` 
### activity_listview_xml:
```python
<?xml version="1.0" encoding="utf-8"?>
<LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:orientation="horizontal">

    <ImageView
        android:id="@+id/icon"
        android:layout_width="50dp"
        android:layout_height="50dp"
        android:src="@drawable/ic_action_name" />

    <TextView
        android:id="@+id/textView2"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        android:layout_weight="1"
        android:text="TextView"
        android:textColor="#9C27B0"
        android:textColorHighlight="#4CAF50"
        android:textColorHint="#03A9F4"
        android:textColorLink="#E91E63"
        android:textSize="24sp" />
</LinearLayout>
```
### CustomAdaptor.Java
```python
package com.example.unit3_ws_1;

import androidx.appcompat.app.AppCompatActivity;

import android.os.Bundle;


import android.widget.ListView;

public class MainActivity extends AppCompatActivity {
    ListView simpleList;
    String countryList[] = {"RDJ", "Scarlett Johansson", "Chris Hemsworth", "Tom Holland", "Chris Evans", "Elizabeth Olsen"};
    int flags[] = {R.drawable.rdj, R.drawable.scar, R.drawable.thor, R.drawable.tom, R.drawable.chrisevans, R.drawable.eli};


    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        simpleList = (ListView) findViewById(R.id.simpleListView);
        CustomAdapter customAdapter = new CustomAdapter(getApplicationContext(), countryList, flags);
        simpleList.setAdapter(customAdapter);

    }
}
```
## OUTPUT
![WhatsApp Image 2022-06-06 at 9 35 28 AM](https://user-images.githubusercontent.com/75236145/172093419-f702cca4-7eb8-493a-b6fb-fd747f0ae862.jpeg)

## RESULT
Thus,we created a To Do List application using android studio.
