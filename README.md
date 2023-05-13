7.AIM: Create an application that uses a text file to store user names and passwords (tab separated fields and one record per line). When the user submits a login name and password through a screen, the details should be verified with the text file data and if they match, show a dialog saying that login is successful. Otherwise, show the dialog with Login Failed message

XML CODE:

activity_main.xml

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    tools:context=".MainActivity">

    <TextView android:layout_width="252dp"
        android:layout_height="75dp"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true"
        android:layout_marginEnd="78dp"
        android:layout_marginBottom="642dp"
        android:background="#99FF33"
        android:fontFamily="sans-serif"
        android:text="Login Activity"
        android:textAlignment="center"
        android:textColor="#FF4633"
        android:textSize="30sp"
        android:textStyle="bold"
        app:layout_constraintBottom_toBottomOf="parent"
        app:layout_constraintEnd_toEndOf="parent"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"/>
    <EditText android:id="@+id/uname"
        android:layout_width="270dp"
        android:layout_height="69dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true" 
        android:layout_marginStart="77dp" 
        android:layout_marginEnd="64dp" 
        android:layout_marginBottom="459dp" 
        android:background="#33FFE9" 
        android:hint="Enter Username" 
        android:textAlignment="center" 
        android:textColor="#FF8633" 
        android:textSize="25sp"/>
    <EditText android:id="@+id/paswd" 
        android:layout_width="270dp" 
        android:layout_height="69dp"
        android:layout_alignParentStart="true"
        android:layout_alignParentTop="true" 
        android:layout_alignParentEnd="true" 
        android:layout_alignParentBottom="true" 
        android:layout_marginStart="77dp" 
        android:layout_marginTop="314dp" 
        android:layout_marginEnd="64dp"
        android:layout_marginBottom="348dp" 
        android:background="#33FFE9"
        android:hint="Enter Your Password" 
        android:textAlignment="center" 
        android:textColor="#FF8633"
        android:textSize="25sp" 
        android:inputType="textPassword"/>
    
    <Button
        android:id="@+id/login" 
        android:layout_width="188dp" 
        android:layout_height="64dp" 
        android:layout_alignParentStart="true" 
        android:layout_alignParentTop="true"
        android:layout_alignParentEnd="true"
        android:layout_alignParentBottom="true" 
        android:layout_marginStart="119dp" 
        android:layout_marginTop="476dp"
        android:layout_marginEnd="102dp" 
        android:layout_marginBottom="191dp"
        android:text="Submit" 
        android:textSize="25sp"/>
</RelativeLayout>

JAVA CODE:

MainActivity.java

package com.example.program7;
import androidx.appcompat.app.AppCompatActivity;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {
    EditText euname,epass;
    Button bsubmit;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        euname = (EditText) findViewById(R.id.uname);
        epass = (EditText) findViewById(R.id.paswd);
        bsubmit = (Button) findViewById(R.id.login);

        bsubmit.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View view) {

                if(euname.getText().toString().equals("xyz") && epass.getText().toString().equals("xyz@123"))
                {
                    Toast.makeText(MainActivity.this,"Login Succesful",Toast.LENGTH_LONG).show();
                }
                else
                    Toast.makeText(MainActivity.this,"Login Failed",Toast.LENGTH_SHORT).show();
            }
     });
    }
}
