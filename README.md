<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>StockQuinca Lite</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>📊 Tableau de Bord</h1>
    <nav>
      <a href="ajouter.html" class="btn">➕ Ajouter Produit</a>
      <a href="vendre.html" class="btn">🛒 Vendre</a>
    </nav>

    <input type="text" id="search" placeholder="Rechercher un produit..." class="search-input" />

    <table id="product-table">
      <thead>
        <tr>
          <th>Référence</th>
          <th>Nom</th>
          <th>Catégorie</th>
          <th>Stock</th>
          <th>Prix Vente</th>
          <th>État</th>
        </tr>
      </thead>
      <tbody id="product-list"></tbody>
    </table>
  </div>

  <script src="script.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Ajouter un produit - StockQuinca</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>➕ Ajouter un produit</h1>
    <form id="add-form">
      <label>Référence (SKU)</label>
      <input type="text" id="sku" required />

      <label>Nom du produit</label>
      <input type="text" id="name" required />

      <label>Catégorie</label>
      <select id="category" required>
        <option value="Outils">Outils</option>
        <option value="Plomberie">Plomberie</option>
        <option value="Électricité">Électricité</option>
        <option value="Peinture">Peinture</option>
        <option value="Jardinage">Jardinage</option>
        <option value="Quincaillerie">Quincaillerie</option>
      </select>

      <label>Stock initial</label>
      <input type="number" id="stock" min="0" required />

      <label>Seuil d'alerte</label>
      <input type="number" id="alert" min="1" value="5" />

      <label>Prix d'achat (€)</label>
      <input type="number" id="buyPrice" step="0.01" min="0" />

      <label>Prix de vente (€)</label>
      <input type="number" id="sellPrice" step="0.01" min="0" required />

      <button type="submit" class="btn">💾 Enregistrer</button>
    </form>
    <a href="index.html" class="btn">← Retour</a>
  </div>

  <script src="script.js"></script>
</body>
</html>

<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Vendre un produit - StockQuinca</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>🛒 Vente</h1>
    <p>Scannez ou sélectionnez un produit :</p>

    <select id="product-select" required>
      <option value="">Sélectionner un produit</option>
    </select>

    <div id="product-info"></div>

    <div id="sale-form" style="display:none;">
      <label>Quantité</label>
      <input type="number" id="quantity" min="1" value="1" />
      <p><strong>Total :</strong> <span id="total">0.00 €</span></p>
      <button id="confirm-sale" class="btn">✅ Confirmer la vente</button>
    </div>

    <a href="index.html" class="btn">← Retour</a>
  </div>

  <script src="script.js"></script>
</body>
</html>

<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Vendre un produit - StockQuinca</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <div class="container">
    <h1>🛒 Vente</h1>
    <p>Scannez ou sélectionnez un produit :</p>

    <select id="product-select" required>
      <option value="">Sélectionner un produit</option>
    </select>

    <div id="product-info"></div>

    <div id="sale-form" style="display:none;">
      <label>Quantité</label>
      <input type="number" id="quantity" min="1" value="1" />
      <p><strong>Total :</strong> <span id="total">0.00 €</span></p>
      <button id="confirm-sale" class="btn">✅ Confirmer la vente</button>
    </div>

    <a href="index.html" class="btn">← Retour</a>
  </div>

  <script src="script.js"></script>
</body>
</html>

* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: #f4f6f9;
  color: #333;
  line-height: 1.6;
}

