<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Painel de Munição</title>
  <link rel="manifest" href="manifest.json">
  <meta name="theme-color" content="#1b1b1f">
  <style>
    body {
      background-color: #1b1b1f;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      padding: 20px;
      color: #e5e5e5;
      margin: 0;
    }
    h1 {
      text-align: center;
      font-size: 2em;
      margin-bottom: 30px;
      color: #9b59b6;
    }
    .container {
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    .municao {
      background: #2b2b30;
      border: 2px solid #9b59b6;
      border-radius: 12px;
      padding: 15px;
      margin-bottom: 20px;
      max-width: 400px;
      width: 90%;
      box-shadow: 2px 2px 6px rgba(0,0,0,0.3);
    }
    .municao h2 {
      margin: 0 0 10px;
      color: #9b59b6;
      font-size: 1.2em;
    }
    .quantidade {
      display: flex;
      justify-content: space-between;
      flex-wrap: wrap;
      margin-top: 10px;
      gap: 10px;
    }
    .botao {
      margin: 0 5px;
      padding: 4px 8px;
      font-weight: bold;
      border: 1px solid #9b59b6;
      border-radius: 6px;
      background-color: #1b1b1f;
      color: #e5e5e5;
      cursor: pointer;
      transition: transform 0.1s ease, background-color 0.2s ease;
    }
    .botao:hover {
      background-color: #333;
    }
    .botao:active {
      transform: scale(0.95);
    }
    .imagem {
      max-height: 40px;
      vertical-align: middle;
    }
    .recarregar {
      margin-top: 10px;
      background-color: #9b59b6;
      color: white;
      border: none;
      padding: 6px 10px;
      cursor: pointer;
      border-radius: 6px;
      transition: transform 0.1s ease, background-color 0.2s ease;
    }
    .recarregar:hover {
      background-color: #7d3c98;
    }
    .recarregar:active {
      transform: scale(0.95);
    }
    .resetar {
      display: block;
      margin: 20px auto;
      background-color: #333;
      color: white;
      border: none;
      padding: 10px 20px;
      border-radius: 8px;
      cursor: pointer;
      transition: transform 0.1s ease, background-color 0.2s ease;
    }
    .resetar:hover {
      background-color: #444;
    }
    .resetar:active {
      transform: scale(0.95);
    }
  </style>
</head>
<body>
  <h1>Ficha de Munição</h1>
  <div class="container">
    <button class="resetar" onclick="resetarTudo()">Resetar Tudo</button>
    <div id="painel"></div>
  </div>

  <script>
    if ('serviceWorker' in navigator) {
      navigator.serviceWorker.register('service-worker.js')
        .then(reg => console.log('Service Worker registrado:', reg.scope))
        .catch(err => console.error('Erro ao registrar Service Worker:', err));
    }

    const municoes = [
      { nome: 'Balas Curtas (Pistola / Revólver / Submetralhadora)', imagem: 'https://png.pngtree.com/png-vector/20220531/ourmid/pngtree-pistol-bullets-icon-gun-bullet-png-image_4779411.png', capacidade: 12 },
      { nome: 'Balas Longas (Fuzis / Metralhadora)', imagem: 'https://png.pngtree.com/png-clipart/20220605/original/pngtree-rifle-ammo-icon-weapon-bullet-png-image_7958968.png', capacidade: 30 },
      { nome: 'Cartuchos (Espingarda)', imagem: 'https://img.freepik.com/vetores-premium/icone-de-municao-cartucho-de-bala-em-estilo-desenhado-a-mao-isolado-no-fundo-branco_53562-14843.jpg', capacidade: 6 },
      { nome: 'Flechas (Arcos / Bestas / Balestra)', imagem: 'https://img.freepik.com/vetores-premium/aljava-de-caca-tradicional-com-setas-icone-isolado-em-ilustracao-vetorial-de-estilo-simples_710508-1345.jpg', capacidade: 1 },
      { nome: 'Combustível (Lança-chamas)', imagem: 'https://static.vecteezy.com/ti/vetor-gratis/p1/9158480-barril-e-canister-com-combustiveis-simbolo-de-petroleo-barril-com-gota-estoques-de-galao-combustivel-vetor.jpg', capacidade: 100 },
      { nome: 'Foguete (Bazuca)', imagem: 'https://cdn-icons-png.flaticon.com/512/290/290491.png', capacidade: 1 },
    ];

    const painel = document.getElementById('painel');
    let inventarioSalvo = JSON.parse(localStorage.getItem('inventario')) || [];

    municoes.forEach((municao, index) => {
      let inventario = inventarioSalvo[index]?.inventario ?? 0;
      let arma = inventarioSalvo[index]?.arma ?? 0;

      const div = document.createElement('div');
      div.className = 'municao';
      div.innerHTML = `
        <h2><img src="${municao.imagem}" class="imagem"> ${municao.nome}</h2>
        <div class="quantidade">
          <div>Inventário: <span id="inv-${index}">${inventario}</span>
            <button class="botao" onclick="add(${index}, 'inv', -1)">-</button>
            <button class="botao" onclick="add(${index}, 'inv', 1)">+</button>
          </div>
          <div>Na Arma: <span id="arma-${index}">${arma}</span> / ${municao.capacidade}
            <button class="botao" onclick="add(${index}, 'arma', -1)">-</button>
            <button class="botao" onclick="add(${index}, 'arma', 1)">+</button>
          </div>
        </div>
        <button class="recarregar" onclick="recarregar(${index}, ${municao.capacidade})">Recarregar</button>
      `;
      painel.appendChild(div);
    });

    function salvarEstado() {
      const estado = municoes.map((_, i) => ({
        inventario: parseInt(document.getElementById(`inv-${i}`).innerText),
        arma: parseInt(document.getElementById(`arma-${i}`).innerText),
      }));
      localStorage.setItem('inventario', JSON.stringify(estado));
    }

    function add(index, tipo, valor) {
      const span = document.getElementById(`${tipo}-${index}`);
      let atual = parseInt(span.innerText);
      if (atual + valor >= 0) {
        span.innerText = atual + valor;
        salvarEstado();
      }
    }

    function recarregar(index, capacidade) {
      const inv = document.getElementById(`inv-${index}`);
      const arma = document.getElementById(`arma-${index}`);
      let invAtual = parseInt(inv.innerText);
      let armaAtual = parseInt(arma.innerText);
      let precisa = capacidade - armaAtual;
      let transferir = Math.min(precisa, invAtual);
      if (transferir > 0) {
        inv.innerText = invAtual - transferir;
        arma.innerText = armaAtual + transferir;
        salvarEstado();
      }
    }

    function resetarTudo() {
      municoes.forEach((_, i) => {
        document.getElementById(`inv-${i}`).innerText = 0;
        document.getElementById(`arma-${i}`).innerText = 0;
      });
      salvarEstado();
    }
  </script>
</body>
</html>
