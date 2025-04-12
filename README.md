<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Diamond Creation - Shop Pastel Stationery</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background-color: #FFFBF0;
      color: #333;
    }
    header {
      background: linear-gradient(135deg, #FFD6A5, #D7C4F0);
      padding: 2rem;
      text-align: center;
    }
    header h1 {
      margin: 0;
      font-size: 2.5rem;
      color: #6A4C93;
    }
    nav {
      background: #A0E7E5;
      padding: 1rem;
      display: flex;
      justify-content: center;
      gap: 1.5rem;
      flex-wrap: wrap;
    }
    nav a {
      text-decoration: none;
      color: #333;
      font-weight: bold;
      transition: color 0.3s ease;
    }
    nav a:hover {
      color: #6A4C93;
    }
    .hero {
      background: #B9FBC0;
      padding: 4rem 2rem;
      text-align: center;
    }
    .hero h2 {
      font-size: 2rem;
      margin-bottom: 1rem;
    }
    .hero p {
      font-size: 1.2rem;
      max-width: 600px;
      margin: auto;
    }
    .products {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 2rem;
      padding: 2rem;
      background: #FFCBDD;
    }
    .product {
      background: white;
      padding: 1rem;
      border-radius: 10px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
      text-align: center;
      transition: transform 0.2s;
    }
    .product:hover {
      transform: translateY(-5px);
    }
    .product img {
      width: 100%;
      max-height: 150px;
      object-fit: contain;
    }
    .product h3 {
      margin: 0.5rem 0 0.25rem;
    }
    .product button {
      margin-top: 0.5rem;
      background-color: #6A4C93;
      color: white;
      border: none;
      padding: 0.5rem 1rem;
      border-radius: 5px;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }
    .product button:hover {
      background-color: #5a3a7e;
    }
    .about, .contact {
      padding: 2rem;
      background-color: #D7C4F0;
      text-align: center;
    }
    .about h2, .contact h2 {
      color: #6A4C93;
    }
    .contact form {
      max-width: 500px;
      margin: auto;
      display: flex;
      flex-direction: column;
      gap: 1rem;
    }
    .contact input, .contact textarea {
      padding: 0.75rem;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    .contact button {
      padding: 0.75rem;
      background-color: #6A4C93;
      color: white;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    .cart {
      padding: 2rem;
      background: #FFD6A5;
      text-align: center;
    }
    .cart h2 {
      margin-bottom: 1rem;
    }
    .cart-items {
      max-width: 600px;
      margin: auto;
      text-align: left;
      background: white;
      padding: 1rem;
      border-radius: 10px;
    }
    .cart-items p {
      margin: 0.5rem 0;
    }
    .checkout-btn {
      margin-top: 1rem;
      background-color: #6A4C93;
      color: white;
      padding: 0.75rem 1.5rem;
      border: none;
      border-radius: 5px;
      cursor: pointer;
    }
    footer {
      background: #6A4C93;
      color: white;
      text-align: center;
      padding: 1rem;
    }
  </style>
</head>
<body>
  <header>
    <h1>Diamond Creation</h1>
    <p>Your go-to place for cute and colorful stationery!</p>
  </header>
  <nav>
    <a href="#">Home</a>
    <a href="#shop">Shop</a>
    <a href="#about">About</a>
    <a href="#contact">Contact</a>
    <a href="#cart">Cart</a>
  </nav>
  <section class="hero">
    <h2>Welcome to Diamond Creation</h2>
    <p>Explore our beautiful collection of pastel-themed stationery, designed to inspire creativity and bring joy to your workspace.</p>
  </section>
  <section id="shop" class="products">
    <div class="product">
      <img src="https://via.placeholder.com/150" alt="Notebook">
      <h3>Pastel Notebook</h3>
      <p>$5.99</p>
      <button>Add to Cart</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/150" alt="Pens">
      <h3>Colorful Gel Pens</h3>
      <p>$3.49</p>
      <button>Add to Cart</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/150" alt="Stickers">
      <h3>Sticker Pack</h3>
      <p>$2.99</p>
      <button>Add to Cart</button>
    </div>
    <div class="product">
      <img src="https://via.placeholder.com/150" alt="Highlighters">
      <h3>Mini Highlighter Set</h3>
      <p>$4.29</p>
      <button>Add to Cart</button>
    </div>
  </section>
  <section id="about" class="about">
    <h2>About Us</h2>
    <p>Diamond Creation was founded with a passion for art and creativity. Our goal is to bring vibrant, inspiring stationery to everyone who loves design, journaling, and self-expression. Every item is curated with love and a splash of pastel joy!</p>
  </section>
  <section id="contact" class="contact">
    <h2>Contact Us</h2>
    <form>
      <input type="text" placeholder="Your Name" required>
      <input type="email" placeholder="Your Email" required>
      <textarea rows="5" placeholder="Your Message" required></textarea>
      <button type="submit">Send Message</button>
    </form>
  </section>
  <section id="cart" class="cart">
    <h2>Your Cart</h2>
    <div class="cart-items">
      <p>No items in cart yet.</p>
    </div>
    <button class="checkout-btn">Checkout</button>
  </section>
  <footer>
    <p>&copy; 2025 Diamond Creation. All rights reserved.</p>
  </footer>
</body>
</html>
