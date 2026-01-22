<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Bishnoi Food Court</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body{
  margin:0;
  font-family:Arial, sans-serif;
  background:#fff7ed;
}
header{
  background:#ff9800;
  color:#fff;
  padding:15px;
  text-align:center;
}
.menu{
  padding:15px;
}
.menu h2{
  border-bottom:2px solid #ff9800;
}
.item{
  display:flex;
  justify-content:space-between;
  padding:8px 0;
  border-bottom:1px dashed #ccc;
}
button{
  width:100%;
  padding:12px;
  background:#25D366;
  color:#fff;
  font-size:18px;
  border:none;
  border-radius:6px;
  margin-top:15px;
}

/* Floating buttons */
.floating{
  position:fixed;
  bottom:20px;
  right:20px;
  display:flex;
  flex-direction:column;
  gap:10px;
}
.floating a{
  padding:14px;
  color:#fff;
  font-weight:bold;
  border-radius:50px;
  text-decoration:none;
}
.call{background:#28a745;}
.wa{background:#25D366;}
</style>
</head>

<body>

<header>
  <h1>Bishnoi Food Court</h1>
  <p>📞 +91 85299 28029 | 24×7 Open</p>
</header>

<div class="menu">
  <h2>Menu</h2>

  <label class="item">
    <span><input type="checkbox" value="Cheese Burger - ₹178"> Cheese Burger</span>
    <span>₹178</span>
  </label>

  <label class="item">
    <span><input type="checkbox" value="Paneer Pizza - ₹329"> Paneer Pizza</span>
    <span>₹329</span>
  </label>

  <label class="item">
    <span><input type="checkbox" value="Plain Maggi - ₹149"> Plain Maggi</span>
    <span>₹149</span>
  </label>

  <label class="item">
    <span><input type="checkbox" value="Veg Momos - ₹160"> Veg Momos</span>
    <span>₹160</span>
  </label>

  <button onclick="orderWA()">Order on WhatsApp</button>
</div>

<!-- Floating Call + WhatsApp -->
<div class="floating">
  <a href="tel:+918529928029" class="call">📞 Call</a>
  <a href="https://wa.me/918529928029" class="wa">💬 WhatsApp</a>
</div>

<script>
// 🔊 AUTO WELCOME VOICE (first tap only)
let welcomed=
