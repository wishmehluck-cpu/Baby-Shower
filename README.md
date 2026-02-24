<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lilly Rose | Celestial Shower</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;500&display=swap" rel="stylesheet">

<style>
body{
margin:0;
font-family:'Poppins',sans-serif;
background:linear-gradient(to bottom,#fff8f2,#f3f8ff);
overflow-x:hidden;
color:#7a5c5c;
scroll-behavior:smooth;
}

/* ===== INTRO DOOR ===== */
#intro{
position:fixed;
inset:0;
background:radial-gradient(circle,#fff3e6,#eaf4ff);
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:9999;
transition:1.2s;
}

.door{
width:120px;
height:200px;
background:linear-gradient(#f8d9b5,#e8b98d);
border-radius:60px 60px 10px 10px;
box-shadow:0 0 40px rgba(255,215,0,.5);
animation:glow 2s infinite alternate;
}

@keyframes glow{
from{box-shadow:0 0 20px gold;}
to{box-shadow:0 0 60px gold;}
}

#intro button{
margin-top:30px;
padding:14px 30px;
border:none;
border-radius:30px;
background:gold;
cursor:pointer;
}

/* ===== TITLE ===== */
header{
padding:120px 20px;
text-align:center;
position:relative;
}

h1{
font-family:'Great Vibes',cursive;
font-size:70px;
color:#d4a017;
text-shadow:0 0 30px rgba(255,215,0,.8);
margin:0;
}

.subtitle{
letter-spacing:4px;
color:#9aa7c9;
}

/* ===== CLOUDS ===== */
.cloud{
position:absolute;
background:white;
border-radius:100px;
opacity:.6;
animation:float 100s linear infinite;
}

@keyframes float{
from{transform:translateX(-400px);}
to{transform:translateX(140%);}
}

/* ===== SECTIONS ===== */
.section{
padding:80px 20px;
opacity:0;
transform:translateY(40px);
transition:1s ease;
}

.section.visible{
opacity:1;
transform:translateY(0);
}

.card{
background:white;
padding:35px;
margin:auto;
max-width:650px;
border-radius:35px;
box-shadow:0 20px 60px rgba(0,0,0,.05);
}

/* ===== BUTTONS ===== */
button{
background:linear-gradient(45deg,#ffd700,#f8c200);
border:none;
padding:12px 28px;
border-radius:30px;
cursor:pointer;
transition:.3s;
}

button:hover{
transform:scale(1.05);
box-shadow:0 0 20px gold;
}

/* ===== GOLD PARTICLES ===== */
.particle{
position:fixed;
width:3px;height:3px;
background:gold;
border-radius:50%;
animation:twinkle 4s infinite;
}

@keyframes twinkle{
0%,100%{opacity:0;}
50%{opacity:1;}
}

/* ===== CURSOR SPARKLES ===== */
.spark{
position:fixed;
font-size:14px;
color:gold;
pointer-events:none;
animation:rise 1s forwards;
}

@keyframes rise{
from{opacity:1;transform:translateY(0);}
to{opacity:0;transform:translateY(-20px);}
}

/* MOBILE */
@media(max-width:768px){
h1{font-size:50px;}
.section{padding:60px 15px;}
}
</style>
</head>
<body>

<div id="intro">
<div class="door"></div>
<button onclick="enter()">✨ Open the Celestial Door ✨</button>
</div>

<!-- Floating Clouds -->
<div class="cloud" style="top:150px;width:250px;height:90px;"></div>
<div class="cloud" style="top:350px;width:300px;height:110px;animation-duration:140s;"></div>

<header>
<h1>Lilly Rose</h1>
<p class="subtitle">A Golden Angel Is On The Way</p>
</header>

<div class="section">
<div class="card">
<h2 style="font-family:'Great Vibes';color:#d4a017;">Receive a Blessing</h2>
<button onclick="bless()">✨ Open Blessing ✨</button>
<p id="blessText"></p>
</div>
</div>

<div class="section">
<div class="card">
<h2 style="font-family:'Great Vibes';color:#d4a017;">Light a Golden Candle</h2>
<button onclick="candle()">🕯 Light Candle</button>
<p id="candleText"></p>
</div>
</div>

<footer style="text-align:center;padding:60px;color:#aaa;">
Made with celestial love ✨
</footer>

<script>
function enter(){
document.getElementById("intro").style.opacity="0";
setTimeout(()=>document.getElementById("intro").style.display="none",1200);
}

/* Scroll reveal */
const sections=document.querySelectorAll('.section');
window.addEventListener('scroll',()=>{
sections.forEach(sec=>{
const rect=sec.getBoundingClientRect();
if(rect.top<window.innerHeight-100){
sec.classList.add('visible');
}
});
});

/* Blessings */
const blessings=[
"May angels guard her every step.",
"She shines brighter than the stars.",
"A golden gift from heaven.",
"Her life will sparkle with joy.",
"Wrapped in eternal love."
];

function bless(){
document.getElementById("blessText").innerText=
blessings[Math.floor(Math.random()*blessings.length)];
}

function candle(){
document.getElementById("candleText").innerText=
"Your golden candle glows for Lilly ✨";
}

/* GOLD PARTICLES BACKGROUND */
for(let i=0;i<120;i++){
let p=document.createElement("div");
p.className="particle";
p.style.top=Math.random()*100+"vh";
p.style.left=Math.random()*100+"vw";
p.style.animationDelay=Math.random()*5+"s";
document.body.appendChild(p);
}

/* CURSOR SPARKLE TRAIL */
document.addEventListener("mousemove",function(e){
let s=document.createElement("div");
s.className="spark";
s.innerText="✨";
s.style.left=e.pageX+"px";
s.style.top=e.pageY+"px";
document.body.appendChild(s);
setTimeout(()=>s.remove(),1000);
});
</script>

</body>
</html>
