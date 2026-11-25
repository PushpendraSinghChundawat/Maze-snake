GitHub में यह हूबहू वैसा ही गेम बनाने के लिए आपको केवल नीचे दिया गया पूरा कोड कॉपी करके अपनी GitHub फाइल में पेस्ट करना है।
मैंने आपके लिए फोटो जैसा हूबहू डिज़ाइन (काला बैकग्राउंड, लेवल बैज, लाइक्स बार, सारे गिफ्ट कार्ड्स, बैंगनी-सुनहरी भूलभुलैया, अपने आप सेब खाने वाला सांप और नीचे 67=ban) एक ही फाइल में तैयार कर दिया है। खास बात यह है कि इसमें आप गिफ्ट आइकन्स पर उंगली से टच (Click) करके भी गेम को कंट्रोल कर सकते हैं (जैसे सांप का रंग बदलना, +5 सेब डालना, बम फोड़ना, टर्बो स्पीड आदि)।

स्टेप 1: नीचे दिया गया पूरा कोड कॉपी (Copy) करें

इस पूरे बॉक्स के अंदर का कोड शुरू (<!DOCTYPE html>) से लेकर आखिर (</html>) तक कॉपी कर लें:
html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>Interactive Snake Maze Live</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; user-select: none; }
  body { background-color: #000000; color: #ffffff; display: flex; flex-direction: column; align-items: center; justify-content: space-between; height: 100vh; overflow: hidden; padding: 12px 8px; }
  
  /* Top Header */
  .top-bar { width: 100%; max-width: 420px; display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .sub-box { background: #141414; border: 1.5px solid #d4af37; border-radius: 10px; padding: 6px 10px; display: flex; align-items: center; gap: 8px; font-size: 11px; }
  .sub-box span { color: #ffcc00; font-weight: bold; display: block; font-size: 12px; }
  .level-box { background: #141414; border: 1.5px solid #d4af37; border-radius: 10px; padding: 8px 14px; font-weight: 800; font-size: 14px; color: #fff; }

  /* Likes Bar */
  .likes-row { width: 100%; max-width: 420px; display: flex; justify-content: space-between; align-items: center; margin-bottom: 8px; }
  .title-text { font-size: 16px; font-weight: 700; }
  .likes-pill { background: #1a1a1a; border: 1px solid #444; border-radius: 20px; padding: 4px 10px; font-size: 11px; font-weight: bold; color: #ffcc00; cursor: pointer; }

  /* Gifts Grid */
  .gifts-grid { width: 100%; max-width: 420px; display: grid; grid-template-columns: repeat(8, 1fr); gap: 4px; margin-bottom: 10px; text-align: center; }
  .gift-card { background: #121212; border: 1px solid #2a2a2a; border-radius: 6px; padding: 4px 2px; cursor: pointer; transition: transform 0.1s; }
  .gift-card:active { transform: scale(0.92); border-color: #ffcc00; }
  .gift-icon { font-size: 18px; display: block; margin-bottom: 2px; }
  .gift-name { font-size: 6.5px; color: #aaa; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
  .gift-cost { font-size: 7.5px; color: #ffcc00; font-weight: bold; margin: 1px 0; }
  .gift-action { font-size: 7px; font-weight: 800; color: #fff; line-height: 1.1; text-transform: uppercase; }

  /* Maze Container */
  .maze-wrapper { position: relative; border: 3px solid #4b1d7a; border-radius: 8px; background: #0d0d0d; box-shadow: 0 0 15px rgba(106, 27, 154, 0.4); }
  canvas { display: block; }

  /* Bottom Footer */
  .bottom-section { width: 100%; max-width: 420px; text-align: center; margin-top: 6px; }
  .ban-text { font-size: 38px; font-weight: 800; letter-spacing: 1px; margin-bottom: 6px; }
  .super-gg-box { display: inline-flex; align-items: center; gap: 8px; background: #141414; border: 1.5px solid #d4af37; border-radius: 10px; padding: 6px 14px; }
  .super-gg-text { text-align: left; font-size: 11px; }
  .super-gg-text b { color: #ff4444; display: block; font-size: 10px; }
</style>
</head>
<body>

  <!-- Top Section -->
  <div class="top-bar">
    <div class="sub-box">
      <div style="font-size: 20px;">🔔</div>
      <div><span id="subName">@viewer_live</span>thanks for subscribing!</div>
    </div>
    <div class="level-box">LEVEL <span id="levelNum">163</span></div>
  </div>

  <!-- Likes Bar -->
  <div class="likes-row">
    <div class="title-text">Game play gifts:</div>
    <div class="likes-pill" onclick="addLikes()">👍 LIKES <span id="likeCount">4071</span>/5000 +50 apples</div>
  </div>

  <!-- Gifts Row (Tap any gift to trigger action!) -->
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

  <!-- Game Maze Canvas -->
  <div class="maze-wrapper">
    <canvas id="mazeCanvas" width="340" height="340"></canvas>
  </div>

  <!-- Bottom Section -->
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

// Maze Generator (Recursive Backtracker)
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
  // Add extra loops so snake doesn't get trapped
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

// BFS Pathfinding for Auto-Snake
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
  // Fallback random valid move
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
    if (snake.length > 25) snake.pop(); // Keep manageable length
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
  ctx.fillStyle = '#3a2e08'; // Golden-brown path background
  ctx.fillRect(0, 0, canvas.width, canvas.height);

  // Draw Walls with Purple Neon Border
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

  // Draw Apples
  apples.forEach(a => {
    ctx.fillStyle = appleColor;
    ctx.beginPath();
    ctx.arc(a.x * cellSize + cellSize/2, a.y * cellSize + cellSize/2, cellSize/3, 0, Math.PI * 2);
    ctx.fill();
    // Apple leaf
    ctx.fillStyle = '#4caf50';
    ctx.fillRect(a.x * cellSize + cellSize/2, a.y * cellSize + 2, 4, 4);
  });

  // Draw Snake
  snake.forEach((s, idx) => {
    ctx.fillStyle = snakeColor;
    ctx.beginPath();
    ctx.arc(s.x * cellSize + cellSize/2, s.y * cellSize + cellSize/2, idx === 0 ? cellSize/2.2 : cellSize/2.6, 0, Math.PI * 2);
    ctx.fill();

Use code with caution.
// Eyes on Head
if (idx === 0) {
ctx.fillStyle = '#fff';
ctx.beginPath();
ctx.arc(s.x * cellSize + cellSize/3, s.y * cellSize + cellSize/3, 3, 0, Math.PI2);
ctx.arc(s.x * cellSize + (cellSize2)/3, s.y * cellSize + cellSize/3, 3, 0, Math.PI2);
ctx.fill();
ctx.fillStyle = '#000';
ctx.fillRect(s.x * cellSize + cellSize/3 - 1, s.y * cellSize + cellSize/3 - 1, 2, 2);
ctx.fillRect(s.x * cellSize + (cellSize2)/3 - 1, s.y * cellSize + cellSize/3 - 1, 2, 2);
}
});
}
// Interactive Gift Functions
function changeSnakeColor() {
const colors = ['#00ffcc', '#ff00ff', '#ffff00', '#00ff00', '#ff5500', '#3399ff'];
snakeColor = colors[Math.floor(Math.random() * colors.length)];
}
function changeAppleColor() {
const colors = ['#00ff00', '#ffff00', '#ff007f', '#00ffff', '#ff2a2a'];
appleColor = colors[Math.floor(Math.random() * colors.length)];
}
function activateTurbo() {
clearInterval(gameLoop);
gameLoop = setInterval(update, 45);
setTimeout(() => { clearInterval(gameLoop); gameLoop = setInterval(update, speed); }, 4000);
}
function fartBoost() {
spawnApples(2);
activateTurbo();
}
function triggerBomb() {
// Clears random walls around snake
let h = snake[0];
for(let dy=-2; dy<=2; dy++) {
for(let dx=-2; dx<=2; dx++) {
let nx = h.x+dx, ny = h.y+dy;
if(nx>0 && nx<cols-1 && ny>0 && ny<rows-1) grid[ny][nx] = 0;
}
}
}
function addLikes() {
likes += 150;
if(likes >= 5000) { likes = 0; spawnApples(50); }
document.getElementById('likeCount').innerText = likes;
}
function superGG() {
spawnApples(25);
changeSnakeColor();
activateTurbo();
}
function resetGame() {
level = 1;
document.getElementById('levelNum').innerText = level;
initLevel();
}
function initLevel() {
snake = [{x: 1, y: 1}];
apples = [];
generateMaze();
spawnApples(4);
clearInterval(gameLoop);
gameLoop = setInterval(update, speed);
}
initLevel();



---

### स्टेप 2: इसे GitHub पर डालकर लाइव कैसे करें? (मोबाइल से आसान तरीका)

1. अपने फोन के ब्राउज़र में **github.com** खोलें और अपना फ्री अकाउंट बनाकर **Sign in** करें।
2. ऊपर दाईं तरफ **`+` (प्लस)** आइकन पर टैप करें और **New repository** चुनें।
3. **Repository name** में लिखें: `snake-game` (या कोई भी नाम)।
4. नीचे **Public** पर टिक रहने दें और हरे बटन **Create repository** पर टैप करें।
5. अगले पेज पर नीले रंग में लिखा होगा **"creating a new file"** — उस पर टैप करें।
6. ऊपर फाइल का नाम लिखने वाले बॉक्स में ठीक यही लिखें: **`index.html`**
7. नीचे बड़े खाली बॉक्स (Edit new file) में **ऊपर कॉपी किया हुआ पूरा कोड पेस्ट (Paste)** कर दें।
8. ऊपर दाईं तरफ हरे बटन **Commit changes...** पर टैप करें और फिर पॉप-अप में भी **Commit changes** दबा दें।

---

### स्टेप 3: गेम का लाइव लिंक निकालें (GitHub Pages ऑन करें)

1. उसी पेज पर ऊपर की तरफ **Settings** टैब पर टैप करें (अगर न दिखे तो दाईं तरफ तीन डॉट्स `...` पर टैप करें)।
2. Settings के अंदर बाईं तरफ (या नीचे स्क्रॉल करने पर) **Pages** लिखा दिखेगा, उस पर टैप करें।
3. **Branch** के नीचे `None` लिखा होगा — उस पर टैप करके **`main`** चुनें और बगल में **Save** बटन दबा दें।
4. **1 से 2 मिनट रुकें** और पेज को रिफ्रेश (Reload) करें। सबसे ऊपर आपको एक बॉक्स में लिखा दिखेगा:
   **`Your site is live at https://आपका-यूज़रनेम.github.io/snake-game/`**

---

### स्टेप 4: Prism Live Studio में चलाएं
1. इस लाइव लिंक को कॉपी करें।
2. अपने **Prism Live Studio** ऐप में जाएं -> **Web Widget** खोलें -> यह लिंक पेस्ट करें और स्क्रीन पर सेट कर दें। 
3. गेम अपने आप चलने लगेगा! आप लाइव स्ट्रीम के दौरान ऊपर बने किसी भी गिफ्ट आइकन पर टच करके सांप का रंग बदल सकते हैं, सेब बढ़ा सकते हैं या बम फोड़ सकते हैं।

<FollowUp>
जब आप यह कोड GitHub पर डाल लें, तो बताइएगा—अगर आपको इसमें **कोई नाम (`67=ban` की जगह कुछ और) या लेवल नंबर बदलना हो**, तो मैं बता दूँगा कि कोड की किस लाइन में बदलाव करना है।
</FollowUp>
