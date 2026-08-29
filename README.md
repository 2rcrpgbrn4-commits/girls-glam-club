<!DOCTYPE html>
<html lang="ru">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>GIRLS GLAM CLUB</title>

<style>
*{box-sizing:border-box}

body{
 margin:0;
 min-height:100vh;
 font-family:Arial,sans-serif;
 color:#fff;
 background:
 radial-gradient(circle at 20% 0%,#68265f 0,#251021 38%,#080808 80%);
}

.app{
 max-width:430px;
 margin:auto;
 padding:22px 16px 40px;
}

.logo{
 text-align:center;
 font-size:29px;
 font-weight:900;
 color:#f5d77a;
 text-shadow:0 0 18px #ff65d0;
}

.subtitle{
 text-align:center;
 color:#f2cce5;
 margin:7px 0 20px;
}

.card{
 background:rgba(255,255,255,.08);
 border:1px solid rgba(245,215,122,.35);
 border-radius:25px;
 padding:20px;
 margin-bottom:16px;
 box-shadow:0 12px 35px rgba(0,0,0,.4);
}

.avatar{
 width:105px;
 height:105px;
 margin:auto;
 border-radius:50%;
 display:flex;
 align-items:center;
 justify-content:center;
 font-size:55px;
 background:linear-gradient(135deg,#f5d77a,#d989b8);
 border:4px solid #f5d77a;
 box-shadow:0 0 30px rgba(255,105,210,.45);
}

.name{
 text-align:center;
 font-size:25px;
 font-weight:bold;
 margin:12px 0 5px;
}

.coins{
 text-align:center;
 font-size:23px;
 color:#f5d77a;
 margin-bottom:10px;
}

button{
 width:100%;
 border:0;
 border-radius:16px;
 padding:14px;
 margin-top:9px;
 font-size:16px;
 font-weight:bold;
 cursor:pointer;
}

.main{
 background:linear-gradient(90deg,#f5d77a,#dca5c9);
 color:#171017;
}

.dark{
 background:rgba(255,255,255,.1);
 color:white;
 border:1px solid rgba(245,215,122,.25);
}

.section{display:none}
.section.active{display:block}

.player{
 display:flex;
 align-items:center;
 gap:12px;
 padding:12px;
 margin:8px 0;
 border-radius:17px;
 background:rgba(255,255,255,.07);
}

.player-avatar{
 width:52px;
 height:52px;
 border-radius:50%;
 display:flex;
 align-items:center;
 justify-content:center;
 font-size:27px;
 background:linear-gradient(135deg,#f5d77a,#d989b8);
}

.player-info{
 flex:1;
 text-align:left;
}

.player-name{font-weight:bold}

.player-coins{
 color:#f5d77a;
 font-size:14px;
}

.player button{
 width:auto;
 margin:0;
 padding:8px 12px;
 font-size:13px;
}

/* DANCE BATTLE */

.battle-title{
 text-align:center;
 color:#ff7bdc;
 text-shadow:0 0 15px #ff4dcc;
}

.timer{
 text-align:center;
 font-size:30px;
 font-weight:bold;
 color:#f5d77a;
 margin:12px;
}

.combo{
 display:flex;
 justify-content:center;
 gap:8px;
 flex-wrap:wrap;
 margin:18px 0;
 min-height:60px;
}

.combo span{
 width:52px;
 height:52px;
 display:flex;
 align-items:center;
 justify-content:center;
 border-radius:15px;
 background:rgba(255,255,255,.08);
 border:1px solid #ff72d8;
 font-size:27px;
 box-shadow:0 0 14px rgba(255,80,210,.35);
}

.combo span.done{
 background:rgba(80,255,170,.2);
 border-color:#6affb0;
 opacity:.65;
}

.neon-grid{
 display:grid;
 grid-template-columns:repeat(2,1fr);
 gap:12px;
 margin-top:20px;
}

.neon{
 height:75px;
 font-size:32px;
 color:#fff;
 background:rgba(255,255,255,.06);
 border:2px solid #ff70dc;
 box-shadow:0 0 16px rgba(255,70,210,.35);
 transition:.12s;
}

.neon:active{
 transform:scale(.93);
 box-shadow:0 0 30px #ff70dc;
}

.level{
 text-align:center;
 color:#f5d77a;
 font-weight:bold;
}

.result{
 text-align:center;
 color:#f5d77a;
 font-weight:bold;
 font-size:18px;
 margin-top:15px;
}

.shop-item{
 display:flex;
 align-items:center;
 justify-content:space-between;
 gap:8px;
 padding:12px;
 margin:8px 0;
 border-radius:15px;
 background:rgba(255,255,255,.06);
}

.shop-item button{
 width:auto;
 padding:8px 12px;
 margin:0;
 font-size:13px;
}
</style>
</head>

<body>

<div class="app">

<div class="logo">💎 GIRLS GLAM CLUB</div>
<div class="subtitle">✨ Rich • Glamour • Dance ✨</div>


<!-- HOME -->

<div id="home" class="section active">

<div class="card">

<div class="avatar" id="avatar">👑</div>

<div class="name" id="playerName">Софа</div>

<div class="coins">
💎 <span id="coins">0</span>
</div>

<button class="main" onclick="startBattle()">
🪩 DANCE BATTLE
</button>

<button class="dark" onclick="show('tasks')">
🎁 ЗАДАНИЯ
</button>

<button class="dark" onclick="show('shop')">
🛍️ GLAM SHOP
</button>

<button class="dark" onclick="show('style')">
👗 МОЙ ОБРАЗ
</button>

<button class="dark" onclick="show('rating')">
🏆 РЕЙТИНГ
</button>

</div>

<div class="card">

<h2>👭 GIRLS CLUB</h2>

<p>
Софа, Лика, Маико и Ани —
четыре подруги в мире гламура!
</p>

<button class="dark" onclick="show('players')">
👭 ВЫБРАТЬ ИГРОКА
</button>

</div>

</div>


<!-- PLAYERS -->

<div id="players" class="section">

<div class="card">

<button class="dark" onclick="show('home')">← Назад</button>

<h2>👭 КТО ИГРАЕТ?</h2>

<div class="player">
<div class="player-avatar">👑</div>
<div class="player-info">
<div class="player-name">Софа</div>
<div class="player-coins" id="sofaCoins">💎 0</div>
</div>
<button class="main" onclick="selectPlayer('sofa')">Играть</button>
</div>

<div class="player">
<div class="player-avatar">🎀</div>
<div class="player-info">
<div class="player-name">Лика</div>
<div class="player-coins" id="likaCoins">💎 0</div>
</div>
<button class="main" onclick="selectPlayer('lika')">Играть</button>
</div>

<div class="player">
<div class="player-avatar">🔥</div>
<div class="player-info">
<div class="player-name">Маико</div>
<div class="player-coins" id="maikoCoins">💎 0</div>
</div>
<button class="main" onclick="selectPlayer('maiko')">Играть</button>
</div>

<div class="player">
<div class="player-avatar">🦋</div>
<div class="player-info">
<div class="player-name">Ани</div>
<div class="player-coins" id="aniCoins">💎 0</div>
</div>
<button class="main" onclick="selectPlayer('ani')">Играть</button>
</div>

</div>
</div>


<!-- DANCE BATTLE -->

<div id="battle" class="section">

<div class="card">

<button class="dark" onclick="leaveBattle()">← Выйти</button>

<h2 class="battle-title">🪩 DANCE BATTLE</h2>

<div class="level" id="levelText">
LEVEL 1 • EASY
</div>

<p style="text-align:center">
Запомни комбинацию и повтори её!
</p>

<div class="timer" id="timer">10</div>

<div class="combo" id="combo"></div>

<div class="neon-grid">

<button class="neon" onclick="press('⬆️')">⬆️</button>
<button class="neon" onclick="press('➡️')">➡️</button>
<button class="neon" onclick="press('⬇️')">⬇️</button>
<button class="neon" onclick="press('⬅️')">⬅️</button>

</div>

<p class="result" id="battleResult"></p>

</div>

</div>


<!-- TASKS -->

<div id="tasks" class="section">

<div class="card">

<button class="dark" onclick="show('home')">← Назад</button>

<h2>🎁 ЗАДАНИЯ</h2>

<p>
Здесь будут задания, которые нужно выполнить,
а не просто нажать кнопку.
</p>

<button class="main" onclick="startBattle()">
💃 Выполнить танцевальное задание
</button>

<p class="result" id="taskResult"></p>

</div>

</div>


<!-- SHOP -->

<div id="shop" class="section">

<div class="card">

<button class="dark" onclick="show('home')">← Назад</button>

<h2>🛍️ GLAM SHOP</h2>

<h3>🍕 ЕДА</h3>

<div class="shop-item">
<span>🍕 Пицца — 100 💎</span>
<button onclick="buy(100,'Пицца')">Купить</button>
</div>

<div class="shop-item">
<span>🧋 Бабл-ти — 150 💎</span>
<button onclick="buy(150,'Бабл-ти')">Купить</button>
</div>

<div class="shop-item">
<span>🍣 Суши — 250 💎</span>
<button onclick="buy(250,'Суши')">Купить</button>
</div>

<h3>💃 GLAM</h3>

<div class="shop-item">
<span>🎤 Микрофон — 300 💎</span>
<button onclick="buy(300,'Микрофон')">Купить</button>
</div>

<div class="shop-item">
<span>🎧 Наушники — 400 💎</span>
<button onclick="buy(400,'Наушники')">Купить</button>
</div>

<div class="shop-item">
<span>🪩 Диско-шар — 700 💎</span>
<button onclick="buy(700,'Диско-шар')">Купить</button>
</div>

<p class="result" id="shopResult"></p>

</div>

</div>


<!-- STYLE -->

<div id="style" class="section">

<div class="card">

<button class="dark" onclick="show('home')">← Назад</button>

<h2>👗 МОЙ ОБРАЗ</h2>

<p>Купленные предметы:</p>

<div id="inventory">
Пока ничего нет ✨
</div>

</div>

</div>


<!-- RATING -->

<div id="rating" class="section">

<div class="card">

<button class="dark" onclick="show('home')">← Назад</button>

<h2>🏆 РЕЙТИНГ</h2>

<div id="ratingList"></div>

</div>

</div>

</div>


<script>

const players={

sofa:{
name:"Софа",
avatar:"👑",
coins:0,
items:[]
},

lika:{
name:"Лика",
avatar:"🎀",
coins:0,
items:[]
},

maiko:{
name:"Маико",
avatar:"🔥",
coins:0,
items:[]
},

ani:{
name:"Ани",
avatar:"🦋",
coins:0,
items:[]
}

};

let current="sofa";

let sequence=[];
let position=0;
let timerValue=10;
let timerInterval=null;
let battleActive=false;

const arrows=["⬆️","➡️","⬇️","⬅️"];


function load(){

const saved=localStorage.getItem("girlsGlamPlayers");

if(saved){

const data=JSON.parse(saved);

Object.keys(players).forEach(key=>{

if(data[key]){
players[key]=data[key];
}

});

}

}


function save(){

localStorage.setItem(
"girlsGlamPlayers",
JSON.stringify(players)
);

}


function update(){

const p=players[current];

document.getElementById("playerName").textContent=p.name;

document.getElementById("avatar").textContent=p.avatar;

document.getElementById("coins").textContent=p.coins;

document.getElementById("sofaCoins").textContent=
"💎 "+players.sofa.coins;

document.getElementById("likaCoins").textContent=
"💎 "+players.lika.coins;

document.getElementById("maikoCoins").textContent=
"💎 "+players.maiko.coins;

document.getElementById("aniCoins").textContent=
"💎 "+players.ani.coins;

}


function selectPlayer(id){

current=id;

update();

show("home");

}


function startBattle(){

show("battle");

battleActive=false;

clearInterval(timerInterval);

sequence=[];

position=0;

timerValue=10;

document.getElementById("timer").textContent=10;

document.getElementById("battleResult").textContent="";

const length=4;

for(let i=0;i<length;i++){

sequence.push(
arrows[Math.floor(Math.random()*arrows.length)]
);

}

renderCombo();

setTimeout(()=>{

battleActive=true;

timerInterval=setInterval(()=>{

timerValue--;

document.getElementById("timer").textContent=timerValue;

if(timerValue<=0){

finishBattle(false);

}

},1000);

},1800);

}


function renderCombo(){

const box=document.getElementById("combo");

box.innerHTML="";

sequence.forEach((arrow,index)=>{

const span=document.createElement("span");

span.textContent=arrow;

if(index<position){
span.classList.add("done");
}

box.appendChild(span);

});

}


function press(arrow){

if(!battleActive)return;

if(arrow===sequence[position]){

position++;

renderCombo();

if(position===sequence.length){

finishBattle(true);

}

}else{

finishBattle(false);

}

}


function finishBattle(success){

if(!battleActive)return;

battleActive=false;

clearInterval(timerInterval);

let reward=0;
let message="";

if(success){

if(timerValue>=8){

reward=150;
message="✨ PERFECT! Идеально! +150 💎";

}else if(timerValue>=5){

reward=100;
message="🔥 ОТЛИЧНО! +100 💎";

}else{

reward=60;
message="💃 ХОРОШО! +60 💎";

}

}else{

reward=0;
message="😅 Комбинация не пройдена. Попробуй ещё раз!";

}

players[current].coins+=reward;

save();

update();

document.getElementById("battleResult").textContent=message;

}


function leaveBattle(){

clearInterval(timerInterval);

battleActive=false;

show("home");

}


function buy(price,item){

if(players[current].coins<price){

document.getElementById("shopResult").textContent=
"💔 Недостаточно монет!";

return;

}

players[current].coins-=price;

players[current].items.push(item);

save();

update();

document.getElementById("shopResult").textContent=
"✨ Куплено: "+item+"!";

}


function updateInventory(){

const items=players[current].items;

document.getElementById("inventory").textContent=
items.length
?items.join(" • ")
:"Пока ничего нет ✨";

}


function updateRating(){

const list=Object.values(players)
.sort((a,b)=>b.coins-a.coins);

const medals=["🥇","🥈","🥉","4️⃣"];

document.getElementById("ratingList").innerHTML=

list.map((p,i)=>

"<div class='player'>"+

"<div class='player-avatar'>"+
p.avatar+
"</div>"+

"<div class='player-info'>"+

"<div class='player-name'>"+
medals[i]+" "+p.name+
"</div>"+

"<div class='player-coins'>"+
"💎 "+p.coins+
"</div>"+

"</div>"+

"</div>"

).join("");

}


function show(id){

clearInterval(timerInterval);

if(id!=="battle"){
battleActive=false;
}

document
.querySelectorAll(".section")
.forEach(x=>x.classList.remove("active"));

document
.getElementById(id)
.classList.add("active");

if(id==="style"){
updateInventory();
}

if(id==="rating"){
updateRating();
}

}


load();

update();

</script>

</body>
</html>
