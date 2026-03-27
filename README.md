<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Younes Parfumerie</title>

<style>
body {
    font-family: Arial;
    margin: 0;
    background: #f5f5f5;
    direction: rtl;
}

header {
    background: black;
    color: white;
    padding: 15px;
    text-align: center;
}

.products {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.product {
    background: white;
    margin: 15px;
    padding: 15px;
    width: 250px;
    border-radius: 10px;
    text-align: center;
    box-shadow: 0 0 10px rgba(0,0,0,0.1);
}

.product img {
    width: 100%;
}

button {
    margin: 5px;
    padding: 10px;
    border: none;
    cursor: pointer;
    border-radius: 5px;
}

.add {
    background: green;
    color: white;
}

.buy {
    background: black;
    color: white;
}

.cart {
    position: fixed;
    top: 10px;
    left: 10px;
    background: black;
    color: white;
    padding: 10px;
    border-radius: 10px;
}

</style>
</head>

<body>

<header>
<h1>Younes Parfumerie</h1>
<p>أفضل العطور بأفضل الأسعار</p>
</header>

<div class="cart">
🛒 السلة: <span id="count">0</span>
</div>

<section class="products">

<div class="product">
<img src="https://via.placeholder.com/250">
<h3>عطر Dior</h3>
<p>3000 دج</p>
<button class="add" onclick="addToCart('Dior',3000)">أضف للسلة</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/250">
<h3>عطر Chanel</h3>
<p>3500 دج</p>
<button class="add" onclick="addToCart('Chanel',3500)">أضف للسلة</button>
</div>

</section>

<div style="text-align:center; margin:20px;">
<button class="buy" onclick="sendOrder()">اطلب عبر واتساب</button>
</div>

<script>

let cart = [];

function addToCart(name, price){
    cart.push({name, price});
    document.getElementById("count").innerText = cart.length;
}

function sendOrder(){
    if(cart.length === 0){
        alert("السلة فارغة!");
        return;
    }

    let message = "طلب جديد:%0A";

    cart.forEach(item => {
        message += item.name + " - " + item.price + " دج%0A";
    });

    let phone = "213XXXXXXXXX"; // حط رقمك هنا

    window.open("https://wa.me/" + phone + "?text=" + message);
}

</script>

</body>
</html>
