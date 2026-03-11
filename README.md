# Calculadora-Reposteria
Calculadora de costos para empresa de postres
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Calculadora de Repostería</title>

<style>

body{
font-family: Arial;
background:#ffe6f2;
text-align:center;
padding:20px;
}

.caja{
background:white;
max-width:420px;
margin:auto;
padding:25px;
border-radius:15px;
box-shadow:0 0 12px rgba(0,0,0,0.2);
}

h1{
color:#ff4da6;
}

input{
width:90%;
padding:10px;
margin:6px;
border-radius:8px;
border:1px solid #ccc;
}

button{
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

.resultado{
margin-top:15px;
font-size:18px;
font-weight:bold;
color:#ff1493;
}

</style>
</head>

<body>

<div class="caja">

<h1>Calculadora de Costos 🍰</h1>

<h3>Ingredientes</h3>

<input type="number" id="ing1" placeholder="Ingrediente 1 (S/)">
<input type="number" id="ing2" placeholder="Ingrediente 2 (S/)">
<input type="number" id="ing3" placeholder="Ingrediente 3 (S/)">
<input type="number" id="ing4" placeholder="Ingrediente 4 (S/)">
<input type="number" id="ing5" placeholder="Ingrediente 5 (S/)">

<h3>Otros costos</h3>

<input type="number" id="manoobra" placeholder="Mano de obra (S/)">

<input type="number" id="empaque" placeholder="Empaque (S/)">

<input type="number" id="porciones" placeholder="Número de porciones">

<input type="number" id="ganancia" placeholder="Ganancia % (ej: 40)">

<button onclick="calcular()">Calcular Precio</button>

<div class="resultado" id="resultado"></div>

</div>

<script>

function calcular(){

let ing1 = Number(document.getElementById("ing1").value)
let ing2 = Number(document.getElementById("ing2").value)
let ing3 = Number(document.getElementById("ing3").value)
let ing4 = Number(document.getElementById("ing4").value)
let ing5 = Number(document.getElementById("ing5").value)

let mano = Number(document.getElementById("manoobra").value)
let empaque = Number(document.getElementById("empaque").value)
let porciones = Number(document.getElementById("porciones").value)
let ganancia = Number(document.getElementById("ganancia").value)

let costoTotal = ing1 + ing2 + ing3 + ing4 + ing5 + mano + empaque

let precioVenta = costoTotal + (costoTotal * ganancia / 100)

let precioPorcion = precioVenta / porciones

document.getElementById("resultado").innerHTML =
"Costo total: S/" + costoTotal.toFixed(2) + "<br>" +
"Precio de venta: S/" + precioVenta.toFixed(2) + "<br>" +
"Precio por porción: S/" + precioPorcion.toFixed(2)

}

</script>

</body>
</html>
