# Ex.No:9 Develop a simple calculator using android studio

Date : 11.05.23

### AIM:

To develop a program to develop a simple calculator in Android Studio.

### EQUIPMENTS REQUIRED:

Android Studio(Latest Version).

### ALGORITHM:

Step 1: Open Android Stdio and then click on File -> New -> New project.

Step 2: Then type the Application name as calculator and click Next. 

Step 3: Then select the Minimum SDK as shown below and click Next.

Step 4: Then select the Empty Activity and click Next. Finally click Finish.

Step 5: Design layout using UI components in activity_main.xml.

Step 6: Display the calculator operation in MainActivity file.

Step 7: Save and run the application.

### PROGRAM:

Program to print the text calculator operation

Developed by:Sreevarsha.D

Registeration Number : 212221040159

activity_main.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/txt2"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:autofillHints=""
        android:ems="10"
        android:hint="@string/second_number"
        android:inputType="numberDecimal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.317"
        tools:ignore="SpeakableTextPresentCheck,TouchTargetSizeCheck" />

    <EditText
        android:id="@+id/txt1"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:autofillHints=""
        android:ems="10"
        android:hint="@string/first_number"
        android:inputType="numberDecimal"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.221"
        tools:ignore="TouchTargetSizeCheck,SpeakableTextPresentCheck" />

    <TextView
        android:id="@+id/result"
        android:layout_width="406dp"
        android:layout_height="56dp"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="1.0"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.456" />

    <Button
        android:id="@+id/btnsubs"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="@string/subtract"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.359"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.842" />

    <Button
        android:id="@+id/btndiv"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="@string/divide"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.981"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.842" />

    <Button
        android:id="@+id/btnadd"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="@string/add"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.048"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.842" />

    <Button
        android:id="@+id/btnmult"
        android:layout_width="80dp"
        android:layout_height="50dp"
        android:text="@string/multiply"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.673"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.842" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:fontFamily="sans-serif-medium"
        android:text="@string/simple_calculator"
        android:textColor="@color/purple_500"
        android:textSize="24sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.498"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.073" />

</androidx.constraintlayout.widget.ConstraintLayout>

```

MainActivity.java

```
package com.example.simplecalculator;

import androidx.appcompat.app.AppCompatActivity;

import android.annotation.SuppressLint;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;
public class MainActivity extends AppCompatActivity {
    Button btnadd,btnsubs,btnmult,btndiv;
    EditText txt1,txt2;
    TextView result;
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        btnadd=findViewById(R.id.btnadd);
        btnsubs=findViewById(R.id.btnsubs);
        btndiv=findViewById(R.id.btndiv);
        btnmult=findViewById(R.id.btnmult);

        txt1=findViewById(R.id.txt1);
        txt2=findViewById(R.id.txt2);

        result=findViewById(R.id.result);

        btnadd.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }

                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a + b; // Using Third Variable To Store Output Value
                    result.setText("The Addition Result Is " + c);

                }

            }
        });

        btnsubs.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }

                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a - b; // Using Third Variable To Store Output Value
                    result.setText("The Subtraction Result Is " + c);

                }
            }
        });
        btnmult.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }

                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a*b; // Using Third Variable To Store Output Value
                    result.setText("The Multiplication Result Is " + c);

                }
            }
        });
        btndiv.setOnClickListener(new View.OnClickListener() {
            @SuppressLint("SetTextI18n")
            @Override
            public void onClick(View view) {
                // Checking Input First Is Blank Or Not
                if (txt1.getText().toString().equals("")) {
                    // Showing Toast (Message)
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                } else if (txt2.getText().toString().equals("")) {
                    Toast.makeText(MainActivity.this, "Please Enter Number", Toast.LENGTH_SHORT).show();
                }

                // Both Inputs Are Not Blank , Starting Calculation
                else {
                    float a, b, c;
                    a = Float.parseFloat(txt1.getText().toString());
                    b = Float.parseFloat(txt2.getText().toString());
                    c = a/b; // Using Third Variable To Store Output Value
                    result.setText("The Division Result Is " + c);

                }
            }
        });
    }
}
```
### OUTPUT:

![](https://github.com/sreevarshad/EXP-9-MAD/blob/main/mmm%209.png)


<img src="https://github.com/KATHIR1611/EXP-9-MAD/blob/main/ab%201.jpg" width=300 height=400> <img src="https://github.com/KATHIR1611/EXP-9-MAD/blob/main/ab%202.jpg" width=300 height=400>

<img src="https://github.com/KATHIR1611/EXP-9-MAD/blob/main/ab%203.jpg" width=300 height=400> <img src="https://github.com/KATHIR1611/EXP-9-MAD/blob/main/ab%204.jpg" width=300 height=400>



### RESULT:
Thus a Simple Android Application develop a program to create simple calculator in Android Studio is developed and executed successfully.
