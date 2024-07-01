<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Casos - Sistema de Advogados</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <img height="250" width="500" src="imagens/hist.PNG
   ">
        <h1>Sistema de Advogados</h1>
        <nav>
            <ul>
                <li><a href="index.html">Início</a></li>
            </ul>
        </nav>
    </header>
    
        <h2>Histórico de Processos</h2>
        <p>Acompanhe alguns dos casos de destaque que estamos trabalhando</p>
        <style>
    
          body {
            font-family: Arial, sans-serif;
          }
      
          form {
            width: 50%;
            margin: 0 auto;
          }
      
          label {
            display: block;
            margin-bottom: 5px;
          }
      
          textarea {
            width: 500px;
            height: 100px;
            padding: 5px;
            margin-bottom: 5px;
          }
      
          button {
            background-color: #008CBA;
            color: #fff;
            padding: 5px 10px;
            border: none;
            border-radius: 5px;
          }
      
          .historico {
            list-style-type: none;
            padding: 0;
            margin: 0;
          }
      
          .historico li {
            padding: 5px;
            margin-bottom: 5px;
            background-color: #eee;
            white-space: pre-wrap;
          }
      
          .historico li span {
            float: right;
            font-size: 12px;
            color: #666;
          }
          
          .historico li button {
            float: right;
            margin-left: 5px;
            padding: 2px 5px;
            border: 1px solid #ccc;
            border-radius: 3px;
            background-color: #c70f0f;
            cursor: pointer;
            color: rgb(255, 247, 247);
          }
        </style>
      
      <body>
    
        <form method="post">
          <label for="texto">Texto:</label>
          <textarea id="texto" rows="4" cols="50"></textarea>
      
          <button type="submit">Postar</button>
          <button type="button" id="limpar-historico">Limpar Histórico</button>
        </form>
      
        <ul class="historico">
        </ul>
        <body style="margin-bottom: 250px;">
            <!-- Conteúdo da página -->
        </body>
        
        <script>
          const formulario = document.querySelector('form');
          const historico = document.querySelector('.historico');
          const botaoLimparHistorico = document.querySelector('#limpar-historico');
          const texto = document.querySelector('#texto');
      
          formulario.addEventListener('submit', (e) => {
            e.preventDefault();
      
            const texto = document.querySelector('#texto').value;
      
            const li = document.createElement('li');
            const p = document.createElement('p');
            p.textContent = texto;
      
            const data = new Date();
            const dataFormatada = `${data.getDate()}/${data.getMonth() + 1}/${data.getFullYear()} ${data.getHours()}:${data.getMinutes()}:${data.getSeconds()}`;
      
            const span = document.createElement('span');
            span.textContent = dataFormatada;
      
            li.appendChild(p);
            li.appendChild(span);
      
            const botaoApagar = document.createElement('button');
            botaoApagar.textContent = 'Apagar';
            botaoApagar.addEventListener('click', () => {
              li.remove();
            });
      
            li.appendChild(botaoApagar);
      
            historico.appendChild(li);
          });
      
          texto.addEventListener('keypress', (e) => {
            if (e.key === 'Enter' && !e.shiftKey) {
              e.preventDefault();
              formulario.dispatchEvent(new Event('submit'));
            }
          });
      
          botaoLimparHistorico.addEventListener('click', () => {
            historico.innerHTML = '';
          });
        </script>
        <br>
        <br>
        <br>

      </body>
      </html>
   
      <footer>
        <p>&copy; 2024 Sistema de Advogados. UNIDESC Todos os direitos reservados.</p>
    </footer>
