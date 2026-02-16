# dots-war

#war dots 1.5v

<!DOCTYPE html>
<html lang="ja">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>War of Dots: Strategic Conquest Edition</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body { margin: 0; overflow: hidden; background: #030305; font-family: 'Inter', sans-serif; color: white; user-select: none; }
        canvas { display: block; touch-action: none; position: absolute; top: 0; left: 0; z-index: 1; }
        
        .ui-layer { position: absolute; inset: 0; pointer-events: none; z-index: 50; }
        .pointer-auto { pointer-events: auto; }

        .top-bar {
            display: flex; justify-content: space-between; align-items: flex-start; padding: 10px 20px;
            background: linear-gradient(to bottom, rgba(0,0,0,0.9), transparent);
        }

        .stat-box { display: flex; flex-direction: column; }
        .cap-info { font-size: 10px; opacity: 0.5; margin-top: -2px; }

        .pause-btn {
            pointer-events: auto; background: rgba(255,255,255,0.1); border: 1px solid rgba(255,255,255,0.2);
            padding: 4px 12px; border-radius: 4px; font-size: 10px; font-weight: 900; letter-spacing: 0.1em;
            cursor: pointer; transition: all 0.2s; color: rgba(255,255,255,0.6);
        }
        .pause-btn:hover { background: rgba(255,255,255,0.2); color: white; }

        #city-inspector {
            position: absolute; background: rgba(0,0,0,0.95); backdrop-filter: blur(12px);
            padding: 10px; border-radius: 8px; border: 1px solid rgba(255, 255, 255, 0.2);
            pointer-events: none; display: none; transform: translate(-50%, -130%);
            z-index: 100; min-width: 120px; box-shadow: 0 10px 25px rgba(0,0,0,0.5);
        }

        .legion-container {
            position: absolute; bottom: 15px; left: 50%; transform: translateX(-50%);
            width: 90vw; max-width: 600px;
            display: flex; gap: 8px; padding: 6px;
            background: rgba(10, 10, 15, 0.7); backdrop-filter: blur(10px);
            border-radius: 12px; border: 1px solid rgba(255,255,255,0.1);
            pointer-events: auto;
        }

        .scroll-area {
            display: flex; gap: 6px; overflow-x: auto; flex-grow: 1;
            scrollbar-width: none;
            -ms-overflow-style: none;
        }
        .scroll-area::-webkit-scrollbar { display: none; }

        .legion-card {
            min-width: 50px; height: 50px;
            background: rgba(255,255,255,0.03); border: 2px solid rgba(255,255,255,0.15);
            border-radius: 8px; display: flex; flex-direction: column;
            align-items: center; justify-content: center;
            transition: transform 0.1s ease; cursor: pointer; position: relative;
            flex-shrink: 0;
        }
        .legion-card .count { font-size: 14px; font-weight: 900; }
        .legion-card .label { font-size: 6px; opacity: 0.8; font-weight: bold; }
        
        .dissolve-btn {
            position: absolute; top: -4px; right: -4px;
            width: 16px; height: 16px; background: #111;
            border-radius: 50%; display: flex; align-items: center; justify-content: center;
            font-size: 10px; border: 1px solid rgba(255,255,255,0.3); z-index: 10;
        }

        .new-legion-btn {
            background: #fff; color: #000; padding: 0 12px; height: 50px;
            border-radius: 8px; font-size: 11px; font-weight: 900; cursor: pointer;
            display: flex; align-items: center; justify-content: center;
            pointer-events: auto; flex-shrink: 0;
        }

        #selection-rect {
            position: absolute; border: 1.5px solid rgba(255,255,255,0.8);
            background: rgba(255,255,255,0.08); pointer-events: none; display: none; z-index: 60;
        }

        .menu-btn {
            padding: 12px 32px; border: 2px solid white; font-weight: 900;
            transition: all 0.2s; cursor: pointer; pointer-events: auto; width: 200px; text-align: center;
        }
        .menu-btn:hover { background: white; color: black; }

        .slider-container { width: 240px; margin: 20px 0; pointer-events: auto; }
        input[type=range] { width: 100%; cursor: pointer; accent-color: white; }
    </style>
</head>
<body>

<div class="ui-layer">
    <div class="top-bar">
        <div class="stat-box">
            <span class="text-[8px] opacity-40 uppercase tracking-widest text-red-500 font-bold">Commander</span>
            <span id="p-count" class="text-xl font-black text-red-500">0</span>
            <span id="p-cap" class="cap-info">Limit: 0</span>
        </div>
        
        <button id="mid-game-menu" class="pause-btn hidden" onclick="showMenu()">MENU</button>

        <div class="stat-box items-end">
            <span class="text-[8px] opacity-40 uppercase tracking-widest text-blue-500 font-bold">Enemy</span>
            <span id="e-count" class="text-xl font-black text-blue-500">0</span>
            <span id="e-cap" class="cap-info">Limit: 0</span>
        </div>
    </div>

    <div id="city-inspector">
        <div id="insp-title" class="text-[8px] uppercase font-black mb-1">COMMAND POST</div>
        <div class="w-full h-1 bg-white/10 rounded-full overflow-hidden mb-1">
            <div id="insp-hp-bar" class="h-full bg-red-500"></div>
        </div>
        <div class="flex justify-between items-center text-[7px]">
            <span id="insp-hp">0/300</span>
            <span id="insp-timer" class="text-yellow-400">0.0s</span>
        </div>
    </div>

    <div id="selection-rect"></div>

    <div class="legion-container" id="bottom-ui">
        <div id="new-legion-area" class="hidden flex mr-1">
            <div id="form-btn" class="new-legion-btn italic">FORM</div>
        </div>
        <div id="legion-scroll" class="scroll-area">
            <div id="legion-list" class="flex gap-1.5"></div>
        </div>
    </div>
