# son
dichvudatdabong
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trang đặt sân bóng đá</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        h1 {
            color: #333;
        }

        form {
            background-color: #fff;
            padding: 20px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        input, select, button {
            display: block;
            margin: 10px 0;
            padding: 10px;
            width: 100%;
            max-width: 300px;
        }
    </style>
</head>
<body>
    <h1>Chào mừng bạn đến với hệ thống đặt sân bóng đá</h1>

    <!-- Phần đăng nhập -->
    <div id="login">
        <h2>Đăng nhập</h2>
        <form id="loginForm" onsubmit="return handleLogin()">
            <label for="username">Tên tài khoản:</label>
            <input type="text" name="username" id="username" required><br>

            <label for="password">Mật khẩu:</label>
            <input type="password" name="password" id="password" required><br>

            <button type="submit">Đăng nhập</button>
        </form>
    </div>

    <!-- Phần đặt sân (Hiển thị sau khi đăng nhập thành công) -->
    <div id="booking" style="display: none;">
        <h2>Chọn sân bóng để đặt</h2>
        <form id="bookingForm" onsubmit="return handleBooking()">
            <label for="field">Chọn sân:</label>
            <select name="field" id="field">
                <option value="Sân 1">Sân 1</option>
                <option value="Sân 2">Sân 2</option>
                <option value="Sân 3">Sân 3</option>
            </select><br>

            <label for="date">Chọn ngày:</label>
            <input type="date" name="date" id="date" required><br>

            <label for="time">Chọn giờ:</label>
            <input type="time" name="time" id="time" required><br>

            <button type="submit">Đặt sân</button>
        </form>
    </div>

    <!-- Phần thông báo -->
    <div id="result" style="display: none;">
        <h2>Kết quả</h2>
        <p id="resultMessage"></p>
    </div>

    <script>
        // Giả sử username: admin và password: admin để mô phỏng đăng nhập
        function handleLogin() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;

            if (username === 'admin' && password === 'admin') {
                alert('Đăng nhập thành công');
                document.getElementById('login').style.display = 'none';
                document.getElementById('booking').style.display = 'block';
            } else {
                alert('Sai tài khoản hoặc mật khẩu');
            }
            return false; // Ngăn không cho trang reload
        }

        // Xử lý khi đặt sân
        function handleBooking() {
            const field = document.getElementById('field').value;
            const date = document.getElementById('date').value;
            const time = document.getElementById('time').value;

            const message = `Bạn đã đặt thành công: ${field} vào ngày ${date} lúc ${time}`;
            document.getElementById('booking').style.display = 'none';
            document.getElementById('resultMessage').innerText = message;
            document.getElementById('result').style.display = 'block';

            return false; // Ngăn không cho trang reload
        }
    </script>
</body>
</html>
