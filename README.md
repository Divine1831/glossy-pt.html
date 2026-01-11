
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Glossy Pout – Premium Lip Gloss</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<style>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    color: #333;
    background: #fff;
}

header {
    background: #e621e6;
    color: #fff;
    padding: 2rem;
    text-align: center;
}

header .header-buttons {
    margin-top: 1rem;
}

nav {
    background: #222;
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
}

nav a {
    color: #fff;
    padding: 1rem 1.5rem;
    text-decoration: none;
}

nav a:hover { background: #f031c6; }

.container {
    max-width: 1100px;
    margin: auto;
    padding: 1.5rem;
}

.hero {
    background: linear-gradient(#ffe0f0, #fff);
    padding: 3rem;
    text-align: center;
    border-radius: 8px;
}

.products {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 1.5rem;
    margin-top: 1rem;
}

.product {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 1.5rem;
    text-align: center;
}

.product img {
    max-width: 100%;
    border-radius: 6px;
}

.price {
    color: #e72fde;
    font-weight: bold;
}

.qty {
    width: 60px;
    padding: 0.4rem;
    margin-bottom: 0.5rem;
}

.btn {
    background: #ff57d5;
    color: #fff;
    border: none;
    padding: 0.7rem 1.4rem;
    cursor: pointer;
    border-radius: 4px;
    transition: background 0.3s;
    margin: 0.2rem;
}

.btn:hover { background: #f308a5; }

footer {
    background: #222;
    color: #fff;
    text-align: center;
    padding: 1rem;
    margin-top: 3rem;
}

.login-modal {
    display: none;
    position: fixed;
    inset: 0;
    background: rgba(0,0,0,0.6);
    z-index: 1000;
}

.login-box {
    background: #fff;
    max-width: 350px;
    margin: 12% auto;
    padding: 2rem;
    border-radius: 8px;
    text-align: center;
    position: relative;
}

.login-box input {
    width: 100%;
    padding: 0.5rem;
    margin-bottom: 1rem;
}

.close {
    position: absolute;
    top: 10px;
    right: 15px;
    font-size: 22px;
    cursor: pointer;
}

#cart {
    position: fixed;
    top: 100px;
    right: 20px;
    background: #fff;
    border: 1px solid #ddd;
    padding: 1rem;
    border-radius: 8px;
    max-width: 250px;
    z-index: 500;
}

#cart h3 {
    margin-top: 0;
}

#newsletter input {
    padding: 0.5rem;
    width: 200px;
}

#reviews textarea {
    resize: none;
    margin-top: 0.5rem;
    margin-bottom: 0.5rem;
}

html {
    scroll-behavior: smooth;
}
</style>
</head>
<body>

<header>
    <h1>Glossy Pout</h1>
    <p>Premium Lip Gloss for Every Mood</p>
    <div class="header-buttons">
        <button class="btn" onclick="openLogin()">Customer Login</button>
        <button class="btn" onclick="logout()">Logout</button>
        <p id="loginStatus"></p>
    </div>
</header>

<nav>
    <a href="#home">Home</a>
    <a href="#products">Products</a>
    <a href="#reviews">Customer Reviews</a>
    <a href="#newsletter">Newsletter</a>
    <a href="#contact">Contact</a>
</nav>

<!-- LOGIN MODAL -->
<div id="loginModal" class="login-modal">
    <div class="login-box">
        <span class="close" onclick="closeLogin()">&times;</span>
        <h2>Customer Login</h2>
        <input type="text" id="customerName" placeholder="Your name">
        <input type="email" id="customerEmail" placeholder="Your email">
        <button class="btn" onclick="login()">Login</button>
    </div>
</div>

<!-- Cart -->
<div id="cart">
    <h3>Cart 🛒</h3>
    <ul id="cartItems"></ul>
    <p id="cartTotal">Total: ₦0</p>
    <button class="btn" onclick="emptyCart()">Empty Cart</button>
    <button class="btn" onclick="checkout()">Checkout</button>
</div>

<div class="container" id="home">

<section class="hero">
    <h2>Embrace Your Beauty. Shine On.</h2>
    <p>High-quality, hydrating, cruelty-free lip gloss.</p>
</section>

<section id="products">
<h2>Our Products</h2>
<div class="products">