</div>

<div id="overlay" class="fixed inset-0 bg-black/95 z-[100] flex flex-col items-center justify-center pointer-auto">
    <h1 id="result-text" class="text-5xl font-black italic mb-2 tracking-tighter uppercase">War of Dots</h1>
    <p id="sub-text" class="text-[10px] opacity-50 mb-4 tracking-[0.2em] uppercase text-center">Final Conquest Engine</p>
    
    <div id="menu-setup" class="flex flex-col items-center mb-8">
        <div class="slider-container">
            <div class="flex justify-between text-[10px] font-bold mb-1">
                <span>TOTAL CITIES (10-50)</span>
                <span id="city-count-val" class="text-yellow-400">20</span>
            </div>
            <input type="range" id="city-slider" min="10" max="50" value="20" oninput="document.getElementById('city-count-val').innerText = this.value">
        </div>
    </div>

    <div id="menu-options" class="flex flex-col gap-4">
        <button onclick="startGame('EASY')" class="menu-btn border-green-500 text-green-500 hover:bg-green-500">EASY</button>
        <button onclick="startGame('NORMAL')" class="menu-btn border-white text-white hover:bg-white hover:text-black">NORMAL</button>
        <button onclick="startGame('HARD')" class="menu-btn border-red-500 text-red-500 hover:bg-red-500">HARD</button>
    </div>
    
    <button id="restart-btn" onclick="showMenu()" class="hidden px-16 py-5 bg-white text-black font-black text-xl tracking-widest hover:bg-red-500 transition-all mt-8 uppercase">Back to Menu</button>
</div>

<canvas id="gameCanvas"></canvas>

<script>
const canvas = document.getElementById('gameCanvas');
const ctx = canvas.getContext('2d');

const TEAM = { NEUTRAL: 0, PLAYER: 1, ENEMY: 2 };
const COLORS = { [TEAM.NEUTRAL]: '#1e293b', [TEAM.PLAYER]: '#ef4444', [TEAM.ENEMY]: '#3b82f6', BG: '#030305' };
const LEGION_PALETTE = ['#facc15', '#a855f7', '#22c55e', '#06b6d4', '#f97316', '#ec4899', '#ffffff', '#84cc16', '#6366f1'];

let cities = [];
let units = [];
let legions = [];
let selectedUnitIds = new Set();
let activeLegionId = null;
let dragStart = null;
let lastTime = performance.now();
let gameState = 'menu';
let inspectedCity = null;
let sparks = [];

let mountains = [];
let rivers = [];

let difficulty = 'NORMAL';
let settings = { enemyCapMult: 1.0, enemySpawnRate: 1.0, enemyHpMult: 1.0, enemyAtkMult: 1.0 };
let customMaxCities = 20;
let dynamicCityRadius = 8;
let dynamicEngageDist = 45; 
let dynamicCircleRadius = 28; 

const UNIT_SPEED = 0.17; 
const CITY_SPAWN_INTERVAL = 18000; 
const SPAWN_COUNT = 6;
const BASE_CAP = 60;
const CAP_PER_CITY = 12;
const RALLY_RANGE = 70; 
const UNIT_ENGAGE_DIST = 28;

function resize() {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
}
window.addEventListener('resize', resize);
resize();

function distToSegment(px, py, x1, y1, x2, y2) {
    let l2 = (x2 - x1)**2 + (y2 - y1)**2;
    if (l2 === 0) return Math.hypot(px - x1, py - y1);
    let t = ((px - x1)*(x2 - x1) + (py - y1)*(y2 - y1)) / l2;
    t = Math.max(0, Math.min(1, t));
    return Math.hypot(px - (x1 + t*(x2 - x1)), py - (y1 + t*(y2 - y1)));
}

function drawMountain(m) {
    ctx.beginPath();
    ctx.moveTo(m.points[0].x, m.points[0].y);
    for (let i = 1; i < m.points.length; i++) ctx.lineTo(m.points[i].x, m.points[i].y);
    ctx.closePath();
    ctx.fillStyle = '#1c1f26';
    ctx.fill();
    ctx.strokeStyle = '#2d333e';
    ctx.lineWidth = 2;
    ctx.stroke();
}

// 街と地形の衝突判定（ピクセル単位の余裕を持たせる）
function isLocationBlocked(x, y, radius) {
    // 画面端の制限
    if (x < 50 || x > canvas.width - 50 || y < 100 || y > canvas.height - 100) return true;
    
    // 山との衝突判定
    for (let m of mountains) {
        if (Math.hypot(m.x - x, m.y - y) < m.radius + radius + 15) return true;
    }
    
    // 川との衝突判定
    for (let r of rivers) {
        for (let seg of r) {
            if (distToSegment(x, y, seg.x1, seg.y1, seg.x2, seg.y2) < (seg.width/2 + radius + 15)) return true;
        }
    }
    return false;
}

