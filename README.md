manav<header>

![Deprecation Badge](https://img.shields.io/badge/Skills-Deprecated-333?logo=github&labelColor=454c54&color=bf8700)

This course has been deprecated. Please visit the [Getting Started with GitHub Copilot](https://github.com/skills/getting-started-with-github-copilot) exercise for the newest <!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Saiyan Bites - Order Online</title>
  <style>
    body { font-family: Arial, sans-serif; padding: 20px; background-color: #f3f3f3; }
    h1 { color: #333; }
    .menu-item { background: #fff; padding: 15px; margin: 10px 0; border-radius: 10px; box-shadow: 0 2px 5px rgba(0,0,0,0.1); }
    .menu-item h2 { margin: 0; }
    .price { font-weight: bold; margin: 10px 0; }
    .cart { position: fixed; top: 20px; right: 20px; background: #fff; padding: 15px; border-radius: 10px; box-shadow: 0 2px 10px rgba(0,0,0,0.2); width: 250px; }
    .cart-item { margin-bottom: 10px; }
    button { padding: 5px 10px; border: none; border-radius: 5px; background-color: #007bff; color: white; cursor: pointer; }
    .qty { width: 30px; text-align: center; }
  </style>
</head>
<body>

  <h1>Order Online</h1>

  <div class="menu-item">
    <h2>Bulma Bento Box</h2>
    <p>Blue rice, fusion tofu, capsule veggies</p>
    <div class="price">$12.99</div>
    <input type="number" class="qty" id="qty-bulma" value="1" min="1">
    <button onclick="addToCart('Bulma Bento Box', 12.99, 'qty-bulma')">Add to Cart</button>
  </div>

  <div class="menu-item">
    <h2>Android 18 Icy Lemonade</h2>
    <p>Lemon mint cooler with ice crystal cube</p>
    <div class="price">$3.99</div>
    <input type="number" class="qty" id="qty-lemonade" value="1" min="1">
    <button onclick="addToCart('Android 18 Icy Lemonade', 3.99, 'qty-lemonade')">Add to Cart</button>
  </div>

  <div class="cart">
    <h3>Your Cart</h3>
    <div id="cart-items"></div>
    <div><strong>Total:</strong> $<span id="total">0.00</span></div>
  </div>

  <script>
    let cart = [];

    function addToCart(name, price, qtyId) {
      const qty = parseInt(document.getElementById(qtyId).value);
      const existing = cart.find(item => item.name === name);

      if (existing) {
        existing.qty += qty;
      } else {
        cart.push({ name, price, qty });
      }

      updateCart();
    }

    function updateCart() {
      const cartItemsDiv = document.getElementById('cart-items');
      cartItemsDiv.innerHTML = '';
      let total = 0;

      cart.forEach(item => {
        const itemTotal = (item.qty * item.price).toFixed(2);
        total += parseFloat(itemTotal);
        cartItemsDiv.innerHTML += `<div class="cart-item">${item.qty}x ${item.name} - $${itemTotal}</div>`;
      });

      document.getElementById('total').innerText = total.toFixed(2);
    }
  </script>

</body>
</html>
