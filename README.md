<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>dflynjeri</title>
  <link rel="stylesheet" href="style.css" />
  <link href="https://fonts.googleapis.com/css2?family=Unica+One&family=Montserrat:wght@300;500;700&display=swap" rel="stylesheet" />
</head>
<body>
  <div class="container">
    <div class="logo">
      <!-- You can replace with your custom SVG later -->
      <img src="dragonfly.svg" alt="dragonfly logo" />
    </div>
    <h1 class="headline">Hey there 👋, I’m <span>dflynjeri</span></h1>
    <p class="subhead">🛠 Backend Engineer • UI/UX Enthusiast • Cybersecurity & AI Explorer</p>
    <div class="stats">
      <img src="https://komarev.com/ghpvc/?username=dflynjeri&label=Profile%20views&color=6a042e&style=flat" alt="profile views" />
      <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=dflynjeri&hide_progress=true&theme=dark&bg_color=0d1117" alt="top langs" class="langs"/>
    </div>
    <div class="buttons">
      <a href="https://github.com/dflynjeri" class="btn" target="_blank">GitHub Profile</a>
      <a href="mailto:youremail@example.com" class="btn secondary">Email Me</a>
    </div>
  </div>
  <script src="script.js"></script>
</body>
</html>
/* Fonts & Reset */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  background: #0a0f26;
  color: #dcdce1;
  font-family: 'Montserrat', sans-serif;
  height: 100vh;
  overflow: hidden;
  display: flex;
  align-items: center;
  justify-content: center;
}
.container {
  text-align: center;
  max-width: 640px;
  padding: 20px;
  position: relative;
  z-index: 2;
}
.logo img {
  width: 100px;
  animation: float 4s ease-in-out infinite;
}
.headline {
  font-family: 'Unica One', cursive;
  font-size: 2.8rem;
  margin-top: 15px;
}
.headline span {
  color: #8b0000;
}
.subhead {
  margin-top: 10px;
  font-size: 1.1rem;
  opacity: 0.9;
}
.stats {
  margin: 20px auto;
  display: flex;
  justify-content: center;
  gap: 20px;
}
.langs {
  height: 120px;
}
.buttons {
  margin-top: 25px;
  display: flex;
  justify-content: center;
  gap: 15px;
}
.btn {
  background: #6a042e;
  color: #f7f7f7;
  padding: 12px 24px;
  font-weight: 500;
  border-radius: 50px;
  text-decoration: none;
  position: relative;
  overflow: hidden;
}
.btn::after {
  content: '';
  position: absolute;
  width: 0;
  height: 100%;
  top: 0;
  left: 0;
  background: rgba(255,255,255,0.15);
  transition: width 0.4s ease-in-out;
}
.btn:hover::after {
  width: 100%;
}
.secondary {
  background: transparent;
  border: 2px solid #6a042e;
}

/* Floating animation */
@keyframes float {
  0%, 100% { transform: translateY(0) rotate(0deg); }
  50% { transform: translateY(-15px) rotate(-5deg); }
}

/* Night-sky particles */
body::before {
  content: '';
  position: absolute;
  width: 200%;
  height: 200%;
  background: transparent;
  top: -50%;
  left: -50%;
  z-index: 1;
  background-image: radial-gradient(#ffffff22 1px, transparent 1px);
  background-size: 30px 30px;
  animation: starspin 200s linear infinite;
}
@keyframes starspin {
  from { transform: rotate(0deg); }
  to { transform: rotate(360deg); }
}
// Simple headline typing effect
const headline = document.querySelector('.headline');
const fullText = headline.textContent;
headline.textContent = '';
let charIndex = 0;
function typeChar() {
  headline.textContent = fullText.slice(0, ++charIndex);
  if (charIndex < fullText.length) {
    setTimeout(typeChar, Math.random() * 100 + 50);
  }
}
window.onload = () => typeChar();
