<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Bishnoi Food Court</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">

  <style>
/* Floating buttons style */
.floating {
  position: fixed;
  bottom: 20px;
  right: 20px;
  display:flex;
  flex-direction:column;
  gap:10px;
  z-index:999;
}
.floating a {
  text-decoration:none;
  padding:14px;
  color:#fff;
  font-weight:bold;
  border-radius:50px;
  display:inline-block;
}
.call { background: #28a745; }
.wa   { background: #25D366; }

/* Order button style */
.order-btn {
  display:block;
  width:100%;
  padding:12px;
  background:#25D366;
  color:#fff;
  border:none;
  border-radius:8px;
  font-size:16px;
  margin-top:10px;
}
</style>

    body{
      margin:0;
      font-family: Arial, sans-serif;
      background:#fff8f0;
    }
    header{
      background:#ff9800;
      color:#fff;
      padding:15px;
      text-align:center;
    }
    .section{
      padding:15px;
    }
    h2{
      border-bottom:2px solid #ff9800;
      padding-bottom:5px;
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
      font-size:18px;
      background:#25D366;
      color:#fff;
      border:none;
      border-radius:6px;
      margin-top:10px;
    }

    /* floating buttons */
    .float{
      position:fixed;
      bottom:20px;
      right:20px;
      display:flex;
      flex-direction:column;
      gap:10px;
    }
    .float a{
      text-decoration:none;
      padding:14px;
      color:#fff;
      font-weight:bold;
      border-radius:50px;
      text-align:center;
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

<div class="section">
  <h2>Menu</h2>

  <label class="item">
    <span><input type="checkbox" value="Cheese Burger"> Cheese Burger</span>
    <span>₹178</span>
  </label>

  <label class="item">
    <span><input type="checkbox" value="Paneer Pizza"> Paneer Pizza</span>
    <span>₹329</span>
  </label>

  <label class="item">
    <span><input type="checkbox" value="Plain Maggi"> Plain Maggi</span>
    <span>₹149</span>
  </label>

  <label class="item">
    <span><input type="checkbox" value="Veg Momos"> Veg Momos</span>
    <span>₹160</span>
  </label>

  <button onclick="orderWhatsApp()">Order on WhatsApp</button>
</div>

<!-- Floating buttons -->
<div class="float">
  <a href="tel:+918529928029" class="call">📞 Call</a>
  <a href="https://wa.me/918529928029" class="wa">💬 WhatsApp</a>
</div>

<script>
/* Auto welcome voice */
let welcomed = false;
function welcomeVoice(){
  if(welcomed) return;
  welcomed = true;
  let msg = new SpeechSynthesisUtterance(
    "Welcome to Bishnoi Food Court. Please select your order."
  );
  msg.lang = "en-IN";
  speechSynthesis.speak(msg);
}
document.addEventListener("click", welcomeVoice, {once:true});
document.addEventListener("scroll", welcomeVoice, {once:true});

/* WhatsApp order */
function orderWhatsApp(){
  let items = [];
  document.querySelectorAll('input[type=checkbox]:checked')
    .forEach(i => items.push(i.value));

  if(items.length === 0){
    alert("Please select items");
    return;
  }

  let text = "Hello Bishnoi Food Court, I want to order:%0A- "
            + items.join("%0A- ");

  window.open(
    "https://wa.me/918529928029?text=" + text,
    "_blank"
  );
}
</script>

</body>
</html>