function generateTerrain(width, height) {
    mountains = []; rivers = [];
    const isVerticalRiver = Math.random() < 0.5;
    let river = [];
    
    // 川の生成
    let startX = isVerticalRiver ? (width * 0.35 + Math.random() * width * 0.3) : -50;
    let startY = isVerticalRiver ? -50 : (height * 0.35 + Math.random() * height * 0.3);
    let cx = startX, cy = startY;
    let attempts = 0;
    
    while((isVerticalRiver ? cy < height + 100 : cx < width + 100) && attempts < 25) {
        attempts++;
        let nx = cx + (isVerticalRiver ? (Math.random() * 80 - 40) : (100 + Math.random() * 100));
        let ny = cy + (isVerticalRiver ? (100 + Math.random() * 100) : (Math.random() * 80 - 40));
        river.push({ x1: cx, y1: cy, x2: nx, y2: ny, width: 35 + Math.random() * 15 });
        cx = nx; cy = ny;
    }
    rivers.push(river);

    // 山の生成
    const numMountains = 3 + Math.floor(Math.random() * 2);
    for (let i = 0; i < numMountains; i++) {
        let mx = width * 0.2 + Math.random() * width * 0.6;
        let my = height * 0.2 + Math.random() * height * 0.6;
        let rad = 40 + Math.random() * 35;
        let points = [];
        let numPoints = 8;
        for (let p = 0; p < numPoints; p++) {
            let angle = (p / numPoints) * Math.PI * 2;
            let pr = rad * (0.8 + Math.random() * 0.4);
            points.push({ x: mx + Math.cos(angle) * pr, y: my + Math.sin(angle) * pr });
        }
        mountains.push({ x: mx, y: my, radius: rad, points: points });
    }
}

class City {
    constructor(x, y, team = TEAM.NEUTRAL, radius = 8) {
        this.x = x; this.y = y; this.team = team;
        this.radius = radius;
        this.hp = team === TEAM.NEUTRAL ? 80 : 300;
        this.maxHp = 300;
        this.spawnTimer = CITY_SPAWN_INTERVAL; 
        this.underAttack = false;
        this.attackerCount = 0;
    }

    spawn(currentCount, maxCap) {
        if (currentCount >= maxCap) return;
        let countToSpawn = (this.team === TEAM.ENEMY && difficulty === 'HARD') ? 8 : SPAWN_COUNT;
        let actualCount = Math.min(countToSpawn, maxCap - currentCount);
        for(let i=0; i<actualCount; i++) {
            const angle = Math.random() * Math.PI * 2;
            const dist = this.radius + 6 + Math.random() * 10;
            const u = new Unit(this.x + Math.cos(angle)*dist, this.y + Math.sin(angle)*dist, this.team);
            if (this.team === TEAM.PLAYER) {
                let bestL = null; let minDist = RALLY_RANGE;
                legions.forEach(l => {
                    if (l.centroid) {
                        const d = Math.hypot(this.x - l.centroid.x, this.y - l.centroid.y);
                        if (d < minDist) { minDist = d; bestL = l; }
                    }
                });
                if (bestL) {
                    u.legionId = bestL.id;
                    u.tx = bestL.targetPos ? (bestL.targetPos.x + (Math.random()-0.5)*30) : (bestL.centroid.x + (Math.random()-0.5)*30);
                    u.ty = bestL.targetPos ? (bestL.targetPos.y + (Math.random()-0.5)*30) : (bestL.centroid.y + (Math.random()-0.5)*30);
                }
            }
            units.push(u);
        }
    }

    update(dt, currentCount, maxCap) {
        if (this.hp < this.maxHp) this.hp += 0.15;
        let isTakingDamage = false;
        this.attackerCount = 0;

        legions.forEach(l => {
            if (!l.centroid) return;
            const lu = units.filter(u => u.legionId === l.id && !u.dead);
            if (lu.length === 0 || lu[0].team === this.team) return;
            if (Math.hypot(l.centroid.x - this.x, l.centroid.y - this.y) < dynamicEngageDist) {
                this.hp -= lu.length * 0.08;
                isTakingDamage = true;
                this.attackerCount += lu.length;
                if (Math.random() < 0.2) createSpark(this.x + (Math.random()-0.5)*12, this.y + (Math.random()-0.5)*12);
            }
        });

        units.forEach(u => {
            if (u.team !== this.team && u.team !== TEAM.NEUTRAL && !u.dead) {
                const d = Math.hypot(u.x - this.x, u.y - this.y);
                if (d < (this.radius + 12)) {
                    this.attackerCount++;
                    isTakingDamage = true;
                    let damage = (u.team === TEAM.ENEMY) ? 0.08 * settings.enemyAtkMult : 0.08;
                    this.hp -= damage;
                }
            }
        });

        this.underAttack = isTakingDamage;

        if (this.hp <= 0) {
            const nearbyUnits = units.filter(u => Math.hypot(u.x - this.x, u.y - this.y) < 70);
            const pCount = nearbyUnits.filter(u => u.team === TEAM.PLAYER).length;
            const eCount = nearbyUnits.filter(u => u.team === TEAM.ENEMY).length;
            if (pCount > 0 || eCount > 0) {
                this.team = pCount > eCount ? TEAM.PLAYER : TEAM.ENEMY;
                this.hp = 120; this.spawnTimer = CITY_SPAWN_INTERVAL;
            }
        }

        if (this.team !== TEAM.NEUTRAL) {
            const ratio = Math.max(0.1, currentCount / maxCap);
            const growthPenalty = Math.pow(1 - ratio, 1.2); 
            const rate = (this.team === TEAM.ENEMY) ? dt * settings.enemySpawnRate * growthPenalty : dt * growthPenalty;
            this.spawnTimer -= rate;
            if (this.spawnTimer <= 0) {
                this.spawn(currentCount, maxCap);
                this.spawnTimer = CITY_SPAWN_INTERVAL;
            }
        }
    }

