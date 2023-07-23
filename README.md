#login-form
<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Campus Selection Portal - Login</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.2.0-beta1/dist/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            background-color: #1c1c1c;
            font-family: Arial, sans-serif;
        }

        .login-container {
            width: 410px;
            padding: 30px;
            border-radius: 8px;
            background-color: #272727;
            box-shadow: 0 2px 6px rgba(0, 0, 0, 0.4);
        }

        .login-container h2 {
            text-align: center;
            margin-bottom: 20px;
            color: #f1c40f;
        }

        .form-group {
            margin-bottom: 20px;
        }

        .form-group label {
            display: block;
            font-size: 14px;
            font-weight: bold;
            margin-bottom: 5px;
            color: #fff;
        }

        .form-group input {
            width: 100%;
            padding: 10px;
            font-size: 16px;
            background-color: #363636;
            color: #fff;
            border: none;
            border-radius: 4px;
            transition: background-color 0.3s ease, border-color 0.3s ease;
        }

        .form-group input:focus {
            outline: none;
            background-color: #444;
            border-color: #f1c40f;
        }

        .apps-store {
            padding: 0.6rem 1.5rem;
            border: 1px solid #01E9F8;
            color: #01E9F8;
        }

        .apps-store i {
            font-size: 5rem;
        }

        .apps-store div span:nth-child(1) {
            font-size: 0.7rem;
            line-height: 13px;
        }

        .btn:hover {
            border: 1px solid #01E9F8;
            color: black;
            box-shadow: 0rem 0rem 1rem 0rem #01E9F8;
            transition: all 0.3s ease-in-out;
        }

        .register-link {
            color: #01E9F8;
            font-size: 17px;
            font-weight: bold;
            cursor: pointer;
            text-decoration: none;
            display: flex;
            align-items: center;
        }

        .register-link a {
            text-decoration: none;
            color: #01E9F8;
            margin-left: 10px;
        }

        .register-link a:hover {
            color: white;
        }

        .form-group input:invalid {
            border-color: #ff4444;
        }

        .form-group input:valid {
            border-color: #444;
        }

        .form-group .error-message {
            color: #ff4444;
            font-size: 14px;
            margin-top: 5px;
        }
    </style>
</head>

<body>
    <div class="login-container">
        <h2>Campus Selection Portal</h2>
        <form id="loginForm">
            <div class="form-group">
                <label for="username">Username</label>
                <input type="text" id="username" name="username" required pattern="[a-zA-Z0-9]+" placeholder="Enter your username">
                <div class="error-message" id="usernameError"></div>
            </div>
            <div class="form-group">
                <label for="password">Password</label>
                <input type="password" id="password" name="password" required placeholder="Enter your password">
                <div class="error-message" id="passwordError"></div>
            </div>
            <div class="d-flex justify-content-between">
                <button class="btn rounded-5 apps-store">
                    <span class="d-flex align-items-center">
                        <div class="ms-2 d-flex flex-column text-start">
                            <span class="">SUBMIT</span>
                        </div>
                    </span>
                </button>
                <div class="register-link">
                    <a href="signup.com">Sign up</a>
                </div>
            </div>
        </form>
    </div>

    <script>
        const loginForm = document.getElementById('loginForm');
        const usernameInput = document.getElementById('username');
        const passwordInput = document.getElementById('password');
        const usernameError = document.getElementById('usernameError');
        const passwordError = document.getElementById('passwordError');

        loginForm.addEventListener('submit', function(event) {
            event.preventDefault();
            if (!usernameInput.validity.valid) {
                usernameError.textContent = 'Please enter a valid username (only alphanumeric characters allowed).';
            } else {
                usernameError.textContent = '';
            }

            if (passwordInput.value === '') {
                passwordError.textContent = 'Please enter a password.';
            } else {
                passwordError.textContent = '';
                alert('Form submitted successfully!');
                loginForm.reset();
            }
        });
    </script>
</body>

</html>
