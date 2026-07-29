[README.md](https://github.com/user-attachments/files/30517102/README.md)
# Emerald-Bastion
um jogo de navegador Tower Defense completo em pixel art chamado Emerald Bastion, com sistema de fases, modo Arcade, loja com moeda Verdalitas, personagens únicos com classes, salvamento de progresso e projeto organizado em múltiplos arquivos
[style.css](https://github.com/user-attachments/files/30517103/style.css)[README.md](https://github.com/user-attachments/files/30517109/README.md)
[index.html](https://github.com/user-attachments/files/30517105/index.html)
[game.js](https://github.com/user-attachments/files/30517104/game.js)
# Assets

Nesta primeira versão, os sprites, cenários e efeitos de pixel art são desenhados dinamicamente no Canvas, em `game.js`. Isso deixa o jogo leve e funcional mesmo offline.

Use esta pasta para incluir futuros arquivos, como spritesheets PNG, efeitos sonoros e música.
<!doctype html>
<html lang="pt-BR">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Emerald Bastion</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <main class="shell">
    <header>
      <div class="brand"><span class="gem">◆</span><div><h1>EMERALD BASTION</h1><p>Defenda o coração da floresta</p></div></div>
      <div class="header-tools"><button id="music-toggle" class="sound" aria-label="Ativar ou desativar música">♫ SOM: OFF</button><div class="wallet">VERDALITAS <strong id="gems">0</strong> <span>◆</span></div></div>
    </header>

    <section id="home" class="panel home-screen">
      <div class="hero-art" aria-hidden="true"><span class="castle">⚙</span><span class="orb">◆</span><span class="tree t1">⌁</span><span class="tree t2">⌁</span><span class="scan">EMERALD PROTOCOL</span></div>
      <p class="eyebrow">CAMPANHA ÉPICA · 80 FASES</p><h2>A GUERRA DAS CIDADES COMEÇOU</h2>
      <p class="intro">No arquipélago de Egeon, a Liga da Coroa e a Aliança de Ferro disputam o Cristal Esmeralda. Escolha seu lado, reúna heróis e defenda a Bastilha.</p>
      <div class="home-actions">
        <button class="primary" data-action="campaign">JOGAR CAMPANHA</button>
        <button class="primary arcade" data-action="arcade">MODO ARCADE</button>
        <button data-action="shop">HERÓIS E SKINS</button>
      </div>
      <p class="tip">Clique em um herói durante a partida e depois em um círculo vazio para posicioná-lo.</p>
    </section>

    <section id="selection" class="panel hidden">
      <button class="back" data-action="home">← VOLTAR</button>
      <h2 id="selection-title">ESCOLHA UMA FASE</h2>
      <div id="stage-list" class="stage-list"></div>
    </section>

    <section id="shop" class="panel hidden">
      <button class="back" data-action="home">← VOLTAR</button>
      <h2>LOJA DE HERÓIS</h2>
      <p class="intro">Heróis comprados ficam disponíveis em todas as partidas.</p>
      <div id="shop-list" class="cards"></div>
    </section>

    <section id="game" class="game-screen hidden">
      <div class="game-top">
        <button class="back" data-action="quit">← SAIR</button>
        <div id="objective">FASE 1</div>
        <div class="stats"><span>♥ <b id="lives">20</b></span><span>☀ <b id="gold">140</b></span><span>☠ <b id="wave">0</b></span></div>
      </div>
      <div class="game-layout">
        <div class="canvas-wrap"><canvas id="canvas" width="960" height="540"></canvas><div id="toast"></div></div>
        <aside class="roster"><h3>HERÓIS</h3><div id="roster-list"></div><div id="selected-info" class="selected-info">Selecione um herói.</div><button id="start-wave" class="primary">INICIAR ONDA</button><button id="speed" class="mini">VELOCIDADE: 1×</button></aside>
      </div>
    </section>
  </main>
  <script src="game.js"></script>
</body>
</html>
