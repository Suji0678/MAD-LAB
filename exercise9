package com.example.myapplication;

import android.os.Bundle;
import android.widget.Button;
import android.widget.EditText;

import androidx.appcompat.app.AlertDialog;
import androidx.appcompat.app.AppCompatActivity;

public class MainActivity extends AppCompatActivity {

    EditText num1, num2;
    Button btnAdd, btnSub, btnMul, btnDiv;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        num1 = findViewById(R.id.num1);
        num2 = findViewById(R.id.num2);

        btnAdd = findViewById(R.id.btnAdd);
        btnSub = findViewById(R.id.btnSub);
        btnMul = findViewById(R.id.btnMul);
        btnDiv = findViewById(R.id.btnDiv);

        btnAdd.setOnClickListener(v -> calculate("+"));
        btnSub.setOnClickListener(v -> calculate("-"));
        btnMul.setOnClickListener(v -> calculate("*"));
        btnDiv.setOnClickListener(v -> calculate("/"));
    }

    private void calculate(String operator) {
        try {
            String n1 = num1.getText().toString().trim();
            String n2 = num2.getText().toString().trim();

            if (n1.isEmpty() || n2.isEmpty()) {
                showAlert("Please enter both numbers");
                return;
            }

            double number1 = Double.parseDouble(n1);
            double number2 = Double.parseDouble(n2);
            double result = 0;

            switch (operator) {
                case "+":
                    result = number1 + number2;
                    break;
                case "-":
                    result = number1 - number2;
                    break;
                case "*":
                    result = number1 * number2;
                    break;
                case "/":
                    if (number2 == 0) {
                        showAlert("Cannot divide by zero");
                        return;
                    }
                    result = number1 / number2;
                    break;
            }

            showAlert("Result: " + result);

        } catch (NumberFormatException e) {
            showAlert("Invalid input. Please enter valid numbers.");
        }
    }

    private void showAlert(String message) {
        new AlertDialog.Builder(this)
                .setTitle("Calculator Result")
                .setMessage(message)
                .setPositiveButton("OK", (dialog, which) -> dialog.dismiss())
                .show();
    }
}
