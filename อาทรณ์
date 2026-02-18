<!DOCTYPE html>
<html lang="th">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Portfolio - อาทรณ์ อุมา</title>

<link href="https://fonts.googleapis.com/css2?family=Kanit:wght@300;400;600;700&display=swap" rel="stylesheet">

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:'Kanit',sans-serif}
body{background:#0d0d0d;color:white}

nav{
position:fixed;top:0;width:100%;
background:#120000;border-bottom:1px solid #ff2e2e;
display:flex;justify-content:center;gap:40px;
padding:15px;z-index:1000;
}
nav a{color:white;text-decoration:none;font-weight:600}
nav a:hover{color:#ff2e2e}

header{
height:100vh;display:flex;flex-direction:column;
justify-content:center;align-items:center;text-align:center;
background:linear-gradient(135deg,#0d0d0d,#1a0000,#330000);
}
h1{font-size:60px;color:#ff2e2e}
section{padding:100px 20px}

.card{
background:#140000;border:1px solid #ff2e2e;
border-radius:20px;padding:30px;margin:30px auto;
max-width:1000px;
}
.title{font-size:30px;margin-bottom:20px;color:#ff3b3b}

.gallery{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(220px,1fr));
gap:20px;
}

.work{
background:#1b0000;border-radius:15px;padding:15px;
border:1px solid #ff2e2e;text-align:center;position:relative;
}

.work img{
width:100%;height:180px;object-fit:cover;
border-radius:10px;margin-bottom:10px;
}

.delete-btn{
background:#ff2e2e;color:white;border:none;
padding:6px 14px;margin-top:8px;border-radius:8px;
cursor:pointer;
}

input{
width:100%;padding:10px;margin-top:10px;
border-radius:10px;border:none;background:#2b0000;color:white;
}

button{
margin-top:10px;padding:10px 20px;border:none;
border-radius:10px;background:#ff2e2e;color:white;cursor:pointer;
}

.skills span{
display:inline-block;background:#ff2e2e;
padding:8px 14px;border-radius:999px;margin:5px;
}

footer{text-align:center;padding:40px;color:#aaa}
</style>
</head>

<body>

<nav>
<a href="#home">หน้าแรก</a>
<a href="#works">ผลงาน</a>
<a href="#about">เกี่ยวกับ</a>
<a href="#skills">ทักษะ</a>
</nav>

<header id="home">
<h1>PORTFOLIO</h1>
<h2>อาทรณ์ อุมา</h2>
</header>

<section id="works">
<div class="card">
<div class="title">ผลงานของฉัน</div>

<div class="gallery" id="gallery"></div>

<h3>➕ เพิ่มผลงาน</h3>
<input type="text" id="workTitle" placeholder="ชื่อผลงาน">
<input type="file" id="workImage">
<input type="text" id="workLink" placeholder="ลิ้งงาน">
<button onclick="addWork()">เพิ่มผลงาน</button>

</div>
</section>

<section id="about"> <div class="card"> <div class="title">เกี่ยวกับฉัน</div> <p> ชื่อ: อาทรณ์ อุมา<br> ชั้น: ม.4/3 เลขที่ 15<br> โรงเรียน: มัธยมนาคนาวาอุปภ์<br> ความสนใจ: ผู้หญิง </p> </div> </section>
<section id="skills"> <div class="card"> <div class="title">ทักษะ</div> <div class="skills"> <span>ออกแบบ</span> <span>ตัดต่อ</span> <span>เขียนโค้ด</span> <span>สร้างสรรค์</span> </div> </div> </section> <section id="contact"> <div class="card"> <div class="title">ติดต่อฉัน nbig2500@gmail.com</div>

<footer>
© 2026 Portfolio | อาทรณ์ อุมา
</footer>

<script>
// โหลดข้อมูลตอนเปิดเว็บ
window.onload=function(){
const data=JSON.parse(localStorage.getItem("works"))||[];
data.forEach(w=>createWork(w));
}

function addWork(){
const title=document.getElementById('workTitle').value;
const file=document.getElementById('workImage').files[0];
const link=document.getElementById('workLink').value;

if(!title||!file) return alert("ใส่ชื่อและรูป");

const reader=new FileReader();
reader.onload=function(e){

const workData={
title:title,
img:e.target.result,
link:link
};

createWork(workData);

// บันทึกลงเครื่อง
const old=JSON.parse(localStorage.getItem("works"))||[];
old.push(workData);
localStorage.setItem("works",JSON.stringify(old));

}

reader.readAsDataURL(file);
}

// สร้างการ์ด
function createWork(data){
const div=document.createElement("div");
div.className="work";

div.innerHTML=`
<img src="${data.img}">
<b>${data.title}</b><br>
<a href="${data.link}" target="_blank" style="color:#ff2e2e">เปิดลิ้ง</a><br>
<button class="delete-btn">ลบ</button>
`;

div.querySelector(".delete-btn").onclick=function(){
div.remove();
deleteFromStorage(data.img);
}

document.getElementById("gallery").appendChild(div);
}

// ลบจาก localStorage
function deleteFromStorage(img){
let data=JSON.parse(localStorage.getItem("works"))||[];
data=data.filter(w=>w.img!==img);
localStorage.setItem("works",JSON.stringify(data));
}
</script>

</body>
</html>
