<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<title>🚕 เช็คราคาเรียกรถ</title>

<style>
body{
font-family:sans-serif;
background:#f5f5f5;
padding:20px;
}

.box{
background:white;
padding:20px;
border-radius:10px;
max-width:400px;
margin:auto;
box-shadow:0 0 10px rgba(0,0,0,0.1);
}

input,button{
width:100%;
padding:12px;
margin-top:10px;
border-radius:8px;
border:1px solid #ddd;
font-size:16px;
}

button{
background:#0d6efd;
color:white;
border:none;
}

.result{
margin-top:15px;
padding:10px;
background:#eef7ff;
border-radius:8px;
}

.call{
background:#28a745;
}

.line{
background:#06c755;
}

.wa{
background:#25d366;
}
</style>

</head>

<body>

<div class="box">

<h2>🚕 เช็คราคาเรียกรถ</h2>

<input id="name" placeholder="ชื่อผู้จอง">

<input id="pickup" placeholder="จุดรับ (เช่น บ้าน / ตำแหน่ง)">
<input id="drop" placeholder="จุดส่ง">

<button onclick="calc()">คำนวณราคา</button>

<div class="result" id="result"></div>

<button class="call" onclick="call()">📞 โทรคนขับ</button>

<button class="line" onclick="sendLine()">ส่งจองผ่าน LINE</button>

<button class="wa" onclick="sendWA()">ส่งจองผ่าน WhatsApp</button>

</div>

<script>

let price=0
let distance=0

function calc(){

distance=(Math.random()*10).toFixed(2)

price=Math.round(distance*10)

document.getElementById("result").innerHTML=
"ระยะทางประมาณ: "+distance+" กม.<br>"+
"ราคาโดยประมาณ: "+price+" บาท"

}

function call(){
window.location.href="tel:0973479694"
}

function sendLine(){

let name=document.getElementById("name").value
let pickup=document.getElementById("pickup").value
let drop=document.getElementById("drop").value

let text="จองรถ\nชื่อ:"+name+"\nรับ:"+pickup+"\nส่ง:"+drop+"\nราคา:"+price+" บาท"

window.open("https://line.me/R/ti/p/~sumet_b")
}
