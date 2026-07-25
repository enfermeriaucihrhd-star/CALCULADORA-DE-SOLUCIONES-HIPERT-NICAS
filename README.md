# CALCULADORA-DE-SOLUCIONES-HIPERT-NICAS
Ingresa volumen y concentración final de la solución requerida
<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<title>Calculadora de Soluciones Hipertónicas - UCI Honorio Delgado</title>
<style>
body { font-family: Arial; text-align: center; background-color: #f5f8ff; }
h1 { color: #003366; }
table { margin: auto; border-collapse: collapse; }
td { padding: 10px; }
input { width: 100px; text-align: center; }
.result { background-color: #e6ffe6; }
</style>
</head>
<body>
<img src="LOGO_UCI_HONORIO_DELGADO.png" alt="Logo UCI Honorio Delgado" width="200">
<h1>Calculadora de Soluciones Hipertónicas</h1>
<table border="1">
<tr><td>Volumen final (ml):</td><td><input id="volFinal" type="number"></td></tr>
<tr><td>Concentración final (%):</td><td><input id="concFinal" type="number" step="0.1"></td></tr>
<tr><td colspan="2"><button onclick="calcular()">Calcular</button></td></tr>
<tr><td>Volumen SF 0.9 % (ml):</td><td class="result" id="sf"></td></tr>
<tr><td>Volumen NaCl 20 % (ml):</td><td class="result" id="nacl"></td></tr>
</table>

<script>
function calcular() {
  let V = parseFloat(document.getElementById('volFinal').value);
  let C = parseFloat(document.getElementById('concFinal').value);
  let Vnacl = (V*C - 0.9*V)/(20 - 0.9);
  let Vsf = V - Vnacl;
  document.getElementById('sf').innerText = Vsf.toFixed(1);
  document.getElementById('nacl').innerText = Vnacl.toFixed(1);
}
</script>

<footer>
<p>Unidad de Cuidados Intensivos – Hospital Honorio Delgado</p>
</footer>
</body>
</html>
