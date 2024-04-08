# workshop  

## AIM:

Develop an android application pass the data between the activities using Intent.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:
Step 1: Create a New Project in Android Studio

Step 2: Working with the activity_main.xml File

Step 3: Working with the MainActivity File

Step 4: Working with the activity_main2.xml File

Step 5: Working with the MainActivity2 File


## PROGRAM:
```
/*
Workshop on developing an android application to pass the data between the activities using Intent .
Developed by: Vikash.A.R
Registeration Number : 212222040179
*/
```
### In activity_main.xml
```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F67EA7"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/textView2"
        android:layout_width="88dp"
        android:layout_height="34dp"
        android:text="Name :"
        android:textSize="20sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toTopOf="@+id/textView"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.133"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.959" />

    <TextView
        android:id="@+id/textView"
        android:layout_width="79dp"
        android:layout_height="37dp"
        android:layout_marginBottom="20dp"
        android:text="Age :"
        android:textSize="20sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toTopOf="@+id/textView3"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.156"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/textView3"
        android:layout_width="99dp"
        android:layout_height="34dp"
        android:layout_marginBottom="36dp"
        android:text="Email Id :"
        android:textSize="20sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toTopOf="@+id/textView4"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.144"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/textView4"
        android:layout_width="245dp"
        android:layout_height="41dp"
        android:layout_marginBottom="16dp"
        android:text="Contact Number :"
        android:textSize="20sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toTopOf="@+id/Phone"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.259"
        app:layout_constraintStart_toStartOf="parent" />

    <EditText
        android:id="@+id/EmailAddress"
        android:layout_width="192dp"
        android:layout_height="48dp"
        android:layout_marginBottom="28dp"
        android:ems="10"
        android:hint="Enter your mail ID"
        android:inputType="textEmailAddress"
        app:layout_constraintBottom_toTopOf="@+id/textView4"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.3"
        app:layout_constraintStart_toEndOf="@+id/textView" />

    <EditText
        android:id="@+id/age"
        android:layout_width="191dp"
        android:layout_height="46dp"
        android:layout_marginBottom="8dp"
        android:ems="10"
        android:hint="Enter your Age"
        android:inputType="text"
        app:layout_constraintBottom_toTopOf="@+id/EmailAddress"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.3"
        app:layout_constraintStart_toEndOf="@+id/textView2" />

    <EditText
        android:id="@+id/nameTextView"
        android:layout_width="187dp"
        android:layout_height="53dp"
        android:layout_marginTop="228dp"
        android:ems="10"
        android:hint="Enter your name"
        android:inputType="text"
        app:layout_constraintBottom_toTopOf="@+id/age"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.29"
        app:layout_constraintStart_toEndOf="@+id/textView2"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="1.0" />

    <EditText
        android:id="@+id/Phone"
        android:layout_width="227dp"
        android:layout_height="44dp"
        android:layout_marginBottom="76dp"
        android:ems="10"
        android:hint="Enter phone number"
        android:inputType="phone"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.233"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/textView5"
        android:layout_width="316dp"
        android:layout_height="60dp"
        android:shadowColor="#E5D337"
        android:text="PERSONAL DETAILS"
        android:textAlignment="center"
        android:textColor="#A74AB6"
        android:textSize="34sp"
        android:textStyle="bold|italic"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.145" />

    <Button
        android:id="@+id/button"
        android:layout_width="155dp"
        android:layout_height="54dp"
        android:layout_marginBottom="96dp"
        android:backgroundTint="#D29CDC"
        android:text="SUBMIT"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.511"
        app:layout_constraintStart_toStartOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```
### In MainActivity.java

```
package com.example.workshop;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity extends AppCompatActivity {
    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        Button nextActivityButton = findViewById(R.id.button);
        nextActivityButton.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                EditText nameEditText = findViewById(R.id.nameTextView);
                EditText ageEditText = findViewById(R.id.age);
                EditText emailEditText = findViewById(R.id.EmailAddress);
                EditText contactNumberEditText = findViewById(R.id.Phone);

                String name = nameEditText.getText().toString();
                String age = ageEditText.getText().toString();
                String email = emailEditText.getText().toString();
                String contactNumber = contactNumberEditText.getText().toString();

                Intent intent = new Intent(MainActivity.this, MainActivity2.class);
                intent.putExtra("name", name);
                intent.putExtra("age", age);
                intent.putExtra("email", email);
                intent.putExtra("contactNumber", contactNumber);
                startActivity(intent);
            }
        });
    }
}
```

### In activity_main2.xml

```
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:background="#F67EA7"
    tools:context=".MainActivity2">

    <TextView
        android:id="@+id/textView5"
        android:layout_width="338dp"
        android:layout_height="66dp"
        android:text="PERSONAL DETAILS"
        android:textAlignment="center"
        android:textColor="#A74AB6"
        android:textSize="34sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.497"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.145" />

    <TextView
        android:id="@+id/nameTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="Name :"
        android:textSize="20sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/ageTextView"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.129"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        app:layout_constraintVertical_bias="0.877" />

    <TextView
        android:id="@+id/ageTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="48dp"
        android:text="Age :"
        android:textSize="20sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/emailTextView"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.123"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/emailTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="40dp"
        android:text="Email_ID :"
        android:textSize="20sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/contactNumberTextView"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.139"
        app:layout_constraintStart_toStartOf="parent" />

    <TextView
        android:id="@+id/contactNumberTextView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:layout_marginBottom="80dp"
        android:text="Contact_no :"
        android:textSize="20sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toTopOf="@+id/button"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintHorizontal_bias="0.151"
        app:layout_constraintStart_toStartOf="parent" />

    <Button
        android:id="@+id/button"
        android:layout_width="143dp"
        android:layout_height="49dp"
        android:layout_marginBottom="124dp"
        android:backgroundTint="#D29CDC"
        android:onClick="back"
        android:text="BACK"
        android:textSize="20sp"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent" />

</androidx.constraintlayout.widget.ConstraintLayout>
```

### In MainActivity2.java

```
package com.example.workshop;

import androidx.appcompat.app.AppCompatActivity;

import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;

public class MainActivity2 extends AppCompatActivity {

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main2);

        Intent intent = getIntent();
        String name = intent.getStringExtra("name");
        String age = intent.getStringExtra("age");
        String email = intent.getStringExtra("email");
        String contactNumber = intent.getStringExtra("contactNumber");

        TextView nameTextView = findViewById(R.id.nameTextView);
        TextView ageTextView = findViewById(R.id.ageTextView);
        TextView emailTextView = findViewById(R.id.emailTextView);
        TextView contactNumberTextView = findViewById(R.id.contactNumberTextView);

        nameTextView.setText("Name: " + name);
        ageTextView.setText("Age: " + age);
        emailTextView.setText("Email_ID: " + email);
        contactNumberTextView.setText("Contact_no: " + contactNumber);
    };
    public void back(View view) {
        Intent i = new Intent(getApplicationContext(), MainActivity.class);
        startActivity(i);
    }
}
```
## OUTPUT:

![WhatsApp Image 2024-04-08 at 09 39 07_74a004e1](https://github.com/VIKASHAR/MAD_WORKSHOP_1/assets/119405655/1919cbc8-8800-4a79-98c7-5b0d71908d6b)

![WhatsApp Image 2024-04-08 at 09 39 07_11165477](https://github.com/VIKASHAR/MAD_WORKSHOP_1/assets/119405655/5cb09580-9146-4173-9e86-d34c023f6b41)


## RESULT
Thus a Simple Android Application to pass the data between the activities using Intent in Android Studio is developed and executed successfully.