    draw() {
        ctx.beginPath(); ctx.arc(this.x, this.y, this.radius, 0, Math.PI*2);
        ctx.fillStyle = COLORS[this.team]; ctx.fill();
        ctx.beginPath();
        ctx.arc(this.x, this.y, this.radius + 4, -Math.PI/2, -Math.PI/2 + (Math.PI*2 * (this.hp/this.maxHp)));
        ctx.strokeStyle = (this.underAttack && Date.now() % 400 < 200) ? '#fff' : COLORS[this.team]; 
        ctx.lineWidth = 2; ctx.stroke();
    }
}

class Unit {
    constructor(x, y, team) {
        this.x = x; this.y = y; this.team = team;
        this.id = Math.random().toString(36).substr(2, 9);
        this.tx = x; this.ty = y;
        this.speed = UNIT_SPEED * (this.team === TEAM.ENEMY ? 1.2 : 0.95 + Math.random() * 0.15); 
        this.hp = (this.team === TEAM.ENEMY) ? 100 * settings.enemyHpMult : 100;
        this.dead = false; this.legionId = null;
        this.aiTimer = Math.random() * 800;
        this.inDefenseRange = false;
    }

    update(dt, totalUnits) {
        let moveX = 0, moveY = 0;
        let isFighting = false;
        let isMovingToTarget = false;

        const legion = this.team === TEAM.PLAYER ? legions.find(lg => lg.id === this.legionId) : null;
        if (legion && legion.targetPos && Math.hypot(legion.targetPos.x - this.x, legion.targetPos.y - this.y) > 30) isMovingToTarget = true;

        this.inDefenseRange = cities.some(c => c.team === this.team && Math.hypot(c.x-this.x, c.y-this.y) < (c.radius + 35));

        const targetTeam = (this.team === TEAM.PLAYER) ? TEAM.ENEMY : TEAM.PLAYER;
        let nearestEnemy = null;
        let minDist = UNIT_ENGAGE_DIST; 
        for(let i=0; i<8; i++) {
            const p = units[Math.floor(Math.random()*units.length)];
            if(p && p.team === targetTeam && !p.dead) {
                const d = Math.hypot(p.x - this.x, p.y - this.y);
                if(d < minDist) { minDist = d; nearestEnemy = p; }
            }
        }

        if (nearestEnemy) {
            isFighting = true;
            const edx = nearestEnemy.x - this.x, edy = nearestEnemy.y - this.y;
            const edist = Math.sqrt(edx*edx + edy*edy);
            moveX = (edx/edist) * this.speed * 1.6; moveY = (edy/edist) * this.speed * 1.6;
            if (edist < 12) {
                const atkMult = this.inDefenseRange ? 1.6 : 1.0;
                let damageDealt = 2.1 * atkMult * (nearestEnemy.inDefenseRange ? 0.5 : 1.0);
                if (this.team === TEAM.ENEMY) damageDealt *= settings.enemyAtkMult;
                nearestEnemy.hp -= damageDealt;
                this.hp -= 0.45 * (this.inDefenseRange ? 0.4 : 1.0);
                if (Math.random() < 0.1) createSpark(this.x, this.y);
            }
        } else {
            let dx = this.tx - this.x, dy = this.ty - this.y;
            let dist = Math.sqrt(dx*dx + dy*dy);
            if (dist > 4) { moveX = (dx/dist)*this.speed; moveY = (dy/dist)*this.speed; }
        }

        if (this.team === TEAM.PLAYER && legion && legion.centroid) {
            const cdx = legion.centroid.x - this.x, cdy = legion.centroid.y - this.y;
            if (Math.hypot(cdx, cdy) > 20) {
                const strength = isFighting ? 0.01 : (isMovingToTarget ? 0.02 : 0.06);
                moveX += cdx * strength; moveY += cdy * strength;
            }
        }

        if (this.team === TEAM.ENEMY && !isFighting) {
            this.aiTimer -= dt;
            if (this.aiTimer < 0) {
                this.aiTimer = 1000 + Math.random() * 1000;
                let bestScore = -Infinity, bestTarget = null;
                cities.forEach(city => {
                    const dist = Math.hypot(this.x - city.x, this.y - city.y);
                    let score = 0;
                    if (city.team === TEAM.ENEMY) {
                        if (city.underAttack) score = 2000 / (dist + 50);
                        else score = 50 / (dist + 1);
                    } else if (city.team === TEAM.NEUTRAL) score = 800 / (dist + 50);
                    else score = (1000 - city.hp * 2) / (dist * 0.5 + 50);
                    if (score > bestScore) { bestScore = score; bestTarget = city; }
                });
                if (bestTarget) { this.tx = bestTarget.x + (Math.random()-0.5)*40; this.ty = bestTarget.y + (Math.random()-0.5)*40; }
            }
        }

        let sx = 0, sy = 0;
        for(let i=0; i<3; i++) {
            const o = units[Math.floor(Math.random()*units.length)];
            if (o && o !== this) {
                const d = Math.hypot(o.x-this.x, o.y-this.y);
                if (d < 8) { sx -= (o.x-this.x)*0.25; sy -= (o.y-this.y)*0.25; }
            }
        }

        let finalMoveX = moveX + sx;
        let finalMoveY = moveY + sy;
        
        for (let m of mountains) {
            const distToM = Math.hypot(m.x - this.x, m.y - this.y);
            if (distToM < m.radius + 40) {
                const dx = m.x - this.x;
                const dy = m.y - this.y;
                const dot = (finalMoveX * dx + finalMoveY * dy) / (distToM || 1);
                if (dot > 0) {
                    const px = -dy / distToM;
                    const py = dx / distToM;
                    const side = (finalMoveX * px + finalMoveY * py) > 0 ? 1 : -1;
                    finalMoveX += px * side * 0.15;
                    finalMoveY += py * side * 0.15;
                }
            }
        }

        let speedMult = 1.0;
        for (let r of rivers) {
            for (let seg of r) {
                if (distToSegment(this.x, this.y, seg.x1, seg.y1, seg.x2, seg.y2) < seg.width/2) {
                    speedMult = 0.5; break;
                }
            }
        }

        let nextX = this.x + finalMoveX * speedMult;
        let nextY = this.y + finalMoveY * speedMult;

        for (let m of mountains) {
            let dx = nextX - m.x, dy = nextY - m.y;
            let dist = Math.hypot(dx, dy);
            if (dist < m.radius + 2) {
                let push = (m.radius + 2) - dist;
                nextX += (dx/dist) * push; nextY += (dy/dist) * push;
            }
        }

        this.x = nextX; this.y = nextY;
        this.hp -= 0.008 * Math.min(2.0, totalUnits / 120);
        if (this.hp <= 0) this.dead = true;
    }

