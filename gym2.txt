<?php
include 'db.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $name = $_POST['name'];
    $email = $_POST['email'];
    $phone = $_POST['phone'];

    $sql = "INSERT INTO users (name, email, phone) VALUES ('$name', '$email', '$phone')";

    if ($conn->query($sql) === TRUE) {
        echo "New user created successfully";
    } else {
        echo "Error: " . $sql . "<br>" . $conn->error;
    }

    $conn->close();
}
?>
<form method="post" action="">
    Name: <input type="text" name="name" required><br>
    Email: <input type="email" name="email" required><br>
    Phone: <input type="text" name="phone"><br>
    <input type="submit" value="Add User">
</form>
