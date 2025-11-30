# Tortieei-Adventurewlee
Projek pertama tortie's wlee
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Tortie's Adventure 🐾</title>
<link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@600;700&family=Bubblegum+Sans&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:Fredoka,sans-serif;background:linear-gradient(180deg,#ffd4e5 0%,#e8c5f5 50%,#c5e3ff 100%);min-height:100vh;overflow-x:hidden}
@keyframes float{0%,100%{transform:translate(0,0)}50%{transform:translate(30px,-40px)}}
.deco{position:fixed;border-radius:50%;background:rgba(255,255,255,.2);pointer-events:none;animation:float 15s infinite}
.container{max-width:1200px;margin:0 auto;padding:25px}
.hdr{background:rgba(255,255,255,.95);border-radius:35px;padding:25px 30px;box-shadow:0 15px 50px rgba(0,0,0,.1);margin-bottom:25px}
.top{display:flex;justify-content:space-between;align-items:center;flex-wrap:wrap;gap:15px;margin-bottom:20px}
.ttl{font-family:'Bubblegum Sans',cursive;font-size:2.3em;background:linear-gradient(135deg,#ff6b9d,#c44569);-webkit-background-clip:text;-webkit-text-fill-color:transparent;display:flex;align-items:center;gap:12px}
.bdg{display:flex;gap:12px;align-items:center;flex-wrap:wrap}
.badge{background:linear-gradient(135deg,#ffd93d,#ffb347);padding:10px 20px;border-radius:25px;font-weight:700;color:#8b4513;display:flex;align-items:center;gap:8px;box-shadow:0 5px 15px rgba(255,179,71,.4);border:3px solid #fff}
.cat-btn{position:relative;padding:14px 26px;border:4px solid #fff;border-radius:22px;font-family:Fredoka,sans-serif;font-weight:700;font-size:1em;cursor:pointer;box-shadow:0 8px 0 rgba(0,0,0,.15),0 10px 25px rgba(0,0,0,.2);transition:all .2s;overflow:visible}
.cat-btn:active{transform:translateY(6px);box-shadow:0 2px 0 rgba(0,0,0,.15)}
.cat-btn::before,.cat-btn::after{content:'';position:absolute;width:22px;height:24px;background:inherit;top:-13px;border:4px solid #fff;border-bottom:none;border-radius:50% 50% 0 0}
.cat-btn::before{left:20%;transform:rotate(-12deg)}
.cat-btn::after{right:20%;transform:rotate(12deg)}
.cat-btn .ear-l,.cat-btn .ear-r{position:absolute;width:11px;height:13px;background:#ffb3d9;border-radius:50%;top:-8px}
.cat-btn .ear-l{left:calc(20% + 5px)}
.cat-btn .ear-r{right:calc(20% + 5px)}
.cat-btn .shine{position:absolute;top:0;left:0;right:0;height:45%;background:linear-gradient(180deg,rgba(255,255,255,.4),transparent);border-radius:inherit;pointer-events:none}
.btn-quest{background:linear-gradient(180deg,#b4f8c8,#7ce89f);color:#2d5a3f}
.btn-music{background:linear-gradient(180deg,#e0c3fc,#c49ddb);color:#5a3a6f;width:55px;height:55px;padding:0;display:flex;align-items:center;justify-content:center;border-radius:50%;font-size:1.4em}
.btn-music::before,.btn-music::after,.btn-music .ear-l,.btn-music .ear-r{display:none}
.btn-music.on{animation:pulse 1s infinite}
@keyframes pulse{0%,100%{transform:scale(1)}50%{transform:scale(1.1)}}
.stats{display:grid;grid-template-columns:repeat(auto-fit,minmax(220px,1fr));gap:15px;margin-bottom:18px}
.stat{background:rgba(255,255,255,.6);padding:12px 16px;border-radius:20px;border:3px solid #fff}
.stat-label{display:flex;align-items:center;gap:8px;font-weight:600;color:#555;margin-bottom:8px}
.bar-bg{background:#fff;height:20px;border-radius:12px;overflow:hidden;border:2px solid rgba(0,0,0,.08);box-shadow:inset 0 2px 4px rgba(0,0,0,.1)}
.bar{height:100%;display:flex;align-items:center;justify-content:center;font-size:.75em;font-weight:700;color:#fff;text-shadow:1px 1px 2px rgba(0,0,0,.3);transition:width .8s}
.bar-hunger{background:linear-gradient(90deg,#ff9a9e,#fecfef)}
.bar-happy{background:linear-gradient(90deg,#fa709a,#fee140)}
.bar-energy{background:linear-gradient(90deg,#30cfd0,#330867)}
.bar-exp{background:linear-gradient(90deg,#a8edea,#fed6e3)}
.arena{background:rgba(255,255,255,.95);border-radius:35px;min-height:480px;padding:35px;box-shadow:0 15px 50px rgba(0,0,0,.15);position:relative;overflow:hidden;margin-bottom:25px}
.cat{position:absolute;cursor:pointer;transition:all 1s cubic-bezier(.34,1.56,.64,1);filter:drop-shadow(0 10px 20px rgba(0,0,0,.15));z-index:10}
.cat:hover{transform:scale(1.08) rotate(-3deg)}
.cat-body{position:relative;width:120px;height:95px}
.tail{position:absolute;right:-50px;top:28px;width:58px;height:13px;background:linear-gradient(90deg,#2d1810,#9d6b4f,#3d2515);border-radius:0 25px 25px 0;transform-origin:left;animation:wag 2.5s ease-in-out infinite;z-index:1}
@keyframes wag{0%,100%{transform:rotate(-8deg)}50%{transform:rotate(18deg)}}
.tail.fast{animation:wagFast .4s ease-in-out infinite}
@keyframes wagFast{0%,100%{transform:rotate(-15deg)}50%{transform:rotate(30deg)}}
.body{width:115px;height:80px;background:linear-gradient(135deg,#2d1810,#8b5a3c,#d4915c,#7a5236,#2d1810);border-radius:48% 48% 52% 52%;position:relative;z-index:2}
.spot{position:absolute;border-radius:60% 40% 50% 50%;opacity:.85}
.s1{width:30px;height:26px;background:radial-gradient(#e89a5b,#d4823f);top:18px;left:18px;transform:rotate(-15deg)}
.s2{width:26px;height:22px;background:radial-gradient(#c17443,#9d5a2f);bottom:20px;right:16px;transform:rotate(25deg)}
.s3{width:22px;height:18px;background:radial-gradient(#956b48,#7a5236);top:35px;right:22px;transform:rotate(-8deg)}
.head{position:absolute;top:-40px;left:26px;width:72px;height:68px;background:linear-gradient(135deg,#2d1810,#a57b5c,#3d2515);border-radius:52% 52% 48% 48%;z-index:3}
.hs1{width:22px;height:18px;background:radial-gradient(#e89a5b,#d4823f);top:13px;right:9px;transform:rotate(15deg)}
.hs2{width:18px;height:16px;background:radial-gradient(#c17443,#9d5a2f);bottom:17px;left:11px;transform:rotate(-20deg)}
.ear{position:absolute;width:18px;height:23px;background:linear-gradient(180deg,#3d2515,#8b5a3c);border-radius:50% 50% 25% 25%;top:-9px}
.ear::after{content:'';position:absolute;width:10px;height:12px;background:#ffb6c1;border-radius:50%;top:4px;left:50%;transform:translateX(-50%)}
.ear-l{left:13px;transform:rotate(-18deg)}
.ear-r{right:13px;transform:rotate(18deg)}
.eye{position:absolute;width:16px;height:19px;background:radial-gradient(#f9e79f,#f4d03f);border-radius:50%;border:2px solid #2d1810;top:28px;display:flex;align-items:center;justify-content:center}
.eye-l{left:15px}
.eye-r{right:15px}
.pupil{width:7px;height:12px;background:#000;border-radius:50%;transition:transform .2s;position:relative}
.pupil::after{content:'';position:absolute;width:3px;height:4px;background:rgba(255,255,255,.6);border-radius:50%;top:2px;left:1px}
.eye.sleep{background:#3d2515;border-radius:50% 50% 0 0;height:10px;overflow:hidden}
.eye.sleep .pupil{display:none}
.nose{position:absolute;width:8px;height:6px;background:#ffb3ba;border-radius:50%;bottom:19px;left:50%;transform:translateX(-50%)}
.mouth{position:absolute;bottom:14px;left:50%;transform:translateX(-50%);font-size:14px;color:#3d2515}
.w{position:absolute;height:1.5px;background:rgba(0,0,0,.4);top:36px}
.w1{width:26px;left:-27px;transform:rotate(-8deg)}
.w2{width:23px;left:-24px;top:40px;transform:rotate(6deg)}
.w3{width:26px;right:-27px;transform:rotate(8deg)}
.w4{width:23px;right:-24px;top:40px;transform:rotate(-6deg)}
.leg{position:absolute;width:18px;height:36px;background:linear-gradient(180deg,#3d2515,#8b5a3c,#7a5236);border-radius:10px 10px 13px 13px;bottom:-33px}
.l1{left:14px}
.l2{left:40px}
.l3{right:40px}
.l4{right:14px}
.toy{position:absolute;cursor:pointer;font-size:46px;animation:bounce 2s ease-in-out infinite;filter:drop-shadow(0 5px 10px rgba(0,0,0,.2));z-index:5}
.toy:hover{transform:scale(1.4) rotate(20deg)}
@keyframes bounce{0%,100%{transform:translateY(0)}50%{transform:translateY(-15px)}}
.food{position:absolute;font-size:40px;animation:fall 1.5s ease-out forwards;filter:drop-shadow(0 5px 10px rgba(0,0,0,.2));z-index:5}
@keyframes fall{0%{transform:translateY(-60px) rotate(0deg);opacity:0}30%{opacity:1}100%{transform:translateY(450px) rotate(240deg);opacity:0}}
.heart{position:absolute;font-size:26px;animation:rise 2.5s ease-out forwards;pointer-events:none;z-index:15}
@keyframes rise{0%{opacity:1;transform:translateY(0) scale(.8)}100%{opacity:0;transform:translateY(-100px) scale(1.5)}}
.actions{display:grid;grid-template-columns:repeat(auto-fit,minmax(145px,1fr));gap:20px;margin-top:25px}
.action{text-align:center}
.action .icon{font-size:2.6em;display:block;margin-bottom:6px;filter:drop-shadow(2px 3px 4px rgba(0,0,0,.2))}
.action .txt{font-size:1.05em;font-weight:700;display:block;position:relative;z-index:2}
.action:disabled{opacity:.45;cursor:not-allowed;filter:grayscale(.6)}
.btn-feed{background:linear-gradient(180deg,#ffe5b4,#ffb347);color:#8b4513}
.btn-play{background:linear-gradient(180deg,#e0aaff,#b892cf);color:#4a2a5a}
.btn-sleep{background:linear-gradient(180deg,#aec6cf,#779ecb);color:#2c3e50}
.btn-pet{background:linear-gradient(180deg,#ffb6d9,#ff85b3);color:#8b1a4f}
.btn-game{background:linear-gradient(180deg,#fffacd,#ffd700);color:#8b6914}
.quest{background:rgba(255,255,255,.95);border-radius:35px;padding:28px;box-shadow:0 15px 50px rgba(0,0,0,.15);margin-bottom:25px;display:none}
.quest.show{display:block;animation:slideIn .5s}
@keyframes slideIn{from{opacity:0;transform:translateY(-30px)}to{opacity:1;transform:translateY(0)}}
.qtitle{font-family:'Bubblegum Sans',cursive;font-size:2.1em;color:#56c596;margin-bottom:22px;display:flex;align-items:center;gap:10px}
.qgrid{display:grid;grid-template-columns:repeat(auto-fit,minmax(270px,1fr));gap:18px}
.qcard{background:linear-gradient(135deg,#d4f1f4,#b8e6e9);padding:22px;border-radius:26px;border:4px solid #fff;box-shadow:0 8px 20px rgba(0,0,0,.12)}
.qcard h4{font-size:1.25em;color:#2c5f5f;margin-bottom:12px;font-weight:700}
.qprog{font-size:.95em;color:#555;margin-bottom:10px;font-weight:600}
.qbar-bg{background:#fff;height:11px;border-radius:9px;overflow:hidden;margin-bottom:16px;border:2px solid rgba(0,0,0,.08)}
.qbar{height:100%;background:linear-gradient(90deg,#56c596,#2aa876);transition:width .5s;border-radius:9px}
.claim{width:100%;padding:11px;border-radius:19px;font-weight:700;font-family:Fredoka,sans-serif;cursor:pointer;border:none;font-size:.95em;transition:all .3s}
.claim:not(:disabled){background:linear-gradient(180deg,#b4f8c8,#7ce89f);color:#2d5a3f;box-shadow:0 5px 0 rgba(0,0,0,.12);border:3px solid #fff}
.claim:not(:disabled):active{transform:translateY(4px);box-shadow:0 1px 0 rgba(0,0,0,.12)}
.claim:disabled{background:#e0e0e0;color:#999;cursor:not-allowed;border:3px solid #f0f0f0}
.msg{position:absolute;background:#fff;padding:12px 24px;border-radius:24px;box-shadow:0 8px 25px rgba(0,0,0,.2);font-weight:700;font-size:1.15em;color:#555;animation:pop 2.5s ease-out forwards;z-index:20;border:3px solid #ffe5ec}
@keyframes pop{0%{opacity:0;transform:scale(.6) translateY(30px)}25%{opacity:1;transform:scale(1.15) translateY(0)}75%{opacity:1;transform:scale(1) translateY(0)}100%{opacity:0;transform:scale(.8) translateY(-40px)}}
@media(max-width:768px){.ttl{font-size:1.8em}.actions{grid-template-columns:repeat(2,1fr)}.stats{grid-template-columns:1fr}.cat{transform:scale(.85)}}
</style>
</head>
<body>
<div class="deco" style="width:170px;height:170px;top:8%;left:6%"></div>
<div class="deco" style="width:130px;height:130px;top:25%;right:8%;animation-delay:3s"></div>
<div class="container">
<div class="hdr">
<div class="top">
<div class="ttl"><span>🐾</span><span>Tortie's Adventure</span></div>
<div class="bdg">
<div class="badge"><span>⭐</span><span>Level <span id="lvl">1</span></span></div>
<div class="badge"><span>🪙</span><span id="coin">0</span></div>
<button class="cat-btn btn-quest" onclick="toggleQ()">
<span class="ear-l"></span><span class="ear-r"></span><span class="shine"></span>
🏆 Quests
</button>
<button class="btn-music" id="mus" onclick="toggleM()">🎵</button>
</div>
</div>
<div class="stats">
<div class="stat">
<div class="stat-label"><span>🍖</span><span>Hunger</span></div>
<div class="bar-bg"><div class="bar bar-hunger" id="h" style="width:75%">75%</div></div>
</div>
<div class="stat">
<div class="stat-label"><span>💝</span><span>Happiness</span></div>
<div class="bar-bg"><div class="bar bar-happy" id="hp" style="width:70%">70%</div></div>
</div>
<div class="stat">
<div class="stat-label"><span>⚡</span><span>Energy</span></div>
<div class="bar-bg"><div class="bar bar-energy" id="e" style="width:65%">65%</div></div>
</div>
</div>
<div class="stat">
<div class="stat-label"><span>✨</span><span>Experience</span><span style="margin-left:auto;font-size:.9em"><span id="ex">0</span>/<span id="exm">100</span></span></div>
<div class="bar-bg"><div class="bar bar-exp" id="exb" style="width:0%"></div></div>
</div>
</div>
<div class="quest" id="qp">
<div class="qtitle"><span>🎯</span><span>Daily Quests</span></div>
<div class="qgrid">
<div class="qcard">
<h4>🍖 Feeding Master</h4>
<div class="qprog">Progress: <span id="qf">0</span>/3</div>
<div class="qbar-bg"><div class="qbar" id="qfb" style="width:0%"></div></div>
<button class="claim" onclick="claim('f')" id="cf" disabled>Claim 50 🪙</button>
</div>
<div class="qcard">
<h4>🎾 Playful Soul</h4>
<div class="qprog">Progress: <span id="qp2">0</span>/5</div>
<div class="qbar-bg"><div class="qbar" id="qpb" style="width:0%"></div></div>
<button class="claim" onclick="claim('p')" id="cp" disabled>Claim 100 🪙</button>
</div>
<div class="qcard">
<h4>💕 Pet Lover</h4>
<div class="qprog">Progress: <span id="qpe">0</span>/10</div>
<div class="qbar-bg"><div class="qbar" id="qpeb" style="width:0%"></div></div>
<button class="claim" onclick="claim('pe')" id="cpe" disabled>Claim 75 🪙</button>
</div>
</div>
</div>
<div class="arena" id="ar">
<div class="cat" id="c" style="left:42%;top:48%" onclick="pet()">
<div class="cat-body">
<div class="tail" id="t"></div>
<div class="body">
<div class="spot s1"></div>
<div class="spot s2"></div>
<div class="spot s3"></div>
</div>
<div class="head">
<div class="spot hs1"></div>
<div class="spot hs2"></div>
<div class="ear ear-l"></div>
<div class="ear ear-r"></div>
<div class="eye eye-l" id="el"><div class="pupil" id="pl"></div></div>
<div class="eye eye-r" id="er"><div class="pupil" id="pr"></div></div>
<div class="nose"></div>
<div class="mouth">ω</div>
<div class="w w1"></div>
<div class="w w2"></div>
<div class="w w3"></div>
<div class="w w4"></div>
</div>
<div class="leg l1"></div>
<div class="leg l2"></div>
<div class="leg l3"></div>
<div class="leg l4"></div>
</div>
</div>
</div>
<div class="actions">
<button class="action cat-btn btn-feed" onclick="feed()" id="bf">
<span class="ear-l"></span><span class="ear-r"></span><span class="shine"></span>
<span class="icon">🐟</span><span class="txt">FEED</span>
</button>
<button class="action cat-btn btn-play" onclick="play()" id="bp">
<span class="ear-l"></span><span class="ear-r"></span><span class="shine"></span>
<span class="icon">🧶</span><span class="txt">PLAY</span>
</button>
<button class="action cat-btn btn-sleep" onclick="sleep()" id="bs">
<span class="ear-l"></span><span class="ear-r"></span><span class="shine"></span>
<span class="icon">😴</span><span class="txt">SLEEP</span>
</button>
<button class="action cat-btn btn-pet" onclick="pet()">
<span class="ear-l"></span><span class="ear-r"></span><span class="shine"></span>
<span class="icon">💖</span><span class="txt">PET</span>
</button>
<button class="action cat-btn btn-game" onclick="game()">
<span class="ear-l"></span><span class="ear-r"></span><span class="shine"></span>
<span class="icon">🎮</span><span class="txt">GAME</span>
</button>
</div>
</div>
<div id="player" style="display:none"></div>
<script>
// Game state object
let gameState = {
    hunger: 75,
    happiness: 70,
    energy: 65,
    level: 1,
    exp: 0,
    coins: 0,
    status: 'idle',
    music: false,
    quests: {
        feed: 0,
        play: 0,
        pet: 0
    }
};

// Audio elements
const sounds = {
    feed: new Audio('https://assets.mixkit.co/active_storage/sfx/2571/2571-preview.mp3'),
    play: new Audio('https://assets.mixkit.co/active_storage/sfx/2000/2000-preview.mp3'),
    sleep: new Audio('https://assets.mixkit.co/active_storage/sfx/2568/2568-preview.mp3'),
    pet: new Audio('https://assets.mixkit.co/active_storage/sfx/2019/2019-preview.mp3'),
    game: new Audio('https://assets.mixkit.co/active_storage/sfx/1999/1999-preview.mp3')
};

// Initialize game
window.onload = function() {
    loadGame();
    updateUI();
    setupEyes();
};

// Save game state to localStorage
function saveGame() {
    localStorage.setItem('tortieGame', JSON.stringify(gameState));
}

// Load game state from localStorage
function loadGame() {
    const saved = localStorage.getItem('tortieGame');
    if (saved) {
        gameState = JSON.parse(saved);
    }
}

// Update all UI elements
function updateUI() {
    // Update stats bars
    updateBar('h', gameState.hunger);
    updateBar('hp', gameState.happiness);
    updateBar('e', gameState.energy);
    
    // Update level and coins
    document.getElementById('lvl').textContent = gameState.level;
    document.getElementById('coin').textContent = gameState.coins;
    
    // Update experience
    const expMax = gameState.level * 100;
    document.getElementById('ex').textContent = Math.floor(gameState.exp);
    document.getElementById('exm').textContent = expMax;
    document.getElementById('exb').style.width = `${(gameState.exp / expMax) * 100}%`;
    
    // Check for level up
    if (gameState.exp >= expMax) {
        levelUp();
    }
    
    // Update quests
    updateQuest('f', 3);
    updateQuest('p', 5);
    updateQuest('pe', 10);
    
    // Update button states
    document.getElementById('bf').disabled = gameState.hunger >= 95;
    document.getElementById('bs').disabled = gameState.energy >= 95;
    document.getElementById('bp').disabled = gameState.energy < 10;
    
    saveGame();
}

// Update a progress bar
function updateBar(id, value) {
    const bar = document.getElementById(id);
    const percent = Math.round(value);
    bar.style.width = `${percent}%`;
    bar.textContent = `${percent}%`;
}

// Update quest progress
function updateQuest(type, target) {
    const current = gameState.quests[type];
    document.getElementById(`q${type}`).textContent = current;
    document.getElementById(`q${type}b`).style.width = `${(current / target) * 100}%`;
    document.getElementById(`c${type}`).disabled = current < target;
}

// Level up function
function levelUp() {
    gameState.level++;
    gameState.exp = 0;
    gameState.hunger = Math.min(100, gameState.hunger + 10);
    gameState.happiness = Math.min(100, gameState.happiness + 15);
    gameState.energy = Math.min(100, gameState.energy + 20);
    gameState.coins += 50;
    
    showMessage(`Level Up! 🎉 Now Level ${gameState.level}`);
    updateUI();
}

// Feed the cat
function feed() {
    if (gameState.hunger >= 95) return;
    
    gameState.status = 'eating';
    gameState.hunger = Math.min(100, gameState.hunger + 25);
    gameState.happiness = Math.min(100, gameState.happiness + 5);
    gameState.exp += 10;
    gameState.quests.feed++;
    
    dropFood();
    showMessage('Yummy! 😋');
    moveCat(Math.random() * 55 + 25, Math.random() * 45 + 25);
    playSound('feed');
    
    setTimeout(() => {
        gameState.status = 'idle';
    }, 2000);
    
    updateUI();
}

// Play with the cat
function play() {
    if (gameState.energy < 10) return;
    
    gameState.status = 'playing';
    gameState.happiness = Math.min(100, gameState.happiness + 20);
    gameState.energy = Math.max(0, gameState.energy - 10);
    gameState.exp += 15;
    gameState.quests.play++;
    
    spawnToy();
    showMessage('Wheee! 🎉');
    document.getElementById('t').classList.add('fast');
    playSound('play');
    
    setTimeout(() => {
        gameState.status = 'idle';
        document.getElementById('t').classList.remove('fast');
    }, 2500);
    
    updateUI();
}

// Put cat to sleep
function sleep() {
    if (gameState.energy >= 95) return;

gameState.status = 'sleeping';
    gameState.energy = Math.min(100, gameState.energy + 40);
    gameState.happiness = Math.min(100, gameState.happiness + 10);
    gameState.exp += 12;
    
    document.getElementById('el').classList.add('sleep');
    document.getElementById('er').classList.add('sleep');
    showMessage('Zzz... 💤');
    spawnEffect('💤', 4);
    playSound('sleep');
    
    setTimeout(() => {
        gameState.status = 'idle';
        document.getElementById('el').classList.remove('sleep');
        document.getElementById('er').classList.remove('sleep');
    }, 3500);
    
    updateUI();
}

// Pet the cat
function pet() {
    gameState.happiness = Math.min(100, gameState.happiness + 15);
    gameState.exp += 8;
    gameState.coins += 5;
    gameState.quests.pet++;
    
    showMessage('Purr~ 💕');
    spawnEffect('💖', 6);
    playSound('pet');
    
    updateUI();
}

// Start minigame
function game() {
    showMessage('Catch them all! 🎯');
    
    for (let i = 0; i < 6; i++) {
        setTimeout(() => {
            const toy = createToy();
            toy.onclick = () => {
                gameState.coins += 10;
                gameState.exp += 20;
                gameState.happiness = Math.min(100, gameState.happiness + 5);
                spawnEffect('⭐', 3);
                toy.remove();
                playSound('game');
                updateUI();
            };
        }, i * 1600);
    }
}

// Move cat to position
function moveCat(x, y) {
    document.getElementById('c').style.left = `${x}%`;
    document.getElementById('c').style.top = `${y}%`;
}

// Drop food animation
function dropFood() {
    const arena = document.getElementById('ar');
    const food = document.createElement('div');
    food.className = 'food';
    food.textContent = '🐟';
    food.style.left = `${Math.random() * 65 + 18}%`;
    food.style.top = '0';
    arena.appendChild(food);
    
    setTimeout(() => food.remove(), 1500);
}

// Create a toy
function createToy() {
    const arena = document.getElementById('ar');
    const toy = document.createElement('div');
    toy.className = 'toy';
    toy.textContent = '🧶';
    
    const randomLeft = Math.random() * 68 + 12;
    const randomTop = Math.random() * 58 + 18;
    
    toy.style.left = `${randomLeft}%`;
    toy.style.top = `${randomTop}%`;
    
    arena.appendChild(toy);
    moveCat(randomLeft, randomTop);
    
    // Remove toy after 5 seconds
    setTimeout(() => {
        if (toy.parentNode) {
            toy.remove();
        }
    }, 5000);
    
    return toy;
}

// Spawn toy (alias for createToy)
function spawnToy() {
    return createToy();
}

// Spawn visual effects
function spawnEffect(emoji, count) {
    const arena = document.getElementById('ar');
    
    for (let i = 0; i < count; i++) {
        const effect = document.createElement('div');
        effect.className = 'heart';
        effect.textContent = emoji;
        effect.style.left = `${Math.random() * 80 + 10}%`;
        effect.style.top = `${Math.random() * 60 + 20}%`;
        
        arena.appendChild(effect);
        
        setTimeout(() => {
            if (effect.parentNode) {
                effect.remove();
            }
        }, 2500);
    }
}

// Show message bubble
function showMessage(text) {
    const arena = document.getElementById('ar');
    const msg = document.createElement('div');
    msg.className = 'msg';
    msg.textContent = text;
    msg.style.left = `${Math.random() * 60 + 20}%`;
    msg.style.top = `${Math.random() * 40 + 10}%`;
    
    arena.appendChild(msg);
    
    setTimeout(() => {
        if (msg.parentNode) {
            msg.remove();
        }
    }, 2500);
}

// Play sound effect
function playSound(type) {
    if (sounds[type]) {
        sounds[type].currentTime = 0;
        sounds[type].play().catch(e => console.log("Audio play failed:", e));
    }
}

// Setup eye tracking
function setupEyes() {
    document.addEventListener('mousemove', (e) => {
        if (gameState.status === 'sleeping') return;
        
        const cat = document.getElementById('c');
        const rect = cat.getBoundingClientRect();
        const catX = rect.left + rect.width / 2;
        const catY = rect.top + rect.height / 2;
        
        const angle = Math.atan2(e.clientY - catY, e.clientX - catX);
        const distance = Math.min(4, Math.sqrt(
            Math.pow(e.clientX - catX, 2) + Math.pow(e.clientY - catY, 2)
        ) / 80);
        
        const moveX = Math.cos(angle) * distance;
        const moveY = Math.sin(angle) * distance;
        
        const pupilL = document.getElementById('pl');
        const pupilR = document.getElementById('pr');
        
        if (pupilL && pupilR) {
            pupilL.style.transform = `translate(${moveX}px, ${moveY}px)`;
            pupilR.style.transform = `translate(${moveX}px, ${moveY}px)`;
        }
    });
}

// Toggle quest panel
function toggleQ() {
    const questPanel = document.getElementById('qp');
    questPanel.classList.toggle('show');
}

// Toggle music
function toggleM() {
    const musicBtn = document.getElementById('mus');
    gameState.music = !gameState.music;
    
    if (gameState.music) {
        musicBtn.classList.add('on');
        // In a real implementation, you would play YouTube music here
        // For now, we'll just log to console
        console.log("Music started");
    } else {
        musicBtn.classList.remove('on');
        console.log("Music stopped");
    }
}

// Claim quest reward
function claim(type) {
    const rewards = {
        'f': 50,
        'p': 100,
        'pe': 75
    };
    
    if (gameState.quests[type] >= (type === 'f' ? 3 : type === 'p' ? 5 : 10)) {
        gameState.coins += rewards[type];
        gameState.quests[type] = 0;
        showMessage(`Claimed ${rewards[type]} coins! 💰`);
        updateUI();
    }
}
</script>
</body>
</html>

