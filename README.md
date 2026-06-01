# EX.NO: 5 Develop a Program to Create a Simple Addition Calculator Using Android Studio

## AIM:

To create and design an Android application that accepts two numbers from the user and displays their sum using Android Studio.

## EQUIPMENTS REQUIRED:

* Android Studio (Latest Version)
* Android SDK
* Java

## ALGORITHM:

**Step 1:** Open Android Studio and create a new project.

**Step 2:** Select **Empty Activity** and click **Next**.

**Step 3:** Enter the application name and finish creating the project.

**Step 4:** Design the user interface in `activity_main.xml` using two EditText fields, one Button, and one TextView.

**Step 5:** Initialize all UI components in `MainActivity.java`.

**Step 6:** Read the numbers entered by the user when the button is clicked.

**Step 7:** Validate the inputs and convert them into numeric values.

**Step 8:** Calculate the sum of the two numbers.

**Step 9:** Display the result in the TextView.

**Step 10:** Save and run the application.

---

## PROGRAM:

```java
/*
Program to create and design an Android application for adding two numbers using Android Studio.

Developed by: Ashwin Akash M
Register Number: 212223230024
*/
```

### MainActivity.java

```java
package com.example.workshop_1;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;
import android.widget.TextView;
import android.widget.Toast;

import androidx.activity.EdgeToEdge;
import androidx.appcompat.app.AppCompatActivity;
import androidx.core.graphics.Insets;
import androidx.core.view.ViewCompat;
import androidx.core.view.WindowInsetsCompat;

public class MainActivity extends AppCompatActivity {

    private EditText editTextNumber1;
    private EditText editTextNumber2;
    private Button buttonAdd;
    private TextView textViewResult;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        EdgeToEdge.enable(this);
        setContentView(R.layout.activity_main);

        ViewCompat.setOnApplyWindowInsetsListener(findViewById(R.id.main), (v, insets) -> {
            Insets systemBars = insets.getInsets(WindowInsetsCompat.Type.systemBars());
            v.setPadding(systemBars.left, systemBars.top, systemBars.right, systemBars.bottom);
            return insets;
        });

        editTextNumber1 = findViewById(R.id.editTextNumber1);
        editTextNumber2 = findViewById(R.id.editTextNumber2);
        buttonAdd = findViewById(R.id.buttonAdd);
        textViewResult = findViewById(R.id.textViewResult);

        buttonAdd.setOnClickListener(v -> calculateSum());
    }

    private void calculateSum() {
        String str1 = editTextNumber1.getText().toString().trim();
        String str2 = editTextNumber2.getText().toString().trim();

        if (str1.isEmpty() || str2.isEmpty()) {
            Toast.makeText(this, "Please enter both numbers", Toast.LENGTH_SHORT).show();
            return;
        }

        try {
            double num1 = Double.parseDouble(str1);
            double num2 = Double.parseDouble(str2);
            double sum = num1 + num2;

            textViewResult.setText("Result: " + sum);

        } catch (NumberFormatException e) {
            Toast.makeText(this, "Invalid Input", Toast.LENGTH_SHORT).show();
        }
    }
}
```

---

### activity_main.xml

```xml
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    android:id="@+id/main"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp">

    <EditText
        android:id="@+id/editTextNumber1"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:hint="Enter First Number"
        android:inputType="numberDecimal"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <EditText
        android:id="@+id/editTextNumber2"
        android:layout_width="0dp"
        android:layout_height="wrap_content"
        android:layout_marginTop="16dp"
        android:hint="Enter Second Number"
        android:inputType="numberDecimal"
        app:layout_constraintTop_toBottomOf="@id/editTextNumber1"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <Button
        android:id="@+id/buttonAdd"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="ADD"
        android:layout_marginTop="20dp"
        app:layout_constraintTop_toBottomOf="@id/editTextNumber2"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

    <TextView
        android:id="@+id/textViewResult"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Result"
        android:textSize="18sp"
        android:textStyle="bold"
        android:layout_marginTop="20dp"
        app:layout_constraintTop_toBottomOf="@id/buttonAdd"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintEnd_toEndOf="parent"/>

</androidx.constraintlayout.widget.ConstraintLayout>
```

---

## OUTPUT
<img width="1917" height="1079" alt="image" src="https://github.com/user-attachments/assets/c10e181f-fb1a-4c69-bb67-8c6a50e9f312" />


## RESULT

Thus, an Android application for adding two numbers was developed and executed successfully using Android Studio.