<div class="product">
<img src="https://via.placeholder.com/250?text=Candy+Cloud" alt="Candy Cloud">
<h3>Candy Cloud</h3>
<p class="price">₦3,000</p>
<input type="number" min="1" value="1" class="qty">
<button class="btn" onclick="addToCart('Candy Cloud',3000,this)">Add to Cart</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/250?text=Choco+Royale" alt="Choco Royale">
<h3>Choco Royale</h3>
<p class="price">₦3,000</p>
<input type="number" min="1" value="1" class="qty">
<button class="btn" onclick="addToCart('Choco Royale',3000,this)">Add to Cart</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/250?text=Clear+Gloss" alt="Clear Gloss">
<h3>Clear Gloss</h3>
<p class="price">₦2,500</p>
<input type="number" min="1" value="1" class="qty">
<button class="btn" onclick="addToCart('Clear Gloss',2500,this)">Add to Cart</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/250?text=Nude+Gloss" alt="Nude Gloss">
<h3>Nude Gloss</h3>
<p class="price">₦3,000</p>
<input type="number" min="1" value="1" class="qty">
<button class="btn" onclick="addToCart('Nude Gloss',3000,this)">Add to Cart</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/250?text=Lip+Scrub" alt="Lip Scrub">
<h3>Lip Scrub</h3>
<p class="price">₦1,500</p>
<input type="number" min="1" value="1" class="qty">
<button class="btn" onclick="addToCart('Lip Scrub',1500,this)">Add to Cart</button>
</div>

<div class="product">
<img src="https://via.placeholder.com/250?text=Lip+Balm" alt="Lip Balm">
<h3>Lip Balm</h3>
<p class="price">₦1,500</p>
<input type="number" min="1" value="1" class="qty">
<button class="btn" onclick="addToCart('Lip Balm',1500,this)">Add to Cart</button>
</div>

</div>
</section>

<!-- Customer Review Section -->
<section id="reviews" style="margin-top:2rem;">
  <h2>Customer Reviews</h2>

  <div style="margin-bottom:1.5rem;">
    <input type="text" id="reviewName" placeholder="Your name" style="padding:0.5rem; width:200px;">
    <br><br>
    <textarea id="reviewText" placeholder="Your review" style="padding:0.5rem; width:300px; height:80px;"></textarea>
    <br><br>
    <button class="btn" onclick="submitReview()">Submit Review</button>
  </div>

  <div id="reviewList" style="border-top:1px solid #ddd; padding-top:1rem;"></div>
</section>

<!-- Newsletter Section -->
<section id="newsletter" style="text-align:center; padding:2rem; background:#ffe0f0; border-radius:8px; margin-top:2rem;">
<h2>Subscribe to Our Newsletter</h2>
<input type="email" id="newsletterEmail" placeholder="Your email">
<button class="btn" onclick="subscribeNewsletter()">Subscribe</button>
<p id="newsletterMsg"></p>
</section>

<section id="contact">
<h2>Contact Us</h2>
<p>Email: okohchristabel06@gmail.com</p>
<p>Phone: +234 811 087 8047</p>
</section>

</div>

<footer>
&copy; 2026 Glossy Pout. All rights reserved.
</footer>

<script>
let loggedIn = false;
let customer = "";
let cart = [];

// Persistent login
window.onload = function() {
    if(localStorage.getItem("customer")) {
        loggedIn = true;
        customer = localStorage.getItem("customer");
        document.getElementById("loginStatus").innerText = "Logged in as " + customer;
    }
}

function openLogin() { document.getElementById("loginModal").style.display = "block"; }
function closeLogin() { document.getElementById("loginModal").style.display = "none"; }

function login() {
    let name = document.getElementById("customerName").value;
    let email = document.getElementById("customerEmail").value;

    if(name && email){
        loggedIn = true;
        customer = name;
        localStorage.setItem("customer", customer);
        document.getElementById("loginStatus").innerText = "Logged in as " + customer;
        closeLogin();
        alert("Welcome " + customer + " 💄");
    } else {
        alert("Please fill all fields");
    }
}

function logout() {
    loggedIn = false;
    customer = "";
    localStorage.removeItem("customer");
    document.getElementById("loginStatus").innerText = "";
    alert("You have logged out 😘");
}

