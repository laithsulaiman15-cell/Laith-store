<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Life Store</title>
<style>
  body { margin:0; font-family:Arial; background:#000; color:#0ff; text-align:center; }
  header { padding:20px; background:#111; border-bottom:2px solid #0ff; }
  .game { display:inline-block; width:220px; margin:20px; padding:15px; border:1px solid #0ff; border-radius:12px; background:#020202; }
  .game img { width:180px; height:180px; border-radius:10px; }
  button { margin-top:10px; padding:10px 15px; background:#0ff; color:#000; border:none; border-radius:6px; cursor:pointer; }
</style>
</head>
<body>

<header>
  <h1>🎮 Life Store</h1>
  <p>Install and play games directly!</p>
</header>

<div id="games-container"></div>

<iframe id="game-frame" style="width:100%;height:400px;border:none;display:none;margin-top:20px;"></iframe>

<script>
// الألعاب التجريبية
const games = [
  {
    name: "Hacker Simulator",
    icon: "https://via.placeholder.com/180/00ffcc/000000?text=HACKER",
    html: `<h1>🕶️ Hacker Simulator</h1><p>Status: Connected</p><p>IP: 192.168.0.1</p><button onclick="document.getElementById('log').innerText='Hacking... Access Granted ✔'">Start Hack</button><p id="log"></p>`
  },
  {
    name: "Spy Mission",
    icon: "https://via.placeholder.com/180/00ffcc/000000?text=SPY",
    html: `<h1>🕵️ Spy Mission</h1><p>Objective: Collect secret files</p><button onclick="document.getElementById('status').innerText='Mission Completed Successfully ✔'">Start Mission</button><p id="status"></p>`
  },
  {
    name: "Puzzle Mania",
    icon: "https://via.placeholder.com/180/00ffcc/000000?text=PUZZLE",
    html: `<h1>🧩 Puzzle Mania</h1><p>Solve the puzzle!</p><button onclick="document.getElementById('result').innerText='Puzzle Solved ✔'">Solve Puzzle</button><p id="result"></p>`
  }
];

// إنشاء المتجر
const container = document.getElementById('games-container');

games.forEach((game,index)=>{
  const div=document.createElement('div');
  div.className='game';
  div.innerHTML=`<img src="${game.icon}"><h3>${game.name}</h3><button onclick="openGame(${index})">Play</button>`;
  container.appendChild(div);
});

function openGame(index){
  const iframe=document.getElementById('game-frame');
  iframe.style.display='block';
  iframe.srcdoc=games[index].html;
  window.scrollTo(0,iframe.offsetTop);
}
</script>

</body>
</html>