    draw(pulse) {
        const isSelected = selectedUnitIds.has(this.id);
        const isFree = this.team === TEAM.PLAYER && !this.legionId;
        if (isSelected || isFree) {
            ctx.beginPath(); ctx.arc(this.x, this.y, isSelected ? 6.5 : 5, 0, Math.PI*2);
            ctx.fillStyle = isSelected ? 'rgba(255,255,255,0.45)' : `rgba(255,255,255,${0.1 + pulse * 0.3})`;
            ctx.fill();
        }
        if (this.team === TEAM.PLAYER) {
            const l = legions.find(lg => lg.id === this.legionId);
            if (l) {
                ctx.beginPath(); ctx.arc(this.x, this.y, 4.2, 0, Math.PI*2);
                ctx.strokeStyle = l.color; ctx.globalAlpha = (activeLegionId === this.legionId) ? 1.0 : 0.35;
                ctx.lineWidth = 1.3; ctx.stroke(); ctx.globalAlpha = 1;
            }
        }
        ctx.beginPath(); ctx.arc(this.x, this.y, 2.6, 0, Math.PI*2);
        ctx.fillStyle = isSelected ? '#fff' : COLORS[this.team]; ctx.fill();
    }
}

function createSpark(x, y) {
    for(let i=0; i<2; i++) sparks.push({ x, y, vx: (Math.random()-0.5)*6, vy: (Math.random()-0.5)*6, life: 1.0, color: '#facc15' });
}

function showMenu() {
    gameState = 'menu';
    document.getElementById('overlay').style.display = 'flex';
    document.getElementById('menu-options').style.display = 'flex';
    document.getElementById('menu-setup').style.display = 'flex';
    document.getElementById('restart-btn').style.display = 'none';
    document.getElementById('mid-game-menu').classList.add('hidden');
    document.getElementById('bottom-ui').classList.add('hidden');
    document.getElementById('result-text').innerText = 'War of Dots';
    document.getElementById('result-text').className = 'text-5xl font-black italic mb-2 tracking-tighter uppercase';
}

function startGame(mode) {
    difficulty = mode; 
    customMaxCities = parseInt(document.getElementById('city-slider').value);
    gameState = 'playing';
    document.getElementById('overlay').style.display = 'none';
    document.getElementById('mid-game-menu').classList.remove('hidden');
    document.getElementById('bottom-ui').classList.remove('hidden');
    switch(mode) {
        case 'EASY': settings = { enemyCapMult: 0.7, enemySpawnRate: 0.8, enemyHpMult: 0.8, enemyAtkMult: 0.8 }; break;
        case 'NORMAL': settings = { enemyCapMult: 1.0, enemySpawnRate: 1.0, enemyHpMult: 1.0, enemyAtkMult: 1.0 }; break;
        case 'HARD': settings = { enemyCapMult: 1.3, enemySpawnRate: 1.3, enemyHpMult: 1.1, enemyAtkMult: 1.2 }; break;
    }
    init();
}

