<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <title>Quiz sobre Leprechaun mexicano (cláudio)</title>
  <link rel="icon" href="favicon.ico" type="image/x-icon"> <!-- Adiciona o favicon aqui -->
  <style>
    /* Animação do gradiente */
    @keyframes gradient {
      0% {
        background-position: 0% 50%;
      }
      50% {
        background-position: 100% 50%;
      }
      100% {
        background-position: 0% 50%;
      }
    }

    body {
      /* Gradiente giratório */
      background: linear-gradient(270deg, #6a0dad, #a45eb5, #6a0dad, #a45eb5);
      background-size: 400% 400%;
      animation: gradient 10s ease infinite;
      color: white;
      font-family: Arial, sans-serif;
      text-align: center;
      padding: 20px;
    }

    form {
      display: inline-block;
      text-align: left;
      background-color: rgba(255, 255, 255, 0.1);
      padding: 20px;
      border-radius: 10px;
    }

    input[type="text"] {
      width: 100%;
      padding: 8px;
      margin-top: 5px;
      margin-bottom: 15px;
      border: none;
      border-radius: 5px;
    }

    button {
      padding: 10px 20px;
      border: none;
      background-color: white;
      color: purple;
      font-weight: bold;
      cursor: pointer;
      border-radius: 5px;
    }

    #resultado {
      margin-top: 20px;
      font-size: 18px;
    }
  </style>
</head>
<body>
  <h1>Bem-vindo(a) ao quiz sobre Cláudio! 😱</h1>

  <form id="quizForm" autocomplete="off"> <!-- Desativa o autocomplete para todo o formulário -->
    <label>Quem és tu? 
      <input type="text" id="nome" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <label>Qual a data de aniversário de Cláudio? 🧐<br>
      <input type="text" id="pergunta1" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>
    
    <label>Qual a cor favorita de mexicano? 🌈<br>
      <input type="text" id="pergunta2" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <label>Em qual bairro Cláudio Emanuel reside atualmente? 😎<br>
      <input type="text" id="pergunta3" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <label>Qual a banda favorita de Cláudio? 🎸<br>
      <input type="text" id="pergunta4" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <label>Qual a altura atual de Cláudio? (sem "cm")<br>
      <input type="text" id="pergunta5" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <label>Qual a sexualidade de Cláudio? 🏳‍🌈<br>
      <input type="text" id="pergunta6" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <label>É verdade que Cláudio ADORA femboys? (sim/não)<br>
      <input type="text" id="pergunta7" required autocomplete="off"> <!-- Desativa o autocomplete -->
    </label><br><br>

    <button type="submit">Enviar Respostas</button>
  </form>

  <div id="resultado"></div>

  <script>
    // Confirmação quando o usuário preenche o nome
    document.getElementById("nome").addEventListener("blur", function () {
      const resposta = confirm("Você ousa tomar o risco de responder este quiz?");
      if (!resposta) {
        alert("Covarde. Adeus!");
        window.close();
      }
    });

    // Função util para mostrar ✔️ ou ❌
    function verificar(condicao, textoCerto, textoErrado) {
      return condicao ? `✔️ ${textoCerto}<br>` : `❌ ${textoErrado}<br>`;
    }

    // Lógica do quiz
    document.getElementById("quizForm").addEventListener("submit", function(e) {
      e.preventDefault();

      const nome = document.getElementById("nome").value;
      const r1 = document.getElementById("pergunta1").value.toLowerCase();
      const r2 = document.getElementById("pergunta2").value.toLowerCase();
      const r3 = document.getElementById("pergunta3").value.toLowerCase();
      const r4 = document.getElementById("pergunta4").value.toLowerCase();
      const r5 = document.getElementById("pergunta5").value;
      const r6 = document.getElementById("pergunta6").value.toLowerCase();
      const r7 = document.getElementById("pergunta7").value.toLowerCase();

      let output = `<strong>Olha olha... Parece que ${nome} OUSA tentar tomar o quiz sobre little leprechaun!!</strong><br><br>`;

      output += verificar(
        r1 === "14 de maio" || r1 === "14/05",
        "Já vá pensando no presente 😘",
        "Ô misera, errou."
      );

      output += verificar(
        r2 === "roxo",
        "Não parecia, né?",
        "nao KAKASDKASKDAKDASK"
      );

      output += verificar(
        r3 === "pina",
        "Só não sequestra ele viu, eu já farei isso 🤣",
        "nao;-;"
      );

      output += verificar(
        r4 === "skillet",
        "YEAHHHHHH!",
        "hm, acho que não."
      );

      output += verificar(
        r5 === "1,52",
        "Por que acha que chamam ele de leprechaun?;-; (acertou)",
        "nao"
      );

      output += verificar(
        r6 === "pansexual",
        "Quem ignora buraco é prefeitura.",
        "Sério? Errou carai;-;"
      );

      output += verificar(
        r7 === "sim",
        "Quem não?",
        "Sua execução está marcada para 4 de outubro, às 18:13 PM por errar a pergunta mais fácil do quiz😗"
      );

      document.getElementById("resultado").innerHTML = output;

      // Limpar os campos após o envio
      document.getElementById("quizForm").reset();
    });
  </script>
</body>
</html>
