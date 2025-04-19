<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Promoção Regional BSBerry</title>
  <link rel="manifest" href="/manifest.json">
  <link rel="icon" sizes="192x192" href="/icon-192.png">
  <link href="https://fonts.googleapis.com/css2?family=Anton&family=Roboto:wght@400;700&display=swap" rel="stylesheet">
  <meta name="theme-color" content="#ff00a5">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Roboto', sans-serif;
    }
    body {
      background: linear-gradient(to right, #ff00a5, #ff6ec7);
      color: white;
      text-align: center;
      overflow-x: hidden;
    }
    #splash {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: #000;
      color: #fff;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24px;
      z-index: 100000;
    }
    header img {
      width: 200px;
      margin: 20px auto;
      border: 5px solid #fff;
      box-shadow: 0 0 25px #ff00f7;
      border-radius: 20px;
    }
    .img-bloco {
      margin: 20px auto;
    }
    .img-bloco img {
      width: 90%;
      border-radius: 20px;
      box-shadow: 0 0 25px #00ffd5;
      margin: 10px 0;
    }
    .promo {
      background-color: #fff;
      color: #000;
      padding: 20px;
      border-radius: 10px;
      margin: 20px;
    }
    .promo h1 {
      color: red;
      font-size: 32px;
      margin-bottom: 10px;
      overflow: hidden;
      white-space: nowrap;
      border-right: 3px solid red;
      width: 0;
      animation: typing 4s steps(60, end) forwards, blink .75s step-end infinite;
    }
    @keyframes typing {
      from { width: 0 }
      to { width: 100% }
    }
    @keyframes blink {
      from, to { border-color: transparent }
      50% { border-color: red; }
    }
    .alerta {
      background-color: yellow;
      color: red;
      padding: 10px;
      font-weight: bold;
      margin: 20px auto;
    }
    .preco {
      font-size: 28px;
      color: #000;
      margin-top: 20px;
    }
    .botao-comprar {
      background-color: green;
      color: white;
      padding: 15px 25px;
      font-size: 24px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      text-decoration: none;
      display: inline-block;
      margin: 20px auto;
      box-shadow: 0 0 15px #00ff00;
      animation: pulse 1.2s infinite, shake 0.5s infinite, vibrar 0.3s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    @keyframes shake {
      0% { transform: translate(1px, 1px) rotate(0deg); }
      25% { transform: translate(-1px, 2px) rotate(-1deg); }
      50% { transform: translate(-3px, 0px) rotate(1deg); }
      75% { transform: translate(3px, 2px) rotate(0deg); }
      100% { transform: translate(1px, -1px) rotate(1deg); }
    }
    @keyframes vibrar {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-3px); }
      100% { transform: translateY(0px); }
    }
    .popup-saida {
      display: none;
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      background: rgba(0,0,0,0.95);
      color: white;
      justify-content: center;
      align-items: center;
      flex-direction: column;
      z-index: 9999;
      padding: 20px;
      backdrop-filter: blur(6px);
    }
    .popup-saida img {
      max-width: 90%;
      border-radius: 20px;
      box-shadow: 0 0 20px #ff0;
    }
    .urgente-piscando {
      font-size: 24px;
      color: yellow;
      background-color: red;
      padding: 10px;
      margin: 10px auto;
      animation: piscar 1s infinite;
    }
    @keyframes piscar {
      0% { opacity: 1; }
      50% { opacity: 0.6; }
      100% { opacity: 1; }
    }
    .selo-exclusivo {
      margin-top: 15px;
      width: 100px;
      animation: pulse 1.5s infinite;
    }
  </style>
</head>
<body onload="iniciarTelaFake()">
  <div id="splash">Carregando Promoção da Região...</div>

  <header>
    <img src="https://i.ibb.co/8g9crn1D/logo.png" alt="logo">
  </header>

  <div class="urgente-piscando">⚠️ ÚLTIMA CHANCE!</div>

  <div class="img-bloco">
    <img src="https://i.ibb.co/Fj2pCKd/tela-fake.png" alt="tela-fake">
    <img src="https://i.ibb.co/PZ6MCVf/criativo.png" alt="criativo">
  </div>

  <div class="promo">
    <h1>VOCÊ FOI SELECIONADO PARA A PROMOÇÃO EXCLUSIVA BSBerry 🍧</h1>
    <img class="selo-exclusivo" src="https://i.ibb.co/XsCV9qk/selo-exclusivo.png" alt="Exclusivo">
    <p>✅ 2 copões gigantes pelo preço de 1</p>
    <p>✅ 9 complementos grátis</p>
    <p>✅ Frete GRÁTIS para <strong id="cidade">sua região</strong></p>
    <div class="alerta">⚠️ Últimas <span id="quantidade">28</span> unidades disponíveis!</div>
    <div class="preco">🔥 Apenas R$12,45 por copão de 700ml</div>
    <a class="botao-comprar" href="https://perfectpay.com/checkout">Garantir Meu Combo Agora</a>
  </div>

  <audio id="notification-sound" src="https://assets.mixkit.co/sfx/preview/mixkit-software-interface-start-2574.mp3"></audio>

  <script>
    function iniciarTelaFake() {
      const audio = document.getElementById('notification-sound');
      try {
        audio.volume = 0.4;
        audio.play();
      } catch (e) {}

      setTimeout(() => {
        document.getElementById('splash').style.display = 'none';
      }, 2000);

      fetch('https://ipapi.co/json/')
        .then(response => response.json())
        .then(data => {
          const cidade = data.city || 'sua região';
          document.getElementById('cidade').innerText = cidade;
        })
        .catch(() => {
          document.getElementById('cidade').innerText = 'sua região';
        });
    }
  </script>
</body>
</html>
