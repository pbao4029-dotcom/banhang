<!doctype html>
<html lang="vi">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Mini Shop - Trang bán hàng</title>

  <style>
    /* Reset */
    *, *::before, *::after { box-sizing: border-box; }
    body { margin:0; font-family: 'Segoe UI', sans-serif; background:#f9fafb; color:#111827; }

    /* Header */
    header {
      background:linear-gradient(90deg,#6366f1,#8b5cf6);
      color:white; padding:16px 24px;
      display:flex; align-items:center; justify-content:space-between;
      box-shadow:0 2px 6px rgba(0,0,0,0.15);
    }
    header h1 { margin:0; font-size:20px; font-weight:700; }
    .cart-btn {
      background:white; color:#4f46e5; font-weight:600;
      padding:8px 14px; border-radius:999px; border:0; cursor:pointer;
      display:flex; align-items:center; gap:6px;
      transition:0.25s;
    }
    .cart-btn:hover { background:#eef2ff; }

    .cart-count {
      background:#4f46e5; color:white;
      padding:2px 6px; border-radius:50%; font-size:13px;
    }

    /* Container */
    .container { max-width:1200px; margin:20px auto; padding:0 20px; display:grid; grid-template-columns:1fr 320px; gap:20px; }
    @media(max-width:900px){ .container { grid-template-columns:1fr; } }

    /* Product grid */
    .products {
      display:grid;
      grid-template-columns:repeat(auto-fill,minmax(250px,1fr));
      gap:20px;
    }
    .card {
      background:white; border-radius:14px; overflow:hidden;
      box-shadow:0 4px 12px rgba(0,0,0,0.08);
      transition:transform 0.25s;
      display:flex; flex-direction:column;
    }
    .card:hover { transform:translateY(-5px); }
    .thumb {
      height:180px; display:flex; align-items:center; justify-content:center;
      background:linear-gradient(135deg,#e0e7ff,#ede9fe);
      font-size:48px;
    }
    .info { padding:14px; flex:1; display:flex; flex-direction:column; }
    .title { font-weight:700; font-size:16px; margin:0 0 6px 0; }
    .desc { font-size:14px; color:#6b7280; flex:1; }
    .price { font-weight:800; color:#4f46e5; margin-top:8px; }
    .add {
      margin-top:12px; padding:10px; border-radius:10px; border:0;
      background:linear-gradient(90deg,#10b981,#059669);
      color:white; font-weight:600; cursor:pointer; transition:0.3s;
    }
    .add:hover { opacity:0.9; }

    /* Cart */
    .cart {
      background:white; border-radius:14px; padding:16px;
      box-shadow:0 4px 12px rgba(0,0,0,0.08);
      position:sticky; top:20px; max-height:80vh; display:flex; flex-direction:column;
    }
    .cart h2 { margin:0 0 12px 0; font-size:18px; }
    .cart-list { flex:1; overflow:auto; display:flex; flex-direction:column; gap:10px; }
    .cart-item { display:flex; gap:10px; align-items:center; padding:8px; border-radius:10px; background:#f9fafb; }
    .ci-thumb { width:48px; height:48px; display:grid; place-items:center; background:#eef2ff; border-radius:8px; font-size:20px; }
    .ci-info { flex:1; }
    .ci-name { font-weight:600; font-size:14px; margin:0; }
    .ci-meta { font-size:13px; color:#6b7280; }
    .qty { display:flex; gap:8px; align-items:center; margin-top:4px; }
    .q-btn { background:#e5e7eb; border:0; border-radius:6px; width:24px; height:24px; cursor:pointer; }
    .q-btn:hover { background:#d1d5db; }
    .total { margin-top:12px; font-weight:700; font-size:16px; display:flex; justify-content:space-between; }
    .checkout {
      margin-top:12px; padding:12px; border:0; border-radius:12px;
      background:linear-gradient(90deg,#6366f1,#8b5cf6);
      color:white; font-weight:700; cursor:pointer; transition:0.3s;
    }
    .checkout:hover { opacity:0.9; }

    .empty { text-align:center; color:#9ca3af; margin:20px 0; }
    footer { text-align:center; color:#6b7280; margin:20px; font-size:14px; }
  </style>
</head>
<body>
  <header>
    <h1>🛒 Mini Shop</h1>
    <button class="cart-btn">Giỏ hàng <span class="cart-count" id="cartCount">0</span></button>
  </header>

  <div class="container">
    <!-- Sản phẩm -->
    <div class="products">
      <div class="card">
        <div class="thumb">👟</div>
        <div class="info">
          <h3 class="title">Giày Sneaker</h3>
          <p class="desc">Thoải mái, phong cách, dễ phối đồ.</p>
          <div class="price">550,000₫</div>
          <button class="add" onclick="addToCart('Giày Sneaker',550000,'👟')">Thêm vào giỏ</button>
        </div>
      </div>
      <div class="card">
        <div class="thumb">👕</div>
        <div class="info">
          <h3 class="title">Áo Thun</h3>
          <p class="desc">Chất vải cotton mềm mịn, thoáng mát.</p>
          <div class="price">250,000₫</div>
          <button class="add" onclick="addToCart('Áo Thun',250000,'👕')">Thêm vào giỏ</button>
        </div>
      </div>
      <div class="card">
        <div class="thumb">🎧</div>
        <div class="info">
          <h3 class="title">Tai nghe</h3>
          <p class="desc">Âm thanh chất lượng, chống ồn chủ động.</p>
          <div class="price">1,200,000₫</div>
          <button class="add" onclick="addToCart('Tai nghe',1200000,'🎧')">Thêm vào giỏ</button>
        </div>
      </div>
      <div class="card">
        <div class="thumb">⌚</div>
        <div class="info">
          <h3 class="title">Đồng hồ</h3>
          <p class="desc">Thiết kế sang trọng, pin bền.</p>
          <div class="price">2,500,000₫</div>
          <button class="add" onclick="addToCart('Đồng hồ',2500000,'⌚')">Thêm vào giỏ</button>
        </div>
      </div>
    </div>

    <!-- Giỏ hàng -->
    <div class="cart">
      <h2>Giỏ hàng</h2>
      <div class="cart-list" id="cartList">
        <p class="empty">Chưa có sản phẩm</p>
      </div>
      <div class="total"><span>Tổng:</span> <span id="cartTotal">0₫</span></div>
      <button class="checkout">Thanh toán</button>
    </div>
  </div>

  <footer>© 2025 Mini Shop Demo</footer>

  <script>
    let cart = [];

    function addToCart(name, price, icon){
      let item = cart.find(p=>p.name===name);
      if(item){ item.qty++; }
      else{ cart.push({name,price,icon,qty:1}); }
      renderCart();
    }

    function changeQty(name,delta){
      let item = cart.find(p=>p.name===name);
      if(item){
        item.qty += delta;
        if(item.qty<=0) cart = cart.filter(p=>p.name!==name);
        renderCart();
      }
    }

    function renderCart(){
      const list = document.getElementById('cartList');
      const totalEl = document.getElementById('cartTotal');
      const countEl = document.getElementById('cartCount');
      list.innerHTML = '';

      if(cart.length===0){
        list.innerHTML = '<p class="empty">Chưa có sản phẩm</p>';
        totalEl.textContent = '0₫';
        countEl.textContent = '0';
        return;
      }

      let total=0, count=0;
      cart.forEach(p=>{
        total += p.price*p.qty; count += p.qty;
        const div=document.createElement('div');
        div.className='cart-item';
        div.innerHTML=`
          <div class="ci-thumb">${p.icon}</div>
          <div class="ci-info">
            <p class="ci-name">${p.name}</p>
            <p class="ci-meta">${p.price.toLocaleString()}₫</p>
            <div class="qty">
              <button class="q-btn" onclick="changeQty('${p.name}',-1)">-</button>
              <span>${p.qty}</span>
              <button class="q-btn" onclick="changeQty('${p.name}',1)">+</button>
            </div>
          </div>`;
        list.appendChild(div);
      });

      totalEl.textContent = total.toLocaleString()+'₫';
      countEl.textContent = count;
    }
  </script>
</body>
</html>
