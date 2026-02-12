# San-valentin
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Para mi reina 💖</title>
  <style>
    body {
      margin: 0;
      padding: 0;
      font-family: 'Arial', sans-serif;
      background: linear-gradient(135deg, #ff758c, #ff7eb3);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      color: #fff;
      text-align: center;
    }

    .card {
      background: rgba(255,255,255,0.15);
      padding: 30px 25px;
      border-radius: 18px;
      max-width: 350px;
      width: 90%;
      box-shadow: 0 10px 25px rgba(0,0,0,0.2);
      animation: fadeIn 1s ease;
    }

    h1, h2, p {
      margin-bottom: 15px;
    }

    button {
      padding: 12px 22px;
      border: none;
      border-radius: 12px;
      font-size: 18px;
      cursor: pointer;
      transition: all 0.3s ease;
    }

    .btn-si {
      background: #00ffb3;
      color: #000;
      margin-right: 10px;
      font-weight: bold;
    }

    .btn-no {
      background: #ff4d6d;
      color: white;
      font-weight: bold;
    }

    .hidden {
      display: none;
    }

    @keyframes fadeIn {
      from {opacity: 0; transform: scale(0.9);}
      to {opacity: 1; transform: scale(1);}
    }
  </style>
</head>
<body>

  <audio id="musica" loop>
    <source src="https://dl.sndup.net/5n8m/amor-emanuel-cortez.mp3" type="audio/mpeg">
  </audio>

  <div class="card" id="pantalla1">
    <h1>Hola mi reina 👑</h1>
    <p>Tengo algo que decirte 💕</p>
    <p><strong>Dale click a la pantalla</strong></p>
    <button onclick="mostrarPregunta()">💖</button>
  </div>

  <div class="card hidden" id="pantalla2">
    <h2 id="textoPregunta">¿Quieres ser mi San Valentín? 🥺💘</h2>
    <p>Te llevaré a la luna 🌙✨</p>
    <div>
      <button class="btn-si" id="btnSi" onclick="aceptar()">Sí 💖</button>
      <button class="btn-no" id="btnNo" onclick="negar()">No 😢</button>
    </div>
  </div>

  <div class="card hidden" id="pantalla3">
    <h2>Gracias por aceptar ser mi San Valentín 💕</h2>
    <p>Eres la mejor, prometo ser el mejor hombre del mundo para poder hacerte feliz.</p>
    <p>Gracias por llenar mis días de amor y espero que disfrutes el día que tengamos nuestra cita.</p>
    <p><strong>Te amo con toda mi alma mi reina 👑💖</strong></p>
  </div>

  <script>
    let contador = 0;
    let frases = [
      "¿Segura? 😳",
      "¿Segura segura? 🥺",
      "¿Segurísima? 😭",
      "Piénsalo bien mi niña 💔",
      "Ándale di que sí 🥹",
      "No seas malita 😞",
      "Mi reina por favor 😭💘"
    ];

    function mostrarPregunta() {
      document.getElementById("pantalla1").classList.add("hidden");
      document.getElementById("pantalla2").classList.remove("hidden");

      let musica = document.getElementById("musica");
      musica.play();
      musica.volume = 0.6;
    }

    function negar() {
      contador++;
      let texto = document.getElementById("textoPregunta");
      texto.innerText = frases[Math.min(contador - 1, frases.length - 1)];

      let btnSi = document.getElementById("btnSi");
      let tamaño = 18 + contador * 6;
      btnSi.style.fontSize = tamaño + "px";
      btnSi.style.padding = (12 + contador * 4) + "px " + (22 + contador * 6) + "px";
    }

    function aceptar() {
      document.getElementById("pantalla2").classList.add("hidden");
      document.getElementById("pantalla3").classList.remove("hidden");
    }
  </script>

</body>
</html>