.container {
  max-width: 1000px;
  margin: 20px auto;
  padding: 20px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

h1 {
  text-align: center;
  margin-bottom: 20px;
  color: #2c3e50;
}

nav {
  text-align: center;
  margin-bottom: 20px;
}

.btn {
  display: inline-block;
  padding: 10px 16px;
  margin: 5px;
  background: #3498db;
  color: white;
  text-decoration: none;
  border-radius: 5px;
  font-weight: bold;
  transition: background 0.3s;
}

.btn:hover {
  background: #2980b9;
}

.search-input {
  width: 100%;
  padding: 10px;
  margin: 15px 0;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 16px;
}

table {
  width: 100%;
  border-collapse: collapse;
  margin-top: 20px;
}

th, td {
  padding: 12px;
  text-align: left;
  border-bottom: 1px solid #ddd;
}

th {
  background: #ecf0f1;
  color: #2c3e50;
}

tr:hover {
  background: #f1f8ff;
}

form {
  display: grid;
  gap: 10px;
  margin: 20px 0;
}

form label {
  font-weight: bold;
  color: #2c3e50;
}

form input, form select {
  padding: 10px;
  border: 1px solid #ddd;
  border-radius: 5px;
  font-size: 16px;
}

form button {
  margin-top: 10px;
}

.alert {
  background: #e74c3c;
  color: white;
  padding: 5px 8px;
  border-radius: 3px;
  font-size: 12px;
}

.low {
  background: #f39c12;
}

.normal {
  background: #27ae60;
}

select, input {
  font-size: 16px;
}

// === Gestion des produits ===
let products = JSON.parse(localStorage.getItem('stockquinca_products')) || [];

// Sauvegarder dans LocalStorage
function saveProducts() {
  localStorage.setItem('stockquinca_products', JSON.stringify(products));
}

// === Page : Liste des produits (index.html) ===
if (document.getElementById('product-list')) {
  const productList = document.getElementById('product-list');
  const searchInput = document.getElementById('search');

  function renderProducts(filter = '') {
    productList.innerHTML = '';
    const filtered = products.filter(p =>
      p.name.toLowerCase().includes(filter.toLowerCase()) ||
      p.sku.toLowerCase().includes(filter.toLowerCase())
    );

    filtered.forEach(p => {
      const tr = document.createElement('tr');

      // Déterminer l'état du stock
      let statusClass = 'normal';
      let statusText = 'OK';
      if (p.stock <= p.alert) statusClass = 'low';
      if (p.stock === 0) {
        statusClass = 'alert';
        statusText = 'Épuisé';
      } else if (p.stock <= p.alert) {
        statusText = 'Bas';
      }

      tr.innerHTML = `
        <td>${p.sku}</td>
        <td>${p.name}</td>
        <td>${p.category}</td>
        <td>${p.stock}</td>
        <td>${p.sellPrice.toFixed(2)} €</td>
        <td><span class="alert ${statusClass}">${statusText}</span></td>
      `;
      productList.appendChild(tr);
    });
  }

  searchInput?.addEventListener('input', (e) => {
    renderProducts(e.target.value);
  });

  renderProducts();
}

// === Page : Ajouter un produit (ajouter.html) ===
if (document.getElementById('add-form')) {
  document.getElementById('add-form').addEventListener('submit', function(e) {
    e.preventDefault();

    const newProduct = {
      sku: document.getElementById('sku').value.trim(),
      name: document.getElementById('name').value.trim(),
      category: document.getElementById('category').value,
      stock: parseInt(document.getElementById('stock').value),
      alert: parseInt(document.getElementById('alert').value),
      buyPrice: parseFloat(document.getElementById('buyPrice').value) || 0,
      sellPrice: parseFloat(document.getElementById('sellPrice').value)
    };

    // Vérifier doublon
    if (products.some(p => p.sku === newProduct.sku)) {
      alert("⚠️ Une référence existe déjà !");
      return;
    }

    products.push(newProduct);
    saveProducts();
    alert("✅ Produit ajouté avec succès !");
    this.reset();
  });
}

// === Page : Vendre (vendre.html) ===
if (document.getElementById('product-select')) {
  const select = document.getElementById('product-select');
  const infoDiv = document.getElementById('product-info');
  const saleForm = document.getElementById('sale-form');
  const quantityInput = document.getElementById('quantity');
  const totalSpan = document.getElementById('total');
  const confirmBtn = document.getElementById('confirm-sale');

  // Remplir le select
  products.forEach(p => {
    const opt = document.createElement('option');
    opt.value = p.sku;
    opt.textContent = `${p.name} (${p.stock} en stock)`;
    select.appendChild(opt);
  });

  select.addEventListener('change', function() {
    const sku = this.value;
    const product = products.find(p => p.sku === sku);
    if (!product) return;

    infoDiv.innerHTML = `
      <p><strong>${product.name}</strong> – ${product.sellPrice.toFixed(2)} €</p>
      <p>Stock disponible : <strong>${product.stock}</strong></p>
    `;

    saleForm.style.display = 'block';
    quantityInput.max = product.stock;
    quantityInput.value = Math.min(1, product.stock);

    // Calcul du total
    updateTotal(product);
  });

  function updateTotal(product) {
    const qty = parseInt(quantityInput.value);
    const total = qty * product.sellPrice;
    totalSpan.textContent = total.toFixed(2) + " €";
  }

  quantityInput?.addEventListener('input', function() {
    const product = products.find(p => p.sku === select.value);
    if (product) updateTotal(product);
  });

  confirmBtn.addEventListener('click', function() {
    const sku = select.value;
    const qty = parseInt(quantityInput.value);
    const product = products.find(p => p.sku === sku);

    if (!product || product.stock < qty) {
      alert("⚠️ Stock insuffisant !");
      return;
    }

    product.stock -= qty;
    saveProducts();
    alert(`✅ Vente confirmée : ${qty} x ${product.name}`);
    saleForm.style.display = 'none';
    infoDiv.innerHTML = "<p>Vente terminée. Vous pouvez enregistrer une nouvelle vente.</p>";
  });
}

