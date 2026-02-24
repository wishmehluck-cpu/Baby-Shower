<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lilly Rose's Celestial Shower</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400&display=swap" rel="stylesheet">

<style>
body{
margin:0;
font-family:'Poppins',sans-serif;
background:linear-gradient(to bottom,#fff6f9,#eaf4ff);
overflow-x:hidden;
text-align:center;
color:#6d5c73;
}

/* INTRO SCREEN */
#intro{
position:fixed;
top:0;left:0;
width:100%;height:100%;
background:linear-gradient(to bottom,#ffeef6,#eaf4ff);
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
z-index:9999;
transition:1s;
}

#intro button{
margin-top:20px;
padding:15px 35px;
border-radius:40px;
border:none;
background:#f8c8dc;
font-size:18px;
cursor:pointer;
}

/* TITLE */
h1{
font-family:'Great Vibes',cursive;
font-size:75px;
color:#d88ca4;
text-shadow:0 0 25px rgba(255,182,193,.8);
position:relative;
}

/* Angel Wings */
.wings{
position:absolute;
top:-40px;
left:50%;
transform:translateX(-50%);
font-size:120px;
opacity:.15;
}

/* Floating Clouds */
.cloud{
position:absolute;
background:white;
border-radius:100px;
opacity:.7;
animation:float 90s linear infinite;
}
@keyframes float{
from{transform:translateX(-300px);}
to{transform:translateX(120%);}
}

/* Sparkles */
.sparkle{
position:fixed;
width:3px;height:3px;
background:white;
border-radius:50%;
animation:twinkle 4s infinite;
}
@keyframes twinkle{
0%,100%{opacity:0;}
50%{opacity:1;}
}

/* Sections */
.section{padding:80px 20px;}
.card{
background:rgba(255,255,255,.95);
margin:30px auto;
padding:35px;
width:85%;
max-width:650px;
border-radius:35px;
box-shadow:0 20px 50px rgba(0,0,0,.05);
}

/* Buttons */
button{
background:#f8c8dc;
border:none;
padding:12px 30px;
border-radius:30px;
cursor:pointer;
transition:.3s;
}
button:hover{background:#e6a8c5;}

input,textarea{
width:80%;
padding:10px;
margin:10px;
border-radius:15px;
border:1px solid #f0d6e0;
}

/* Floating Hearts */
.heart{
position:fixed;
font-size:22px;
animation:rise 3s linear forwards;
}
@keyframes rise{
from{transform:translateY(0);opacity:1;}
to{transform:translateY(-200px);opacity:0;}
}
</style>
</head>

<body>

<div id="intro">
<h2 style="font-family:'Great Vibes';font-size:50px;color:#d88ca4;">
Welcome to Lilly Rose’s Celestial Nursery
</h2>
<button onclick="enterSite()">🚪 Open the Nursery Door</button>
</div>

<div class="cloud" style="top:120px;width:200px;height:80px;"></div>
<div class="cloud" style="top:350px;width:260px;height:100px;animation-duration:110s;"></div>

<header style="padding:120px 20px;">
<div class="wings">🕊️</div>
<h1>Lilly Rose</h1>
<p style="letter-spacing:4px;color:#8fa6c9;">
A Precious Angel Sent From Above
</p>
<button onclick="toggleMusic()">🎵 Angel Music</button>
</header>

<div class="section">
<h2 style="font-family:'Great Vibes';color:#d88ca4;font-size:45px;">
✨ Receive a Heavenly Blessing ✨
</h2>
<div class="card">
<button onclick="blessing()">Open Blessing</button>
<p id="blessText"></p>
</div>
</div>

<div class="section">
<h2 style="font-family:'Great Vibes';color:#d88ca4;font-size:45px;">
🕯 Light a Candle Wall
</h2>
<div class="card">
<button onclick="lightCandle()">Light a Candle</button>
<p id="candleMsg"></p>
</div>
</div>

<div class="section">
<h2 style="font-family:'Great Vibes';color:#d88ca4;font-size:45px;">
🎀 Baby Predictions
</h2>
<div class="card">
<form action="https://formspree.io/f/YOURFORMID" method="POST">
<input type="text" name="name" placeholder="Your Name">
<input type="text" name="arrival" placeholder="Guess Arrival Date">
<input type="text" name="weight" placeholder="Guess Weight">
<textarea name="advice" placeholder="Leave angel advice..."></textarea>
<br>
<button type="submit">Send to Heaven 🤍</button>
</form>
</div>
</div>

<footer style="padding:50px;color:#aaa;">
Made with love for our celestial baby 👼✨
</footer>

<audio id="angelMusic" loop>
<source src="https://cdn.pixabay.com/download/audio/2022/03/15/audio_c8e5c6b03e.mp3?filename=heavenly-ambient-110624.mp3" type="audio/mpeg">
</audio>

<script>
function enterSite(){
document.getElementById("intro").style.opacity="0";
setTimeout(()=>{document.getElementById("intro").style.display="none";},1000);
}

const blessings=[
"May angels guide her every step.",
"She is wrapped in eternal love.",
"A precious light in this world.",
"Heaven sent the sweetest gift.",
"Her life will sparkle with joy."
];

function blessing(){
document.getElementById("blessText").innerText=
blessings[Math.floor(Math.random()*blessings.length)];
createHeart();
}

function lightCandle(){
document.getElementById("candleMsg").innerText=
"Your candle glows for Lilly 🕯✨";
createHeart();
}

function createHeart(){
let heart=document.createElement("div");
heart.className="heart";
heart.innerText="🤍";
heart.style.left=Math.random()*100+"vw";
heart.style.top="70vh";
document.body.appendChild(heart);
setTimeout(()=>heart.remove(),3000);
}

function toggleMusic(){
let music=document.getElementById("angelMusic");
music.paused?music.play():music.pause();
}

/* Sparkles */
for(let i=0;i<80;i++){
let s=document.createElement("div");
s.className="sparkle";
s.style.top=Math.random()*100+"vh";
s.style.left=Math.random()*100+"vw";
s.style.animationDelay=Math.random()*5+"s";
document.body.appendChild(s);
}
</script>

</body>
</html>
