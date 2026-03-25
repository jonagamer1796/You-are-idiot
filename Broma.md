<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>LOL</title>

<style>
body {
  background: black;
  color: red;
  font-family: monospace;
  text-align: center;
  overflow: hidden;
}

h1 {
  font-size: 40px;
  animation: shake 0.2s infinite;
}

@keyframes shake {
  0% { transform: translate(2px, 2px); }
  25% { transform: translate(-2px, -2px); }
  50% { transform: translate(2px, -2px); }
  75% { transform: translate(-2px, 2px); }
  100% { transform: translate(2px, 2px); }
}

#fakeData {
  position: fixed;
  bottom: 10px;
  width: 100%;
  font-size: 18px;
  color: lime;
}
</style>
</head>

<body>

<h1 onclick="activar()">YOU ARE AN IDIOT 😂</h1>

<div id="fakeData">
  <p>Accediendo al sistema...</p>
  <p id="data"></p>
</div>

<audio id="audio" loop>
  <source src="https://www.myinstants.com/media/sounds/windows-error.mp3">
</audio>

<script>
function randomNum(len) {
  let result = "";
  for (let i = 0; i < len; i++) {
    result += Math.floor(Math.random() * 10);
  }
  return result;
}

function generateFakeData() {
  return `
  ID: ${randomNum(9)}<br>
  IP: ${randomNum(3)}.${randomNum(3)}.${randomNum(3)}.${randomNum(3)}<br>
  TOKEN: ${randomNum(16)}<br>
  KEY: ${randomNum(12)}<br>
  DEVICE: ${randomNum(8)}-${randomNum(4)}
  `;
}

setInterval(() => {
  document.getElementById("data").innerHTML = generateFakeData();
}, 800);

// ACTIVAR (necesario para GitHub Pages por el audio)
function activar() {
  let el = document.documentElement;

  if (el.requestFullscreen) {
    el.requestFullscreen();
  }

  let audio = document.getElementById("audio");
  audio.play().catch(() => {});
}
</script>

</body>
</html>
