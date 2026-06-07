<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>DailyFlow</title>

<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css" />
<script src="https://cdnjs.cloudflare.com/ajax/libs/Chart.js/4.4.1/chart.umd.js"></script>

<style>
*{
margin:0;
padding:0;
box-sizing:border-box;
font-family:system-ui;
}

body{
background:#0f172a;
color:white;
padding:20px;
}

.app{
max-width:900px;
margin:auto;
}

h1{
font-size:32px;
margin-bottom:20px;
font-weight:700;
}

.cards{
display:grid;
grid-template-columns:repeat(auto-fit,minmax(180px,1fr));
gap:15px;
margin-bottom:20px;
}

.card{
background:#1e293b;
padding:20px;
border-radius:18px;
}

.card h3{
font-size:14px;
color:#94a3b8;
margin-bottom:8px;
}

.card p{
font-size:28px;
font-weight:700;
}

.form{
background:#1e293b;
padding:20px;
border-radius:18px;
margin-bottom:20px;
}

.form h2{
margin-bottom:15px;
}

.inputs{
display:grid;
grid-template-columns:1fr 1fr 1fr auto;
gap:10px;
}

input,select{
height:45px;
border:none;
border-radius:12px;
padding:0 15px;
background:#334155;
color:white;
font-size:15px;
}

button{
height:45px;
border:none;
padding:0 20px;
border-radius:12px;
background:#3b82f6;
color:white;
cursor:pointer;
font-weight:600;
}

button:hover{
opacity:.9;
}

.expenses{
background:#1e293b;
padding:20px;
border-radius:18px;
}

.expense{
display:flex;
justify-content:space-between;
align-items:center;
padding:14px;
background:#334155;
border-radius:12px;
margin-bottom:10px;
}

.left{
display:flex;
gap:12px;
align-items:center;
}

.dot{
width:12px;
height:12px;
border-radius:50%;
}

.amount{
font-weight:700;
font-size:18px;
}

.delete{
background:#ef4444;
padding:8px 14px;
height:auto;
}

canvas{
margin-top:20px;
background:#1e293b;
padding:20px;
border-radius:18px;
}

@media(max-width:700px){

.inputs{
grid-template-columns:1fr;
}

}
</style>
</head>

<body>

<div class="app">

<h1>💸 DailyFlow</h1>

<div class="cards">

<div class="card">
<h3>Gastos Hoy</h3>
<p id="today">$0</p>
</div>

<div class="card">
<h3>Total Mes</h3>
<p id="month">$0</p>
</div>

<div class="card">
<h3>Cantidad</h3>
<p id="count">0</p>
</div>

</div>

<div class="form">

<h2>Agregar gasto</h2>

<div class="inputs">

<input type="number" id="amount" placeholder="Monto">

<select id="category">
<option value="Comida">🍔 Comida</option>
<option value="Transporte">🚌 Transporte</option>
<option value="Ropa">👕 Ropa</option>
<option value="Café">☕ Café</option>
<option value="Gaming">🎮 Gaming</option>
<option value="Otros">📦 Otros</option>
</select>

<input type="text" id="description" placeholder="Descripción">

<button onclick="addExpense()">
Agregar
</button>

</div>

</div>

<div class="expenses">

<h2 style="margin-bottom:15px;">Tus gastos</h2>

<div id="list"></div>

</div>

<canvas id="chart"></canvas>

</div>

<script>

const colors = {
Comida:"#ef4444",
Transporte:"#3b82f6",
Ropa:"#8b5cf6",
Café:"#f59e0b",
Gaming:"#22c55e",
Otros:"#94a3b8"
}

let expenses = JSON.parse(localStorage.getItem("dailyflow")) || []

function save(){
localStorage.setItem("dailyflow",JSON.stringify(expenses))
}

function format(n){
return "$" + n.toLocaleString("es-AR")
}

function today(){
return new Date().toISOString().slice(0,10)
}

function addExpense(){

const amount = Number(document.getElementById("amount").value)

const category = document.getElementById("category").value

const description = document.getElementById("description").value || category

if(!amount) return

expenses.push({
id:Date.now(),
amount,
category,
description,
date:today()
})

save()

document.getElementById("amount").value=""
document.getElementById("description").value=""

render()

}

function deleteExpense(id){

expenses = expenses.filter(e=>e.id!==id)

save()

render()

}

function renderCards(){

const todayTotal = expenses
.filter(e=>e.date===today())
.reduce((a,b)=>a+b.amount,0)

const month = today().slice(0,7)

const monthTotal = expenses
.filter(e=>e.date.startsWith(month))
.reduce((a,b)=>a+b.amount,0)

document.getElementById("today").innerText = format(todayTotal)

document.getElementById("month").innerText = format(monthTotal)

document.getElementById("count").innerText = expenses.length

}

function renderExpenses(){

const list = document.getElementById("list")

if(expenses.length===0){

list.innerHTML = `
<p style="color:#94a3b8;">
No hay gastos todavía
</p>
`

return

}

list.innerHTML = expenses.reverse().map(e=>`

<div class="expense">

<div class="left">

<div class="dot" style="background:${colors[e.category]}"></div>

<div>

<div>${e.description}</div>

<small style="color:#94a3b8;">
${e.category}
</small>

</div>

</div>

<div style="display:flex;align-items:center;gap:10px;">

<div class="amount">
${format(e.amount)}
</div>

<button class="delete" onclick="deleteExpense(${e.id})">
X
</button>

</div>

</div>

`).join("")

}

let chart

function renderChart(){

const categories = {}

expenses.forEach(e=>{

if(!categories[e.category]){
categories[e.category]=0
}

categories[e.category]+=e.amount

})

const labels = Object.keys(categories)

const data = Object.values(categories)

if(chart){
chart.destroy()
}

chart = new Chart(document.getElementById("chart"),{

type:"doughnut",

data:{
labels,
datasets:[{
data,
backgroundColor:labels.map(l=>colors[l])
}]
},

options:{
plugins:{
legend:{
labels:{
color:"white"
}
}
}
}

})

}

function render(){

renderCards()

renderExpenses()

renderChart()

}

render()

</script>

</body>
</html>