function init() {
    cities = []; units = []; legions = []; selectedUnitIds.clear();
    activeLegionId = null; inspectedCity = null; sparks = [];
    
    // 1. 地形の生成を最優先で行う
    generateTerrain(canvas.width, canvas.height);
    
    dynamicCityRadius = Math.max(5, 8 - (customMaxCities - 10) * 0.1);
    dynamicEngageDist = Math.max(25, 45 - (customMaxCities - 10) * 0.6); 
    dynamicCircleRadius = Math.max(16, 28 - (customMaxCities - 10) * 0.3); 

    let minDistance = Math.max(40, 85 - (customMaxCities - 10) * 1.2);
    const armyXOffset = 60;

    // 2. 初期拠点の配置（地形を回避しながら）
    const sides = [
        { team: TEAM.PLAYER, xRange: [ armyXOffset, armyXOffset + 80 ], yRange: [ canvas.height*0.3, canvas.height*0.7 ] },
        { team: TEAM.ENEMY, xRange: [ canvas.width - armyXOffset - 80, canvas.width - armyXOffset ], yRange: [ canvas.height*0.3, canvas.height*0.7 ] }
    ];

    sides.forEach(side => {
        for(let i=0; i<2; i++) {
            let placed = false;
            let attempts = 0;
            while(!placed && attempts < 100) {
                attempts++;
                let rx = side.xRange[0] + Math.random() * (side.xRange[1] - side.xRange[0]);
                let ry = side.yRange[0] + Math.random() * (side.yRange[1] - side.yRange[0]);
                
                if (!isLocationBlocked(rx, ry, dynamicCityRadius)) {
                    cities.push(new City(rx, ry, side.team, dynamicCityRadius));
                    placed = true;
                }
            }
        }
    });

    // 3. 中立都市の配置（地形と既存の街を回避）
    let failSafe = 0;
    while(cities.length < customMaxCities && failSafe < 3000) {
        failSafe++;
        let rx = 50 + Math.random()*(canvas.width - 100);
        let ry = 100 + Math.random()*(canvas.height - 200); 
        
        let overlap = false;
        // 地形チェック
        if (isLocationBlocked(rx, ry, dynamicCityRadius)) overlap = true;
        // 既存の街との距離チェック
        if (!overlap) {
            for (let c of cities) {
                if (Math.hypot(c.x-rx, c.y-ry) < minDistance) { overlap = true; break; }
            }
        }
        
        if (!overlap) cities.push(new City(rx, ry, TEAM.NEUTRAL, dynamicCityRadius));
        if (failSafe % 300 === 0) minDistance = Math.max(dynamicCityRadius * 3.5, minDistance - 5);
    }

    // 各陣営の初期ユニット生成
    cities.forEach(c => {
        if(c.team !== TEAM.NEUTRAL) c.spawn(0, 999);
    });

    updateLegionUI();
}

