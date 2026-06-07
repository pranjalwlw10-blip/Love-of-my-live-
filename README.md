# Love-of-my-life-
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For My Love ❤️</title>

<style>
body{
    margin:0;
    overflow:hidden;
    font-family:Arial,sans-serif;
    background:linear-gradient(180deg,#ffb6d9,#ffdff0);
}

#counter{
    position:fixed;
    top:15px;
    left:15px;
    background:white;
    padding:10px 15px;
    border-radius:20px;
    font-weight:bold;
    z-index:100;
}

#title{
    position:fixed;
    top:15px;
    width:100%;
    text-align:center;
    color:white;
    font-size:28px;
    font-weight:bold;
    text-shadow:1px 1px 5px rgba(0,0,0,0.2);
}

.heart{
    position:absolute;
    font-size:42px;
    cursor:pointer;
    animation:float 8s linear forwards;
    user-select:none;
}

@keyframes float{
    from{
        transform:translateY(100vh);
    }
    to{
        transform:translateY(-120px);
    }
}

#messageBox{
    position:fixed;
    top:50%;
    left:50%;
    transform:translate(-50%,-50%);
    background:white;
    width:300px;
    padding:20px;
    border-radius:20px;
    text-align:center;
    display:none;
    z-index:200;
    box-shadow:0 0 20px rgba(0,0,0,0.2);
}

button{
    padding:10px 20px;
    border:none;
    border-radius:15px;
    cursor:pointer;
}

#letterScreen{
    position:fixed;
    inset:0;
    background:rgba(255,240,248,0.98);
    display:none;
    justify-content:center;
    align-items:center;
    z-index:500;
}

#letter{
    max-width:600px;
    background:white;
    padding:30px;
    border-radius:25px;
    text-align:center;
    margin:20px;
    box-shadow:0 0 25px rgba(0,0,0,0.2);
}

.sparkle{
    position:absolute;
    font-size:20px;
    animation:spark 1s forwards;
    pointer-events:none;
}

@keyframes spark{
    from{
        opacity:1;
        transform:scale(1);
    }
    to{
        opacity:0;
        transform:scale(2);
    }
}
</style>
</head>

<body>

<div id="counter">❤️ Hearts Found: 0/15</div>

<div id="title">Happy 3 Months ❤️</div>

<div id="messageBox">
    <h2>💌</h2>
    <p id="msg"></p>
    <button onclick="closeBox()">Close</button>
</div>

<div id="letterScreen">
    <div id="letter">
        <h1>💖 Happy 3 Months 💖</h1>

        <p>
        Dear Love,
        </p>

        <p>
        Thank you for being part of my life.
        These past 3 months have given me so many memories,
        smiles, laughs and moments I'll always treasure.
        </p>

        <p>
        Every day with you feels special and I'm grateful
        for every conversation, every joke and every little
        moment we share.
        </p>

        <p>
        I hope this tiny game made you smile.
        </p>

        <p>
        ❤️ I love you ❤️
        </p>

        <p>
        — Yours 🌸
        </p>

        <button onclick="showSecret()">
            One More Secret 💖
        </button>

        <p id="secret"></p>
    </div>
</div>

<script>

const TOTAL_HEARTS = 15;

let collected = 0;

const messages = [
"You're my favorite notification ❤️",
"You make ordinary days special 💕",
"Thank you for these amazing 3 months 🌸",
"I still smile when I see your name 😭",
"Achievement Unlocked: Best Girlfriend 🏆",
"You deserve all the happiness 💖",
"You're my comfort person 🫂",
"Every memory with you is precious ✨",
"You mean so much to me ❤️",
"You make my world brighter 🌷",
"Sending you infinite hugs 💕",
"You're adorable and you know it 😌",
"Thank you for staying ❤️",
"You're my favorite person 🌸",
"I love youuu 💖"
];

function createHeart(){

    if(collected >= TOTAL_HEARTS) return;

    let heart = document.createElement("div");
    heart.className = "heart";
    heart.innerHTML = "❤️";

    heart.style.left = Math.random()*90 + "vw";

    heart.onclick = function(e){

        createSparkle(e.pageX,e.pageY);

        document.getElementById("msg").innerText =
        messages[collected];

        document.getElementById("messageBox").style.display="block";

        collected++;

        document.getElementById("counter").innerText =
        "❤️ Hearts Found: " + collected + "/" + TOTAL_HEARTS;

        heart.remove();

        if(collected === TOTAL_HEARTS){
            setTimeout(()=>{
                document.getElementById("letterScreen").style.display="flex";
            },1000);
        }
    };

    document.body.appendChild(heart);

    setTimeout(()=>{
        if(heart.parentNode){
            heart.remove();
        }
    },8000);
}

function createSparkle(x,y){
    let s=document.createElement("div");
    s.className="sparkle";
    s.innerHTML="✨";

    s.style.left=x+"px";
    s.style.top=y+"px";

    document.body.appendChild(s);

    setTimeout(()=>{
        s.remove();
    },1000);
}

function closeBox(){
    document.getElementById("messageBox").style.display="none";
}

function showSecret(){
    document.getElementById("secret").innerHTML =
    "❤️ No matter how many hearts were in this game, I'd still choose you every time. ❤️";
}

setInterval(createHeart,1000);

</script>

</body>
</html>
