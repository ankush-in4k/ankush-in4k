<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Member Login</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            margin: 0;
            padding: 0;
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
        }

        .login-container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 400px;
        }

        .login-container h2 {
            text-align: center;
            color: #333;
        }

        .login-form {
            margin-top: 20px;
        }

        .form-group {
            margin-bottom: 15px;
        }

        .form-group label {
            display: block;
            font-size: 14px;
            margin-bottom: 5px;
            color: #555;
        }

        .form-group input {
            width: 100%;
            padding: 8px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 4px;
        }

        .form-group button {
            background-color: #007bff;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
            width: 100%;
        }

        .logout-container {
            margin-top: 20px;
            text-align: center;
        }

        .logout-button {
            background-color: #dc3545;
            color: #fff;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }

        .error-message {
            color: #dc3545;
            margin-top: 5px;
        }
    </style>
</head>
<body>

<div class="login-container" id="loginContainer">
    <h2>MWBT Member Login</h2>
    <form class="login-form" id="loginForm">
        <div class="form-group">
            <label for="username">Username:</label>
            <input type="text" id="username" name="username" required>
            <p class="error-message" id="usernameError"></p>
        </div>

        <div class="form-group">
            <label for="password">Password:</label>
            <input type="password" id="password" name="password" required>
            <p class="error-message" id="passwordError"></p>
        </div>

        <div class="form-group">
            <button type="button" onclick="login()">Login</button>
        </div>
    </form>
</div>

<div class="logout-container" id="logoutContainer" style="display: none;">
    <button class="logout-button" onclick="logout()">Logout</button>
</div>

<script>
    function login() {
        var username = document.getElementById('username').value;
        var password = document.getElementById('password').value;

        // Regular expressions for username and password validation
        var usernameRegex = /^ID-\d{4}$/;
        var passwordRegex = /^\d{4}$/;

        // Reset error messages
        document.getElementById('usernameError').innerText = '';
        document.getElementById('passwordError').innerText = '';

        if (usernameRegex.test(username) && passwordRegex.test(password)) {
            // Hide login container
            document.getElementById('loginContainer').style.display = 'none';
            
            // Display logout container
            document.getElementById('logoutContainer').style.display = 'block';

            // Display login success message (you might want to customize this)
            alert('Login Successful to SERVER! Welcome, ' + username);
        } else {
            // Display error messages if validation fails
            if (!usernameRegex.test(username)) {
                document.getElementById('Username Error, RECHECK').innerText = 'Invalid Username Check your Format. Please use the format "ID-1234".';
            }

            if (!passwordRegex.test(password)) {
                document.getElementById('Password Error, RECHECK').innerText = 'Invalid Password. Please use the 4-digit password.';
            }
        }
    }

    function logout() {
        // Clear any stored user data or session information

        // Hide logout container
        document.getElementById('logoutContainer').style.display = 'none';

        // Display login container
        document.getElementById('loginContainer').style.display = 'block';
    }
</script>

</body>
</html>

