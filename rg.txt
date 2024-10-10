<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Simple Registration Form</title>
    <style>
        body {
    font-family: Arial, sans-serif;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
    margin: 0;
    background-color: #e9ecef; /* Light gray background */
}

h2 {
    margin-bottom: 20px;
    color: #343a40; /* Darker text color */
}

form {
    width: 350px;
    background-color: #ffffff; /* White background for the form */
    padding: 20px;
    border-radius: 8px; /* Rounded corners */
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2); /* Subtle shadow */
}

label {
    display: block;
    margin-top: 10px;
    color: #495057; /* Slightly lighter dark color */
}

input {
    width: 95%; /* Full width input */
    padding: 10px; /* Increased padding for comfort */
    margin-top: 5px;
    margin-bottom: 10px;
    border: 1px solid #ced4da; /* Light border color */
    border-radius: 4px; /* Slightly rounded edges */
    font-size: 16px; /* Larger font size */
    transition: border-color 0.3s; /* Transition for border color change */
}

input:focus {
    border-color: #80bdff; /* Change border color on focus */
    outline: none; /* Remove default outline */
}

.error {
    color: red;
    font-size: 12px;
    margin-top: -8px; /* Adjust margin to be closer to input */
    margin-bottom: 10px;
}

button {
    width: 100%; /* Full width button */
    padding: 10px;
    background-color: #007bff; /* Bootstrap primary color */
    color: white;
    border: none;
    border-radius: 4px; /* Rounded button edges */
    cursor: pointer; /* Pointer cursor on hover */
    font-size: 16px; /* Larger font size */
    transition: background-color 0.3s; /* Transition for background color change */
}

button:hover {
    background-color: #0056b3; /* Darker shade on hover */
}
    </style>
</head>

<body>
    <h2>Register</h2>
    <form id="registerForm">
        <label for="username">Username:</label>
        <input type="text" id="username" required>
        <div class="error" id="usernameError"></div>

        <label for="password">Password:</label>
        <input type="password" id="password" required>
        <div class="error" id="passwordError"></div>

        <label for="confirmPassword">Confirm Password:</label>
        <input type="password" id="confirmPassword" required>
        <div class="error" id="confirmPasswordError"></div>

        <button type="submit">Register</button>
    </form>

    <script src="index.js">
        const form = document.getElementById('registerForm');

form.addEventListener('submit', function(event) {
    event.preventDefault(); // Prevent form submission

    // Clear previous error messages
    document.getElementById('usernameError').textContent = '';
    document.getElementById('passwordError').textContent = '';
    document.getElementById('confirmPasswordError').textContent = '';

    const username = document.getElementById('username').value.trim();
    const password = document.getElementById('password').value;
    const confirmPassword = document.getElementById('confirmPassword').value;

    let valid = true;

    // Username validation
    if (username === '') {
        document.getElementById('usernameError').textContent = 'Username is required';
        valid = false;
    }

    // Password validation
    if (password === '') {
        document.getElementById('passwordError').textContent = 'Password is required';
        valid = false;
    } else if (password.length < 😎 {
        document.getElementById('passwordError').textContent = 'Password must be at least 8 characters';
        valid = false;
    }

    // Confirm password validation
    if (confirmPassword === '') {
        document.getElementById('confirmPasswordError').textContent = 'Please confirm your password';
        valid = false;
    } else if (confirmPassword !== password) {
        document.getElementById('confirmPasswordError').textContent = "Passwords don't match";
        valid = false;
    }

    // If all validations pass, show success message
    if (valid) {
        alert('Registration successful!');
        form.reset(); // Reset the form
    }
});

    </script>
</body>
</html>
