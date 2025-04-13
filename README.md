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
      animation: fadeOut 2s ease-out forwards;
      animation-delay: 2.5s;
    }
    .splash-logo {
      height: 120px;
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
    header h1 {
      margin: 0.5rem 0 0.2rem;
    }
    header p {
      margin: 0;
      font-style: italic;
      font-weight: 500;
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
      position: relative;
      padding-bottom: 4px;
    }
    nav a:hover,
    nav a.active {
      color: #6A4C93;
      border-bottom: 2px solid #6A4C93;
    }

    section {
      padding: 2rem;
    }

    .hero {
      background: #B9FBC0;
      text-align: center;
      padding: 2rem;
      border-radius: 10px;
    }

    .products {
      background: #FFCBDD;
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1.5rem;
      padding: 1rem;
      border-radius: 10px;
    }

    .product {
      background: white;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      text-align: center;
      transition: transform 0.2s ease;
    }

    .product:hover {
      transform: scale(1.02);
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
      transition: background 0.3s;
    }

    .product button:hover {
      background-color: #59347e;
    }

    .about, .contact, .cart {
      background: #D7C4F0;
      border-radius: 10px;
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

    button[type="submit"] {
      background-color: #6A4C93;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 5px;
      cursor: pointer;
    }

    button[type="submit"]:hover {
      background-color: #59347e;
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

    @media (max-width: 600px) {
      nav {
        flex-direction: column;
        gap: 1rem;
      }
      .products {
        grid-template-columns: 1fr;
      }
    }
  </style>
</head>
<body>
  <!-- Splash -->
  <div id="splash-screen">
    <img src="logo.png" alt="Diamond Creation Logo" class="splash-logo">
  </div>

  <!-- Header -->
  <header>
    <img src="logo.png" alt="Diamond Creation Logo">
    <h1>Diamond Creation</h1>
    <p>Your pastel stationery paradise</p>
  </header>

  <!-- Navigation -->
  <nav aria-label="Main navigation">
    <a href="#" onclick="showPage('home', this)">Home</a>
    <a href="#" onclick="showPage('shop', this)">Shop</a>
    <a href="#" onclick="showPage('about', this)">About</a>
    <a href="#" onclick="showPage('contact', this)">Feedback</a>
    <a href="#" onclick="showPage('cart', this)">Cart</a>
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
        <img src="https://via.placeholder.com/150" alt="Pastel Notebook">
        <h3>Pastel Notebook</h3>
        <p>$5.99</p>
        <button onclick="addToCart('Pastel Notebook', 5.99)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Colorful Gel Pens">
        <h3>Colorful Gel Pens</h3>
        <p>$3.49</p>
        <button onclick="addToCart('Colorful Gel Pens', 3.49)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Sticker Pack">
        <h3>Sticker Pack</h3>
        <p>$2.99</p>
        <button onclick="addToCart('Sticker Pack', 2.99)">Add to Cart</button>
      </div>
      <div class="product">
        <img src="https://via.placeholder.com/150" alt="Mini Highlighter Set">
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
   
