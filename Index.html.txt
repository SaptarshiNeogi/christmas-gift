<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️🎄</title>

<style>
* { margin: 0; padding: 0; box-sizing: border-box; }
body {
    height: 100vh;
    background: radial-gradient(circle at top, #102542, #020b18);
    display: flex;
    justify-content: center;
    align-items: center;
    font-family: 'Poppins', sans-serif;
    overflow: hidden;
    color: white;
}

/* Snow */
.snow { position: fixed; top: -10px; background: white; border-radius: 50%; opacity: 0.8; animation: fall linear infinite; }
@keyframes fall { to { transform: translateY(110vh); } }

/* Center container */
.container { text-align: center; z-index: 5; }

/* Gift */
.gift { position: relative; width: 200px; height: 200px; cursor: pointer; }
.box { width: 100%; height: 100%; background: #c1121f; border-radius: 18px; }
.ribbon { position: absolute; width: 30px; height: 100%; background: gold; left: 50%; transform: translateX(-50%); }
.ribbon::after { content: ""; position: absolute; width: 100%; height: 30px; background: gold; top: 50%; transform: translateY(-50%); }
.lid {
    position: absolute; width: 100%; height: 45px;
    background: #9b111e; top: -45px; border-radius: 18px 18px 0 0;
    transform-origin: bottom; transition: transform 1s ease;
}
.gift.open .lid { transform: rotateX(120deg); }

/* Surprise reveal */
.surprise { display: none; margin-top: 30px; animation: appear 1.8s ease forwards; }
@keyframes appear { from { opacity: 0; transform: scale(0.9); } to { opacity: 1; transform: scale(1); } }

.surprise img {
    width: 260px;
    border-radius: 22px;
    box-shadow: 0 0 35px rgba(255,182,193,0.6);
}

.message {
    margin-top: 22px; font-size: 1.25rem; line-height: 1.8; color: #ffe6eb;
    animation: glowText 2s infinite alternate;
}
@keyframes glowText { from { text-shadow: 0 0 5px pink; } to { text-shadow: 0 0 15px hotpink; } }

.tap { margin-top: 15px; color: #ffb6c1; animation: blink 1.6s infinite; }
@keyframes blink { 50% { opacity: 0.4; } }
</style>
</head>

<body>

<div class="container">
    <div class="gift" onclick="openGift()">
        <div class="lid"></div>
        <div class="box"></div>
        <div class="ribbon"></div>
    </div>

    <div class="tap">Tap the gift 🎁</div>

    <div class="surprise" id="surprise">
        <img src="https://drive.google.com/uc?export=view&id=10c-1inF3SpOOPnzZ509ffJaj5MKL_S8Q" alt="My Forever ❤️">
        <div class="message">
            🎄 Merry Christmas 🎄<br><br>
            You are my Santa,<br>
            you gifted <b>yourself</b> to me —<br>
            the best gift I can ever receive ❤️✨<br><br>
            <b>I love you forever and infinity,<br>
            shonnnnahh babbbahh amr 🥺❤️</b>
        </div>
    </div>
</div>

<!-- 🎶 Background music -->
<audio id="music" loop>
    <source src="https://drive.google.com/uc?export=download&id=1FxZY-aZlcUJuCOX8LGSavFHjSu_OAwjF" type="audio/mpeg">
</audio>

<script>
function openGift() {
    document.querySelector(".gift").classList.add("open");
    document.querySelector(".tap").style.display = "none";

    setTimeout(() => {
        document.querySelector(".gift").style.display = "none";
        document.getElementById("surprise").style.display = "block";
        document.getElementById("music").play();
    }, 1000);
}

/* Create snow */
for (let i = 0; i < 45; i++) {
    let s = document.createElement("div");
    s.className = "snow";
    s.style.left = Math.random() * 100 + "vw";
    s.style.width = s.style.height = (4 + Math.random() * 6) + "px";
    s.style.animationDuration = (3 + Math.random() * 5) + "s";
    s.style.opacity = Math.random();
    document.body.appendChild(s);
}
</script>

</body>
</html>
