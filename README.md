<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Roleta de Prêmios</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background-color: #f4f4f4;
    }
    #roleta {
      width: 300px;
      height: 300px;
      border: 10px solid #ddd;
      border-radius: 50%;
      position: relative;
    }
    #roleta div {
      position: absolute;
      width: 50%;
      height: 50%;
      background-color: #1E3A8A; /* Azul escuro */
      transform-origin: 100% 100%;
      clip-path: polygon(100% 0, 100% 100%, 0 100%);
      color: white;
      font-size: 12px;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 10px;
    }
    #roleta div:nth-child(2n) {
      background-color: #93C5FD; /* Azul claro */
    }
    #roleta div:nth-child(3n) {
      background-color: #E5E7EB; /* Branco */
      color: black;
    }
    #botao {
      margin-top: 20px;
      padding: 10px 20px;
      background-color: #1E3A8A; /* Azul escuro */
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
      font-size: 16px;
    }
  </style>
</head>
<body>
  <div id="roleta">
    <div>15% OFF</div>
    <div>15% OFF</div>
    <div>15% OFF</div>
    <div>15% OFF</div>
    <div>Não foi dessa vez</div>
    <div>Não foi dessa vez</div>
    <div>Mês cortesia</div>
    <div>Mês cortesia</div>
    <div>Mês cortesia</div>
    <div>5 dias de acesso teste</div>
    <div>5 dias de acesso teste</div>
    <div>5 dias de acesso teste</div>
  </div>
  <button id="botao">Girar</button>

  <script>
    const roleta = document.getElementById('roleta');
    const botao = document.getElementById('botao');
    const premios = ['15% OFF', '15% OFF', '15% OFF', '15% OFF', 'Não foi dessa vez', 'Não foi dessa vez', 'Mês cortesia', 'Mês cortesia', 'Mês cortesia', '5 dias de acesso teste', '5 dias de acesso teste', '5 dias de acesso teste'];

    botao.addEventListener('click', () => {
      const premioSorteado = Math.floor(Math.random() * premios.length);
      roleta.style.transition = 'transform 4s ease-out';
      roleta.style.transform = `rotate(${360 * 5 + premioSorteado * 30}deg)`; // 30 graus por seção (360/12)

      setTimeout(() => {
        alert('Parabéns! Você ganhou: ' + premios[premioSorteado]);
      }, 4000);
    });
  </script>
</body>
</html>