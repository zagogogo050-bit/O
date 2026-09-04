<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <title>Meu App</title>

  <style>
    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: Arial, sans-serif;
    }

    body {
      background: #0f0f0f;
      color: white;
      min-height: 100vh;
    }

    header {
      padding: 18px;
      text-align: center;
      background: #171717;
      border-bottom: 1px solid #292929;
    }

    header h1 {
      font-size: 24px;
    }

    header p {
      margin-top: 5px;
      color: #aaa;
      font-size: 14px;
    }

    main {
      width: 100%;
      max-width: 600px;
      margin: auto;
      padding: 20px 15px 90px;
    }

    .card {
      background: #191919;
      border: 1px solid #292929;
      border-radius: 18px;
      padding: 20px;
      margin-bottom: 15px;
      box-shadow: 0 5px 20px rgba(0,0,0,.25);
    }

    .card h2 {
      margin-bottom: 10px;
      font-size: 20px;
    }

    .card p {
      color: #aaa;
      line-height: 1.5;
    }

    .btn {
      width: 100%;
      border: none;
      border-radius: 14px;
      padding: 15px;
      margin-top: 12px;
      background: #ffffff;
      color: #111;
      font-size: 16px;
      font-weight: bold;
      cursor: pointer;
      transition: .2s;
    }

    .btn:active {
      transform: scale(.97);
    }

    .btn.secondary {
      background: #292929;
      color: white;
    }

    .input {
      width: 100%;
      padding: 14px;
      margin-top: 10px;
      border-radius: 12px;
      border: 1px solid #333;
      background: #101010;
      color: white;
      outline: none;
    }

    .result {
      display: none;
      margin-top: 15px;
      padding: 15px;
      background: #101010;
      border-radius: 12px;
      border: 1px solid #333;
    }

    nav {
      position: fixed;
      bottom: 0;
      left: 0;
      width: 100%;
      height: 70px;
      background: #171717;
      border-top: 1px solid #292929;
      display: flex;
      justify-content: space-around;
      align-items: center;
    }

    nav button {
      background: none;
      border: none;
      color: #aaa;
      font-size: 13px;
      cursor: pointer;
    }

    nav button.active {
      color: white;
      font-weight: bold;
    }

    .page {
      display: none;
    }

    .page.active {
      display: block;
    }

    .logo {
      width: 70px;
      height: 70px;
      border-radius: 20px;
      background: white;
      color: black;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 30px;
      font-weight: bold;
      margin: 0 auto 15px;
    }
  </style>
</head>

<body>

  <header>
    <div class="logo">APP</div>
    <h1>Meu App</h1>
    <p>Uma experiência simples para celular</p>
  </header>

  <main>

    <!-- INÍCIO -->
    <section id="inicio" class="page active">

      <div class="card">
        <h2>👋 Bem-vindo!</h2>
        <p>
          Este é o seu aplicativo funcionando diretamente
          no navegador do celular.
        </p>

        <button class="btn" onclick="mostrarMensagem()">
          Começar
        </button>

        <div id="mensagem" class="result">
          ✅ Aplicativo iniciado com sucesso!
        </div>
      </div>

      <div class="card">
        <h2>🚀 Recursos</h2>
        <p>
          Use o menu inferior para navegar entre as páginas
          do aplicativo.
        </p>
      </div>

    </section>


    <!-- FERRAMENTA -->
    <section id="ferramenta" class="page">

      <div class="card">
        <h2>🛠️ Ferramenta</h2>

        <p>
          Digite alguma coisa abaixo:
        </p>

        <input
          id="texto"
          class="input"
          type="text"
          placeholder="Digite aqui..."
        >

        <button class="btn" onclick="processar()">
          Processar
        </button>

        <div id="resultado" class="result"></div>
      </div>

    </section>


    <!-- SOBRE -->
    <section id="sobre" class="page">

      <div class="card">
        <h2>ℹ️ Sobre</h2>

        <p>
          Este projeto foi desenvolvido em HTML, CSS e
          JavaScript e foi otimizado para telas de celular.
        </p>

        <button class="btn secondary" onclick="alert('Versão 1.0')">
          Ver versão
        </button>
      </div>

    </section>

  </main>


  <!-- MENU -->
  <nav>

    <button
      id="nav-inicio"
      class="active"
      onclick="abrirPagina('inicio')">
      🏠<br>Início
    </button>

    <button
      id="nav-ferramenta"
      onclick="abrirPagina('ferramenta')">
      🛠️<br>Ferramenta
    </button>

    <button
      id="nav-sobre"
      onclick="abrirPagina('sobre')">
      ℹ️<br>Sobre
    </button>

  </nav>


  <script>

    function abrirPagina(pagina) {

      document.querySelectorAll('.page')
        .forEach(function(el) {
          el.classList.remove('active');
        });

      document.getElementById(pagina)
        .classList.add('active');

      document.querySelectorAll('nav button')
        .forEach(function(el) {
          el.classList.remove('active');
        });

      document.getElementById('nav-' + pagina)
        .classList.add('active');
    }


    function mostrarMensagem() {

      const mensagem =
        document.getElementById('mensagem');

      mensagem.style.display = 'block';
    }


    function processar() {

      const texto =
        document.getElementById('texto').value;

      const resultado =
        document.getElementById('resultado');

      if (texto.trim() === '')# O
