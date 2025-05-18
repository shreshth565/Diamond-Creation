<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Diamond Stationers</title>
  <link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root {
      --primary: #B4E9E2;
      --secondary: #FFC3A0;
      --accent: #D3B5E5;
      --highlight: #FFD6E0;
      --background: #FFF8F1;
      --text: #3D3D4E;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Quicksand', sans-serif;
    }

    body {
      background-color: var(--background);
      padding-top: 4rem;
      color: var(--text);
      position: relative;
      overflow-x: hidden;
    }

    body::before {
      content: "";
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background-image: 
        url('https://cdn-icons-png.flaticon.com/512/2875/2875430.png'),
        url('https://cdn-icons-png.flaticon.com/512/2875/2875450.png'),
        url('https://cdn-icons-png.flaticon.com/512/2875/2875466.png'),
        url('https://cdn-icons-png.flaticon.com/512/189/189690.png'),
        url('https://cdn-icons-png.flaticon.com/512/2329/2329078.png');
      background-repeat: repeat;
      background-size: 60px;
      background-position: 0 0, 150px 150px, 300px 100px, 400px 200px, 100px 300px;
      opacity: 0.06;
      z-index: 0;
    }

    header {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      background: linear-gradient(135deg, var(--primary), var(--accent));
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 2rem;
      z-index: 1000;
      box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }

    header img {
      height: 40px;
    }

    nav a {
      margin: 0 1rem;
      color: var(--text);
      text-decoration: none;
      font-weight: bold;
    }

    nav a:hover {
      color: var(--highlight);
    }

    #diamond-popup {
      position: fixed;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 9999;
      animation: shine 2s ease-out forwards;
    }

    #diamond-popup img {
      width: 80px;
      animation: rotateDiamond 2s linear infinite;
    }

    @keyframes shine {
      0% {opacity: 0; transform: scale(0.5) translate(-50%, -50%);}
      50% {opacity: 1; transform: scale(1.2) translate(-50%, -50%);}
      100% {opacity: 0; transform: scale(0.5) translate(-50%, -50%);}
    }

    @keyframes rotateDiamond {
      0% {transform: rotate(0deg);}
      100% {transform: rotate(360deg);}
    }

    .container {
      max-width: 1200px;
      margin: auto;
      padding: 2rem;
      position: relative;
      z-index: 1;
    }

    footer {
      background: var(--secondary);
      color: white;
      text-align: center;
      padding: 1rem;
    }

    #camera-section {
      margin: 2rem auto;
      text-align: center;
    }

    #video {
      width: 100%;
      max-width: 400px;
      border: 2px solid var(--accent);
      border-radius: 10px;
      margin-bottom: 1rem;
    }

    .filter-section {
      margin: 2rem auto;
      text-align: center;
    }

    .filter-section select {
      padding: 0.5rem;
      margin: 0.5rem;
      border-radius: 5px;
      border: 1px solid var(--accent);
    }
  </style>
</head>
<body>
  <div id="diamond-popup">
    <img src="https://cdn-icons-png.flaticon.com/512/3468/3468373.png" alt="diamond" />
  </div>
  <header>
    <img src="your-logo.png" alt="Diamond Stationers">
    <nav>
      <a href="#home">Home</a>
      <a href="#products">Products</a>
      <a href="#cart">Cart</a>
      <a href="#login">Login</a>
    </nav>
  </header>

  <main class="container">
    <h1>Welcome to Diamond Stationers</h1>
    <p>Best place for all your stationery needs!</p>

    <section id="camera-section">
      <h2>Find Products by Image</h2>
      <video id="video" autoplay></video><br>
      <button onclick="capturePhoto()">Capture & Search</button>
    </section>

    <section class="filter-section">
      <h2>Filter Products</h2>
      <select id="categoryFilter">
        <option value="all">All</option>
        <option value="pens">Pens</option>
        <option value="notebooks">Notebooks</option>
        <option value="markers">Markers</option>
        <option value="accessories">Accessories</option>
      </select>
      <select id="priceFilter">
        <option value="all">All Prices</option>
        <option value="low">Low to High</option>
        <option value="high">High to Low</option>
      </select>
      <button onclick="applyFilters()">Apply</button>
    </section>
  </main>

  <footer>
    &copy; 2025 Diamond Stationers. All rights reserved.
  </footer>

  <script>
    window.addEventListener('load', () => {
      const popup = document.getElementById('diamond-popup');
      setTimeout(() => {
        popup.style.display = 'none';
      }, 2000);

      if (navigator.mediaDevices && navigator.mediaDevices.getUserMedia) {
        navigator.mediaDevices.getUserMedia({ video: true })
          .then(function(stream) {
            const video = document.getElementById('video');
            video.srcObject = stream;
            video.play();
          })
          .catch(function(err) {
            console.error("Camera access error:", err);
          });
      }
    });

    function capturePhoto() {
      alert("This feature will match captured item with available products (AI-powered coming soon!)");
    }

    function applyFilters() {
      const category = document.getElementById('categoryFilter').value;
      const price = document.getElementById('priceFilter').value;
      alert(`Filtering by category: ${category}, price: ${price}`);
      // Filtering logic will go here in future updates
    }
  </script>
</body>
</html>
