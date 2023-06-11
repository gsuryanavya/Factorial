# Ex.No:4 To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## AIM:

To create a two screens , first screen will take one number input from user. After click on Factorial button, second screen will open and it should display factorial of the same number using Explicit Intents.


## EQUIPMENTS REQUIRED:

Latest Version Android Studio

## ALGORITHM:



## PROGRAM:
```
/*
Program to print the text “ExplicitIntent”.
Developed by:Golla Navya
Registeration Number :212221040048
*/
```
## activity_main.xml:
```
activity_main.xml:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
     xmlns:app="http://schemas.android.com/apk/res-auto"
      xmlns:tools="http://schemas.android.com/tools"
      android:layout_width="match_parent"
      android:layout_height="match_parent"
      tools:context=".MainActivity">
 <EditText
          android:id="@+id/numberEditText1"
          android:layout_width="wrap_content"
          android:layout_height="wrap_content"
          android:layout_marginTop="172dp"
          android:ems="10"
          android:inputType="textPersonName"
          android:text=""
          app:layout_constraintEnd_toEndOf="parent"
          app:layout_constraintHorizontal_bias="0.497"
          app:layout_constraintStart_toStartOf="parent"
          app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
 <Button
         android:id="@+id/factorialButton"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_marginTop="340dp"
         android:text="Button"
         app:layout_constraintEnd_toEndOf="parent"
         app:layout_constraintHorizontal_bias="0.498"
         app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
 
```
## activity_main2.xml:
```
activity_main2.xml:
<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout
xmlns:android="http://schemas.android.com/apk/res/android"
         xmlns:app="http://schemas.android.com/apk/res-auto"
         xmlns:tools="http://schemas.android.com/tools"
         android:layout_width="match_parent"
         android:layout_height="match_parent"
         tools:context=".MainActivity">
 <EditText
                 android:id="@+id/numberEditText1"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_marginTop="172dp"
         android:ems="10"
         android:inputType="textPersonName"
         android:text=""
         app:layout_constraintEnd_toEndOf="parent"
         app:layout_constraintHorizontal_bias="0.497"
         app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
 <Button
         android:id="@+id/factorialButton"
         android:layout_width="wrap_content"
         android:layout_height="wrap_content"
         android:layout_marginTop="340dp"
         android:text="Button"
         app:layout_constraintEnd_toEndOf="parent"
         app:layout_constraintHorizontal_bias="0.498"
         app:layout_constraintStart_toStartOf="parent"
         app:layout_constraintTop_toTopOf="parent" />
</androidx.constraintlayout.widget.ConstraintLayout>
```
##  MainActivity.java:
```
 MainActivity.java:
package com.example.factorialexplicit;
import static com.example.factorialexplicit.R.id.factorialButton;
import static com.example.factorialexplicit.R.id.numberEditText1;
import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
public class MainActivity extends AppCompatActivity {
 private EditText numberEditText;
 private Button factorialButton;
 @Override
       protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        numberEditText = findViewById(R.id.numberEditText1);
               factorialButton = findViewById(R.id.factorialButton);
        factorialButton.setOnClickListener(new View.OnClickListener() {
 @Override
        public void onClick(View v) {
        int number =
       Integer.parseInt(numberEditText.getText().toString());
               Intent intent = new Intent(MainActivity.this,
MainActivity2.class);
 intent.putExtra("number", number);
 startActivity(intent);
        }
     });
   }
}
```
## MainActivity2.java:
```
MainActivity2.java:
package com.example.factorialexplicit;
import static com.example.factorialexplicit.R.id.factorialTextView;
import androidx.appcompat.app.AppCompatActivity;
import android.annotation.SuppressLint;
import android.content.Intent;
import android.os.Bundle;
import android.widget.TextView;
public class MainActivity2 extends AppCompatActivity 
private TextView factorialTextView;
 @SuppressLint("MissingInflatedId")
 @Override
 protected void onCreate(Bundle savedInstanceState) {
          super.onCreate(savedInstanceState);
         setContentView(R.layout.activity_main);
         factorialTextView = findViewById(R.id.factorialButton);
         Intent intent = getIntent();
                 int number = intent.getIntExtra("number", 0);
         long factorial = calculateFactorial(number);
         factorialTextView.setText("Factorial of " + number + " is " +
factorial);
 }
         private long calculateFactorial(int number) {
         long factorial = 1;
 for (int i = 1; i <= number; i++) {
 factorial *= i;
         }
 return factorial;
      }
}

```

## OUTPUT
![WhatsApp Image 2023-06-11 at 14 14 46](https://github.com/gsuryanavya/Factorial/assets/133086963/6ca550a1-07ff-4fee-9483-2e43472a62a2)
![WhatsApp Image 2023-06-11 at 14 14 47](https://github.com/gsuryanavya/Factorial/assets/133086963/2899d966-b49e-4c79-8e4e-6760bf596220)




## RESULT
Thus a Simple Android Application create a Explicit Intents using Android Studio is developed and executed successfully.

