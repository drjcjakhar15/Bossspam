# Bossspam<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Be My Valentine 💖</title>
  <style>
    * { box-sizing: border-box; }
    body {
      margin: 0;
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      background: linear-gradient(135deg, #ff9a9e, #fad0c4);
      font-family: 'Poppins', Arial, sans-serif;
      overflow: hidden;
    }
    #container {
      text-align: center;
      background: white;
      padding: 35px 30px;
      border-radius: 18px;
      box-shadow: 0 20px 40px rgba(0,0,0,0.15);
      width: 90%;
      max-width: 360px;
      position: relative;
    }
    h1 {
      font-size: 24px;
      margin-bottom: 25px;
      color: #ff4d6d;
      animation: pulse 2s infinite;
    }
    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.05); }
      100% { transform: scale(1); }
    }
    button {
      margin: 10px;
      padding: 12px 26px;
      font-size: 16px;
      cursor: pointer;
      border-radius: 30px;
      border: none;
      transition: transform 0.15s ease, box-shadow 0.15s ease;
    }
    button:active {
      transform: scale(0.95);
    }
    #yesBtn {
      background: #ff4d6d;
      color: white;
      box-shadow: 0 8px 18px rgba(255,77,109,0.4);
    }
    #noBtn {
      background: #adb5bd;
      color: white;
      position: absolute;
    }
    .heart {
      position: fixed;
      bottom: -20px;
      font-size: 20px;
      animation: floatUp 4s linear forwards;
    }
    @keyframes floatUp {
      0% { transform: translateY(0) scale(1); opacity: 1; }
      100% { transform: translateY(-110vh) scale(1.5); opacity: 0; }
    }
  </style>
</head>
<body>
  <div id="container">
    <h1 id="question">Dr Rohini 💖<br>Will you be my Valentine?<br><span style="font-size:14px;color:#666;">— by <span style="font-family:cursive;">Dr JC Jakhar ✨</span></span></h1>
    <button id="yesBtn" onclick="handleYes()">Yes 💖</button>
    <button id="noBtn" onclick="handleNo()">No 🙃</button>
    <button id="shareBtn" onclick="shareInstagram()" style="display:none;margin-top:15px;background:#E1306C;color:white;">Share on Instagram 📸</button>
  </div>  <script>
    const noBtn = document.getElementById('noBtn');
    const container = document.getElementById('container');

    // place No button initially
    noBtn.style.left = '55%';
    noBtn.style.top = '70%';

    function handleYes() {
      document.getElementById('question').innerText = 'Yaaay! 💕 You are my Valentine!';
      noBtn.style.display = 'none';
      document.getElementById('shareBtn').style.display = 'inline-block';
      launchHearts();
      launchHearts();
      launchHearts();
    }

    function handleNo() {
      const rect = container.getBoundingClientRect();
      const x = Math.random() * (rect.width - 100);
      const y = Math.random() * (rect.height - 50);
      noBtn.style.left = x + 'px';
      noBtn.style.top = y + 'px';
      noBtn.style.transform = `rotate(${Math.random()*20 - 10}deg)`;
    }

    function launchHearts() {
      for (let i = 0; i < 15; i++) {
        const heart = document.createElement('div');
        heart.className = 'heart';
        heart.innerText = '💖';
        heart.style.left = Math.random() * 100 + 'vw';
        heart.style.animationDuration = (3 + Math.random() * 2) + 's';
        document.body.appendChild(heart);
        setTimeout(() => heart.remove(), 5000);
      }
    }

    function shareInstagram() {
      const text = 'I just said YES! 💖 Will you be my Valentine?';
      const url = window.location.href;
      // Instagram does not support direct web sharing, so we use story intent
      const shareUrl = `https://www.instagram.com/stories/create/?text=${encodeURIComponent(text)}%20${encodeURIComponent(url)}`;
      window.open(shareUrl, '_blank');
    }
    }
  </script></body>
</html>
