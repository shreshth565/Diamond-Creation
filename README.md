<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Diamond Creation - Stationery Shop</title>
  <meta name="description" content="Shop colorful pastel stationery from Diamond Creation.">
  <link rel="icon" type="image/png" href="logo.png">
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #FFFBF0;
      color: #333;
    }

    /* Splash */
    #splash-screen {
      position: fixed;
      inset: 0;
      background: white;
      display: flex;
      justify-content: center;
      align-items: center;
      z-index: 9999;
    }
    .splash-logo {
      height: 120px;
      animation: fadeOut 2s ease-out forwards;
      animation-delay: 1.5s;
    }
    @keyframes fadeOut {
      to {
        opacity: 0;
        visibility: hidden;
      }
    }

    header {
      background: linear-gradient(135deg, #FFD6A5, #D7C4F0);
      padding: 1rem;
      text-align: center;
    }
    header img {
      height: 60px;
    }
    nav {
      background: #A0E7E5;
      padding: 1rem;
      display: flex;
      justify-content: center;
      gap: 2rem;
      flex-wrap: wrap;
    }
    nav a {
      text-decoration: none;
      color: #333;
      font-weight: bold;
    }

    section {
      padding: 2rem;
    }
    .hero {
      background: #B9FBC0;
      text-align: center;
    }
    .products {
      background: #FFCBDD;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1.5rem;
    }
    .product {
      background: white;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      text-align: center;
    }
    .product img {
      width: 100%;
      max-height: 150px;
      object-fit: contain;
    }
    .product button {
      background-color: #6A4C93;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 5px;
      margin-top: 0.5rem;
      cursor: pointer;
    }

    .about, .contact, .cart {
      background: #D7C4F0;
    }

    .contact form {
      max-width: 500px;
      margin: auto;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    input, textarea {
      padding: 0.75rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }

    .cart-items {
      max-width: 500px;
      margin: auto;
      background: white;
      padding: 1rem;
      border-radius: 10px;
    }

    footer {
      background: #6A4C93;
      color: white;
      text-align: center;
      padding: 1rem;
    }

    .hidden {
      display: none;
    }
  </style>
</head>
<body>
  <!-- Splash -->
  <div id="splash-screen">
    <img src="logo.png" alt="Diamond Logo" class="splash-logo">
  </div>

  <!-- Header -->
  <header>
    <img src="logo.png" alt="Diamond Logo">
    <h1>Diamond Creation</h1>
    <p>Your pastel stationery paradise</p>
  </header>

  <!-- Navigation -->
  <nav>
    <a href="#" onclick="showPage('home')">Home</a>
    <a href="#" onclick="showPage('shop')">Shop</a>
    <a href="#" onclick="showPage('about')">About</a>
    <a href="#" onclick="showPage('contact')">Feedback</a>
    <a href="#" onclick="showPage('cart')">Cart</a>
  </nav>

  <!-- Pages -->
  <section id="home">
    <div class="hero">
      <h2>Welcome to Diamond Creation</h2>
      <p>Explore pastel stationery that sparks creativity and joy!</p>
    </div>
  </section>

  <section id="shop" class="hidden">
    <h2>Our Products</h2>
    <div class="products">
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Notebook">
        <h3>Pastel Notebook</h3>
        <p>$5.99</p>
        <button onclick="addToCart('Pastel Notebook', 5.99)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Pens">
        <h3>Colorful Gel Pens</h3>
        <p>$3.49</p>
        <button onclick="addToCart('Colorful Gel Pens', 3.49)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Stickers">
        <h3>Sticker Pack</h3>
        <p>$2.99</p>
        <button onclick="addToCart('Sticker Pack', 2.99)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Highlighters">
        <h3>Mini Highlighter Set</h3>
        <p>$4.29</p>
        <button onclick="addToCart('Mini Highlighter Set', 4.29)">Add to Cart</button>
      </div>
    </div>
  </section>

  <section id="about" class="hidden about">
    <h2>About Diamond Creation</h2>
    <p>We’re passionate about pastel, paper, and pens. Based on creativity and quality, Diamond Creation offers hand-picked stationery that makes organizing fun again!</p>
  </section>

  <section id="contact" class="hidden contact">
    <h2>Feedback & Suggestions</h2>
    <form id="feedback-form">
      <input type="text" id="name" placeholder="Your Name" required>
      <input type="email" id="email" placeholder="Your Email" required>
      <textarea id="message" rows="5" placeholder="Your Feedback" required></textarea>
      <button type="submit">Send Feedback</button>
    </form>
    <p id="form-status" style="text-align:center;margin-top:1rem;"></p>
  </section>

  <section id="cart" class="hidden cart">
    <h2>Your Cart</h2>
    <div class="cart-items" id="cart-items">
      <p>No items yet.</p>
    </div>
    <button onclick="checkout()">Checkout</button>
  </section>

  <footer>
    <p>&copy; 2025 Diamond Creation. All rights reserved.</p>
  </footer>

  <!-- JS -->
  <script>
    // Splash screen
    window.addEventListener("load", () => {
      setTimeout(() => {
        document.getElementById("splash-screen").style.display = "none";
      }, 2500);
    });

    // Multipage routing
    function showPage(pageId) {
      document.querySelectorAll("section").forEach(sec => sec.classList.add("hidden"));
      document.getElementById(pageId).classList.remove("hidden");
    }

    // Cart logic
    const cart = [];
    function addToCart(item, price) {
      cart.push({ item, price });
      updateCart();
    }
    function updateCart() {
      const container = document.getElementById('cart-items');
      if (cart.length === 0) {
        container.innerHTML = '<p>No items yet.</p>';
      } else {
        container.innerHTML = cart.map(c => `<p>${c.item} - $${c.price.toFixed(2)}</p>`).join('');
      }
    }
    function checkout() {
      alert("Checkout feature coming soon!");
    }

    // Feedback form
    document.getElementById("feedback-form").addEventListener("submit", function(e) {
      e.preventDefault();
      const status = document.getElementById("form-status");
      status.textContent = "Sending...";
      setTimeout(() => {
        status.textContent = "Thanks for your feedback!";
        this.reset();
      }, 1500);
    });
  </script>
</body>
</html>
