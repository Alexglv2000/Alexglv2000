<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>TheGreyHat - Preview</title>
  <style>
    body {
      background-color: #0d1117;
      color: white;
      font-family: sans-serif;
    }

    .led-frame {
      display: flex;
      justify-content: center;
      align-items: center;
      margin-top: 40px;
      padding: 12px;
      border-radius: 20px;
      background: #0d1117;
      animation: glow 2s infinite alternate;
      box-shadow: 0 0 25px rgba(0, 255, 255, 0.3);
    }

    .led-frame img {
      width: 450px;
      border-radius: 14px;
      box-shadow: 0 0 12px rgba(0, 255, 255, 0.2);
    }

    @keyframes glow {
      0% {
        box-shadow: 0 0 10px rgba(0, 255, 255, 0.2), 0 0 20px rgba(0, 255, 255, 0.3);
      }
      100% {
        box-shadow: 0 0 20px rgba(0, 255, 255, 0.5), 0 0 40px rgba(0, 255, 255, 0.8);
      }
    }

    hr {
      border: 1px solid #3498db;
      margin: 40px 0;
    }

    h2 {
      text-align: center;
    }

    ul {
      line-height: 1.8;
      max-width: 700px;
      margin: auto;
      font-size: 16px;
    }

    strong {
      color: #00ffff;
    }
  </style>
</head>
<body>

  <div class="led-frame">
    <a href="https://thegreyhat.vercel.app" target="_blank">
      <img src="https://image.thum.io/get/width/800/https://thegreyhat.vercel.app" alt="Live preview">
    </a>
  </div>

  <hr>

  <h2>Confusion is part of Programming</h2>

  <ul>
    <li>🌱 I am currently learning how to build applications with scalable <strong>micro services</strong>.</li>
    <li>☁️ I have great interest in <strong>cloud computing</strong> as well as <strong>cybersecurity</strong> using different tools.</li>
    <li>💬 Ask me about <strong>java</strong>, <strong>web programming</strong> as well as <strong>styles for web pages</strong>.</li>
    <li>📫 Don't hesitate to contact me: <strong>alexglv2000@gmail.com</strong></li>
    <li>🏠 I am also interested in projects making <strong>100% free energy</strong> prototypes.</li>
  </ul>

</body>
</html>

