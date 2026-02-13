<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>دعاء ❤️</title>

<style>
body{
margin:0;
font-family:Arial;
background:#111;
color:white;
text-align:center;
overflow:hidden;
}

.section{
display:none;
height:100vh;
display:flex;
flex-direction:column;
justify-content:center;
align-items:center;
padding:20px;
}

.active{
display:flex;
}

button{
padding:12px 25px;
font-size:18px;
border:none;
border-radius:30px;
background:#ff4b5c;
color:white;
cursor:pointer;
margin-top:20px;
}

#slider{
width:300px;
height:400px;
background-size:cover;
background-position:center;
border-radius:20px;
margin:20px 0;
transition:1s;
}

#counter{
margin-top:20px;
font-size:20px;
}
</style>
</head>
<body>

<audio id="music" loop>
<source src="song.mp3" type="audio/mpeg">
</audio>

<!-- الصفحة 1 -->
<div id="s1" class="section active">
<h1>إلى دعاء ❤️</h1>
<p>من 2021… وانتي أجمل حاجة في حياتي.</p>
<button onclick="start()">ابدأي الحكاية</button>
</div>

<!-- الصفحة 2 -->
<div id="s2" class="section">
<h1>ذكرياتنا</h1>
<div id="slider"></div>
<button onclick="next('s3')">كمّلي</button>
</div>

<!-- الصفحة 3 -->
<div id="s3" class="section">
<h1>رسالة ليكي</h1>
<p>
يا دعاء…<br>
يمكن الدنيا كلها تناديكي دعاء،<br>
بس أنا بس اللي ليا أقولك كوتي موتي بوتي ❤️
</p>
<button onclick="final()">آخر حاجة</button>
</div>

<!-- الصفحة 4 -->
<div id="s4" class="section">
<h1>كوتي موتي بوتي للأبد ♾️</h1>
<div id="counter"></div>
</div>

<script>

/* تشغيل الموسيقى + انتقال */
function start(){
show('s2');

let music=document.getElementById("music");
music.volume=0.6;
music.play().catch(()=>{});
}

/* تنقل */
function next(id){
show(id);
}

function show(id){
document.querySelectorAll(".section").forEach(sec=>{
sec.classList.remove("active");
});
document.getElementById(id).classList.add("active");
}

/* سلايدر بسيط */
let images=["photo1.jpg","photo2.jpg","photo3.jpg"];
let index=0;
let slider=document.getElementById("slider");

if(slider){
slider.style.backgroundImage="url('photo1.jpg')";
setInterval(()=>{
index=(index+1)%images.length;
slider.style.backgroundImage="url('"+images[index]+"')";
},3000);
}

/* النهاية + عداد */
function final(){
show('s4');

let startDate=new Date("2021-01-01");
let today=new Date();
let days=Math.floor((today-startDate)/(1000*60*60*24));

document.getElementById("counter").innerHTML=
"بقالنا "+days+" يوم حب ❤️";
}

</script>

</body>
</html>
