<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>inniedoobee gom!</title>
  <link href="https://fonts.googleapis.com/css2?family=Manrope:wght@400;600&display=swap" rel="stylesheet">
  <style>
    html, body {
      margin: 0;
      height: 100%;
      font-family: 'Manrope', sans-serif;
      background: #f5d6ff;
      color: #5a3e2b;
      display: flex;
      justify-content: center;
      align-items: center;
      text-align: center;
      background-size: cover;
      background-position: center;
      background-repeat: no-repeat;
    }

    .container {
      background-color: #fbfdf7;
      padding: 40px;
      border-radius: 20px;
      max-width: 500px;
      width: 90%;
      box-sizing: border-box;
      box-shadow: 0 4px 12px rgba(0,0,0,0.1);
    }

    img {
      max-width: 280px;
      margin-bottom: 20px;
      width: 100%;
      height: auto;
    }

    input, button {
      padding: 12px;
      font-size: 18px;
      margin: 10px 5px;
      border-radius: 10px;
      border: 1px solid #a68c6d;
      font-family: inherit;
    }

    button {
      background-color: #a7795c;
      color: white;
      cursor: pointer;
      border: none;
    }

    .resultado {
      margin-top: 20px;
      font-size: 22px;
      font-weight: bold;
    }

    #aclaracion {
      font-size: 14px;
      color: #5a3e2b;
    }

    @media (max-width: 768px) {
      .container {
        padding: 25px;
      }

      input, button {
        font-size: 16px;
        padding: 10px;
      }

      .resultado {
        font-size: 20px;
      }

      #aclaracion {
        font-size: 13px;
      }

      img {
        max-width: 85%;
        margin-bottom: 15px;
      }
    }
  </style>
</head>
<body>
  <div class="container">
    <img src="https://i.imgur.com/kmRam5G.png" alt="logo" />
    <p>cotiza tus links acá ( ﾉ^ω^)ﾉ</p>
    <input type="number" id="idr" placeholder="Ej: 15000">
    <button onclick="calcular()">Cotizar</button>

    <div class="resultado" id="resultado"></div>
    <p id="aclaracion"></p>
  </div>

  <script>
    function calcular() {
      const tasaCambio = 1550 / 15550;
      const idr = parseFloat(document.getElementById("idr").value);

      if (isNaN(idr)) {
        document.getElementById("resultado").innerText = "Por favor, ingresá un número válido.";
        document.getElementById("aclaracion").innerText = "";
        return;
      }

      const ars = idr * tasaCambio;
      document.getElementById("resultado").innerText = `≈ $${ars.toFixed(2)} ARS`;
      document.getElementById("aclaracion").innerText = "precio sin fees!";
    }
  </script>
</body>
</html>
