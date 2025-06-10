<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cadastro de Usuário</title>
</head>
<body>
    <form id="form">
        <div>
            <label for="nome">Nome:</label>
            <input type="text" id="nome" name="nome" required>
        </div>
        <div>
            <label for="anoNascimento">Ano de nascimento:</label>
            <input type="number" id="anoNascimento" name="anoNascimento" required>
        </div>
        <button type="submit">Enviar</button>
    </form>

    <script>
        document.getElementById("form").addEventListener("submit", function(event) {
            event.preventDefault();

            const nome = document.getElementById("nome").value;
            const anoNascimento = parseInt(document.getElementById("anoNascimento").value);
            const idade = new Date().getFullYear() - anoNascimento;

            if (idade >= 18) {
                alert(`Olá, ${nome}! Bem-vindo(a)!`);

                const nomeUsuario = prompt("Escolha um nome de usuário:");
                const senha = prompt("Escolha uma senha:");

                const usuario = {
                    nome: nome,
                    idade: idade,
                    nomeUsuario: nomeUsuario,
                    senha: senha
                };

                const usuarioJSON = JSON.stringify(usuario, null, 2);
                console.log("Dados do usuário em formato JSON:");
                console.log(usuarioJSON);
            } else {
                alert("Você não tem idade suficiente para realizar o login.");
            }
        });
    </script>
</body>
</html>
