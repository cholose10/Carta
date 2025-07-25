<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF‑8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tilo Café</title>
  <style>
    body { font-family: Arial, sans-serif; margin: 0; padding: 0; background: #f5f5f5; }
    header { background: #fff; padding: 20px; text-align: center; }
    header h1 { margin: 0; font-size: 2em; }
    .banner { padding: 15px; background: #ffe; margin-bottom: 10px; }
    .banner p { margin: 5px 0; }
    .categories { display: flex; overflow-x: auto; background: #fff; padding: 10px; }
    .categories button { margin-right: 8px; padding: 10px 15px; border: none; border-radius: 5px; background: #eee; }
    .item-list { padding: 10px; }
    .item { background: #fff; padding: 10px; margin-bottom: 10px; border-radius: 5px; display: flex; }
    .item img { width: 80px; height: 80px; object-fit: cover; border-radius: 5px; margin-right: 10px; }
    .item div { flex: 1; }
    .item h3 { margin: 0; }
    .item p { margin: 5px 0; }
  </style>
</head>
<body>

<header>
  <h1>Tilo Café</h1>
</header>

<div class="banner">
  <p><b>Sugerencia del Día:</b> Brownie tibio con helado de vainilla.</p>
  <p><b>Menú del Día:</b> Milanesa napolitana + papas + bebida chica a $3.500.</p>
</div>

<div class="categories">
  <button data-cat="cafeteria">☕ Cafetería</button>
  <button data-cat="pasteleria">🍰 Pastelería</button>
  <button data-cat="promoCafe">💥 Promoción Café</button>
  <button data-cat="tartas">🥧 Tartas</button>
  <button data-cat="burritos">🌯 Burritos</button>
  <button data-cat="sandwiches">🥪 Sándwiches</button>
  <button data-cat="entradas">🥖 Entradas</button>
  <button data-cat="burgers">🍔 Lomitos & Burgers</button>
  <button data-cat="omelettes">🧆 Omelettes / Tortillas</button>
  <button data-cat="almuerzo">🍽️ Almuerzo & Cena</button>
  <button data-cat="postres">🧁 Postres</button>
  <button data-cat="refrescos">🧃 Refrescos</button>
  <button data-cat="kids">👶 Menú Kids</button>
</div>

<div class="item-list" id="item-list">
  <p>Seleccioná una categoría para ver los platos.</p>
</div>

<script>
  const items = {
    cafeteria: [
      { img:'https://via.placeholder.com/80', name:'Café expreso', desc:'Café solo, 50 ml.', price:'$1.200' },
      { img:'https://via.placeholder.com/80', name:'Capuchino', desc:'Espresso + leche espumada', price:'$2.000' },
    ],
    pasteleria: [
      { img:'https://via.placeholder.com/80', name:'Medialuna', desc:'Manteca o dulce de leche', price:'$400' },
      { img:'https://via.placeholder.com/80', name:'Muffin de chocolate', desc:'Con chips de chocolate', price:'$700' },
    ],
    promoCafe: [
      { img:'https://via.placeholder.com/80', name:'Café + Medialuna', desc:'Combo express', price:'$1.500' },
    ],
    tartas: [],
    burritos: [],
    sandwiches: [],
    entradas: [],
    burgers: [],
    omelettes: [],
    almuerzo: [],
    postres: [],
    refrescos: [],
    kids: [],
  };

  document.querySelectorAll('.categories button').forEach(btn =>
    btn.addEventListener('click', () => {
      const cat = btn.dataset.cat;
      const list = items[cat];
      const container = document.getElementById('item-list');
      container.innerHTML = '';
      if (list.length === 0) {
        container.innerHTML = '<p>No hay ítems en esta categoría aún.</p>';
      } else {
        list.forEach(it => {
          const div = document.createElement('div');
          div.className = 'item';
          div.innerHTML = `<img src="${it.img}" alt="${it.name}">
                           <div>
                             <h3>${it.name} - ${it.price}</h3>
                             <p>${it.desc}</p>
                           </div>`;
          container.appendChild(div);
        });
      }
    })
  );
</script>

</body>
</html>
# Carta
