# Index.html
My bakery
<!DOCTYPE html>
<html>
<head>
    <title>Delight Bakery</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

    <style>
        body {
            margin: 0;
            font-family: 'Segoe UI', sans-serif;
            background: #fffaf5;
        }

        header {
            background: linear-gradient(45deg, #ff7e5f, #feb47b);
            color: white;
            text-align: center;
            padding: 30px;
        }

        nav {
            background: #ff9a8b;
            text-align: center;
            padding: 12px;
        }

        nav a {
            color: white;
            margin: 15px;
            text-decoration: none;
            font-weight: bold;
        }

        .hero {
            text-align: center;
            padding: 40px;
        }

        .hero h1 {
            font-size: 40px;
        }

        section {
            padding: 30px;
        }

        .menu {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }

        .card {
            width: 250px;
            background: white;
            border-radius: 12px;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            text-align: center;
            padding: 15px;
        }

        .card img {
            width: 100%;
            border-radius: 10px;
        }

        button {
            background: #ff7e5f;
            color: white;
            border: none;
            padding: 10px;
            margin-top: 10px;
            border-radius: 5px;
            cursor: pointer;
        }

        #cart {
            max-width: 400px;
            margin: auto;
        }

        form {
            max-width: 400px;
            margin: auto;
        }

        input, textarea {
            width: 100%;
            padding: 10px;
            margin: 10px 0;
        }

        footer {
            background: #ff7e5f;
            color: white;
            text-align: center;
            padding: 15px;
        }
    </style>
</head>

<body>

<header>
    <h1>Delight Bakery 🍰</h1>
    <p>Fresh Cakes | Pastries | Online Orders</p>
</header>

<nav>
    <a href="#home">Home</a>
    <a href="#menu">Menu</a>
    <a href="#order">Order</a>
    <a href="#contact">Contact</a>
</nav>

<div class="hero" id="home">
    <h1>Welcome to Delight Bakery</h1>
    <p>Delicious handmade pastries delivered to your doorstep</p>
</div>

<section id="menu">
    <h2 style="text-align:center;">Our Menu</h2>

    <div class="menu">

        <div class="card">
            <img src="https://source.unsplash.com/300x200/?cake">
            <h3>Chocolate Cake</h3>
            <p>₹500</p>
            <button onclick="addToCart('Chocolate Cake')">Add</button>
        </div>

        <div class="card">
            <img src="https://source.unsplash.com/300x200/?pastry">
            <h3>Strawberry Pastry</h3>
            <p>₹90</p>
            <button onclick="addToCart('Strawberry Pastry')">Add</button>
        </div>

        <div class="card">
            <img src="https://source.unsplash.com/300x200/?cupcake">
            <h3>Cupcake</h3>
            <p>₹60</p>
            <button onclick="addToCart('Cupcake')">Add</button>
        </div>

    </div>
</section>

<section id="order">
    <h2 style="text-align:center;">Your Cart 🛒</h2>
    <ul id="cart"></ul>
    <button onclick="placeOrder()">Place Order</button>
</section>

<section id="contact">
    <h2 style="text-align:center;">Contact Us</h2>

    <form onsubmit="sendMsg(event)">
        <input type="text" placeholder="Your Name" required>
        <input type="email" placeholder="Your Email" required>
        <textarea placeholder="Your Message"></textarea>
        <button type="submit">Send</button>
    </form>
</section>

<footer>
    <p>📍 Panvel | 🕒 9 AM - 9 PM</p>
    <p>© 2026 Delight Bakery</p>
</footer>

<script>
let cart = [];

function addToCart(item){
    cart.push(item);
    displayCart();
}

function displayCart(){
    let list = document.getElementById("cart");
    list.innerHTML = "";
    cart.forEach(i => {
        let li = document.createElement("li");
        li.textContent = i;
        list.appendChild(li);
    });
}

function placeOrder(){
    if(cart.length === 0){
        alert("Cart is empty!");
    } else {
        alert("Order placed successfully!");
        cart = [];
        displayCart();
    }
}

function sendMsg(e){
    e.preventDefault();
    alert("Message sent!");
}
</script>

</body>
</html>
