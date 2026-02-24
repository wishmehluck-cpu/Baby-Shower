<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Baby Girl’s Digital Shower</title>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Ocean+Delight&display=swap" rel="stylesheet">

<style>
/* Global Styles */
body {
  margin: 0;
  font-family: 'Lato', sans-serif;
  background: linear-gradient(to bottom, #ffe6f0, #fff0f5);
  overflow-x: hidden;
  position: relative;
}

/* Headings */
h1, h2, h3 {
  font-family: 'Ocean Delight', cursive;
  text-align: center;
  color: #d46a7e;
}

/* Hero Section */
.hero {
  height: 100vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  position: relative;
  overflow: hidden;
  padding: 0 20px;
}

.hero h1 {
  font-size: 3em;
  margin-bottom: 20px;
}

.hero p {
  font-size: 1.5em;
  color: #666;
  text-align: center;
  max-width: 600px;
}

/* Floating Animations */
.floating {
  position: absolute;
  pointer-events: none;
  animation: float linear infinite;
}

.cloud { width: 120px; opacity: 0.6; animation-duration: 30s; }
.star { width: 20px; opacity: 0.8; animation-duration: 25s; }
.angel { width: 80px; opacity: 1; animation-duration: 35s; }
.toy { width: 40px; opacity: 0.9; animation-duration: 28s; }

@keyframes float {
  0% { transform: translateY(100vh) translateX(0); }
  100% { transform: translateY(-150px) translateX(50px); }
}

/* Buttons */
.btn {
  background-color: #f9c0d6;
  border: none;
  padding: 15px 30px;
  margin: 10px;
  font-size: 1.2em;
  border-radius: 50px;
  cursor: pointer;
  transition: 0.3s;
  color: white;
  font-family: 'Ocean Delight', cursive;
}

.btn:hover { background-color: #d46a7e; }

/* Popups */
.popup {
  display: none;
  position: fixed;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #fff0f5;
  padding: 30px;
  border-radius: 15px;
  box-shadow: 0 0 15px rgba(0,0,0,0.3);
  z-index: 1000;
  max-width: 90%;
}

.popup h2 { margin-top: 0; color: #d46a7e; }
.popup input, .popup select {
  width: 100%;
  padding: 10px;
  margin: 10px 0;
  border-radius: 10px;
  border: 1px solid #ccc;
}
.popup .close-btn {
  background: #d46a7e;
  color: white;
  padding: 10px 20px;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  float: right;
  margin-top: 10px;
}

/* Music Button */
#music-btn {
  position: fixed;
  top: 20px;
  right: 20px;
  background: #f9c0d6;
  color: white;
  padding: 10px 15px;
  border: none;
  border-radius: 50px;
  cursor: pointer;
  font-family: 'Ocean Delight', cursive;
  z-index: 1001;
}
</style>
</head>
<body>

<!-- Hero Section -->
<div class="hero">
  <h1>Welcome to Baby Girl's Digital Shower!</h1>
  <p>Celebrate with us the arrival of our precious little angel!</p>
  <button class="btn" onclick="openPopup('rsvpPopup')">RSVP Here</button>
  <button class="btn" onclick="openPopup('giftPopup')">Gift Registry</button>
</div>

<!-- Floating Elements -->
<img src="https://i.ibb.co/0JpRr3V/cloud.png" class="cloud floating" style="top:20%; left:10%;" />
<img src="https://i.ibb.co/0JpRr3V/cloud.png" class="cloud floating" style="top:60%; left:70%;" />
<img src="https://i.ibb.co/FXjKy8m/star.png" class="star floating" style="top:10%; left:50%;" />
<img src="https://i.ibb.co/FXjKy8m/star.png" class="star floating" style="top:80%; left:20%;" />
<img src="https://i.ibb.co/2W3v0Fz/angel-baby.png" class="angel floating" style="top:50%; left:40%;" />
<img src="https://i.ibb.co/vqJxv7F/toy.png" class="toy floating" style="top:70%; left:60%;" />

<!-- Welcome Popup -->
<div class="popup" id="welcomePopup">
  <h2>Welcome!</h2>
  <p>We’re thrilled you’re here to celebrate our baby girl!</p>
  <button class="close-btn" onclick="closePopup('welcomePopup')">Close</button>
</div>

<!-- RSVP Popup -->
<div class="popup" id="rsvpPopup">
  <h2>RSVP</h2>
  <form>
    <input type="text" placeholder="Your Name" required>
    <input type="email" placeholder="Email Address" required>
    <select required>
      <option value="">Will you attend?</option>
      <option value="yes">Yes</option>
      <option value="no">No</option>
    </select>
    <button class="btn" type="submit">Submit</button>
  </form>
  <button class="close-btn" onclick="closePopup('rsvpPopup')">Close</button>
</div>

<!-- Gift Registry Popup -->
<div class="popup" id="giftPopup">
  <h2>Gift Registry</h2>
  <p>Click below to see our registry and send a gift!</p>
  <a href="#" target="_blank" class="btn">View Gifts</a>
  <button class="close-btn" onclick="closePopup('giftPopup')">Close</button>
</div>

<!-- Music Button -->
<button id="music-btn" onclick="toggleMusic()">🔊 Music</button>
<audio id="baby-music" autoplay loop>
  <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
  Your browser does not support the audio element.
</audio>

<script>
// Show Welcome Popup on Load
window.onload = () => { openPopup('welcomePopup'); };

// Popup Functions
function openPopup(id) { document.getElementById(id).style.display = 'block'; }
function closePopup(id) { document.getElementById(id).style.display = 'none'; }

// Music Toggle
const music = document.getElementById('baby-music');
let playing = true;
function toggleMusic() {
  if(playing){ music.pause(); playing=false; }
  else { music.play(); playing=true; }
}
</script>

</body>
</html>