function update(time) {
    const dt = Math.min(time - lastTime, 100); lastTime = time;
    const pulse = (Math.sin(time / 200) + 1) / 2;
    ctx.fillStyle = COLORS.BG; ctx.fillRect(0,0,canvas.width,canvas.height);

    ctx.lineCap = 'round'; ctx.lineJoin = 'round';
    for (let r of rivers) {
        ctx.beginPath(); ctx.moveTo(r[0].x1, r[0].y1);
        for (let seg of r) ctx.lineTo(seg.x2, seg.y2);
        ctx.strokeStyle = 'rgba(14, 165, 233, 0.15)'; ctx.lineWidth = 38; ctx.stroke();
        ctx.strokeStyle = 'rgba(14, 165, 233, 0.1)'; ctx.lineWidth = 18; ctx.stroke();
    }

    mountains.forEach(drawMountain);
    
    if (gameState === 'playing') {
        const pUnits = units.filter(u => u.team === TEAM.PLAYER);
        const eUnits = units.filter(u => u.team === TEAM.ENEMY);
        const pCities = cities.filter(c => c.team === TEAM.PLAYER);
        const eCities = cities.filter(c => c.team === TEAM.ENEMY);
        const pCap = BASE_CAP + pCities.length * CAP_PER_CITY;
        const eCap = Math.floor((BASE_CAP + eCities.length * CAP_PER_CITY) * settings.enemyCapMult);
        
        document.getElementById('p-count').innerText = pUnits.length;
        document.getElementById('e-count').innerText = eUnits.length;
        document.getElementById('p-cap').innerText = `Limit: ${pCap}`;
        document.getElementById('e-cap').innerText = `Limit: ${eCap}`;
        
        cities.forEach(c => c.update(dt, c.team === TEAM.PLAYER ? pUnits.length : eUnits.length, c.team === TEAM.PLAYER ? pCap : eCap));
        units = units.filter(u => !u.dead);
        units.forEach(u => u.update(dt, u.team === TEAM.PLAYER ? pUnits.length : eUnits.length));
        
        legions.forEach(l => {
            const lu = units.filter(u => u.legionId === l.id && !u.dead);
            if (lu.length > 0) {
                const nx = lu.reduce((a,b)=>a+b.x,0)/lu.length, ny = lu.reduce((a,b)=>a+b.y,0)/lu.length;
                if (!l.centroid) l.centroid = { x: nx, y: ny };
                else { l.centroid.x += (nx - l.centroid.x) * 0.2; l.centroid.y += (ny - l.centroid.y) * 0.2; }
            } else l.centroid = null;
        });

        if (inspectedCity && inspectedCity.team === TEAM.PLAYER) {
            const el = document.getElementById('city-inspector');
            el.style.display = 'block'; el.style.left = inspectedCity.x + 'px'; el.style.top = inspectedCity.y + 'px';
            document.getElementById('insp-hp').innerText = `${Math.floor(inspectedCity.hp)}/300`;
            document.getElementById('insp-hp-bar').style.width = (inspectedCity.hp/300*100) + '%';
            document.getElementById('insp-timer').innerText = (inspectedCity.spawnTimer/1000).toFixed(1) + 's';
        } else document.getElementById('city-inspector').style.display = 'none';

        if (pCities.length === 0) endGame('DEFEAT');
        else if (eCities.length === 0) endGame('VICTORY');
        
        if (Math.random() < 0.05) updateLegionUI();
    }

    sparks = sparks.filter(s => s.life > 0);
    sparks.forEach(s => { s.x += s.vx; s.y += s.vy; s.life -= 0.05; ctx.fillStyle = s.color; ctx.globalAlpha = s.life; ctx.fillRect(s.x, s.y, 1.5, 1.5); });
    ctx.globalAlpha = 1.0;

    legions.forEach(l => {
        if (!l.centroid) return;
        const isAct = activeLegionId === l.id;
        const lu = units.filter(u => u.legionId === l.id && !u.dead);
        const dist = l.targetPos ? Math.hypot(l.centroid.x - l.targetPos.x, l.centroid.y - l.targetPos.y) : Infinity;
        let status = "IDLE"; 
        const nearC = cities.find(c => Math.hypot(c.x-l.centroid.x, c.y-l.centroid.y) < (c.radius + 15));
        if (dist < Infinity && dist > 30) status = "MARCH"; else if (nearC) status = nearC.team === TEAM.PLAYER ? "GUARD" : "ATK";

        if (l.targetPos) {
            ctx.beginPath(); ctx.arc(l.targetPos.x, l.targetPos.y, dynamicCircleRadius, 0, Math.PI * 2);
            ctx.strokeStyle = l.color; ctx.setLineDash([4, 4]); ctx.globalAlpha = isAct ? 0.6 : 0.2; ctx.stroke();
            ctx.beginPath(); ctx.moveTo(l.centroid.x, l.centroid.y); ctx.lineTo(l.targetPos.x, l.targetPos.y);
            ctx.setLineDash([isAct ? 8 : 2, isAct ? 6 : 8]); ctx.globalAlpha = isAct ? 0.5 : 0.1; ctx.stroke(); ctx.setLineDash([]);
        }
        ctx.fillStyle = l.color; ctx.font = `bold ${Math.max(8, 11 - (customMaxCities-10)*0.1)}px Inter`; ctx.textAlign = 'center'; ctx.globalAlpha = isAct ? 1.0 : 0.5;
        ctx.fillText(`${lu.length} [${status}]`, l.centroid.x, l.centroid.y - (dynamicCircleRadius + 6)); 
        ctx.beginPath(); ctx.arc(l.centroid.x, l.centroid.y, dynamicCircleRadius, 0, Math.PI*2);
        ctx.strokeStyle = l.color; ctx.lineWidth = isAct ? 2.2 : 1.3; if (!isAct) ctx.setLineDash([2, 3]);
        ctx.globalAlpha = isAct ? 1.0 : 0.4; ctx.stroke(); ctx.setLineDash([]); ctx.globalAlpha = 1.0;
    });

    cities.forEach(c => c.draw());
    units.forEach(u => u.draw(pulse));
    requestAnimationFrame(update);
}

function endGame(res) {
    gameState = 'ended'; document.getElementById('overlay').style.display = 'flex';
    document.getElementById('menu-options').style.display = 'none';
    document.getElementById('menu-setup').style.display = 'none';
    document.getElementById('restart-btn').style.display = 'block';
    document.getElementById('mid-game-menu').classList.add('hidden');
    document.getElementById('result-text').innerText = res;
    document.getElementById('result-text').className = `text-7xl font-black italic mb-4 ${res === 'VICTORY' ? 'text-green-500' : 'text-red-500'}`;
}

function createLegion() {
    if (selectedUnitIds.size === 0) return;
    const lid = 'L' + Math.floor(Math.random() * 9999);
    const used = new Set(legions.map(l => l.color));
    const color = LEGION_PALETTE.find(c => !used.has(c)) || LEGION_PALETTE[Math.floor(Math.random() * LEGION_PALETTE.length)];
    units.forEach(u => { if (selectedUnitIds.has(u.id)) u.legionId = lid; });
    legions.push({ id: lid, color: color, targetPos: null });
    selectedUnitIds.clear(); activeLegionId = lid; updateLegionUI();
}

function dissolveLegion(id, e) {
    if(e) e.stopPropagation();
    legions = legions.filter(l => l.id !== id);
    units.forEach(u => { if (u.legionId === id) u.legionId = null; });
    if (activeLegionId === id) activeLegionId = null;
    updateLegionUI();
}

