<index.html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Calculadora de Repostería Perú</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background:#ffe6f2;
      text-align:center;
      padding:20px;
    }
    .caja {
      background:white;
      max-width:420px;
      margin:auto;
      padding:25px;
      border-radius:15px;
      box-shadow:0 0 12px rgba(0,0,0,0.2);
    }
    h1 { color:#ff4da6; }
    input, select {
      width:90%;
      padding:10px;
      margin:6px;
      border-radius:8px;
      border:1px solid #ccc;
    }
    button {
      background:#ff4da6;
      color:white;
      border:none;
      padding:12px;
      margin-top:10px;
      border-radius:10px;
      cursor:pointer;
      width:90%;
      font-size:16px;
    }
    .resultado {
      margin-top:15px;
      font-size:18px;
      font-weight:bold;
      color:#ff1493;
    }
  </style>
</head>
<body>
<div class="caja">
  <h1>Calculadora de Costos Perú 🍰</h1>

  <h3>Ingredientes Principales</h3>
  <input type="number" id="harina" placeholder="Harina (S/) * ej: 5">
  <input type="number" id="azucar" placeholder="Azúcar (S/) * ej: 3">
  <input type="number" id="huevos" placeholder="Huevos (S/) * ej: 4">
  <input type="number" id="mantequilla" placeholder="Mantequilla (S/) * ej: 10">
  <input type="number" id="leche" placeholder="Leche (S/) * ej: 2">

  <h3>Otros costos</h3>
  <input type="number" id="manoobra" placeholder="Mano de obra (S/) * ej: 15">
  <input type="number" id="empaque" placeholder="Caja/empaque (S/) * ej: 3">

  <input type="number" id="porciones" placeholder="Número de porciones * ej: 12">
  <input type="number" id="ganancia" placeholder="Ganancia % (ej: 35)">

  <button onclick="calcular()">Calcular Precio</button>

  <div class="resultado" id="resultado"></div>
</div>

<script>
function calcular(){
  let harina = Number(document.getElementById("harina").value) || 0;
  let azucar = Number(document.getElementById("azucar").value) || 0;
  let huevos = Number(document.getElementById("huevos").value) || 0;
  let mantequilla = Number(document.getElementById("mantequilla").value) || 0;
  let leche = Number(document.getElementById("leche").value) || 0;

  let mano = Number(document.getElementById("manoobra").value) || 0;
  let empaque = Number(document.getElementById("empaque").value) || 0;
  let porciones = Number(document.getElementById("porciones").value) || 1;
  let ganancia = Number(document.getElementById("ganancia").value) || 0;

  let costoTotal = harina + azucar + huevos + mantequilla + leche + mano + empaque;
  let precioVenta = costoTotal + (costoTotal * ganancia / 100);
  let precioPorcion = precioVenta / porciones;

  document.getElementById("resultado").innerHTML =
    "Costo total: S/" + costoTotal.toFixed(2) + "<br>" +
    "Precio de venta: S/" + precioVenta.toFixed(2) + "<br>" +
    "Precio por porción: S/" + precioPorcion.toFixed(2);
}
</script>
</body>
</html>
