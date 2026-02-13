<!DOCTYPE html>
<html lang="fr">
<head>
<meta charset="UTF-8">
<title>Tanya 💘</title>

<style>
body {
    margin: 0;
    overflow: hidden;
    background: linear-gradient(135deg, #ff758c, #ff7eb3);
    font-family: Arial, sans-serif;
    text-align: center;
    color: white;
}

h1 {
    margin-top: 100px;
    font-size: 3em;
}

.buttons {
    margin-top: 50px;
}

button {
    padding: 15px 30px;
    font-size: 20px;
    border: none;
    border-radius: 30px;
    cursor: pointer;
    transition: 0.3s;
}

#yes {
    background-color: #ff4d6d;
    color: white;
}

#no {
    background-color: white;
    color: #ff4d6d;
    position: absolute;
}

.heart {
    position: absolute;
    font-size: 20px;
    pointer-events: none;
    animation: fall linear infinite;
}

@keyframes fall {
    0% { transform: translateY(-10vh); }
    100% { transform: translateY(110vh); }
}

#secretMessage {
    position: fixed;
    bottom: 20px;
    width: 100%;
    font-size: 18px;
    opacity: 0;
    transition: opacity 2s;
}

/* Explosion animation */
.explosion {
    position: absolute;
    font-size: 25px;
    animation: explode 1s ease-out forwards;
    pointer-events: none;
}

@keyframes explode {
    0% { transform: scale(0); opacity: 1; }
    100% { transform: scale(3); opacity: 0; }
}
</style>
</head>

<body>

<h1>Tanya 💖<br>Will you be my Valentine?</h1>

<div class="buttons">
    <button id="yes">Oui 🥰</button>
    <button id="no">Non 😏</button>
</div>

<div id="secretMessage">
My Love ❤️ i just wanted to remind you how much you mean to me🥰. 
Everyday with you feels warmer, brighter🤩 and a little more magical✨.
<br><br>
Thank you for the laughs, the late nights🌚 and the quiet moments in between. 
No matter where life takes us, you are my favorite place to return to🌍.
<br><br>
I'm so grateful for you. Always....
<br><br>
❤️ I LOVE YOU SO MUCH ❤️
</div>

<audio id="bgMusic" autoplay loop>
    <source src="music.mp3" type="audio/mpeg">
</audio>

<script>
const noBtn = document.getElementById("no");
const yesBtn = document.getElementById("yes");

// Bouton NON qui fuit
noBtn.addEventListener("mouseover", () => {
    const x = Math.random() * (window.innerWidth - 100);
    const y = Math.random() * (window.innerHeight - 50);
    noBtn.style.left = x + "px";
    noBtn.style.top = y + "px";
});

// Quand elle clique sur OUI
yesBtn.addEventListener("click", () => {

    document.body.innerHTML = `
        <h1 style="margin-top:150px;">JE SAVAIS QUE TU ALLAIS DIRE OUI 😍💍</h1>
        <h2>Tanya, you just made me the happiest person alive ❤️</h2>
        <h3>Our Valentine’s story starts now ✨</h3>
    `;
    document.body.style.background = "#ff4d6d";

    // Lancer feu d'artifice
    setInterval(createExplosion, 200);
});

// Cœurs qui tombent
function createHeart() {
    const heart = document.createElement("div");
    heart.classList.add("heart");
    heart.innerHTML = "💖";
    heart.style.left = Math.random() * 100 + "vw";
    heart.style.animationDuration = (Math.random() * 3 + 2) + "s";
    document.body.appendChild(heart);

    setTimeout(() => {
        heart.remove();
    }, 5000);
}

setInterval(createHeart, 300);

// Explosion romantique
function createExplosion() {
    const explosion = document.createElement("div");
    explosion.classList.add("explosion");
    explosion.innerHTML = "💖";
    explosion.style.left = Math.random() * window.innerWidth + "px";
    explosion.style.top = Math.random() * window.innerHeight + "px";
    document.body.appendChild(explosion);

    setTimeout(() => {
        explosion.remove();
    }, 1000);
}

// Message secret après 5 secondes
setTimeout(() => {
    document.getElementById("secretMessage").style.opacity = 1;
}, 5000);

</script>

</body>
</html>
