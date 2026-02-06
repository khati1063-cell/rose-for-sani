<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For My Sani 🌹</title>

<style>
body {
  margin: 0;
  height: 100vh;
  background: linear-gradient(135deg, #ff758c, #ff7eb3);
  display: flex;
  justify-content: center;
  align-items: center;
  font-family: 'Segoe UI', sans-serif;
  overflow: hidden;
}

.card {
  background: white;
  padding: 30px;
  border-radius: 25px;
  text-align: center;
  box-shadow: 0 15px 40px rgba(0,0,0,0.25);
  max-width: 500px;
  position: relative;
  z-index: 2;
}

h1 { color: #d1003f; }

button {
  padding: 12px 25px;
  border: none;
  border-radius: 30px;
  background: #d1003f;
  color: white;
  font-size: 16px;
  cursor: pointer;
  margin-top: 15px;
}

button:hover { background: #a00030; }

#message { margin-top: 15px; min-height: 120px; }

#loveGlow {
  font-size: 22px;
  color: #ff004c;
  text-shadow: 0 0 10px #ff4d6d, 0 0 20px #ff1a4d;
  opacity: 0;
  transition: 2s;
}

#signature {
  margin-top: 10px;
  font-weight: bold;
  font-size: 20px;
  opacity: 0;
  transition: 2s;
  color: #d1003f;
}

img {
  width: 200px;
  border-radius: 20px;
  margin-top: 10px;
  box-shadow: 0 10px 25px rgba(0,0,0,0.3);
}

.rose {
  position: absolute;
  font-size: 26px;
  animation: fall linear infinite;
}

@keyframes fall {
  0% { transform: translateY(-100px); opacity: 1; }
  100% { transform: translateY(100vh); opacity: 0; }
}

canvas {
  position: absolute;
  top: 0;
  left: 0;
  z-index: 1;
}
</style>
</head>
<body>

<audio autoplay loop>
  <source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_9d7c2f7b8b.mp3" type="audio/mpeg">
</audio>

<audio id="heartbeat">
  <source src="https://cdn.pixabay.com/download/audio/2021/08/04/audio_88447a0e2e.mp3" type="audio/mpeg">
</audio>

<canvas id="fireworks"></canvas>

<div class="card">
  <h1>🌹 Happy Rose Day Sani 💋</h1>

  <!-- Your Real Photo -->
  <img src="YOUR_IMAGE_FILE_NAME.jpg" alt="Arjun & Sani">

  <p>मेरो मुटुले तिमीलाई केही भन्न चाहन्छ...</p>
  <button onclick="celebrate()">Open Your Roses ❤️</button>

  <div id="message"></div>
  <div id="loveGlow">I Love You Sani ❤️</div>
  <div id="signature">सधैं तिम्रो,<br>Arjun ❤️</div>

  <button id="proposalBtn" style="display:none;">Will You Be Mine Forever? 💍</button>
</div>

<script>
const text = "सानी 💋 तिमी मेरो जीवनको सबैभन्दा सुन्दर फूल हौ 🌹। तिम्रो मुस्कान मेरो शान्ति हो, तिम्रो साथ मेरो शक्ति हो। तिमी बिना मेरो संसार अधुरो छ। मेरो मुटु सधैं तिम्रै नामले धड्किन्छ ❤️";

let index = 0;

function celebrate() {
  document.getElementById("message").innerHTML = "";
  index = 0;
  typeText();
  createRoses();
}

function typeText() {
  if (index < text.length) {
    document.getElementById("message").innerHTML += text.charAt(index);
    index++;
    setTimeout(typeText, 40);
  } else {
    showEnding();
  }
}

function showEnding() {
  document.getElementById("loveGlow").style.opacity = 1;
  document.getElementById("signature").style.opacity = 1;
  document.getElementById("proposalBtn").style.display = "inline-block";
  document.getElementById("heartbeat").play();
  startFireworks();
}

function createRoses() {
  for (let i = 0; i < 40; i++) {
    let rose = document.createElement("div");
    rose.classList.add("rose");
    rose.innerHTML = "🌹";
    rose.style.left = Math.random() * window.innerWidth + "px";
    rose.style.animationDuration = (Math.random() * 3 + 2) + "s";
    document.body.appendChild(rose);
  }
}

const canvas = document.getElementById("fireworks");
const ctx = canvas.getContext("2d");
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;

function startFireworks() {
  setInterval(() => {
    let x = Math.random() * canvas.width;
    let y = Math.random() * canvas.height / 2;
    for (let i = 0; i < 20; i++) {
      ctx.beginPath();
      ctx.arc(x + Math.random()*60-30, y + Math.random()*60-30, 3, 0, 2*Math.PI);
      ctx.fillStyle = "white";
      ctx.fill();
    }
  }, 500);
}
</script>

</body>
</html>