function addToCart(product, price, btn) {
    if(!loggedIn){
        alert("Please login to order");
        openLogin();
        return;
    }

    let qty = parseInt(btn.previousElementSibling.value);
    if(qty < 1){
        alert("Quantity must be at least 1");
        return;
    }

    cart.push({ product, price, qty });
    updateCart();
}

function updateCart() {
    let cartItems = document.getElementById("cartItems");
    let cartTotal = document.getElementById("cartTotal");
    cartItems.innerHTML = "";
    let total = 0;

    cart.forEach(item => {
        let li = document.createElement("li");
        li.textContent = `${item.product} x ${item.qty} = ₦${item.price * item.qty}`;
        cartItems.appendChild(li);
        total += item.price * item.qty;
    });

    cartTotal.textContent = `Total: ₦${total}`;
}

// Empty Cart
function emptyCart() {
    if(cart.length === 0){
        alert("Cart is already empty!");
        return;
    }
    if(confirm("Are you sure you want to empty your cart?")) {
        cart = [];
        updateCart();
    }
}

// Bank Transfer Checkout with Receipt Upload
function checkout() {
    if(cart.length === 0){
        alert("Your cart is empty! Add products to checkout.");
        return;
    }

    let total = cart.reduce((sum, item) => sum + item.price * item.qty, 0);

    // Show bank transfer instructions
    alert(
        `Please make payment to the following account:\n\n` +
        `Bank: PalmPay\n` +
        `Account Name: Okoh Christabel\n` +
        `Account Number: 8161478722\n\n` +
        `After payment, upload a picture of your payment receipt to verify.`
    );

    // Receipt Upload Modal
    let receiptDiv = document.createElement("div");
    receiptDiv.style.position = "fixed";
    receiptDiv.style.top = "0";
    receiptDiv.style.left = "0";
    receiptDiv.style.width = "100%";
    receiptDiv.style.height = "100%";
    receiptDiv.style.background = "rgba(0,0,0,0.6)";
    receiptDiv.style.zIndex = "2000";
    receiptDiv.style.display = "flex";
    receiptDiv.style.justifyContent = "center";
    receiptDiv.style.alignItems = "center";

    receiptDiv.innerHTML = `
        <div style="background:#fff; padding:2rem; border-radius:8px; text-align:center; max-width:400px;">
            <h3>Upload Payment Receipt</h3>
            <input type="file" id="receiptFile" accept="image/*"><br><br>
            <button class="btn" id="verifyBtn">Verify Payment</button>
            <button class="btn" id="cancelBtn">Cancel</button>
        </div>
    `;

    document.body.appendChild(receiptDiv);

    document.getElementById("verifyBtn").onclick = function(){
        let fileInput = document.getElementById("receiptFile");
        if(fileInput.files.length === 0){
            alert("❌ Please select a receipt image to verify payment.");
            return;
        }
        alert(
            `✅ Payment Verified!\n\n` +
            `Customer: ${customer}\n` +
            `Total Paid: ₦${total}\n` +
            `Thank you for shopping at Glossy Pout!`
        );
        cart = [];
        updateCart();
        document.body.removeChild(receiptDiv);
    }

    document.getElementById("cancelBtn").onclick = function(){
        document.body.removeChild(receiptDiv);
    }
}

// Newsletter
function subscribeNewsletter() {
    let email = document.getElementById("newsletterEmail").value;
    if(email) {
        document.getElementById("newsletterMsg").innerText = "Subscribed successfully! 💌";
        document.getElementById("newsletterEmail").value = "";
    } else {
        alert("Please enter your email");
    }
}

// Customer Reviews
function submitReview() {
    let name = document.getElementById("reviewName").value;
    let text = document.getElementById("reviewText").value;

    if(name && text){
        let reviewList = document.getElementById("reviewList");
        let reviewDiv = document.createElement("div");
        reviewDiv.style.borderBottom = "1px solid #ddd";
        reviewDiv.style.marginBottom = "0.5rem";
        reviewDiv.style.paddingBottom = "0.5rem";
        reviewDiv.innerHTML = `<strong>${name}:</strong> <p>${text}</p>`;
        reviewList.prepend(reviewDiv);

        document.getElementById("reviewName").value = "";
        document.getElementById("reviewText").value = "";
    } else {
        alert("Please enter your name and review.");
    }
}
</script>

</body>
</html>
