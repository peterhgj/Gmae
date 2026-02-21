<!DOCTYPE html>
<html lang="my">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Starfighter Pro Edition</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;900&display=swap');
        
        body { margin: 0; overflow: hidden; background: #000; touch-action: none; font-family: 'Orbitron', sans-serif; }
        canvas { display: block; }
        
        /* UI Containers */
        .overlay { position: absolute; inset: 0; display: flex; flex-direction: column; align-items: center; justify-content: center; z-index: 100; transition: opacity 0.5s; }
        .hidden { display: none !important; opacity: 0; pointer-events: none; }
        
        /* Glassmorphism UI */
        .glass-panel { background: rgba(0, 20, 40, 0.8); backdrop-filter: blur(10px); border: 2px solid rgba(0, 255, 255, 0.2); border-radius: 24px; padding: 40px; box-shadow: 0 0 40px rgba(0, 255, 255, 0.1); text-align: center; max-width: 90%; }
        
        .btn-primary { background: linear-gradient(45deg, #00f2ff, #0062ff); color: white; padding: 16px 48px; border-radius: 50px; font-weight: 900; font-size: 1.5rem; letter-spacing: 2px; box-shadow: 0 0 20px rgba(0, 242, 255, 0.5); transition: 0.2s; cursor: pointer; border: none; }
        .btn-primary:active { transform: scale(0.95); box-shadow: 0 0 10px rgba(0, 242, 255, 0.3); }
        
        .game-ui { position: absolute; inset: 0; pointer-events: none; padding: 20px; z-index: 50; display: none; }
        
        /* Ship Selector */
        .ship-option { width: 60px; height: 60px; border: 2px solid transparent; border-radius: 12px; display: flex; align-items: center; justify-content: center; cursor: pointer; transition: 0.3s; }
        .ship-option.active { border-color: #00f2ff; background: rgba(0, 242, 255, 0.1); transform: scale(1.1); }
        
        .stat-bar { width: 120px; height: 6px; background: rgba(255,255,255,0.1); border-radius: 3px; overflow: hidden; }
        #hp-fill { width: 100%; height: 100%; background: #00f2ff; transition: width 0.3s; }
        
        #boss-ui { position: absolute; top: 40px; left: 50%; transform: translateX(-50%); width: 80%; display: none; }
        .boss-hp-bg { width: 100%; height: 8px; background: #222; border-radius: 4px; border: 1px solid #f00; overflow: hidden; }
        #boss-hp-fill { width: 100%; height: 100%; background: #f00; }

        .shop-btn { pointer-events: auto; background: rgba(0,0,0,0.5); border: 1px solid rgba(0,255,255,0.2); padding: 8px; border-radius: 12px; min-width: 65px; }
        .shop-btn.disabled { opacity: 0.3; filter: grayscale(1); }
    </style>
</head>
<body>

    <!-- Start Menu -->
    <div id="start-menu" class="overlay">
        <div class="glass-panel">
            <h1 class="text-4xl md:text-6xl font-black italic text-transparent bg-clip-text bg-gradient-to-b from-cyan-400 to-blue-600 mb-2">STARFIGHTER</h1>
            <p class="text-cyan-400/60 tracking-[0.3em] text-xs mb-8 uppercase">Pro Evolution War</p>
            
            <div class="mb-8">
                <p class="text-gray-400 text-[10px] mb-3 uppercase tracking-widest">Select Your Ship</p>
                <div class="flex justify-center gap-4">
                    <div onclick="selectShip('#00f2ff', 0)" class="ship-option active" id="ship-0">
                        <svg width="30" height="30" viewBox="0 0 40 40"><path d="M20,5 L5,35 L20,25 L35,35 Z" fill="#00f2ff"/></svg>
                    </div>
                    <div onclick="selectShip('#ff3e3e', 1)" class="ship-option" id="ship-1">
                        <svg width="30" height="30" viewBox="0 0 40 40"><path d="M20,5 L5,35 L20,25 L35,35 Z" fill="#ff3e3e"/></svg>
                    </div>
                    <div onclick="selectShip('#facc15', 2)" class="ship-option" id="ship-2">
                        <svg width="30" height="30" viewBox="0 0 40 40"><path d="M20,5 L5,35 L20,25 L35,35 Z" fill="#facc15"/></svg>
                    </div>
                </div>
            </div>

            <button onclick="startGame()" class="btn-primary mb-6">LAUNCH</button>
            <div class="text-gray-500 text-[10px] uppercase">High Score: <span id="best-score">0</span></div>
        </div>
    </div>

    <!-- In-Game UI -->
    <div id="game-ui" class="game-ui">
        <div class="flex justify-between items-start text-white">
            <div class="space-y-2">
                <div>
                    <div class="text-[9px] uppercase opacity-50 font-bold">Health</div>
                    <div class="stat-bar"><div id="hp-fill"></div></div>
                </div>
                <div class="text-yellow-400 font-bold">💎 <span id="gem-txt">0</span></div>
            </div>
            <div class="text-right">
                <div class="text-xs text-cyan-400 font-bold" id="sector-txt">SECTOR 1</div>
                <div class="text-2xl font-black italic" id="score-txt">0</div>
            </div>
        </div>

        <div id="boss-ui">
            <div class="text-red-500 text-[9px] font-black tracking-widest mb-1 text-center">BOSS DETECTED</div>
            <div class="boss-hp-bg"><div id="boss-hp-fill"></div></div>
        </div>

        <!-- Mobile Shop -->
        <div class="absolute bottom-6 left-0 right-0 flex justify-center gap-3 px-4">
            <button onclick="buyUpgrade('weapon')" id="btn-weapon" class="shop-btn flex flex-col items-center">
                <span class="text-[8px] text-gray-400">WEAPON</span>
                <span class="text-[10px] text-white">🔫 1</span>
            </button>
            <button onclick="activateShield()" id="btn-shield" class="shop-btn flex flex-col items-center disabled">
                <span class="text-[8px] text-gray-400">SHIELD</span>
                <span class="text-[10px] text-white">🛡️ RDY</span>
            </button>
            <button onclick="buyUpgrade('heal')" id="btn-heal" class="shop-btn flex flex-col items-center">
                <span class="text-[8px] text-gray-400">REPAIR</span>
                <span class="text-[10px] text-white">🛠️ 30</span>
            </button>
        </div>
    </div>

    <!-- Game Over -->
    <div id="game-over" class="overlay hidden">
        <div class="glass-panel border-red-500/30">
            <h2 class="text-4xl font-black text-red-500 mb-2">SYSTEM FAILURE</h2>
            <p class="text-gray-400 text-xs mb-8 uppercase">ယာဉ်ပျက်စီးသွားပါပြီ</p>
            <div class="flex justify-around mb-10 text-white">
                <div><div class="text-[10px] opacity-50">SCORE</div><div class="text-2xl font-bold" id="final-score">0</div></div>
                <div><div class="text-[10px] opacity-50">BEST</div><div class="text-2xl font-bold" id="final-best">0</div></div>
            </div>
            <button onclick="resetGame()" class="btn-primary">RELAUNCH</button>
        </div>
    </div>

    <canvas id="gameCanvas"></canvas>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth;
        canvas.height = window.innerHeight;

        // --- Game State ---
        let gameState = 'START'; // START, PLAY, OVER
        let score = 0, gems = 0, level = 1, playerHP = 100;
        let bestScore = localStorage.getItem('starfighter_best') || 0;
        document.getElementById('best-score').innerText = bestScore;

        let playerColor = '#00f2ff';
        let player = { x: canvas.width/2, y: canvas.height - 150, targetX: canvas.width/2, targetY: canvas.height - 150 };
        let projectiles = [], enemyProjectiles = [], enemies = [], boss = null, items = [], particles = [];
        let stars = [], frame = 0, weaponLevel = 1, shieldActive = false, shieldCharge = 0;

        for(let i=0; i<100; i++) stars.push({ x: Math.random()*canvas.width, y: Math.random()*canvas.height, s: Math.random()*2, v: Math.random()*3+1 });

        // --- Controls ---
        const handleMove = (e) => {
            if(gameState !== 'PLAY') return;
            const x = e.touches ? e.touches[0].clientX : e.clientX;
            const y = e.touches ? e.touches[0].clientY : e.clientY;
            player.targetX = x; player.targetY = y - 60;
        };
        window.addEventListener('mousemove', handleMove);
        window.addEventListener('touchmove', e => { e.preventDefault(); handleMove(e); }, { passive: false });

        function selectShip(color, index) {
            playerColor = color;
            document.querySelectorAll('.ship-option').forEach(el => el.classList.remove('active'));
            document.getElementById('ship-' + index).classList.add('active');
        }

        function startGame() {
            gameState = 'PLAY';
            document.getElementById('start-menu').classList.add('hidden');
            document.getElementById('game-ui').style.display = 'block';
            spawnEnemy();
        }

        function resetGame() {
            location.reload();
        }

        function buyUpgrade(type) {
            if(type === 'weapon' && gems >= 50 && weaponLevel < 4) {
                gems -= 50; weaponLevel++;
            } else if(type === 'heal' && gems >= 30) {
                gems -= 30; playerHP = Math.min(100, playerHP + 40);
            }
            updateUI();
        }

        function activateShield() {
            if(shieldCharge >= 100) {
                shieldActive = true;
                shieldCharge = 0;
                setTimeout(() => shieldActive = false, 5000);
            }
            updateUI();
        }

        function updateUI() {
            document.getElementById('gem-txt').innerText = gems;
            document.getElementById('score-txt').innerText = score;
            document.getElementById('hp-fill').style.width = playerHP + '%';
            document.getElementById('sector-txt').innerText = 'SECTOR ' + level;
            
            const btn = document.getElementById('btn-shield');
            if(shieldCharge >= 100) btn.classList.remove('disabled');
            else btn.classList.add('disabled');
        }

        // --- Drawing ---
        function drawPlayer(x, y) {
            ctx.save(); ctx.translate(x, y);
            
            // Shield effect
            if(shieldActive) {
                ctx.beginPath(); ctx.arc(0,0,50,0,Math.PI*2);
                ctx.strokeStyle = '#00f2ff'; ctx.lineWidth = 3; ctx.stroke();
                ctx.fillStyle = 'rgba(0, 242, 255, 0.1)'; ctx.fill();
            }

            // Ship body
            ctx.fillStyle = playerColor;
            ctx.shadowBlur = 15; ctx.shadowColor = playerColor;
            ctx.beginPath();
            ctx.moveTo(0, -35); ctx.lineTo(-25, 15); ctx.lineTo(0, 5); ctx.lineTo(25, 15); ctx.closePath(); ctx.fill();
            
            // Cockpit
            ctx.fillStyle = '#fff'; ctx.beginPath(); ctx.ellipse(0, -5, 4, 8, 0, 0, Math.PI*2); ctx.fill();
            ctx.restore();
        }

        function spawnEnemy() {
            if(gameState !== 'PLAY' || boss) return;
            enemies.push({
                x: Math.random()*(canvas.width-60)+30, y: -50, r: 25,
                hp: 1 + Math.floor(level/2), v: 2 + level*0.3,
                ls: frame, color: `hsl(${200 + level*20}, 70%, 50%)`
            });
            setTimeout(spawnEnemy, Math.max(300, 1500 - level*100));
        }

        function spawnBoss() {
            document.getElementById('boss-ui').style.display = 'block';
            const hp = 100 + (level*50);
            boss = { x: canvas.width/2, y: -150, ty: 150, r: 100, hp, maxHp: hp, ls: frame, v: 2, dir: 1 };
        }

        function update() {
            ctx.fillStyle = '#00050a'; ctx.fillRect(0,0,canvas.width, canvas.height);

            // Stars
            ctx.fillStyle = '#444';
            stars.forEach(s => {
                s.y += s.v; if(s.y > canvas.height) s.y = -10;
                ctx.fillRect(s.x, s.y, s.s, s.s);
            });

            if(gameState === 'PLAY') {
                player.x += (player.targetX - player.x) * 0.15;
                player.y += (player.targetY - player.y) * 0.15;
                drawPlayer(player.x, player.y);

                // Shoot
                if(frame % 10 === 0) {
                    projectiles.push({ x: player.x, y: player.y-25, vx: 0, vy: -15, c: playerColor });
                    if(weaponLevel >= 2) {
                        projectiles.push({ x: player.x-15, y: player.y-5, vx: -1, vy: -14, c: playerColor });
                        projectiles.push({ x: player.x+15, y: player.y-5, vx: 1, vy: -14, c: playerColor });
                    }
                }

                // Projectiles
                projectiles.forEach((p, i) => {
                    p.x += p.vx; p.y += p.vy;
                    ctx.fillStyle = p.c; ctx.fillRect(p.x-2, p.y, 4, 15);
                    if(p.y < -50) projectiles.splice(i, 1);
                });

                enemyProjectiles.forEach((p, i) => {
                    p.y += p.vy;
                    ctx.fillStyle = '#ff4444'; ctx.beginPath(); ctx.arc(p.x, p.y, 6, 0, Math.PI*2); ctx.fill();
                    if(Math.hypot(p.x-player.x, p.y-player.y) < 30) {
                        if(!shieldActive) { playerHP -= 10; updateUI(); }
                        enemyProjectiles.splice(i, 1);
                        if(playerHP <= 0) endGame();
                    }
                    if(p.y > canvas.height+50) enemyProjectiles.splice(i, 1);
                });

                // Enemies
                enemies.forEach((e, i) => {
                    e.y += e.v;
                    ctx.fillStyle = e.color; ctx.beginPath(); ctx.moveTo(e.x, e.y+e.r); ctx.lineTo(e.x-e.r, e.y-e.r); ctx.lineTo(e.x+e.r, e.y-e.r); ctx.fill();
                    
                    if(frame - e.ls > 100 - level*5) {
                        enemyProjectiles.push({ x: e.x, y: e.y+10, vy: 6+level*0.4 });
                        e.ls = frame;
                    }

                    projectiles.forEach((p, pi) => {
                        if(Math.hypot(p.x-e.x, p.y-e.y) < e.r) {
                            e.hp--; projectiles.splice(pi, 1);
                            if(e.hp <= 0) {
                                score += 200; gems += 5; shieldCharge = Math.min(100, shieldCharge + 2);
                                updateUI(); enemies.splice(i, 1);
                                if(score > level * 8000 && !boss) spawnBoss();
                            }
                        }
                    });
                    if(e.y > canvas.height+50) enemies.splice(i, 1);
                });

                // Boss
                if(boss) {
                    boss.y < boss.ty ? boss.y += 2 : (boss.x += boss.dir * boss.v);
                    if(boss.x > canvas.width-100 || boss.x < 100) boss.dir *= -1;
                    
                    ctx.fillStyle = '#f00'; ctx.beginPath();
                    ctx.moveTo(boss.x, boss.y-60); ctx.lineTo(boss.x-110, boss.y+40); ctx.lineTo(boss.x+110, boss.y+40); ctx.fill();

                    if(frame % 30 === 0) {
                        for(let a=-2; a<=2; a++) enemyProjectiles.push({ x: boss.x+a*30, y: boss.y+40, vy: 7+level });
                    }

                    projectiles.forEach((p, pi) => {
                        if(Math.hypot(p.x-boss.x, p.y-boss.y) < 100) {
                            boss.hp--; projectiles.splice(pi, 1);
                            document.getElementById('boss-hp-fill').style.width = (boss.hp/boss.maxHp*100) + '%';
                            if(boss.hp <= 0) {
                                score += 10000; level++; boss = null;
                                document.getElementById('boss-ui').style.display = 'none';
                                updateUI(); spawnEnemy();
                            }
                        }
                    });
                }
            }

            frame++; requestAnimationFrame(update);
        }

        function endGame() {
            gameState = 'OVER';
            if(score > bestScore) {
                bestScore = score;
                localStorage.setItem('starfighter_best', score);
            }
            document.getElementById('game-ui').style.display = 'none';
            document.getElementById('game-over').classList.remove('hidden');
            document.getElementById('final-score').innerText = score;
            document.getElementById('final-best').innerText = bestScore;
        }

        update();
        window.addEventListener('resize', () => { canvas.width = window.innerWidth; canvas.height = window.innerHeight; });

    </script>
</body>
</html>

