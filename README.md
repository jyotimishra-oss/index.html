<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>For Saarthak ❤️</title>

<style>
body {
  margin: 0;
  font-family: Arial, sans-serif;
  background: linear-gradient(135deg, #ffe6ef, #fff);
  text-align: center;
  overflow: hidden;
}

section {
  display: none;
  height: 100vh;
  padding: 40px 20px;
}

section.active {
  display: block;
}

h1 {
  color: #e91e63;
}

button {
  background: #ff4d6d;
  color: white;
  border: none;
  padding: 16px 30px;
  font-size: 18px;
  border-radius: 30px;
  cursor: pointer;
  margin: 10px;
}

button:hover {
  background: #e91e63;
}

.decor img {
  width: 120px;
  margin: 10px;
}

.teddy {
  width: 280px;
  margin: 20px 0;
}

/* runaway button */
#noBtn {
  background: #ccc;
  color: #000;
  position: absolute;
}

/* hearts */
.heart {
  position: fixed;
  top: -20px;
  font-size: 26px;
  animation: fall linear forwards;
}

@keyframes fall {
  to {
    transform: translateY(100vh);
    opacity: 0;
  }
}
</style>
</head>

<body>

<!-- STEP 1 -->
<section id="step1" class="active">
  <div class="decor">
    <img src="https://media.giphy.com/media/MDJ9IbxxvDUQM/giphy.gif">
    <img src="https://media.giphy.com/media/l0MYt5jPR6QX5pnqM/giphy.gif">
    <img src="https://media.giphy.com/media/3oriO0OEd9QIDdllqo/giphy.gif">
  </div>

  <h1>Hello Saarthak,</h1>
  <h2>There is an important question for you</h2>

  <button onclick="goTo(2)">Yes, Ask Me</button>
</section>

<!-- STEP 2 -->
<section id="step2">
  <h1>Do you love me? 💕</h1>

  <img class="teddy"
    src="https://media.giphy.com/media/26BRv0ThflsHCqDrG/giphy.gif">

  <div>
    <button onclick="goTo(3)">Yes</button>
    <button onclick="goTo(3)">Yes, A lot</button>
  </div>
</section>

<!-- STEP 3 -->
<section id="step3">
  <h1>Will you be my valentine? 💖</h1>

  <button onclick="goTo(4)">Yes</button>
  <button id="noBtn" onmouseover="moveNo()">No</button>
</section>

<!-- STEP 4 -->
<section id="step4">
  <h1>See you on 14th, my love! 💘</h1>
</section>

<script>
function goTo(step) {
  document.querySelectorAll("section").forEach(s => s.classList.remove("active"));
  document.getElementById("step" + step).classList.add("active");

  if (step === 4) startHearts();
}

function moveNo() {
  const btn = document.getElementById("noBtn");
  btn.style.left = Math.random() * (window.innerWidth - 120) + "px";
  btn.style.top = Math.random() * (window.innerHeight - 60) + "px";
}

function startHearts() {
  setInterval(() => {
    const heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (3 + Math.random() * 3) + "s";
    document.body.appendChild(heart);
    setTimeout(() => heart.remove(), 6000);
  }, 250);
}
</script>

</body>
</html>