function selectLegionDirectly(id) {
    activeLegionId = (activeLegionId === id) ? null : id;
    selectedUnitIds.clear(); inspectedCity = null; updateLegionUI();
}

function clearAllSelection() { activeLegionId = null; selectedUnitIds.clear(); inspectedCity = null; updateLegionUI(); }

function updateLegionUI() {
    const list = document.getElementById('legion-list');
    document.getElementById('new-legion-area').classList.toggle('hidden', selectedUnitIds.size === 0);
    list.innerHTML = '';
    legions.forEach((l, idx) => {
        const lu = units.filter(u => u.legionId === l.id && !u.dead);
        if (lu.length === 0) { dissolveLegion(l.id); return; }
        let status = "IDLE";
        if (l.centroid) {
            const dist = l.targetPos ? Math.hypot(l.centroid.x - l.targetPos.x, l.centroid.y - l.targetPos.y) : Infinity;
            const nearC = cities.find(c => Math.hypot(c.x-l.centroid.x, c.y-l.centroid.y) < (c.radius + 15));
            if (dist < Infinity && dist > 30) status = "MARCH"; else if (nearC) status = nearC.team === TEAM.PLAYER ? "GUARD" : "ATK";
        }
        const card = document.createElement('div');
        const isActive = activeLegionId === l.id;
        card.className = `legion-card`;
        card.style.borderColor = isActive ? l.color : 'rgba(255,255,255,0.15)';
        card.style.background = isActive ? `${l.color}22` : 'rgba(255,255,255,0.03)';
        card.style.color = isActive ? '#fff' : l.color;
        card.onclick = (e) => { e.stopPropagation(); selectLegionDirectly(l.id); };
        card.innerHTML = `<div class="dissolve-btn" onclick="dissolveLegion('${l.id}', event)">×</div><div class="count">${lu.length}</div><div class="label">LG ${idx+1} [${status}]</div>`;
        list.appendChild(card);
    });
}

document.getElementById('form-btn').onclick = (e) => { e.stopPropagation(); createLegion(); };

canvas.addEventListener('pointerdown', (e) => {
    if (gameState !== 'playing') return;
    const mx = e.clientX, my = e.clientY;
    const clickedUnit = units.find(u => u.team === TEAM.PLAYER && u.legionId && Math.hypot(u.x-mx, u.y-my) < 25);
    if (clickedUnit) { selectLegionDirectly(clickedUnit.legionId); dragStart = null; return; }
    const clickedCity = cities.find(c => Math.hypot(c.x-mx, c.y-my) < (c.radius * 2.5));
    if (clickedCity && clickedCity.team === TEAM.PLAYER && activeLegionId === null && selectedUnitIds.size === 0) { inspectedCity = clickedCity; dragStart = null; return; }
    dragStart = { x: mx, y: my, time: Date.now(), moved: false };
});

window.addEventListener('pointermove', (e) => {
    if (!dragStart) return;
    if (Math.hypot(dragStart.x - e.clientX, dragStart.y - e.clientY) < 10) return;
    dragStart.moved = true;
    const rect = document.getElementById('selection-rect');
    rect.style.display = 'block';
    const x = Math.min(dragStart.x, e.clientX), y = Math.min(dragStart.y, e.clientY), w = Math.abs(dragStart.x - e.clientX), h = Math.abs(dragStart.y - e.clientY);
    rect.style.left = x + 'px'; rect.style.top = y + 'px'; rect.style.width = w + 'px'; rect.style.height = h + 'px';
    selectedUnitIds.clear(); activeLegionId = null; 
    units.forEach(u => { if (u.team === TEAM.PLAYER && u.x > x && u.x < x+w && u.y > y && u.y < y+h) selectedUnitIds.add(u.id); });
    updateLegionUI();
});

window.addEventListener('pointerup', (e) => {
    if (!dragStart) return;
    document.getElementById('selection-rect').style.display = 'none';
    if (!dragStart.moved) {
        const mx = e.clientX, my = e.clientY;
        const hitAnything = units.some(u => u.team === TEAM.PLAYER && Math.hypot(u.x-mx, u.y-my) < 25) || cities.some(c => Math.hypot(c.x-mx, c.y-my) < (c.radius * 2.5));
        if (activeLegionId !== null || selectedUnitIds.size > 0) {
            const targets = activeLegionId ? units.filter(u => u.legionId === activeLegionId) : units.filter(u => selectedUnitIds.has(u.id));
            if (targets.length > 0) {
                let tx = mx, ty = my;
                const nearC = cities.find(c => Math.hypot(c.x - mx, c.y - my) < (c.radius * 3.5));
                if (nearC) { tx = nearC.x; ty = nearC.y; }
                if (activeLegionId) { const l = legions.find(lg => lg.id === activeLegionId); if (l) l.targetPos = { x: tx, y: ty }; }
                targets.forEach(u => { u.tx = tx + (Math.random()-0.5)*45; u.ty = ty + (Math.random()-0.5)*45; });
            }
        }
        if (!hitAnything) clearAllSelection();
    }
    dragStart = null;
});

requestAnimationFrame(update);
</script>
</body>
</html>

