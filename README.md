<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Gabo's Profile</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background-color: #f4f4f4;
      margin: 0;
      padding: 0;
    }
    img {
      width: 100%;
    }
    #user-content-toc h1, #user-content-toc h2 {
      color: #3498db;
      text-align: center;
    }
    hr {
      border: 1px solid #3498db;
      margin: 20px 0;
    }
    .game-container {
      display: flex;
      justify-content: center;
      align-items: center;
      flex-direction: column;
    }
    canvas {
      background-color: #000;
      border: 3px solid #3498db;
      border-radius: 10px;
      box-shadow: 5px 5px 15px rgba(0, 0, 0, 0.2);
    }
    ul {
      list-style-type: none;
      padding: 0;
      margin: 20px auto;
      max-width: 600px;
    }
    ul li {
      font-size: 18px;
      margin-bottom: 10px;
      color: #333;
    }
    ul li strong {
      color: #3498db;
    }
    /* Intro text center */
    ul li {
      text-align: center;
    }

  </style>
</head>
<body>

<!-- Horizontal divider (gradient) -->
<img src="https://user-images.githubusercontent.com/73097560/115834477-dbab4500-a447-11eb-908a-139a6edaec5c.gif" alt="divider">

<!-- h1 without bottom border -->
<div id="user-content-toc">
  <ul align="center">
    <summary><h1 style="display: inline-block">Hi 👋, I'm Gabo</h1></summary>
  </ul>
</div>

<hr>

<!-- Snake Game Section -->
<div class="game-container">
  <h2>Play Snake Game 🐍</h2>
  <canvas id="gameCanvas" width="400" height="400"></canvas>
</div>

<!-- h2 without bottom border -->
<div id="user-content-toc">
  <ul align="center">
    <summary><h2 style="display: inline-block">Confusion is part of Programming</h2></summary>
  </ul>
</div>

<!-- Intro start -->
<ul>
  <li>🌱 I am currently learning how to build applications with scalable <strong>micro services</strong>.</li>
  <li>☁️ I have great interest in <strong>cloud computing</strong> as well as <strong>cybersecurity</strong> using different tools.</li>
  <li>💬 Ask me about <strong>java</strong>, <strong>web programming</strong> as well as <strong>styles for web pages</strong>.</li>
  <li>📫 Don't hesitate to contact me: <strong>alexglv2000@gmail.com</strong></li>
  <li>🏠 I am also interested in projects making <strong>100% free energy</strong> prototypes.</li>
</ul>
<!-- Intro end -->

<!-- Snake Game Script -->
<script>
  const canvas = document.getElementById("gameCanvas");
  const ctx = canvas.getContext("2d");

  const box = 20;
  let snake = [];
  snake[0] = { x: 9 * box, y: 10 * box };
  let direction;
  let food = {
    x: Math.floor(Math.random() * 19 + 1) * box,
    y: Math.floor(Math.random() * 19 + 1) * box
  };
  let score = 0;

  document.addEventListener("keydown", setDirection);

  function setDirection(event) {
    if (event.keyCode == 37 && direction != "RIGHT") direction = "LEFT";
    else if (event.keyCode == 38 && direction != "DOWN") direction = "UP";
    else if (event.keyCode == 39 && direction != "LEFT") direction = "RIGHT";
    else if (event.keyCode == 40 && direction != "UP") direction = "DOWN";
  }

  function collision(head, array) {
    for (let i = 0; i < array.length; i++) {
      if (head.x == array[i].x && head.y == array[i].y) {
        return true;
      }
    }
    return false;
  }

  function drawGame() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);

    for (let i = 0; i < snake.length; i++) {
      ctx.fillStyle = i == 0 ? "#3498db" : "white";
      ctx.fillRect(snake[i].x, snake[i].y, box, box);
      ctx.strokeStyle = "black";
      ctx.strokeRect(snake[i].x, snake[i].y, box, box);
    }

    ctx.fillStyle = "red";
    ctx.fillRect(food.x, food.y, box, box);

    let snakeX = snake[0].x;
    let snakeY = snake[0].y;

    if (direction == "LEFT") snakeX -= box;
    if (direction == "UP") snakeY -= box;
    if (direction == "RIGHT") snakeX += box;
    if (direction == "DOWN") snakeY += box;

    if (snakeX == food.x && snakeY == food.y) {
      score++;
      food = {
        x: Math.floor(Math.random() * 19 + 1) * box,
        y: Math.floor(Math.random() * 19 + 1) * box
      };
    } else {
      snake.pop();
    }

    let newHead = {
      x: snakeX,
      y: snakeY
    };

    if (
      snakeX < 0 ||
      snakeY < 0 ||
      snakeX >= canvas.width ||
      snakeY >= canvas.height ||
      collision(newHead, snake)
    ) {
      clearInterval(game);
      alert("Game Over! Your score: " + score);
    }

    snake.unshift(newHead);

    ctx.fillStyle = "white";
    ctx.font = "20px Arial";
    ctx.fillText("Score: " + score, 10, canvas.height - 10);
  }

  let game = setInterval(drawGame, 100);
</script>

</body>
</html>

