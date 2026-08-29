<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1.0">
<title>💎 Girls Glam Club</title>

<style>
*{box-sizing:border-box}
body{
margin:0;
font-family:Arial,sans-serif;
color:#fff;
background:radial-gradient(circle at top,#792c70,#241020 45%,#070707);
min-height:100vh
}
.app{max-width:440px;margin:auto;padding:18px 14px 40px}
.logo{
text-align:center;font-size:29px;font-weight:900;color:#f7d978;
text-shadow:0 0 15px #ff63d2;margin-bottom:4px
}
.subtitle{text-align:center;color:#eec9e6;margin-bottom:16px}
.card{
background:rgba(255,255,255,.08);
border:1px solid rgba(247,217,120,.35);
border-radius:24px;padding:18px;margin-bottom:14px;
box-shadow:0 10px 35px rgba(0,0,0,.35)
}
.section{display:none}
.section.active{display:block}
button{
width:100%;border:0;border-radius:15px;padding:13px;
margin-top:9px;font-size:15px;font-weight:800;cursor:pointer
}
.gold{background:linear-gradient(90deg,#f7d978,#d996c5);color:#171017}
.dark{background:rgba(255,255,255,.1);color:white;border:1px solid #8c5b82}
.back{margin-bottom:8px}
.avatar{
width:100px;height:100px;margin:auto;border-radius:50%;
display:flex;align-items:center;justify-content:center;font-size:52px;
background:linear-gradient(135deg,#f7d978,#d88bbd);
border:4px solid #f7d978;box-shadow:0 0 25px #d45cb8
}
.name{text-align:center;font-size:25px;font-weight:bold;margin:10px}
.coins{text-align:center;color:#f7d978;font-size:22px}
h2{text-align:center;color:#f7d978}
.center{text-align:center}
.small{font-size:13px;color:#d9bfd5}

.player{
display:flex;align-items:center;gap:10px;
padding:11px;background:rgba(255,255,255,.06);
border-radius:16px;margin:8px 0
}
.pavatar{
width:50px;height:50px;border-radius:50%;
display:flex;align-items:center;justify-content:center;
font-size:27px;background:linear-gradient(135deg,#f7d978,#d88bbd)
}
.pinfo{flex:1}
.pname{font-weight:bold}
.pcoins{color:#f7d978;font-size:13px}
.player button{width:auto;margin:0;padding:8px 12px}

/* RUNNER */
canvas{
display:block;width:100%;height:auto;border-radius:20px;
background:#111;border:2px solid #f7d978
}
.gamehud{
display:flex;justify-content:space-between;
font-weight:bold;color:#f7d978;margin:8px 2px
}
.controls{
display:grid;grid-template-columns:repeat(3,1fr);gap:7px;margin-top:9px
}
.controls button{
height:54px;margin:0;font-size:23px;
background:rgba(255,255,255,.1);color:white;border:1px solid #ff72d7
}
.controls .empty{visibility:hidden}

/* QUIZ */
.answers{
display:grid;grid-template-columns:1fr 1fr;gap:9px
}
.answers button{margin:0;min-height:58px}
.question{
font-size:19px;text-align:center;
padding:15px;background:rgba(255,255,255,.06);
border-radius:17px;margin:12px 0
}
.timer{text-align:center;font-size:27px;color:#f7d978;font-weight:bold}
.result{text-align:center;color:#f7d978;font-weight:bold;min-height:25px}

/* SHOP */
.item{
display:flex;justify-content:space-between;align-items:center;
padding:12px;background:rgba(255,255,255,.06);
border-radius:14px;margin:7px 0
}
.item button{width:auto;margin:0;padding:8px 12px}
.badge{
display:inline-block;padding:7px 12px;border-radius:20px;
background:rgba(255,255,255,.08);margin:4px
}
</style>
</head>

<body>
<div class="app">

<div class="logo">💎 GIRLS GLAM CLUB</div>
<div class="subtitle">✨ Glam • Games • Girls ✨</div>

<!-- HOME -->
<div id="home" class="section active">
<div class="card">
<div class="avatar" id="avatar">👑</div>
<div class="name" id="playerName">Софа</div>
<div class="coins">💎 <span id="coins">0</span></div>

<button class="gold" onclick="startDance()">🪩 DANCE BATTLE</button>
<button class="gold" onclick="startRun()">🏃‍♀️ ДОБЕГИ ДО ПАРНЯ</button>
<button class="gold" onclick="openQuiz()">🎵 ОТГАДАЙ ПЕСНЮ</button>
<button class="gold" onclick="openChallenge()">💄 GLAM CHALLENGE</button>

<button class="dark" onclick="show('shop')">🛍️ GLAM SHOP</button>
<button class="dark" onclick="show('style')">👗 МОЙ ОБРАЗ</button>
<button class="dark" onclick="show('rating')">🏆 РЕЙТИНГ</button>
<button class="dark" onclick="show('players')">👭 СМЕНИТЬ ДЕВОЧКУ</button>
</div>
</div>

<!-- PLAYERS -->
<div id="players" class="section">
<div class="card">
<button class="dark back" onclick="show('home')">← Назад</button>
<h2>👭 ВЫБЕРИ ДЕВОЧКУ</h2>

<div class="player">
<div class="pavatar">👑</div><div class="pinfo">
<div class="pname">Софа</div><div class="pcoins" id="c0">💎 0</div>
</div><button class="gold" onclick="choose('sofa')">Играть</button>
</div>

<div class="player">
<div class="pavatar">🎀</div><div class="pinfo">
<div class="pname">Лика</div><div class="pcoins" id="c1">💎 0</div>
</div><button class="gold" onclick="choose('lika')">Играть</button>
</div>

<div class="player">
<div class="pavatar">🔥</div><div class="pinfo">
<div class="pname">Маико</div><div class="pcoins" id="c2">💎 0</div>
</div><button class="gold" onclick="choose('maiko')">Играть</button>
</div>

<div class="player">
<div class="pavatar">🦋</div><div class="pinfo">
<div class="pname">Ани</div><div class="pcoins" id="c3">💎 0</div>
</div><button class="gold" onclick="choose('ani')">Играть</button>
</div>
</div>
</div>

<!-- DANCE -->
<div id="dance" class="section">
<div class="card">
<button class="dark back" onclick="stopGame()">← Выйти</button>
<h2>🪩 DANCE BATTLE</h2>
<div class="gamehud">
<span>⏱️ <span id="danceTime">5</span></span>
<span>💎 <span id="danceCoins">0</span></span>
</div>
<canvas id="danceCanvas" width="800" height="430"></canvas>
<p class="center small">Собирай 💎 и избегай препятствий!</p>
<div class="controls">
<button class="empty"> </button>
<button onclick="movePlayer(0,-1)">⬆️</button>
<button class="empty"> </button>
<button onclick="movePlayer(-1,0)">⬅️</button>
<button onclick="movePlayer(0,1)">⬇️</button>
<button onclick="movePlayer(1,0)">➡️</button>
</div>
<div class="result" id="danceResult"></div>
</div>
</div>

<!-- RUNNER -->
<div id="run" class="section">
<div class="card">
<button class="dark back" onclick="stopGame()">← Выйти</button>
<h2>🏃‍♀️ ДОБЕГИ ДО ПАРНЯ</h2>
<p class="center" id="boyText">Софа → Лексо 💙</p>
<div class="gamehud">
<span>🏃 <span id="runDistance">0</span> м</span>
<span>💎 <span id="runCoins">0</span></span>
</div>
<canvas id="runCanvas" width="800" height="430"></canvas>
<div class="controls">
<button class="empty"> </button>
<button onclick="runJump()">⬆️</button>
<button class="empty"> </button>
<button onclick="runLeft()">⬅️</button>
<button onclick="runSlide()">⬇️</button>
<button onclick="runRight()">➡️</button>
</div>
<div class="result" id="runResult"></div>
</div>
</div>

<!-- QUIZ -->
<div id="quiz" class="section">
<div class="card">
<button class="dark back" onclick="show('home')">← Назад</button>
<h2>🎵 ОТГАДАЙ ПЕСНЮ</h2>

<div id="quizCategories">
<p class="center">Выбери категорию:</p>
<button class="gold" onclick="quizStart('ru')">🇷🇺 Русская музыка</button>
<button class="gold" onclick="quizStart('ge')">🇬🇪 Грузинские песни</button>
<button class="gold" onclick="quizStart('ost')">🎬 Саундтреки</button>
</div>

<div id="quizGame" style="display:none">
<div class="timer">⏱️ <span id="quizTime">10</span></div>
<div class="question" id="question"></div>
<div class="answers" id="answers"></div>
<div class="result" id="quizResult"></div>
</div>
</div>
</div>

<!-- CHALLENGE -->
<div id="challenge" class="section">
<div class="card">
<button class="dark back" onclick="show('home')">← Назад</button>
<h2>💄 GLAM CHALLENGE</h2>
<p class="center" id="challengeText"></p>
<div id="challengeOptions"></div>
<div class="result" id="challengeResult"></div>
</div>
</div>

<!-- SHOP -->
<div id="shop" class="section">
<div class="card">
<button class="dark back" onclick="show('home')">← Назад</button>
<h2>🛍️ GLAM SHOP</h2>
<div id="shopList"></div>
<div class="result" id="shopResult"></div>
</div>
</div>

<!-- STYLE -->
<div id="style" class="section">
<div class="card">
<button class="dark back" onclick="show('home')">← Назад</button>
<h2>👗 МОЙ ОБРАЗ</h2>
<p class="center" id="stylePlayer"></p>
<div id="inventory"></div>
</div>
</div>

<!-- RATING -->
<div id="rating" class="section">
<div class="card">
<button class="dark back" onclick="show('home')">← Назад</button>
<h2>🏆 РЕЙТИНГ</h2>
<div id="ratingList"></div>
</div>
</div>

</div>

<script>
const players={
sofa:{name:"Софа",avatar:"👑",boy:"Лексо",boyEmoji:"💙",coins:0,items:[]},
lika:{name:"Лика",avatar:"🎀",boy:"Самвел",boyEmoji:"🖤",coins:0,items:[]},
maiko:{name:"Маико",avatar:"🔥",boy:"Ника",boyEmoji:"💜",coins:0,items:[]},
ani:{name:"Ани",avatar:"🦋",boy:"Габи",boyEmoji:"💚",coins:0,items:[]}
};

let current="sofa";
let gameTimer=null;
let keys={};
let danceState=null;
let runState=null;
let quizState=null;

function load(){
try{
const s=localStorage.getItem("ggc");
if(s){
const d=JSON.parse(s);
Object.keys(players).forEach(k=>{
if(d[k]) players[k]=d[k];
});
}
}catch(e){}
}

function save(){
localStorage.setItem("ggc",JSON.stringify(players));
}

function choose(id){
current=id;
update();
show("home");
}

function update(){
const p=players[current];
document.getElementById("playerName").textContent=p.name;
document.getElementById("avatar").textContent=p.avatar;
document.getElementById("coins").textContent=p.coins;

document.getElementById("c0").textContent="💎 "+players.sofa.coins;
document.getElementById("c1").textContent="💎 "+players.lika.coins;
document.getElementById("c2").textContent="💎 "+players.maiko.coins;
document.getElementById("c3").textContent="💎 "+players.ani.coins;
}

function addCoins(n){
players[current].coins+=n;
save();
update();
}

function show(id){
clearInterval(gameTimer);
document.querySelectorAll(".section").forEach(x=>x.classList.remove("active"));
document.getElementById(id).classList.add("active");
if(id==="shop") renderShop();
if(id==="style") renderStyle();
if(id==="rating") renderRating();
}

function stopGame(){
clearInterval(gameTimer);
danceState=null;
runState=null;
show("home");
}

/* DANCE BATTLE — 5 SECONDS */
function startDance(){
show("dance");
const canvas=document.getElementById("danceCanvas");
const ctx=canvas.getContext("2d");

danceState={
x:400,y:215,
coins:0,
obstacles:[],
start:performance.now(),
duration:5000,
lastSpawn:0,
finished:false
};

document.getElementById("danceResult").textContent="";
requestAnimationFrame(danceLoop);
}

function movePlayer(dx,dy){
if(!danceState||danceState.finished)return;
danceState.x+=dx*45;
danceState.y+=dy*45;
danceState.x=Math.max(30,Math.min(770,danceState.x));
danceState.y=Math.max(35,Math.min(395,danceState.y));
}

function danceLoop(now){
if(!danceState)return;

const elapsed=now-danceState.start;
const left=Math.max(0,5000-elapsed);
document.getElementById("danceTime").textContent=(left/1000).toFixed(1);

if(elapsed>=5000){
finishDance();
return;
}

const canvas=document.getElementById("danceCanvas");
const ctx=canvas.getContext("2d");

ctx.fillStyle="#120b18";
ctx.fillRect(0,0,800,430);

ctx.fillStyle="#25142d";
ctx.fillRect(0,0,800,430);

ctx.strokeStyle="#71305f";
for(let x=0;x<800;x+=50){
ctx.beginPath();ctx.moveTo(x,0);ctx.lineTo(x,430);ctx.stroke();
}
for(let y=0;y<430;y+=50){
ctx.beginPath();ctx.moveTo(0,y);ctx.lineTo(800,y);ctx.stroke();
}

if(now-danceState.lastSpawn>450){
danceState.lastSpawn=now;
danceState.obstacles.push({
x:Math.random()*740+30,
y:Math.random()*370+30,
r:18
});
}

if(Math.random()<.025){
danceState.coinsList=danceState.coinsList||[];
danceState.coinsList.push({
x:Math.random()*740+30,
y:Math.random()*370+30
});
}

danceState.obstacles.forEach(o=>{
ctx.fillStyle="#ff4c5f";
ctx.beginPath();
ctx.arc(o.x,o.y,o.r,0,Math.PI*2);
ctx.fill();

if(Math.hypot(o.x-danceState.x,o.y-danceState.y)<30){
danceState.obstacles=[];
}
});

if(danceState.coinsList){
danceState.coinsList=danceState.coinsList.filter(c=>{
ctx.fillStyle="#f7d978";
ctx.beginPath();
ctx.arc(c.x,c.y,10,0,Math.PI*2);
ctx.fill();

if(Math.hypot(c.x-danceState.x,c.y-danceState.y)<25){
danceState.coins++;
return false;
}
return true;
});
}

ctx.font="38px Arial";
ctx.textAlign="center";
ctx.fillText(players[current].avatar,danceState.x,danceState.y+13);

document.getElementById("danceCoins").textContent=danceState.coins;

requestAnimationFrame(danceLoop);
}

function finishDance(){
if(!danceState||danceState.finished)return;
danceState.finished=true;

const reward=danceState.coins*10;

addCoins(reward);

document.getElementById("danceResult").textContent=
"🪩 Батл закончен! Собрано 💎 "+danceState.coins+
" → награда 💎 "+reward;
}

/* RUNNER */
function startRun(){
show("run");

const p=players[current];
document.getElementById("boyText").textContent=
p.name+" → "+p.boy+" "+p.boyEmoji;

runState={
x:150,y:340,
vy:0,
jump:false,
slide:false,
distance:0,
coins:0,
obstacles:[],
start:performance.now(),
last:performance.now(),
finished:false,
goal:900
};

document.getElementById("runResult").textContent="";
requestAnimationFrame(runLoop);
}

function runLeft(){
if(runState)runState.x=Math.max(80,runState.x-55);
}
function runRight(){
if(runState)runState.x=Math.min(300,runState.x+55);
}
function runJump(){
if(runState&&!runState.jump){
runState.vy=-11;
runState.jump=true;
}
}
function runSlide(){
if(runState)runState.slide=true;
setTimeout(()=>{if(runState)runState.slide=false},450);
}

function runLoop(now){
if(!runState)return;

const dt=Math.min(40,now-runState.last);
runState.last=now;

if(now-runState.start>30000){
finishRun(false);
return;
}

runState.distance+=dt*.08;

if(Math.random()<.025){
runState.obstacles.push({
x:820,
y:340,
w:35,
h:50
});
}

if(Math.random()<.02){
runState.coinsList=runState.coinsList||[];
runState.coinsList.push({x:820,y:260+Math.random()*90});
}

runState.vy+=.5;
runState.y+=runState.vy;

if(runState.y>=340){
runState.y=340;
runState.vy=0;
runState.jump=false;
}

runState.obstacles.forEach(o=>o.x-=dt*.45);
runState.obstacles=runState.obstacles.filter(o=>o.x>-80);

if(runState.coinsList){
runState.coinsList.forEach(c=>c.x-=dt*.45);
runState.coinsList=runState.coinsList.filter(c=>c.x>-30);
}

const canvas=document.getElementById("runCanvas");
const ctx=canvas.getContext("2d");

ctx.fillStyle="#100d20";
ctx.fillRect(0,0,800,430);

ctx.fillStyle="#261b38";
ctx.fillRect(0,300,800,130);

ctx.fillStyle="#3c2a51";
ctx.fillRect(0,370,800,60);

for(let x=0;x<800;x+=80){
ctx.fillStyle="#f7d978";
ctx.fillRect((x-(now*.2)%80),365,40,5);
}

runState.obstacles.forEach(o=>{
ctx.fillStyle="#ff5271";
ctx.fillRect(o.x,o.y,o.w,o.h);

if(
Math.abs(o.x-runState.x)<45 &&
Math.abs(o.y-runState.y)<45 &&
!runState.jump &&
!runState.slide
){
runState.distance=Math.max(0,runState.distance-25);
o.x=-100;
}
});

if(runState.coinsList){
runState.coinsList.forEach(c=>{
ctx.fillStyle="#f7d978";
ctx.beginPath();
ctx.arc(c.x,c.y,11,0,Math.PI*2);
ctx.fill();

if(Math.hypot(c.x-runState.x,c.y-runState.y)<35){
runState.coins++;
c.x=-100;
}
});
}

ctx.font="42px Arial";
ctx.textAlign="center";
ctx.fillText(players[current].avatar,runState.x,runState.y+5);

if(runState.distance>=runState.goal){
finishRun(true);
return;
}

document.getElementById("runDistance").textContent=
Math.floor(runState.distance);

document.getElementById("runCoins").textContent=
runState.coins;

requestAnimationFrame(runLoop);
}

function finishRun(win){
if(!runState||runState.finished)return;
runState.finished=true;

const reward=runState.coins*12+(win?250:0);
addCoins(reward);

document.getElementById("runResult").textContent=
win
?"💖 "+players[current].boy+" дождался! +"+reward+" 💎"
:"😅 Не успела добежать. Собрано +"+reward+" 💎";
}

/* QUIZ */
const quizData={
ru:[
["Кто исполняет песню «Комета»?","Люся Чеботина","Дима Билан","Zivert","Мот",0],
["Какая группа исполняет «Районы-кварталы»?","Звери","Руки Вверх!","Би-2","Градусы",0],
["Кто поёт «Знаешь ли ты»?","МакSим","Ёлка","Полина Гагарина","Вера Брежнева",0]
],
ge:[
["Какая страна известна многоголосным грузинским пением?","Грузия","Италия","Испания","Франция",0],
["Как называется известный грузинский танец?","Картули","Самба","Танго","Фламенко",0],
["Какой инструмент часто используется в грузинской музыке?","Пандури","Скрипка","Арфа","Саксофон",0]
],
ost:[
["Из какого фильма песня «Let It Go»?","Холодное сердце","Барби","Аватар","Шрек",0],
["Как называется музыка из фильма или сериала?","Саундтрек","Ремикс","Сингл","Кавер",0],
["В каком фильме есть песня «Hakuna Matata»?","Король Лев","Гарри Поттер","Матильда","Аладдин",0]
]
};

function openQuiz(){
show("quiz");
document.getElementById("quizCategories").style.display="block";
document.getElementById("quizGame").style.display="none";
}

function quizStart(cat){
const arr=quizData[cat];
quizState={arr,index:Math.floor(Math.random()*arr.length),time:10,answered:false};

document.getElementById("quizCategories").style.display="none";
document.getElementById("quizGame").style.display="block";

renderQuestion();

clearInterval(gameTimer);
gameTimer=setInterval(()=>{
quizState.time--;
document.getElementById("quizTime").textContent=quizState.time;
if(quizState.time<=0)quizAnswer(-1);
},1000);
}

function renderQuestion(){
const q=quizState.arr[quizState.index];
document.getElementById("question").textContent="🎵 "+q[0];
document.getElementById("quizTime").textContent=quizState.time;
document.getElementById("quizResult").textContent="";

const box=document.getElementById("answers");
box.innerHTML="";

for(let i=0;i<4;i++){
const b=document.createElement("button");
b.className="dark";
b.textContent=q[i+1];
b.onclick=()=>quizAnswer(i);
box.appendChild(b);
}
}

function quizAnswer(index){
if(!quizState||quizState.answered)return;
quizState.answered=true;
clearInterval(gameTimer);

const q=quizState.arr[quizState.index];

if(index===q[5]){
addCoins(100);
document.getElementById("quizResult").textContent=
"✨ Правильно! +100 💎";
}else{
document.getElementById("quizResult").textContent=
"❌ Неверно. Правильный ответ: "+q[q[5]+1];
}

setTimeout(()=>{
quizState.answered=false;
quizState.index=Math.floor(Math.random()*quizState.arr.length);
quizState.time=10;
renderQuestion();
gameTimer=setInterval(()=>{
quizState.time--;
document.getElementById("quizTime").textContent=quizState.time;
if(quizState.time<=0)quizAnswer(-1);
},1000);
},1300);
}

/* GLAM CHALLENGE */
const challenges=[
["💖 Выбери образ для свидания",["👗 Розовое платье","🖤 Чёрный костюм","👕 Спортивный образ","🧥 Зимняя куртка"]],
["🪩 Выбери образ для вечеринки",["✨ Блестящее платье","👖 Джинсы","🧢 Кепка","🧥 Пальто"]],
["🌴 Выбери образ для пляжа",["👙 Пляжный образ","🧥 Пальто","🎓 Школьная форма","🧣 Шарф"]]
];

function openChallenge(){
show("challenge");
const c=challenges[Math.floor(Math.random()*challenges.length)];

document.getElementById("challengeText").textContent=c[0];

const box=document.getElementById("challengeOptions");
box.innerHTML="";

c[1].forEach((x,i)=>{
const b=document.createElement("button");
b.className="dark";
b.textContent=x;
b.onclick=()=>{
addCoins(i===0?120:40);
document.getElementById("challengeResult").textContent=
i===0?"✨ Идеальный Glam-образ! +120 💎":"💎 Хороший выбор! +40 💎";
};
box.appendChild(b);
});
}

/* SHOP */
const shop=[
["💎","Алмазные серьги",120],
["👑","Золотая корона",250],
["💄","VIP косметика",180],
["👗","Гламурное платье",350],
["👠","Золотые туфли",300],
["🪩","Диско-аксессуар",200],
["🎀","Розовый бант",100]
];

function renderShop(){
const box=document.getElementById("shopList");
box.innerHTML="";

shop.forEach(x=>{
const d=document.createElement("div");
d.className="item";
d.innerHTML=
"<span>"+x[0]+" "+x[1]+"<br><small>"+x[2]+" 💎</small></span>";

const b=document.createElement("button");
b.className="gold";
b.textContent="Купить";
b.onclick=()=>buyItem(x);

d.appendChild(b);
box.appendChild(d);
});
}

function buyItem(x){
if(players[current].coins<x[2]){
document.getElementById("shopResult").textContent="💔 Не хватает монет!";
return;
}

players[current].coins-=x[2];
players[current].items.push(x[0]+" "+x[1]);
save();
update();

document.getElementById("shopResult").textContent=
"✨ Куплено: "+x[1];
}

function renderStyle(){
const p=players[current];
document.getElementById("stylePlayer").textContent=
p.avatar+" "+p.name;

const box=document.getElementById("inventory");

if(!p.items.length){
box.innerHTML="<p class='center'>Пока гардероб пуст ✨</p>";
return;
}

box.innerHTML=p.items.map(x=>
"<span class='badge'>"+x+"</span>"
).join("");
}

/* RATING */
function renderRating(){
const arr=Object.values(players).sort((a,b)=>b.coins-a.coins);
const medals=["🥇","🥈","🥉","🏅"];

document.getElementById("ratingList").innerHTML=
arr.map((p,i)=>
"<div class='player'>"+
"<div class='pavatar'>"+p.avatar+"</div>"+
"<div class='pinfo'>"+
"<div class='pname'>"+medals[i]+" "+p.name+"</div>"+
"<div class='pcoins'>💎 "+p.coins+"</div>"+
"</div></div>"
).join("");
}

/* KEYBOARD */
document.addEventListener("keydown",e=>{
if(e.key==="ArrowLeft")movePlayer(-1,0);
if(e.key==="ArrowRight")movePlayer(1,0);
if(e.key==="ArrowUp"){
if(runState)runJump();
else movePlayer(0,-1);
}
if(e.key==="ArrowDown"){
if(runState)runSlide();
else movePlayer(0,1);
}
});

load();
update();
</script>
</body>
</html>
