<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
  <meta name="description" content="Snake Game Pro - A modern take on the classic Snake game with multiple difficulty levels, power-ups, and responsive controls.">
  <meta name="keywords" content="snake game, classic game, html5 game, mobile game, responsive game">
  <meta name="author" content="Snake Game Pro">
  <title>Snake Game Pro - Play Online</title>
  
  <!-- Open Graph Meta Tags for Social Sharing -->
  <meta property="og:title" content="Snake Game Pro - Play Online">
  <meta property="og:description" content="A modern take on the classic Snake game with multiple difficulty levels, power-ups, and responsive controls.">
  <meta property="og:type" content="website">
  <meta property="og:url" content="https://yourwebsite.com/snake-game">
  <meta property="og:image" content="https://i.ibb.co/8DdF9Mf/grass-texture.jpg">
  
  <!-- Favicon -->
  <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>🐍</text></svg>">
  
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }
    
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      display: flex;
      justify-content: center;
      align-items: center;
      min-height: 100vh;
      margin: 0;
      background: linear-gradient(135deg, #1a472a, #2d8659, #38a169);
      overflow: hidden;
      color: white;
    }
    
    .game-container {
      position: relative;
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: 600px;
      padding: 10px;
    }
    
    .game-header {
      display: flex;
      justify-content: space-between;
      width: 100%;
      margin-bottom: 10px;
      padding: 0 10px;
    }
    
    .score-board {
      background: rgba(0, 0, 0, 0.5);
      padding: 8px 15px;
      border-radius: 20px;
      font-size: 18px;
      font-weight: bold;
    }
    
    .high-score {
      background: rgba(255, 215, 0, 0.3);
      padding: 8px 15px;
      border-radius: 20px;
      font-size: 18px;
      font-weight: bold;
    }
    
    canvas {
      border: 4px solid #fff;
      background: url("https://i.ibb.co/8DdF9Mf/grass-texture.jpg");
      background-size: cover;
      box-shadow: 0 0 25px rgba(0, 255, 100, 0.6);
      touch-action: none;
      border-radius: 10px;
    }
    
    .controls {
      display: flex;
      justify-content: center;
      margin-top: 20px;
      width: 100%;
    }
    
    .control-btn {
      background: rgba(255, 255, 255, 0.2);
      border: 2px solid white;
      border-radius: 50%;
      width: 60px;
      height: 60px;
      margin: 0 10px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24px;
      color: white;
      cursor: pointer;
      transition: all 0.2s;
    }
    
    .control-btn:active {
      background: rgba(255, 255, 255, 0.4);
      transform: scale(0.95);
    }
    
    .menu-screen, .game-over-screen, .pause-screen, .instructions-screen {
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: rgba(0, 0, 0, 0.85);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      z-index: 10;
      border-radius: 10px;
      padding: 20px;
      overflow-y: auto;
    }
    
    .menu-screen h1, .game-over-screen h1, .instructions-screen h1 {
      font-size: 48px;
      margin-bottom: 30px;
      text-shadow: 0 0 10px rgba(0, 255, 100, 0.7);
      text-align: center;
    }
    
    .menu-btn, .game-over-btn {
      background: linear-gradient(135deg, #2d8659, #38a169);
      border: none;
      color: white;
      padding: 15px 30px;
      margin: 10px;
      border-radius: 30px;
      font-size: 20px;
      cursor: pointer;
      transition: all 0.3s;
      box-shadow: 0 4px 8px rgba(0, 0, 0, 0.3);
      min-width: 200px;
    }
    
    .menu-btn:hover, .game-over-btn:hover {
      background: linear-gradient(135deg, #38a169, #2d8659);
      transform: translateY(-3px);
      box-shadow: 0 6px 12px rgba(0, 0, 0, 0.4);
    }
    
    .difficulty-selector {
      margin: 20px 0;
      display: flex;
      flex-direction: column;
      align-items: center;
    }
    
    .difficulty-selector h3 {
      margin-bottom: 15px;
    }
    
    .difficulty-options {
      display: flex;
      gap: 15px;
      flex-wrap: wrap;
      justify-content: center;
    }
    
    .difficulty-btn {
      background: rgba(255, 255, 255, 0.2);
      border: 2px solid white;
      color: white;
      padding: 10px 20px;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.2s;
    }
    
    .difficulty-btn.active {
      background: rgba(0, 255, 100, 0.3);
    }
    
    .hidden {
      display: none !important;
    }
    
    .pause-screen h2 {
      font-size: 36px;
      margin-bottom: 30px;
    }
    
    .sound-toggle {
      position: absolute;
      top: 20px;
      right: 20px;
      background: rgba(255, 255, 255, 0.2);
      border: 2px solid white;
      border-radius: 50%;
      width: 50px;
      height: 50px;
      display: flex;
      justify-content: center;
      align-items: center;
      font-size: 24px;
      color: white;
      cursor: pointer;
      z-index: 5;
    }
    
    .instructions-content {
      max-width: 500px;
      text-align: center;
      line-height: 1.6;
    }
    
    .instructions-content h3 {
      margin: 20px 0 10px;
      color: #4ade80;
    }
    
    .instructions-content p {
      margin-bottom: 15px;
    }
    
    .instructions-content ul {
      text-align: left;
      margin: 0 auto 20px;
      max-width: 400px;
    }
    
    .instructions-content li {
      margin-bottom: 8px;
    }
    
    .footer {
      position: fixed;
      bottom: 10px;
      left: 0;
      width: 100%;
      text-align: center;
      font-size: 14px;
      color: rgba(255, 255, 255, 0.7);
      z-index: 1;
    }
    
    .share-buttons {
      display: flex;
      gap: 15px;
      margin-top: 20px;
    }
    
    .share-btn {
      background: rgba(255, 255, 255, 0.2);
      border: 2px solid white;
      color: white;
      padding: 10px 15px;
      border-radius: 20px;
      cursor: pointer;
      transition: all 0.2s;
      display: flex;
      align-items: center;
      gap: 5px;
    }
    
    .share-btn:hover {
      background: rgba(255, 255, 255, 0.4);
    }
    
    @media (max-width: 600px) {
      .game-header {
        font-size: 14px;
      }
      
      .control-btn {
        width: 50px;
        height: 50px;
        font-size: 20px;
      }
      
      .menu-screen h1, .game-over-screen h1, .instructions-screen h1 {
        font-size: 36px;
      }
      
      .menu-btn, .game-over-btn {
        font-size: 16px;
        padding: 12px 24px;
        min-width: 160px;
      }
    }
  </style>
</head>
<body>
  <div class="game-container">
    <div class="menu-screen" id="menuScreen">
      <h1>🐍 Snake Game Pro</h1>
      <div class="difficulty-selector">
        <h3>Select Difficulty</h3>
        <div class="difficulty-options">
          <button class="difficulty-btn active" data-level="easy">Easy</button>
          <button class="difficulty-btn" data-level="medium">Medium</button>
          <button class="difficulty-btn" data-level="hard">Hard</button>
        </div>
      </div>
      <button class="menu-btn" id="startBtn">Start Game</button>
      <button class="menu-btn" id="instructionsBtn">How to Play</button>
      <div class="share-buttons">
        <button class="share-btn" id="shareBtn">📤 Share</button>
        <button class="share-btn" id="tweetBtn">🐦 Tweet</button>
      </div>
    </div>
    
    <div class="instructions-screen hidden" id="instructionsScreen">
      <h1>How to Play</h1>
      <div class="instructions-content">
        <h3>Objective</h3>
        <p>Control the snake to eat food and grow longer without hitting the walls or yourself!</p>
        
        <h3>Controls</h3>
        <ul>
          <li><strong>Desktop:</strong> Use arrow keys to control the snake</li>
          <li><strong>Mobile:</strong> Use the on-screen buttons or swipe gestures</li>
          <li><strong>Pause:</strong> Press Space, P, or the pause button</li>
        </ul>
        
        <h3>Game Elements</h3>
        <ul>
          <li><strong>Red Apple:</strong> Regular food (+1 point)</li>
          <li><strong>Gold Star:</strong> Power-up (+5 points)</li>
        </ul>
        
        <h3>Tips</h3>
        <ul>
          <li>The game speeds up as your score increases</li>
          <li>Power-ups appear randomly - grab them for bonus points!</li>
          <li>Try to beat your high score!</li>
        </ul>
      </div>
      <button class="menu-btn" id="backToMenuBtn">Back to Menu</button>
    </div>
    
    <div class="game-over-screen hidden" id="gameOverScreen">
      <h1>Game Over</h1>
      <p style="font-size: 24px; margin-bottom: 20px;">Your Score: <span id="finalScore">0</span></p>
      <p style="font-size: 20px; margin-bottom: 30px;">High Score: <span id="finalHighScore">0</span></p>
      <button class="game-over-btn" id="restartBtn">Play Again</button>
      <button class="game-over-btn" id="menuBtnFromGameOver">Main Menu</button>
      <div class="share-buttons">
        <button class="share-btn" id="shareScoreBtn">📤 Share Score</button>
      </div>
    </div>
    
    <div class="pause-screen hidden" id="pauseScreen">
      <h2>Game Paused</h2>
      <button class="game-over-btn" id="resumeBtn">Resume</button>
      <button class="game-over-btn" id="quitBtn">Quit Game</button>
    </div>
    
    <div class="sound-toggle" id="soundToggle">🔊</div>
    
    <div class="game-header">
      <div class="score-board">Score: <span id="score">0</span></div>
      <div class="high-score">High: <span id="highScore">0</span></div>
    </div>
    
    <canvas id="gameCanvas"></canvas>
    
    <div class="controls">
      <button class="control-btn" id="leftBtn">◀</button>
      <button class="control-btn" id="upBtn">▲</button>
      <button class="control-btn" id="downBtn">▼</button>
      <button class="control-btn" id="rightBtn">▶</button>
    </div>
  </div>
  
  <div class="footer">
    <p>© 2023 Snake Game Pro | Play for free online</p>
  </div>

  <script>
    // Game variables
    const canvas = document.getElementById("gameCanvas");
    const ctx = canvas.getContext("2d");
    const scoreElement = document.getElementById("score");
    const highScoreElement = document.getElementById("highScore");
    const finalScoreElement = document.getElementById("finalScore");
    const finalHighScoreElement = document.getElementById("finalHighScore");
    const menuScreen = document.getElementById("menuScreen");
    const instructionsScreen = document.getElementById("instructionsScreen");
    const gameOverScreen = document.getElementById("gameOverScreen");
    const pauseScreen = document.getElementById("pauseScreen");
    const soundToggle = document.getElementById("soundToggle");
    
    // Game state
    let grid = 20;
    let snake = [];
    let dx = grid;
    let dy = 0;
    let food = {};
    let score = 0;
    let highScore = localStorage.getItem("snakeHighScore") || 0;
    let count = 0;
    let gameSpeed = 10;
    let gameRunning = false;
    let gamePaused = false;
    let soundEnabled = true;
    let difficulty = "easy";
    let powerUp = null;
    let particles = [];
    
    // Difficulty settings
    const difficultySettings = {
      easy: { speed: 10, powerUpChance: 0.05 },
      medium: { speed: 8, powerUpChance: 0.03 },
      hard: { speed: 6, powerUpChance: 0.01 }
    };
    
    // Initialize game
    function initGame() {
      resizeCanvas();
      highScoreElement.textContent = highScore;
      
      // Set up event listeners
      document.getElementById("startBtn").addEventListener("click", startGame);
      document.getElementById("restartBtn").addEventListener("click", startGame);
      document.getElementById("menuBtnFromGameOver").addEventListener("click", showMenu);
      document.getElementById("instructionsBtn").addEventListener("click", showInstructions);
      document.getElementById("backToMenuBtn").addEventListener("click", showMenu);
      document.getElementById("resumeBtn").addEventListener("click", resumeGame);
      document.getElementById("quitBtn").addEventListener("click", showMenu);
      soundToggle.addEventListener("click", toggleSound);
      
      // Share buttons
      document.getElementById("shareBtn").addEventListener("click", shareGame);
      document.getElementById("tweetBtn").addEventListener("click", tweetGame);
      document.getElementById("shareScoreBtn").addEventListener("click", shareScore);
      
      // Difficulty buttons
      document.querySelectorAll(".difficulty-btn").forEach(btn => {
        btn.addEventListener("click", function() {
          document.querySelectorAll(".difficulty-btn").forEach(b => b.classList.remove("active"));
          this.classList.add("active");
          difficulty = this.dataset.level;
        });
      });
      
      // Control buttons
      document.getElementById("leftBtn").addEventListener("click", () => changeDirection(-grid, 0));
      document.getElementById("upBtn").addEventListener("click", () => changeDirection(0, -grid));
      document.getElementById("downBtn").addEventListener("click", () => changeDirection(0, grid));
      document.getElementById("rightBtn").addEventListener("click", () => changeDirection(grid, 0));
      
      // Keyboard controls
      document.addEventListener("keydown", handleKeyPress);
      
      // Touch controls
      setupTouchControls();
      
      // Window resize
      window.addEventListener("resize", resizeCanvas);
    }
    
    function resizeCanvas() {
      canvas.width = Math.min(window.innerWidth - 40, 600);
      canvas.height = Math.min(window.innerHeight - 200, 600);
      grid = Math.floor(Math.min(canvas.width, canvas.height) / 20);
    }
    
    function startGame() {
      // Reset game state
      snake = [
        {x: Math.floor(canvas.width / 2 / grid) * grid, y: Math.floor(canvas.height / 2 / grid) * grid},
        {x: Math.floor(canvas.width / 2 / grid) * grid - grid, y: Math.floor(canvas.height / 2 / grid) * grid},
        {x: Math.floor(canvas.width / 2 / grid) * grid - grid * 2, y: Math.floor(canvas.height / 2 / grid) * grid}
      ];
      dx = grid;
      dy = 0;
      score = 0;
      scoreElement.textContent = score;
      food = randomFood();
      powerUp = null;
      particles = [];
      gameSpeed = difficultySettings[difficulty].speed;
      
      // Hide menus and start game
      menuScreen.classList.add("hidden");
      instructionsScreen.classList.add("hidden");
      gameOverScreen.classList.add("hidden");
      pauseScreen.classList.add("hidden");
      gameRunning = true;
      gamePaused = false;
      
      // Start game loop
      gameLoop();
    }
    
    function gameLoop() {
      if (!gameRunning) return;
      
      requestAnimationFrame(gameLoop);
      
      if (gamePaused) return;
      
      if (++count < gameSpeed) return;
      count = 0;
      
      clearCanvas();
      
      // Move snake
      const head = {x: snake[0].x + dx, y: snake[0].y + dy};
      snake.unshift(head);
      
      // Check if snake ate food
      if (head.x === food.x && head.y === food.y) {
        score++;
        scoreElement.textContent = score;
        playSound("eat");
        createParticles(food.x + grid/2, food.y + grid/2, "red");
        food = randomFood();
        
        // Randomly spawn power-up
        if (Math.random() < difficultySettings[difficulty].powerUpChance && !powerUp) {
          powerUp = randomPowerUp();
        }
        
        // Increase speed every 5 points
        if (score % 5 === 0 && gameSpeed > 3) {
          gameSpeed--;
        }
      } else {
        snake.pop();
      }
      
      // Check if snake ate power-up
      if (powerUp && head.x === powerUp.x && head.y === powerUp.y) {
        score += 5;
        scoreElement.textContent = score;
        playSound("powerup");
        createParticles(powerUp.x + grid/2, powerUp.y + grid/2, "gold");
        powerUp = null;
      }
      
      // Check collisions
      if (checkCollision(head)) {
        gameOver();
        return;
      }
      
      // Draw game elements
      drawApple(food.x, food.y);
      if (powerUp) drawPowerUp(powerUp.x, powerUp.y);
      drawSnakeSmooth();
      drawParticles();
    }
    
    function clearCanvas() {
      ctx.clearRect(0, 0, canvas.width, canvas.height);
    }
    
    function randomFood() {
      return {
        x: Math.floor(Math.random() * (canvas.width / grid)) * grid,
        y: Math.floor(Math.random() * (canvas.height / grid)) * grid
      };
    }
    
    function randomPowerUp() {
      return {
        x: Math.floor(Math.random() * (canvas.width / grid)) * grid,
        y: Math.floor(Math.random() * (canvas.height / grid)) * grid
      };
    }
    
    function checkCollision(head) {
      // Wall collision
      if (head.x < 0 || head.x >= canvas.width || head.y < 0 || head.y >= canvas.height) {
        return true;
      }
      
      // Self collision
      for (let i = 1; i < snake.length; i++) {
        if (head.x === snake[i].x && head.y === snake[i].y) {
          return true;
        }
      }
      
      return false;
    }
    
    function gameOver() {
      gameRunning = false;
      playSound("gameover");
      
      // Update high score
      if (score > highScore) {
        highScore = score;
        localStorage.setItem("snakeHighScore", highScore);
        highScoreElement.textContent = highScore;
      }
      
      // Show game over screen
      finalScoreElement.textContent = score;
      finalHighScoreElement.textContent = highScore;
      gameOverScreen.classList.remove("hidden");
    }
    
    function showMenu() {
      gameRunning = false;
      gamePaused = false;
      menuScreen.classList.remove("hidden");
      instructionsScreen.classList.add("hidden");
      gameOverScreen.classList.add("hidden");
      pauseScreen.classList.add("hidden");
    }
    
    function showInstructions() {
      menuScreen.classList.add("hidden");
      instructionsScreen.classList.remove("hidden");
    }
    
    function togglePause() {
      if (!gameRunning) return;
      
      gamePaused = !gamePaused;
      if (gamePaused) {
        pauseScreen.classList.remove("hidden");
      } else {
        pauseScreen.classList.add("hidden");
      }
    }
    
    function resumeGame() {
      gamePaused = false;
      pauseScreen.classList.add("hidden");
    }
    
    function toggleSound() {
      soundEnabled = !soundEnabled;
      soundToggle.textContent = soundEnabled ? "🔊" : "🔇";
    }
    
    function playSound(type) {
      if (!soundEnabled) return;
      
      // In a real implementation, you would play actual sound files
      // For this example, we'll just log to console
      console.log(`Playing sound: ${type}`);
    }
    
    function changeDirection(newDx, newDy) {
      // Prevent 180-degree turns
      if ((newDx === -dx && newDy === 0) || (newDx === 0 && newDy === -dy)) {
        return;
      }
      
      dx = newDx;
      dy = newDy;
    }
    
    function handleKeyPress(e) {
      if (!gameRunning) return;
      
      switch(e.key) {
        case "ArrowLeft":
          changeDirection(-grid, 0);
          break;
        case "ArrowUp":
          changeDirection(0, -grid);
          break;
        case "ArrowRight":
          changeDirection(grid, 0);
          break;
        case "ArrowDown":
          changeDirection(0, grid);
          break;
        case " ":
        case "p":
        case "P":
          togglePause();
          break;
      }
    }
    
    function setupTouchControls() {
      let startX, startY;
      
      canvas.addEventListener("touchstart", e => {
        const touch = e.touches[0];
        startX = touch.clientX;
        startY = touch.clientY;
      });
      
      canvas.addEventListener("touchend", e => {
        if (!gameRunning || gamePaused) return;
        
        const touch = e.changedTouches[0];
        const endX = touch.clientX;
        const endY = touch.clientY;
        const diffX = endX - startX;
        const diffY = endY - startY;
        
        // Determine swipe direction
        if (Math.abs(diffX) > Math.abs(diffY)) {
          // Horizontal swipe
          if (diffX > 0) {
            changeDirection(grid, 0); // Right
          } else {
            changeDirection(-grid, 0); // Left
          }
        } else {
          // Vertical swipe
          if (diffY > 0) {
            changeDirection(0, grid); // Down
          } else {
            changeDirection(0, -grid); // Up
          }
        }
      });
    }
    
    function drawApple(x, y) {
      // Apple body
      ctx.fillStyle = "red";
      ctx.beginPath();
      ctx.arc(x + grid/2, y + grid/2, grid/2 - 2, 0, Math.PI * 2);
      ctx.fill();
      
      // Apple stem
      ctx.fillStyle = "brown";
      ctx.fillRect(x + grid/2 - 2, y + 2, 4, 6);
      
      // Apple leaf
      ctx.fillStyle = "green";
      ctx.beginPath();
      ctx.ellipse(x + grid/2 + 5, y + 4, 5, 3, Math.PI / 4, 0, Math.PI * 2);
      ctx.fill();
    }
    
    function drawPowerUp(x, y) {
      // Power-up glow
      ctx.fillStyle = "rgba(255, 215, 0, 0.3)";
      ctx.beginPath();
      ctx.arc(x + grid/2, y + grid/2, grid/2 + 3, 0, Math.PI * 2);
      ctx.fill();
      
      // Power-up core
      ctx.fillStyle = "gold";
      ctx.beginPath();
      ctx.arc(x + grid/2, y + grid/2, grid/2 - 2, 0, Math.PI * 2);
      ctx.fill();
      
      // Power-up star
      ctx.fillStyle = "white";
      drawStar(x + grid/2, y + grid/2, 5, grid/3, grid/6);
    }
    
    function drawStar(cx, cy, spikes, outerRadius, innerRadius) {
      let rot = Math.PI / 2 * 3;
      let x = cx;
      let y = cy;
      const step = Math.PI / spikes;
      
      ctx.beginPath();
      ctx.moveTo(cx, cy - outerRadius);
      
      for (let i = 0; i < spikes; i++) {
        x = cx + Math.cos(rot) * outerRadius;
        y = cy + Math.sin(rot) * outerRadius;
        ctx.lineTo(x, y);
        rot += step;
        
        x = cx + Math.cos(rot) * innerRadius;
        y = cy + Math.sin(rot) * innerRadius;
        ctx.lineTo(x, y);
        rot += step;
      }
      
      ctx.lineTo(cx, cy - outerRadius);
      ctx.closePath();
      ctx.fill();
    }
    
    function drawSnakeSmooth() {
      // Draw snake body
      ctx.lineJoin = "round";
      ctx.lineCap = "round";
      ctx.strokeStyle = "limegreen";
      ctx.lineWidth = grid;
      
      ctx.beginPath();
      ctx.moveTo(snake[0].x + grid/2, snake[0].y + grid/2);
      
      for (let i = 1; i < snake.length; i++) {
        ctx.lineTo(snake[i].x + grid/2, snake[i].y + grid/2);
      }
      
      ctx.stroke();
      
      // Draw snake head
      const headX = snake[0].x + grid/2;
      const headY = snake[0].y + grid/2;
      
      // Eyes background
      ctx.fillStyle = "white";
      ctx.beginPath();
      ctx.arc(headX - 5, headY - 5, 4, 0, Math.PI * 2);
      ctx.arc(headX + 5, headY - 5, 4, 0, Math.PI * 2);
      ctx.fill();
      
      // Eyes pupils
      ctx.fillStyle = "black";
      ctx.beginPath();
      ctx.arc(headX - 5, headY - 5, 2, 0, Math.PI * 2);
      ctx.arc(headX + 5, headY - 5, 2, 0, Math.PI * 2);
      ctx.fill();
    }
    
    function createParticles(x, y, color) {
      for (let i = 0; i < 10; i++) {
        particles.push({
          x: x,
          y: y,
          size: Math.random() * 5 + 2,
          speedX: (Math.random() - 0.5) * 4,
          speedY: (Math.random() - 0.5) * 4,
          color: color,
          life: 30
        });
      }
    }
    
    function drawParticles() {
      for (let i = particles.length - 1; i >= 0; i--) {
        const p = particles[i];
        
        ctx.fillStyle = p.color;
        ctx.beginPath();
        ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
        ctx.fill();
        
        p.x += p.speedX;
        p.y += p.speedY;
        p.life--;
        
        if (p.life <= 0) {
          particles.splice(i, 1);
        }
      }
    }
    
    // Share functions
    function shareGame() {
      if (navigator.share) {
        navigator.share({
          title: 'Snake Game Pro',
          text: 'Check out this awesome Snake game!',
          url: window.location.href
        });
      } else {
        // Fallback for browsers that don't support Web Share API
        const dummy = document.createElement('input');
        document.body.appendChild(dummy);
        dummy.value = window.location.href;
        dummy.select();
        document.execCommand('copy');
        document.body.removeChild(dummy);
        
        alert('Game link copied to clipboard!');
      }
    }
    
    function tweetGame() {
      const text = 'Check out this awesome Snake game!';
      const url = window.location.href;
      window.open(`https://twitter.com/intent/tweet?text=${encodeURIComponent(text)}&url=${encodeURIComponent(url)}`, '_blank');
    }
    
    function shareScore() {
      const text = `I just scored ${score} points in Snake Game Pro! Can you beat my score?`;
      const url = window.location.href;
      
      if (navigator.share) {
        navigator.share({
          title: 'Snake Game Pro',
          text: text,
          url: url
        });
      } else {
        // Fallback for browsers that don't support Web Share API
        window.open(`https://twitter.com/intent/tweet?text=${encodeURIComponent(text)}&url=${encodeURIComponent(url)}`, '_blank');
      }
    }
    
    // Initialize the game
    initGame();
  </script>
</body>
</html>
