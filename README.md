<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ali Essam - Profile</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@900&family=Space+Mono:wght@400;700&display=swap" rel="stylesheet">
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }
  body {
    background: #080d12;
    color: #c9d1d9;
    font-family: 'Space Mono', monospace;
    min-height: 100vh;
  }

  .hero {
    padding: 60px 40px 30px;
    position: relative;
    overflow: hidden;
  }

  .hero-greeting {
    font-size: 16px;
    color: #8b949e;
    margin-bottom: 16px;
    letter-spacing: 2px;
    text-transform: uppercase;
    animation: fadeIn 1s ease both;
  }

  .hero-name {
    font-family: 'Orbitron', monospace;
    font-weight: 900;
    font-size: clamp(64px, 13vw, 160px);
    line-height: 0.95;
    letter-spacing: -2px;
    color: #58ffdb;
    text-shadow:
      0 0 10px #58ffdb,
      0 0 30px #58ffdb,
      0 0 60px #00e5c4,
      0 0 120px #00b8ff,
      0 0 200px #0066ff;
    animation: flicker 3s infinite alternate, fadeIn 1s ease both;
    margin-bottom: 20px;
  }

  .hero-wave {
    display: inline-block;
    font-size: clamp(40px, 6vw, 80px);
    animation: wave 1.5s ease-in-out infinite;
    text-shadow: none;
  }

  @keyframes flicker {
    0%, 19%, 21%, 23%, 25%, 54%, 56%, 100% {
      text-shadow:
        0 0 10px #58ffdb,
        0 0 30px #58ffdb,
        0 0 60px #00e5c4,
        0 0 120px #00b8ff,
        0 0 200px #0066ff;
    }
    20%, 24%, 55% {
      text-shadow: none;
      color: #3acdaa;
    }
  }

  @keyframes wave {
    0%, 100% { transform: rotate(0deg); }
    25% { transform: rotate(20deg); }
    75% { transform: rotate(-10deg); }
  }

  @keyframes fadeIn {
    from { opacity: 0; transform: translateY(20px); }
    to { opacity: 1; transform: translateY(0); }
  }

  .hero::after {
    content: '';
    position: absolute;
    inset: 0;
    background: repeating-linear-gradient(
      0deg,
      transparent,
      transparent 2px,
      rgba(0,0,0,0.05) 2px,
      rgba(0,0,0,0.05) 4px
    );
    pointer-events: none;
  }

  .matrix-panel {
    position: absolute;
    top: 0; right: 0;
    width: 300px; height: 340px;
    overflow: hidden;
    opacity: 0.4;
  }

  hr { border: none; border-top: 1px solid #1a2332; margin: 0 40px 30px; }

  .bio {
    padding: 0 40px 30px;
    max-width: 600px;
    font-size: 15px;
    line-height: 1.8;
    color: #8b949e;
  }
  .bio strong { color: #58ffdb; }

  .section-title {
    padding: 0 40px;
    font-family: 'Orbitron', monospace;
    font-size: 18px;
    color: #58ffdb;
    text-shadow: 0 0 10px #58ffdb, 0 0 25px #00b8ff;
    margin-bottom: 18px;
    letter-spacing: 3px;
    text-transform: uppercase;
  }

  .tools {
    padding: 0 40px 30px;
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
  }

  .tool-badge {
    background: transparent;
    border: 1px solid #58ffdb44;
    border-radius: 4px;
    padding: 7px 14px;
    font-size: 12px;
    color: #58ffdb;
    letter-spacing: 1px;
    transition: all 0.2s;
    cursor: default;
    font-family: 'Space Mono', monospace;
  }
  .tool-badge:hover {
    border-color: #58ffdb;
    box-shadow: 0 0 12px #58ffdb66;
    background: #58ffdb11;
  }

  .current-work {
    padding: 0 40px 30px;
  }
  .current-work ul { list-style: none; display: flex; flex-direction: column; gap: 14px; }
  .current-work li {
    display: flex;
    align-items: center;
    gap: 12px;
    font-size: 14px;
    color: #8b949e;
  }
  .current-work li strong { color: #c9d1d9; }
  .current-work li .icon { font-size: 18px; }

  .connect {
    text-align: center;
    padding: 30px 40px 60px;
  }
  .connect h2 {
    font-family: 'Orbitron', monospace;
    font-size: 16px;
    letter-spacing: 4px;
    margin-bottom: 22px;
    color: #58ffdb;
    text-shadow: 0 0 10px #58ffdb;
    text-transform: uppercase;
  }
  .connect-links {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
  }
  .connect-links a {
    padding: 10px 20px;
    border-radius: 4px;
    font-size: 12px;
    font-family: 'Space Mono', monospace;
    font-weight: bold;
    text-decoration: none;
    letter-spacing: 1px;
    transition: all 0.2s;
  }
  .connect-links a:hover { transform: translateY(-3px); filter: brightness(1.2); box-shadow: 0 4px 20px rgba(88,255,219,0.3); }
  .linkedin { background: #0a66c2; color: white; }
  .instagram { background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888); color: white; }
  .twitter { background: #1d9bf0; color: white; }
  .gmail { background: #ea4335; color: white; }
  .behance { background: #1769ff; color: white; }
  .facebook { background: #1877f2; color: white; }
</style>
</head>
<body>

<div class="hero">
  <div class="matrix-panel"><canvas id="matrix" width="300" height="340"></canvas></div>
  <p class="hero-greeting">Hey, welcome 👾</p>
  <h1 class="hero-name">Ali<br>Essam <span class="hero-wave">👋</span></h1>
</div>

<hr>

<p class="bio">
  I graduated with a degree in Computer Science from <strong>HTI</strong>. I am skilled in
  <strong>Python and Data Engineering</strong>, and I also have experience in photography and photo editing.
</p>

<div class="section-title">// Languages & Tools</div>
<div class="tools">
  <span class="tool-badge">Bootstrap</span>
  <span class="tool-badge">CSS3</span>
  <span class="tool-badge">HTML5</span>
  <span class="tool-badge">Illustrator</span>
  <span class="tool-badge">JavaScript</span>
  <span class="tool-badge">MySQL</span>
  <span class="tool-badge">Python</span>
  <span class="tool-badge">Sass</span>
  <span class="tool-badge">NumPy</span>
  <span class="tool-badge">TensorFlow</span>
</div>

<div class="section-title">// Current Work</div>
<div class="current-work">
  <ul>
    <li><span class="icon">💻</span> Graduated in Computer Science from <strong>HTI</strong></li>
    <li><span class="icon">🔄</span> Passionate about <strong>Python</strong> and <strong>Data Engineering</strong></li>
    <li><span class="icon">📷</span> Skilled in <strong>photography</strong> and photo editing</li>
  </ul>
</div>

<hr>

<div class="connect">
  <h2>// Connect with me</h2>
  <div class="connect-links">
    <a href="#" class="linkedin">LINKEDIN</a>
    <a href="#" class="instagram">📷 INSTAGRAM</a>
    <a href="#" class="twitter">TWITTER</a>
    <a href="#" class="gmail">M GMAIL</a>
    <a href="#" class="behance">Bē BEHANCE</a>
    <a href="#" class="facebook">FACEBOOK</a>
  </div>
</div>

<script>
  const canvas = document.getElementById('matrix');
  const ctx = canvas.getContext('2d');
  const chars = '01アイウエオカキクケコサシスセソタチツテトナニヌネノ';
  const fontSize = 12;
  const cols = Math.floor(canvas.width / fontSize);
  const drops = Array(cols).fill(1);

  function drawMatrix() {
    ctx.fillStyle = 'rgba(8,13,18,0.05)';
    ctx.fillRect(0, 0, canvas.width, canvas.height);
    ctx.font = fontSize + 'px monospace';
    drops.forEach((y, i) => {
      const char = chars[Math.floor(Math.random() * chars.length)];
      ctx.fillStyle = Math.random() > 0.9 ? '#ffffff' : '#58ffdb';
      ctx.globalAlpha = Math.random() * 0.5 + 0.3;
      ctx.fillText(char, i * fontSize, y * fontSize);
      ctx.globalAlpha = 1;
      if (y * fontSize > canvas.height && Math.random() > 0.975) drops[i] = 0;
      drops[i]++;
    });
  }
  setInterval(drawMatrix, 50);
</script>
</body>
</html>
