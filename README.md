<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HOJE A NOITE</title>
    <style>
        body {
            background-color: #f0f0f0;
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            position: relative;
        }
        #botoes {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            margin: 10px;
            cursor: pointer;
            border-radius: 5px;
            transition: background-color 0.3s;
            position: relative;
        }
        button:hover {
            background-color: #ddd;
        }
        #nao {
            position: absolute;
            top: 90%;
            left: 90%;
            transform: translate(-50%, -50%);
            transition: top 0.5s, left 0.5s;
            animation: none; /* Removendo a animação inicial */
        }
        #nao.invertido {
            top: 0;
            left: 100%;
        }
        #nao-invisivel {
            display: none;
        }

        @keyframes moveCorners {
            0% {
                top: 50%;
                left: 50%;
            }
            25% {
                top: 0;
                left: calc(100% - 80px);
            }
            50% {
                top: calc(100% - 40px);
                left: calc(100% - 80px);
            }
            75% {
                top: calc(100% - 40px);
                left: 0;
            }
            100% {
                top: 50%;
                left: 50%;
            }
        }
    </style>
</head>
<body>
    <h1>Cuzinho Hoje?</h1>
    <div id="botoes">
        <button onclick="window.open('https://jornalinfocruzeiro.com.br/wp-content/uploads/2019/09/WhatsApp-Image-2019-09-09-at-08.50.02.jpeg')">Sim</button>
        <button id="nao" onclick="alternarNao()">Não</button>
        <button id="nao-invisivel" onclick="alert('Você não pode clicar em NÃO!')" style="display: none;">Não</button>
    </div>

    <script>
        function alternarNao() {
            var botaoNao = document.getElementById("nao");
            var botaoNaoInvisivel = document.getElementById("nao-invisivel");
            
            botaoNao.style.animation = "moveCorners 2s infinite"; // Iniciando a animação manualmente
            
            setTimeout(function() {
                botaoNao.classList.add("invertido"); // Mudando a posição do botão para a esquerda superior
            }, 2000);
            
            setTimeout(function() {
                botaoNao.style.display = "none"; // Escondendo o botão
                botaoNaoInvisivel.style.display = "block"; // Exibindo o botão invisível
                botaoNao.classList.remove("invertido"); // Removendo a classe de posição invertida
                botaoNao.style.animation = "none"; // Removendo a animação
            }, 4000);
        }
    </script>
</body>
</html>
