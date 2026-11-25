<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Interactive Snake Maze Live</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; user-select: none; }
  body { background-color: #000000; color: #ffffff; display: flex; flex-direction: column; align-items: center; justify-content: space-between; height: 100vh; overflow: hidden; padding: 12px 8px; }
  .top-bar { width: 100%; max-width: 420px; display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .sub-box { background: #141414; border: 1.5px solid #d4af37; border-radius: 10px; padding: 6px 10px; display: flex; align-items: center; gap: 8px; font-size: 11px; }
  .sub-box span { color: #ffcc00; font-weight: bold; display: block; font-size: 12px; }
  .level-box { background: #141414; border: 1.5px solid #d4af37; border-radius: 10px; padding: 8px 14px; font-weight: 800; font-size: 14px; color: #fff; }
  .likes-row { width: 100%; max-width: 420px; display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .title-text { font-size: 16px; font-weight: 700; }
  .likes-pill { background: #1a1a1a; border: 1px solid #444; border-radius: 20px; padding: 4px 10px; font-size: 11px; font-weight: bold; color: #ffcc00; cursor: pointer; }
  .gifts-grid { width: 100%; max-width: 420px; display: grid; grid-template-columns: repeat(8, 1fr); gap: 4px; margin-bottom: 10px; text-align: center; }
  .gift-card { background: #121212; border: 1px solid #2a2a2a; border-radius: 6px; padding: 4px 2px; cursor: pointer; transition: transform 0.1s; }
  .gift-card:active { transform: scale(0.92); border-color: #ffcc00; }
  .gift-icon { font-size: 18px; display: block; margin-bottom: 2px; }
  .gift-name { font-size: 6.5px; color: #aaa; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .gift-cost { font-size: 7.5px; color: #ffcc00; font-weight: bold; margin: 1px 0; }
  .gift-action { font-size: 7px; font-weight: 800; color: #fff; line-height: 1.1; text-transform: uppercase; }
  .maze-wrapper { position: relative; border: 3px solid #4b1d7a; border-radius: 8px; background: #0d0d0d; box-shadow: 0 0 15px rgba(106, 27, 154, 0.4); }
  canvas { display: block; }
  .bottom-section { width: 100%; max-width: 420px; text-align: center; margin-top: 6px; }
  .ban-text { font-size: 38px; font-weight: 800; letter-spacing: 1px; margin-bottom: 6px; }
  .super-gg-box { display: inline-flex; align-items: center; gap: 8px; background: #141414; border: 1.5px solid #d4af37; border-radius: 10px; padding: 6px 14px; }
  .super-gg-text { text-align: left; font-size: 11px; }
  .super-gg-text b { color: #ff4444; display: block; font-size: 10px; }
</style>
</head>
<body>

  <div class="top-bar">
    <div class="sub-box">
      <div style="font-size: 20px;">🔔</div>
      <div><span id="subName">@viewer_live</span>thanks for subscribing!</div>
    </div>
    <div class="level-box">LEVEL <span id="levelNum">163</span></div>
  </div>

  <div class="likes-row">
    <div class="title-text">Game play gifts:</div>
    <div class="likes-pill" onclick="addLikes()">👍 LIKES <span id="likeCount">4071</span>/5000 +50 apples</div>
  </div>

  <div class="gifts-grid">
    <div class="gift-card" onclick="changeSnakeColor()">
      <span class="gift-icon">⭐</span>
      <div class="gift-name">Estrella</div>
      <div class="gift-cost">🪙 2</div>
      <div class="gift-action">CHANGE<br>COLOR</div>
    </div>
    <div class="gift-card" onclick="changeAppleColor()">
      <span class="gift-icon">🦴</span>
      <div class="gift-name">Chuche</div>
      <div class="gift-cost">🪙 5</div>
      <div class="gift-action">APPLE<br>COLOR</div>
    </div>
    <div class="gift-card" onclick="spawnApples(5)">
      <span class="gift-icon">🪙</span>
      <div class="gift-name">Moneda</div>
      <div class="gift-cost">🪙 10</div>
      <div class="gift-action">SEND +5<br>APPLES</div>
    </div>
    <div class="gift-card" onclick="fartBoost()">
      <span class="gift-icon">💨</span>
      <div class="gift-name">Pulsa F</div>
      <div class="gift-cost">🪙 10</div>
      <div class="gift-action">FART<br>BOOST</div>
    </div>
    <div class="gift-card" onclick="triggerBomb()">
      <span class="gift-icon">💣</span>
      <div class="gift-name">Gorro</div>
      <div class="gift-cost">🪙 20</div>
      <div class="gift-action">x1<br>BOMB</div>
    </div>
    <div class="gift-card" onclick="activateTurbo()">
      <span class="gift-icon">⚡</span>
      <div class="gift-name">Zorro</div>
      <div class="gift-cost">🪙 60</div>
      <div class="gift-action">TURBO<br>SPEED</div>
    </div>
    <div class="gift-card" onclick="resetGame()">
      <span class="gift-icon">💀</span>
      <div class="gift-name">Disco</div>
      <div class="gift-cost">🪙 250</div>
      <div class="gift-action">GAME<br>OVER</div>
    </div>
    <div class="gift-card" onclick="superGG()">
      <span class="gift-icon">👾</span>
      <div class="gift-name">Super GG</div>
      <div class="gift-cost">🪙 10000</div>
      <div class="gift-action">RIP<br>LIVE</div>
    </div>
  </div>

  <div class="maze-wrapper">
    <canvas id="mazeCanvas" width="340" height="340"></canvas>
  </div>

  <div class="bottom-section">
    <div class="ban-text">67=ban</div>
    <div class="super-gg-box">
      <span style="font-size: 22px;">👾</span>
      <div class="super-gg-text">
        <b>LAST SUPER GG</b>
        <span id="lastGG">@richardhandal3037</span>
      </div>
    </div>
  </div>

<script>
const canvas = document.getElementById('mazeCanvas');
const ctx = canvas.getContext('2d');
const cols = 17, rows = 17;
const cellSize = canvas.width / cols;

let grid = [];
let snake = [{x: 1, y: 1}];
let apples = [];
let snakeColor = '#ff8800';
let appleColor = '#ff2a2a';
let speed = 130;
let likes = 4071;
let level = 163;
let gameLoop;

function generateMaze() {
  grid = Array.from({ length: rows }, () => Array(cols).fill(1));
  function carve(x, y) {
    grid[y][x] = 0;
    const dirs = [[0,-2],[2,0],[0,2],[-2,0]].sort(() => Math.random() - 0.5);
    for (let [dx, dy] of dirs) {
      let nx = x + dx, ny = y + dy;
      if (nx > 0 && nx < cols - 1 && ny > 0 && ny < rows - 1 && grid[ny][nx] === 1) {
        grid[y + dy/2][x + dx/2] = 0;
        carve(nx, ny);
      }
    }
  }
  carve(1, 1);
  for(let i=0; i<12; i++) {
    let rx = Math.floor(Math.random()*(cols-2))+1;
    let ry = Math.floor(Math.random()*(rows-2))+1;
    if(rx%2===1 || ry%2===1) grid[ry][rx] = 0;
  }
}

function spawnApples(count) {
  for (let i = 0; i < count; i++) {
    let empty = [];
    for (let y = 1; y < rows - 1; y++) {
      for (let x = 1; x < cols - 1; x++) {
        if (grid[y][x] === 0 && !snake.some(s => s.x === x && s.y === y)) {
          empty.push({x, y});
        }
      }
    }
    if (empty.length > 0) {
      apples.push(empty[Math.floor(Math.random() * empty.length)]);
    }
  }
}

function getNextMove() {
  if (apples.length === 0) spawnApples(3);
  let head = snake[0];
  let queue = [[head]];
  let visited = new Set([`${head.x},${head.y}`]);

  while (queue.length > 0) {
    let path = queue.shift();
    let curr = path[path.length - 1];

    if (apples.some(a => a.x === curr.x && a.y === curr.y)) {
      return path[1] || head;
    }

    for (let [dx, dy] of [[0,-1],[1,0],[0,1],[-1,0]]) {
      let nx = curr.x + dx, ny = curr.y + dy;
      let key = `${nx},${ny}`;
      if (nx >= 0 && nx < cols && ny >= 0 && ny < rows && grid[ny][nx] === 0 && !visited.has(key)) {
        visited.add(key);
        queue.push([...path, {x: nx, y: ny}]);
      }
    }
  }
  for (let [dx, dy] of [[0,-1],[1,0],[0,1],[-1,0]]) {
    let nx = head.x + dx, ny = head.y + dy;
    if (grid[ny] && grid[ny][nx] === 0) return {x: nx, y: ny};
  }
  return head;
}

function update() {
  let next = getNextMove();
  snake.unshift(next);

  let appleIdx = apples.findIndex(a => a.x === next.x && a.y === next.y);
  if (appleIdx !== -1) {
    apples.splice(appleIdx, 1);
    if (snake.length > 25) snake.pop();
    if (apples.length === 0) {
      level++;
      document.getElementById('levelNum').innerText = level;
      initLevel();
      return;
    }
  } else {
    snake.pop();
  }
  draw();
}

function draw() {
  ctx.fillStyle = '#3a2e08';
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  for (let y = 0; y < rows; y++) {
    for (let x = 0; x < cols; x++) {
      if (grid[y][x] === 1) {
        ctx.fillStyle = '#09090b';
        ctx.fillRect(x * cellSize, y * cellSize, cellSize, cellSize);
        ctx.strokeStyle = '#6a1b9a';
        ctx.lineWidth = 1.5;
        ctx.strokeRect(x * cellSize + 1, y * cellSize + 1, cellSize - 2, cellSize - 2);
      }
    }
  }

  apples.forEach(a => {
    ctx.fillStyle = appleColor;
    ctx.beginPath();
    ctx.arc(a.x * cellSize + cellSize/2, a.y * cellSize + cellSize/2, cellSize/3, 0, Math.PI * 2);
    ctx.fill();
    ctx.fillStyle = '#4caf50';
    ctx.fillRect(a.x * cellSize + cellSize/2, a.y * cellSize + 2, 4, 4);
  });

  snake.forEach((s, idx) => {
    ctx.fillStyle = snakeColor;
    ctx.beginPath();
    ctx.arc(s.x * cellSize + cellSize/2, s.y * cellSize + cellSize/2, idx === 0 ? cellSize/2.2 : cellSize/2.6, 0, Math.PI * 2);
    ctx.fill();

    if (idx === 0) {
      ctx.fillStyle = '#fff';
      ctx.beginPath();
      ctx.arc(s.x * cellSize + cellSize/3, s.y * cellSize + cellSize/3, 3, 0, Math.PI*2);
      ctx.arc(s.x * cellSize + (cellSize*2)/3, s.y * cellSize + cellSize/3, 3, 0, Math.PI*2);
      ctx.fill();
      ctx.fillStyle = '#000';
      ctx.fillRect(s.x * cellSize + cellSize/3 - 1, s.y * cellSize + cellSize/3 - 1, 2, 2);
      ctx.fillRect(s.x * cellSize + (cellSize*2)/3 - 1, s.y * cellSize + cellSize/3 - 1, 2, 2);
    }
  });
}

function changeSnakeColor() {
