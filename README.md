# jusette
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aceitas?</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #ffc8dd;
            font-family: 'Montserrat', sans-serif;
        }

        .container {
            text-align: center;
            position: relative;
            width: 100%;
            height: 100%;
        }

        h1 {
            font-size: 2rem;
            font-weight: bold;
            color: #000;
            margin-bottom: 20px;
        }

        button {
            font-size: 1rem;
            font-weight: bold;
            padding: 10px 20px;
            border: none;
            cursor: pointer;
            position: absolute;
            width: 100px; /* Largura fixa */
            height: 40px; /* Altura fixa */
            box-sizing: border-box; /* Inclui padding e border no tamanho */
        }

        .yes {
            background-color: #02BF38;
            color: #fff;
        }

        .no {
            background-color: #FF1604;
            color: #fff;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Juliana, você quer sair comigo?</h1>
        <button class="yes" style="left: 60%; bottom: 30%;">Sim</button>
        <button class="no" style="left: 30%; bottom: 30%;">Não</button>
    </div>

    <script>
        const yesButton = document.querySelector('.yes');
        const noButton = document.querySelector('.no');
        const container = document.querySelector('.container');

        // Função para mover o botão "Não"
        function moveButton() {
            const containerWidth = container.offsetWidth;
            const containerHeight = container.offsetHeight;
            const buttonWidth = noButton.offsetWidth;
            const buttonHeight = noButton.offsetHeight;

            // Garantir que o botão sempre mova para um novo lugar
            let newX, newY;

            do {
                newX = Math.random() * (containerWidth - buttonWidth);
                newY = Math.random() * (containerHeight - buttonHeight);
            } while (
                Math.abs(newX - parseFloat(noButton.style.left || 0)) < 50 &&
                Math.abs(newY - parseFloat(noButton.style.top || 0)) < 50
            );

            noButton.style.left = `${newX}px`;
            noButton.style.top = `${newY}px`;
        }

        // Evento de movimento constante no botão "Não"
        noButton.addEventListener('mouseover', moveButton);

        // Evento de clique no botão "Sim"
        yesButton.addEventListener('click', () => {
            alert('ACHO QUE AGORA É SÓ MARCAR NÉ?');
        });
    </script>
</body>
</html>
