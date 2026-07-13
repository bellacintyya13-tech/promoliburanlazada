<!DOCTYPE html>
<html lang="id">
<head>

<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>Cyber Neon Tetris</title>

<style>

*{
box-sizing:border-box;
font-family:Arial,sans-serif;
}

body{

margin:0;
height:100vh;

display:flex;
justify-content:center;
align-items:center;

overflow:hidden;

background:
linear-gradient(#020617,#000);

color:white;

}


body:before{

content:"";

position:absolute;
inset:0;

background:
linear-gradient(
120deg,
rgba(0,255,255,.2),
rgba(255,0,255,.2)
);

animation:city 6s infinite alternate;

}


@keyframes city{

from{
filter:hue-rotate(0deg);
}

to{
filter:hue-rotate(90deg);
}

}


.game{

position:relative;
z-index:2;

display:flex;

gap:20px;

}


canvas{

background:#020617;

border:3px solid cyan;

box-shadow:

0 0 20px cyan,
0 0 40px magenta;

}


.panel{

width:200px;

}


.box{

background:#050b1c;

border:2px solid magenta;

padding:10px;

margin-bottom:12px;

text-align:center;

}


button{

width:100%;

padding:12px;

margin-top:8px;

background:#00ffff;

border:none;

font-weight:bold;

cursor:pointer;

}



#musicBtn{

position:fixed;

top:20px;

right:20px;

width:160px;

z-index:10;

}



@media(max-width:700px){

.game{

transform:scale(.75);

}

.panel{

display:none;

}

}

</style>

</head>


<body>


<button id="musicBtn">
🎵 MUSIC MAHJONG
</button>


<audio id="mahjongMusic" loop>

<source src="mahjong-aways.mp3" type="audio/mpeg">

</audio>



<div class="game">


<canvas id="board" width="300" height="600"></canvas>


<div class="panel">


<h1>
CYBER<br>
TETRIS
</h1>



<div class="box">

SCORE

<h2 id="score">
0
</h2>

</div>


<div class="box">

HIGH SCORE

<h2 id="high">
0
</h2>

</div>


<button onclick="rotate()">
🔄 ROTATE
</button>


<button onclick="hardDrop()">
⚡ HARD DROP
</button>


<button onclick="holdPiece()">
📦 HOLD
</button>


</div>


</div>
