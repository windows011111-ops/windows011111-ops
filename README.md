<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Simple Shop</title>
<style>
body {
  font-family: Arial, sans-serif;
  margin: 0;
  background: #f5f5f5;
}
header {
  background: #111;
  color: white;
  padding: 15px;
  text-align: center;
}
.container {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 15px;
  padding: 20px;
}
.card {
  background: white;
  padding: 15px;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
}
.card button {
  margin-top: 10px;
  padding: 8px;
  width: 100%;
  border: none;
  background: #28a745;
  color: white;
  cursor: pointer;
  border-radius: 5px;
}
.cart {
  position: fixed;
  right: 0;
  top: 0;
  width: 250px;
  height: 100%;
  background: white;
  box-shadow: -2px 0 5px rgba(0,0,0,0.2);
  padding: 10px;
  overflow-y: auto;
}
.cart h3 {
  text-align: center;
}
</style>
</head>
<body>

<header>
  <h1>Simple Shopping Website</h1>
</header>

<div class="container" id="products">
  <div class="card">
    <h3>Product 1</h3>
    <p>₹100</p>
    <button onclick="addToCart('Product 1', 100)">Add to Cart</button>
  </div>

  <div class="card">
    <h3>Product 2</h3>
    <p>₹200</p>
    <button onclick="addToCart('Product 2', 200)">Add to Cart</button>
  </div>

  <div class="card">
    <h3>Product 3</h3>
    <p>₹300</p>
    <button onclick="addToCart('Product 3', 300)">Add to Cart</button>
  </div>
</div>

<div class="cart">
  <h3>Cart</h3>
  <ul id="cartItems"></ul>
  <h4>Total: ₹<span id="total">0</span></h4>
</div>

<script>
let total = 0;

function addToCart(name, price) {
  const list = document.getElementById('cartItems');
  const item = document.createElement('li');
  item.textContent = name + ' - ₹' + price;
  list.appendChild(item);

  total += price;
  document.getElementById('total').textContent = total;
}
</script>

</body>
</html>
