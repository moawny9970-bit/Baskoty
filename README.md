<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<title>For Shahd 🤍</title>

<style>
body {
    margin: 0;
    font-family: 'Tahoma', sans-serif;
    background: linear-gradient(135deg,#2a003f,#5b0f73,#8e2de2);
    color: white;
    text-align: center;
    overflow-x: hidden;
}

.lock-screen {
    position: fixed;
    width: 100%;
    height: 100%;
    background: #1a0026;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
}

input {
    padding: 12px;
    border-radius: 10px;
    border: none;
    font-size: 18px;
    text-align: center;
}

button {
    margin-top: 10px;
    padding: 10px 20px;
    border: none;
    border-radius: 10px;
    background: #8e2de2;
    color: white;
    font-size: 18px;
}

.content {
    display: none;
    padding: 20px;
}

.date {
    font-size: 22px;
    margin-top: 20px;
    opacity: 0.9;
}

.message {
    font-size: 20px;
    margin: 30px auto;
    width: 90%;
    max-width: 600px;
    line-height: 1.8;
    border-right: 3px solid white;
    white-space: pre-line;
    overflow: hidden;
}

.gallery img {
    width: 90%;
    max-width: 350px;
    margin: 15px 0;
    border-radius: 20px;
    box-shadow: 0 0 20px rgba(255,255,255,0.4);
}

.heart {
    position: fixed;
    top: -10px;
    color: pink;
    font-size: 20px;
    animation: fall linear infinite;
}

@keyframes fall {
    to {
        transform: translateY(100vh);
    }
}
</style>

</head>

<body>

<div class="lock-screen" id="lock">
<h2>Enter Password 🔒</h2>

<input type="password" id="password">

<button onclick="checkPassword()">Open</button>

</div>

<div class="content" id="content">

<div class="date">
2023/10/30 🤍
</div>

<div class="message" id="text"></div>

<div class="gallery">

<img src="IMG-20260407-WA0061.jpg">
<img src="IMG-20260407-WA0060.jpg">
<img src="IMG-20260407-WA0026.jpg">
<img src="IMG-20260407-WA0022.jpg">
<img src="IMG-20260407-WA0017.jpg">
<img src="IMG-20260407-WA0013.jpg">
<img src="IMG-20260407-WA0012.jpg">
<img src="IMG-20260407-WA0010.jpg">
<img src="IMG-20260407-WA0006.jpg">
<img src="IMG-20260407-WA0000.jpg">

</div>

<audio autoplay loop>
<source src="song.mp3" type="audio/mpeg">
</audio>

</div>

<script>

function checkPassword() {
    var pass = document.getElementById("password").value;

    if(pass === "29/11/2008") {
        document.getElementById("lock").style.display = "none";
        document.getElementById("content").style.display = "block";
        startTyping();
        startHearts();
    } else {
        alert("Wrong Password!");
    }
}

var messageText = `شهد… 🤍

عارفة إيه أكتر حاجة فرحت قلبي بجد؟
إننا رجعنا لبعض تاني… وكأن الدنيا إدّتني فرصة جديدة علشان أعيش إحساس جميل كنت مفتقده جدًا.

من يوم ما رجعتي، وأنا حاسس إن في حاجة جوايا رجعت تنور من تاني…
رجعت الضحكة اللي بتظهر لما بشوف اسمك،
ورجع الإحساس اللي بيخليني أحس إن في حد في حياتي مهم وغالي.

إنتي بجد مش شخص عادي بالنسبة لي…
إنتي فرحة دخلت حياتي وخلتها أحلى،
ووجودك جنبي بيفرق معايا فرق كبير بجد.

أنا مبسوط إننا رجعنا،
ومبسوط أكتر إن إحساسنا بقى أقوى من الأول،
وكأن كل اللي فات خلانا نفهم قيمة بعض أكتر ونتمسك ببعض أكتر.

بجد يا شهد…
أنا مش عاوز أشوف يوم تبعدي فيه عني تاني،
ولا عاوز إحساس البعد يتكرر،
لأن وجودك في حياتي بقى حاجة جميلة أنا بتمسك بيها من قلبي.

كل صورة هنا ليها ذكرى…
وكل ذكرى فيها لحظة حلوة بينا،
وأنا نفسي نعيش لحظات أحلى بكتير من اللي فات.

أنا مبسوط إنك رجعتي لحياتي…
ومبسوط أكتر إنك لسه معايا 🤍`;

var i = 0;

function startTyping() {

    function typing() {
        if (i < messageText.length) {
            document.getElementById("text").innerHTML += messageText.charAt(i);
            i++;
            setTimeout(typing, 40);
        }
    }

    typing();
}

function startHearts() {

    setInterval(() => {

        var heart = document.createElement("div");
        heart.classList.add("heart");
        heart.innerHTML = "🤍";

        heart.style.left = Math.random() * 100 + "vw";
        heart.style.animationDuration = (Math.random() * 3 + 3) + "s";

        document.body.appendChild(heart);

        setTimeout(() => {
            heart.remove();
        }, 5000);

    }, 300);
}

</script>

</body>
</html>
