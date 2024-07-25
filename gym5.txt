<?php
include 'db.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $user_id = $_POST['user_id'];
    $date = $_POST['date'];

    $sql = "INSERT INTO attendance (user_id, date) VALUES ('$user_id', '$date')";

    if ($conn->query($sql) === TRUE) {
        echo "Attendance recorded successfully";
    } else {
        echo "Error: " . $sql . "<br>" . $conn->error;
    }

    $conn->close();
}
?>
<form method="post" action="">
    User ID: <input type="text" name="user_id" required><br>
    Date: <input type="date" name="date" required><br>
    <input type="submit" value="Record Attendance">
</form>
