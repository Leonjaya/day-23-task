# day-23-task
<div id="product-list">
  <div class="product" data-product-id="1">
    <h3>Product Name 1</h3>
    <p>Description of Product 1</p>
    <button class="cart-btn">Add to Cart</button>
  </div>
  <div class="product" data-product-id="2">
    <h3>Product Name 2</h3>
    <p>Description of Product 2</p>
    <button class="cart-btn">Add to Cart</button>
  </div>
  <!-- Add more products as needed -->
</div>

<div id="cart">
  <h3>Shopping Cart</h3>
  <p>Items in Cart: <span id="cart-quantity">0</span></p>
</div>

document.addEventListener('DOMContentLoaded', function() {
  const cartQuantityElement = document.getElementById('cart-quantity');
  let cartQuantity = 0;

  document.querySelectorAll('.cart-btn').forEach(button => {
    button.addEventListener('click', function() {
      const productElement = this.closest('.product');
      const productId = productElement.getAttribute('data-product-id');

      if (this.textContent === 'Add to Cart') {
        // Add to cart
        cartQuantity++;
        this.textContent = 'Remove from Cart';
      } else {
        // Remove from cart
        cartQuantity--;
        this.textContent = 'Add to Cart';
      }

      cartQuantityElement.textContent = cartQuantity;
    });
  });
});

#product-list {
  display: flex;
  flex-direction: column;
}

.product {
  border: 1px solid #ccc;
  padding: 10px;
  margin: 10px 0;
}

.cart-btn {
  background-color: #008cba;
  color: white;
  padding: 10px;
  border: none;
  cursor: pointer;
}

.cart-btn:hover {
  background-color: #005f5f;
}

#cart {
  margin-top: 20px;
  padding: 10px;
  border: 1px solid #000;
}
