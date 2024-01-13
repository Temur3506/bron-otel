# bron-otel
<?php
$db_host = 'localhost';
$db_name = 'database_name';
$db_user = 'username';
$db_pass = 'password';

$connection = new PDO("mysql:host=$db_host;dbname=$db_name", $db_user, $db_pass);


$check_in_date = $_POST['check-in-date'];
$check_out_date = $_POST['check-out-date'];


$stmt = $connection->prepare("INSERT INTO bookings (check_in_date, check_out_date) VALUES (?, ?)");
$stmt->execute([$check_in_date, $check_out_date]);

echo 'Бронирование успешно сохранено!';
?>
