
<html lang="pt-BR">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Mensagem pra Você</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      background-color: #000;
      color: white;
      font-family: 'Arial', sans-serif;
      text-align: center;
      overflow: hidden;
    }

    .mensagem {
      position: relative;
      padding: 20px;
      top: 10%;
    }

    .emoji-triste {
      font-size: 60px;
      animation: pulse 2s infinite;
      margin-bottom: 10px;
    }

    .mensagem p {
      font-size: 1.2em;
      line-height: 1.5em;
      margin: 10px 0;
    }

    .coraçoes {
      position: fixed;
      top: 0;
      left: 0;
      pointer-events: none;
      width: 100%;
      height: 100%;
      overflow: hidden;
      z-index: -1;
    }

    .coraçao {
      position: absolute;
      color: red;
      font-size: 24px;
      animation: subir 5s linear infinite;
    }

    @keyframes subir {
      0% {
        transform: translateY(100vh) scale(1);
        opacity: 1;
      }
      100% {
        transform: translateY(-10vh) scale(1.5);
        opacity: 0;
      }
    }

    @keyframes pulse {
      0%, 100% {
        transform: scale(1);
      }
      50% {
        transform: scale(1.2);
      }
    }

    .botao {
      margin-top: 30px;
      display: inline-block;
      padding: 15px 20px;
      font-size: 1em;
      background-color: #ff4da6;
      border: none;
      border-radius: 25px;
      color: white;
      cursor: pointer;
      animation: pulsar 1.5s infinite;
      box-shadow: 0 0 12px #ff4da6;
      max-width: 90%;
    }

    @keyframes pulsar {
      0%, 100% {
        transform: scale(1);
        box-shadow: 0 0 15px #ff4da6;
      }
      50% {
        transform: scale(1.1);
        box-shadow: 0 0 30px #ff1a8c;
      }
    }
  </style>
</head>
<body>

  <div class="mensagem">
    <div class="emoji-triste">🥺</div>
    <p>Nem sei explicar direito...</p>
    <p>Só queria você aqui, agora, comigo. 🥺❤️</p>
    <p>Só nós dois, deitados, sem palavras...</p>
    <p>Só sentindo a presença um do outro. 😌</p>
    <p>Isso pra mim já seria o paraíso. 🌌💖</p>

    <button class="botao">
      Quero te abraçar forte, não te soltar mais.  
      Te fazer cosquinha na sua cintura 😍
    </button>
  </div>

  <div class="coraçoes" id="coraçoes"></div>

  <script>
    function criarCoraçao() {
      const coracao = document.createElement("div");
      coracao.classList.add("coraçao");
      coracao.innerText = "❤️";

      coracao.style.left = Math.random() * 100 + "vw";
      coracao.style.fontSize = Math.random() * 20 + 20 + "px";

      document.getElementById("coraçoes").appendChild(coracao);

      setTimeout(() => {
        coracao.remove();
      }, 5000);
    }

    setInterval(criarCoraçao, 300);
  </script>

</body>
</html>
