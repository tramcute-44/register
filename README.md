
<!DOCTYPE html>
<html>
<head>
  <title>Đăng ký</title>
</head>
<body>
  <h2>Form Đăng ký</h2>
  <form action="register.php" method="post">
    <label>Tên người dùng:</label><br>
    <input type="text" name="username"><br><br>
    <label>Mật khẩu:</label><br>
    <input type="password" name="password"><br><br>
    <input type="submit" value="Đăng ký">
  </form>
</body>
</html
<?php
// Nhận dữ liệu từ form
$username = $_POST['username'];
$password = password_hash($_POST['password'], PASSWORD_DEFAULT); // mã hóa mật khẩu

// Lưu thông tin vào file
$file = fopen("users.txt", "a");
fwrite($file, "$username,$password\n");
fclose($file);

// Phản hồi người dùng
echo "Đăng ký thành công cho người dùng: $username";
?>
