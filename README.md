# Password-strength-hacking-<!DOCTYPE html>
<html>
<head>
    <title>Password Strength Checker</title>
    <style>
        #strength {
            font-weight: bold;
        }
    </style>
</head>
<body>
    <h1>Password Strength Checker</h1>
    <input type="password" id="password" placeholder="Enter your password" />
    <p>Password Strength: <span id="strength">Enter a password</span></p>

    <script>
        const passwordInput = document.getElementById("password");
        const strengthText = document.getElementById("strength");

        passwordInput.addEventListener("input", () => {
            const password = passwordInput.value;
            const strength = checkPasswordStrength(password);
            strengthText.textContent = strength;
            strengthText.style.color = getStrengthColor(strength);
        });

        function checkPasswordStrength(password) {
            let strength = 0;

            if (password.length >= 8) strength++; // Minimum length
            if (/[A-Z]/.test(password)) strength++; // Uppercase letter
            if (/[a-z]/.test(password)) strength++; // Lowercase letter
            if (/[0-9]/.test(password)) strength++; // Digit
            if (/[@$!%*?&#]/.test(password)) strength++; // Special character

            switch (strength
