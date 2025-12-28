<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8">
  <title>Color Prediction App</title>

  <style>
    body{
      font-family: Arial;
      background:#0f172a;
      color:white;
      text-align:center;
      padding:20px;
    }

    .card{
      background:#020617;
      padding:20px;
      border-radius:14px;
      max-width:400px;
      margin:auto;
      box-shadow:0 0 18px rgba(255,255,255,.08);
    }

    .color-box{
      width:120px;
      height:120px;
      border-radius:12px;
      margin:15px auto;
      border:2px solid white;
    }

    button{
      padding:12px 18px;
      border-radius:10px;
      border:none;
      margin:6px;
      font-size:15px;
      cursor:pointer;
    }

    .green{background:#22c55e}
    .red{background:#ef4444}
    .blue{background:#3b82f6}
    .yellow{background:#eab308}

    .result{
      margin-top:12px;
      font-size:18px;
      font-weight:bold;
    }
  </style>
</head>

<body>

  <h2>🎨 Color Prediction Game</h2>

  <div class="रंग",>

    <p>नीचे दिए गए रंग का अनुमान लगाइए</p>

    <div id="colorBox" class="color-box"></div>

    <p>अपना Prediction चुनें 👇</p>

    <div>
      <button onclick="predict('red')" class="red">Red</button>
      <button onclick="predict('green')" class="green">Green</button>
      <button onclick="predict('blue')" class="blue">Blue</button>
      <button onclick="predict('yellow')" class="yellow">Yellow</button>
    </div>

    <p class="result" id="resultText"></p>
    <p>Round: <span id="round">0</span></p>

    <button onclick="newRound()">Next Round</button>

  </div>

<script>

let colors = ["red","green","blue","yellow"];
let generatedColor = "";
let round = 0;

function newRound(){
    round++;
    document.getElementById("round").innerText = round;

    generatedColor = colors[Math.floor(Math.random()*colors.length)];
    document.getElementById("colorBox").style.background = generatedColor;

    document.getElementById("resultText").innerText = "";
}

function predict(userColor){

    if(userColor === generatedColor){
        document.getElementById("resultText").innerText = "🎉 You Win!";
        document.getElementById("resultText").style.color = "#22c55e"
        document.getElementById("resultText").style.color = "#ef4444";
    }
}

newRound();

</script>

</body>
</html>
