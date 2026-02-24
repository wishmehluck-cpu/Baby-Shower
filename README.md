<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Lilly Rose's Virtual Baby Shower</title>
<link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400&display=swap" rel="stylesheet">

<style>
body {
    margin: 0;
    font-family: 'Poppins', sans-serif;
    background: linear-gradient(to bottom, #fff6f9, #f0f8ff);
    color: #6b5b73;
    text-align: center;
}

header {
    padding: 60px 20px;
    background: radial-gradient(circle at top, #ffffff, #ffeef4);
}

h1 {
    font-family: 'Great Vibes', cursive;
    font-size: 60px;
    color: #d88ca4;
    margin-bottom: 10px;
}

.subtitle {
    font-size: 18px;
    letter-spacing: 2px;
    color: #8fa6c9;
}

.section {
    padding: 60px 20px;
}

h2 {
    font-family: 'Great Vibes', cursive;
    font-size: 40px;
    color: #d88ca4;
}

.cloud {
    background: white;
    margin: 30px auto;
    padding: 30px;
    width: 80%;
    max-width: 600px;
    border-radius: 50px;
    box-shadow: 0 10px 30px rgba(0,0,0,0.05);
}

button {
    background-color: #f8c8dc;
    border: none;
    padding: 12px 25px;
    border-radius: 25px;
    font-size: 16px;
    cursor: pointer;
    transition: 0.3s ease;
}

button:hover {
    background-color: #e6a8c5;
}

input, textarea {
    width: 80%;
    padding: 10px;
    margin: 10px 0;
    border-radius: 15px;
    border: 1px solid #f0d6e0;
}

footer {
    padding: 30px;
    font-size: 14px;
    color: #aaa;
}
</style>
</head>

<body>

<header>
    <h1>Lilly Rose</h1>
    <div class="subtitle">A Heavenly Blessing Is On The Way</div>
</header>

<div class="section">
    <h2>Welcome to Our Virtual Baby Shower</h2>
    <div class="cloud">
        Though we may not gather in person, your love surrounds our sweet baby girl.
        <br><br>
        Lilly Rose is already cherished beyond words, and we are so grateful you’re here to celebrate her.
    </div>
</div>

<div class="section">
    <h2>✨ Guess About Lilly ✨</h2>
    <div class="cloud">
        <p>When do you think Lilly Rose will arrive?</p>
        <input type="text" placeholder="Your guess">
        
        <p>How much will she weigh?</p>
        <input type="text" placeholder="Your guess">
        
        <p>Leave a loving piece of advice for mommy 🤍</p>
        <textarea rows="4" placeholder="Write your message..."></textarea>
        
        <br><br>
        <button onclick="alert('Thank you for your sweet wishes for Lilly Rose! 🤍')">
            Send Blessing
        </button>
    </div>
</div>

<div class="section">
    <h2>🌸 Leave a Blessing</h2>
    <div class="cloud">
        Write a prayer, wish, or message for Lilly Rose.
        <br><br>
        <textarea rows="4" placeholder="Your loving message..."></textarea>
        <br>
        <button onclick="alert('Your blessing has been sent with love 🤍')">
            Send Message
        </button>
    </div>
</div>

<div class="section">
    <h2>🎁 Registry</h2>
    <div class="cloud">
        Registry link coming soon 🤍
    </div>
</div>

<footer>
    Made with love for our precious angel, Lilly Rose 🕊️
</footer>

</body>
</html>
