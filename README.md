<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Tilo Café</title>
  <style>
    body {
      font-family: 'Segoe UI', sans-serif;
      margin: 0;
      background: #7bd5b4;
      color: #333;
    }
    header {
      background: #c7bdbd;
      text-align: center;
      padding: 20px;
      box-shadow: 0 2px 5px rgba(0,0,0,0.1);
    }
    header img {
      width: 120px;
      height: auto;
    }
    .banner {
      text-align: center;
      padding: 10px;
      font-size: 1.5rem;
      color: #555;
    }
    .categories {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 10px;
      padding: 10px;
    }
    .categories button {
      padding: 10px 20px;
      background-color: #040404;
      color: #fff;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.3s;
    }
    .categories button:hover {
      background-color: #555;
    }
    .item-list {
      display: flex;
      flex-wrap: wrap;
      justify-content: center;
      gap: 15px;
      padding: 20px;
    }
    .item {
      background: #fff;
      border-radius: 12px;
      box-shadow: 0 2px 10px rgba(0,0,0,0.1);
      overflow: hidden;
      width: 280px;
      cursor: pointer;
      transition: transform 0.2s ease;
    }
    .item:hover {
      transform: scale(1.02);
    }
    .item img {
      width: 100%;
      height: 180px;
      object-fit: cover;
    }
    .item h3 {
      margin: 10px;
    }
    .item p {
      margin: 0 10px 10px;
      font-weight: bold;
    }
    /* Modal */
    .modal {
      display: none;
      position: fixed;
      z-index: 10;
      padding-top: 60px;
      left: 0;
      top: 0;
      width: 100%;
      height: 100%;
      background-color: rgba(135, 11, 11, 0.8);
    }
    .modal-content {
      margin: auto;
      display: block;
      max-width: 90%;
      max-height: 80%;
      border-radius: 10px;
    }
    .modal:target {
      display: block;
    }
    .close {
      position: absolute;
      top: 20px;
      right: 30px;
      font-size: 30px;
      color: #fff;
      text-decoration: none;
    }
  </style>
</head>
<body>
  <header>
  <img src="logo.png" alt="Logo Tilo Café" />

  </header>
  <div class="banner">¡Bienvenidos a Tilo Café Aguero!</div>
  <div class="categories">
    <button onclick="filterCategory('Café')">Café</button>
    <button onclick="filterCategory('Pastelería')">Pastelería</button>
    <button onclick="filterCategory('Promo')">Promoción Café</button>
    <button onclick="filterCategory('Tartas')">Tartas</button>
    <button onclick="filterCategory('Burritos')">Burritos</button>
    <button onclick="filterCategory('Sándwiches')">Sándwiches</button>
    <button onclick="filterCategory('Menú')">Menú del Día</button>
    <button onclick="filterCategory('Sugerencia')">Sugerencia del Día</button>
  </div>

  <div class="item-list" id="product-list">
    <div class="item" data-category="Café">
      <a href="#img1"><img src="café.jpg" alt="Café 1"></a>
      <h3>Café Espresso</h3>
      <p>$800</p>
    </div>
    <div class="item" data-category="Pastelería">
      <a href="#img2"><img src="Chocola.jpg" alt="Torta"></a>
      <h3>Torta de Chocolate</h3>
      <p>$1200</p>
    </div>
    <!-- Agregar más productos aquí -->
  </div>

  <!-- MODALS -->
  <div id="img1" class="modal">
    <a href="#" class="close">&times;</a>
    <img class="modal-content" src="café.jpg">
  </div>
  <div id="img2" class="modal">
    <a href="#" class="close">&times;</a>
    <img class="modal-content" src="img/torta1.jpg">
  </div>

  <script>
    function filterCategory(category) {
      const items = document.querySelectorAll('.item');
      items.forEach(item => {
        item.style.display = item.dataset.category === category || category === 'Todos' ? 'block' : 'none';
      });
    }
  </script>
</body>
</html>
