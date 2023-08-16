```php
//Código do login.php
<?php
        session_start();
        if (($_SERVER['REQUEST_METHOD'] == 'POST')) {
            require "listar.php";
        }
    ?>

<!DOCTYPE html>
<html lang="pt-br">

<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Desafio 04</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.0-alpha3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-KK94CHFLLe+nY2dmCWGMq91rCGa5gtU4mk92HdvYe+M/SXH301p5ILy+dN9+nJOZ" crossorigin="anonymous">
</head>

<body>
    <div class="container">
        <div class="login">
            <h1 class="text-center">Efetuar Login</h1>
            <form method="POST" action="listar.php">
                <label for="login">Login:</label>
                <input type="text" name="login" id="login" required class="form-control"><br>

                <label for="senha">Senha</label>
                <input type="password" name="senha" id="senha" required class="form-control"><br>

                <button type="submit" class="btn btn-dark w-100">Efetuar</button>
            </form>
        </div>
    </div>
</body>
</html>

//Código do listar.php
<?php
session_start();
    $_SESSION['login'] = $_POST['login'];
    $_SESSION['senha'] = $_POST['senha'];

    $login = $_SESSION['login'];
    $senha = $_SESSION['senha'];
?>

<h1>Dados do usuário</h1>
<h2>Nome: <?= $login ?></h2>
<h2>Senha: <?= $senha ?></h2>
´´´