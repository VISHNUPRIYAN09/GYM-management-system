<?php
include 'db.php';

if ($_SERVER['REQUEST_METHOD'] == 'POST') {
    $user_id = $_POST['user_id'];
    $plan = $_POST['plan'];
    $start_date = $_POST['start_date'];
    $end_date = $_POST['end_date'];

    $sql = "INSERT INTO memberships (user_id, plan, start_date, end_date) VALUES ('$user_id', '$plan', '$start_date', '$end_date')";

    if ($conn->query($sql) === TRUE) {
        echo "New membership added successfully";
    } else {
        echo "Error: " . $sql . "<br>" . $conn->error;
    }

    $conn->close();
}
?>
<form method="post" action="">
    User ID: <input type="text" name="user_id" required><br>
    Plan: <input type="text" name="plan" required><br>
    Start Date: <input type="date" name="start_date" required><br>
    End Date: <input type="date" name="end_date" required><br>
    <input type="submit" value="Add Membership">
</form>
