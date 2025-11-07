# index.html
<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>BOUTIQUE - Modern KadÄ±n Giyim</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #fce4ec 0%, #ffffff 50%, #f3e5f5 100%);
            min-height: 100vh;
        }

        header {
            background: white;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            position: sticky;
            top: 0;
            z-index: 1000;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        .header-content {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
            flex-wrap: wrap;
            gap: 20px;
        }

        .logo {
            font-size: 28px;
            font-weight: bold;
            background: linear-gradient(135deg, #ec4899, #9333ea);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .nav-categories {
            display: flex;
            gap: 20px;
            flex-wrap: wrap;
        }

        .nav-categories button {
            background: none;
            border: none;
            padding: 8px 16px;
            cursor: pointer;
            font-size: 16px;
            color: #374151;
            transition: all 0.3s;
            text-transform: capitalize;
        }

        .nav-categories button:hover,
        .nav-categories button.active {
            color: #ec4899;
            font-weight: 600;
        }

        .header-icons {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .search-box {
            position: relative;
        }

        .search-box input {
            padding: 10px 40px 10px 15px;
            border: 1px solid #e5e7eb;
            border-radius: 25px;
            width: 250px;
            outline: none;
            transition: all 0.3s;
        }

        .search-box input:focus {
            border-color: #ec4899;
            box-shadow: 0 0 0 3px rgba(236, 72, 153, 0.1);
        }

        .icon-btn {
            position: relative;
            background: none;
            border: none;
            padding: 10px;
            cursor: pointer;
            border-radius: 50%;
            transition: all 0.3s;
        }

        .icon-btn:hover {
            background: #f3f4f6;
        }

        .badge {
            position: absolute;
            top: 0;
            right: 0;
            background: #ec4899;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 12px;
            font-weight: bold;
        }

        .hero {
            background: linear-gradient(135deg, #f472b6, #a855f7, #f472b6);
            color: white;
            text-align: center;
            padding: 80px 20px;
            margin-bottom: 40px;
        }

        .hero h2 {
            font-size: 48px;
            margin-bottom: 20px;
        }

        .hero p {
            font-size: 24px;
            margin-bottom: 30px;
        }

        .hero button {
            background: white;
            color: #ec4899;
            border: none;
            padding: 15px 40px;
            font-size: 18px;
            font-weight: 600;
            border-radius: 30px;
            cursor: pointer;
            transition: all 0.3s;
        }

        .hero button:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0,0,0,0.2);
        }

        .admin-panel {
            background: white;
            border-radius: 15px;
            padding: 30px;
            margin: 30px auto;
            box-shadow: 0 4px 20px rgba(0,0,0,0.1);
            display: none;
        }

        .admin-panel.active {
            display: block;
        }

        .admin-form {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 15px;
            margin-top: 20px;
        }

        .admin-form input,
        .admin-form select {
            padding: 12px;
            border: 1px solid #e5e7eb;
            border-radius: 8px;
            font-size: 16px;
            outline: none;
            transition: all 0.3s;
        }

        .admin-form input:focus,
        .admin-form select:focus {
            border-color: #ec4899;
            box-shadow: 0 0 0 3px rgba(236, 72, 153, 0.1);
        }

        .btn-primary {
            background: linear-gradient(135deg, #ec4899, #9333ea);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 8px;
            font-size: 16px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(236, 72, 153, 0.3);
        }

        .products-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 30px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 60px;
        }

        .product-card {
            background: white;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: all 0.3s;
            position: relative;
        }

        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.15);
        }

        .product-image {
            position: relative;
            overflow: hidden;
            height: 300px;
        }

        .product-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.5s;
        }

        .product-card:hover .product-image img {
            transform: scale(1.1);
        }

        .product-actions {
            position: absolute;
            top: 10px;
            right: 10px;
            display: flex;
            gap: 10px;
        }

        .action-btn {
            background: white;
            border: none;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            transition: all 0.3s;
        }

        .action-btn:hover {
            transform: scale(1.1);
        }

        .action-btn.active {
            background: #ec4899;
            color: white;
        }

        .delete-btn {
            background: #ef4444;
            color: white;
        }

        .stock-badge {
            position: absolute;
            bottom: 10px;
            left: 10px;
            background: rgba(0,0,0,0.6);
            color: white;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 14px;
        }

        .product-info {
            padding: 20px;
        }

        .product-name {
            font-size: 18px;
            font-weight: 600;
            margin-bottom: 10px;
            color: #1f2937;
        }

        .product-footer {
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .product-price {
            font-size: 24px;
            font-weight: bold;
            color: #ec4899;
        }

        .add-to-cart {
            background: linear-gradient(135deg, #ec4899, #9333ea);
            border: none;
            width: 45px;
            height: 45px;
            border-radius: 50%;
            color: white;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s;
        }

        .add-to-cart:hover {
            transform: scale(1.1);
            box-shadow: 0 5px 15px rgba(236, 72, 153, 0.4);
        }

        .cart-sidebar {
            position: fixed;
            right: -100%;
            top: 0;
            width: 400px;
            height: 100vh;
            background: white;
            box-shadow: -5px 0 25px rgba(0,0,0,0.2);
            transition: right 0.3s;
            z-index: 2000;
            overflow-y: auto;
        }

        .cart-sidebar.active {
            right: 0;
        }

        .cart-header {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px;
            border-bottom: 1px solid #e5e7eb;
        }

        .cart-items {
            padding: 20px;
        }

        .cart-item {
            display: flex;
            gap: 15px;
            background: #f9fafb;
            padding: 15px;
            border-radius: 10px;
            margin-bottom: 15px;
        }

        .cart-item img {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 8px;
        }

        .cart-item-info {
            flex: 1;
        }

        .cart-item-name {
            font-weight: 600;
            margin-bottom: 8px;
        }

        .cart-item-price {
            color: #ec4899;
            font-weight: bold;
            margin-bottom: 10px;
        }

        .quantity-controls {
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .quantity-btn {
            background: #e5e7eb;
            border: none;
            width: 30px;
            height: 30px;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
        }

        .quantity-btn:hover {
            background: #d1d5db;
        }

        .remove-btn {
            background: none;
            border: none;
            color: #ef4444;
            cursor: pointer;
            padding: 5px;
        }

        .cart-footer {
            padding: 20px;
            border-top: 1px solid #e5e7eb;
        }

        .cart-total {
            display: flex;
            justify-content: space-between;
            font-size: 20px;
            font-weight: bold;
            margin-bottom: 20px;
        }

        .checkout-btn {
            width: 100%;
            padding: 15px;
            background: linear-gradient(135deg, #ec4899, #9333ea);
            color: white;
            border: none;
            border-radius: 10px;
            font-size: 18px;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .checkout-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 20px rgba(236, 72, 153, 0.3);
        }

        .modal-overlay {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0,0,0,0.5);
            z-index: 3000;
            align-items: center;
            justify-content: center;
            padding: 20px;
        }

        .modal-overlay.active {
            display: flex;
        }

        .checkout-modal {
            background: white;
            border-radius: 15px;
            max-width: 600px;
            width: 100%;
            max-height: 90vh;
            overflow-y: auto;
        }

        .checkout-section {
            background: #f9fafb;
            padding: 20px;
            border-radius: 10px;
            margin-bottom: 20px;
        }

        .checkout-section h3 {
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .checkout-section input,
        .checkout-section textarea {
            width: 100%;
            padding: 12px;
            border: 1px solid #e5e7eb;
            border-radius: 8px;
            margin-bottom: 10px;
            font-size: 16px;
        }

        .empty-cart {
            text-align: center;
            padding: 60px 20px;
            color: #9ca3af;
        }

        .order-item {
            display: flex;
            justify-content: space-between;
            font-size: 14px;
            margin-bottom: 8px;
        }

        .order-total {
            display: flex;
            justify-content: space-between;
            font-weight: bold;
            font-size: 18px;
            margin-top: 15px;
            padding-top: 15px;
            border-top: 2px solid #e5e7eb;
            color: #ec4899;
        }

        @media (max-width: 768px) {
            .search-box {
                width: 100%;
            }
            
            .search-box input {
                width: 100%;
            }

            .cart-sidebar {
                width: 100%;
            }

            .hero h2 {
                font-size: 32px;
            }

            .hero p {
                font-size: 18px;
            }

            .nav-categories {
                width: 100%;
                justify-content: center;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="header-content">
                <div class="logo">BOUTIQUE</div>
                
                <nav class="nav-categories" id="navCategories"></nav>
                
                <div class="header-icons">
                    <div class="search-box">
                        <input type="text" id="searchInput" placeholder="ÃœrÃ¼n ara...">
                    </div>
                    
                    <button class="icon-btn" id="adminBtn" title="YÃ¶netim Paneli">
                        <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 21v-2a4 4 0 0 0-4-4H8a4 4 0 0 0-4 4v2"></path><circle cx="12" cy="7" r="4"></circle></svg>
                    </button>
                    
                    <button class="icon-btn" id="favBtn" title="Favoriler">
                        <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>
                        <span class="badge" id="favBadge" style="display: none;">0</span>
                    </button>
                    
                    <button class="icon-btn" id="cartBtn" title="Sepet">
                        <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>
                        <span class="badge" id="cartBadge" style="display: none;">0</span>
                    </button>
                </div>
            </div>
        </div>
    </header>

    <div class="hero" id="heroBanner">
        <h2>Yeni Sezon Koleksiyonu</h2>
        <p>%50'ye Varan Ä°ndirimler</p>
        <button>AlÄ±ÅŸveriÅŸe BaÅŸla</button>
    </div>

    <div class="container">
        <div class="admin-panel" id="adminPanel">
            <h2>YÃ¶netim Paneli - ÃœrÃ¼n Ekle</h2>
            <div class="admin-form">
                <input type="text" id="productName" placeholder="ÃœrÃ¼n AdÄ±">
                <input type="number" id="productPrice" placeholder="Fiyat (TL)">
                <select id="productCategory">
                    <option value="bluz">Bluz</option>
                    <option value="pantolon">Pantolon</option>
                    <option value="kazak">Kazak</option>
                    <option value="etek">Etek</option>
                    <option value="ceket">Ceket</option>
                    <option value="elbise">Elbise</option>
                    <option value="hirka">HÄ±rka</option>
                </select>
                <input type="text" id="productImage" placeholder="GÃ¶rsel URL">
                <input type="number" id="productStock" placeholder="Stok Adedi">
                <button class="btn-primary" onclick="addProduct()">ÃœrÃ¼n Ekle</button>
            </div>
        </div>
    </div>

    <div class="container">
        <div class="products-header">
            <h2 id="productsTitle">TÃ¼m ÃœrÃ¼nler</h2>
            <span id="productCount">0 Ã¼rÃ¼n</span>
        </div>
        <div class="products-grid" id="productsGrid"></div>
    </div>

    <div class="cart-sidebar" id="cartSidebar">
        <div class="cart-header">
            <h2>Sepetim</h2>
            <button class="icon-btn" onclick="toggleCart()">
                <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
            </button>
        </div>
        <div class="cart-items" id="cartItems"></div>
        <div class="cart-footer" id="cartFooter" style="display: none;">
            <div class="cart-total">
                <span>Toplam:</span>
                <span id="cartTotal">0.00 TL</span>
            </div>
            <button class="checkout-btn" onclick="openCheckout()">Ã–demeye GeÃ§</button>
        </div>
    </div>

    <div class="modal-overlay" id="checkoutModal">
        <div class="checkout-modal">
            <div class="cart-header">
                <h2>Ã–deme</h2>
                <button class="icon-btn" onclick="closeCheckout()">
                    <svg width="24" height="24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><line x1="18" y1="6" x2="6" y2="18"></line><line x1="6" y1="6" x2="18" y2="18"></line></svg>
                </button>
            </div>
            
            <div style="padding: 20px;">
                <div class="checkout-section">
                    <h3>
                        <svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M21 10c0 7-9 13-9 13s-9-6-9-13a9 9 0 0 1 18 0z"></path><circle cx="12" cy="10" r="3"></circle></svg>
                        Teslimat Adresi
                    </h3>
                    <input type="text" placeholder="Ad Soyad">
                    <input type="tel" placeholder="Telefon">
                    <textarea placeholder="Adres" rows="3"></textarea>
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
                        <input type="text" placeholder="Ä°l">
                        <input type="text" placeholder="Ä°lÃ§e">
                    </div>
                </div>

                <div class="checkout-section">
                    <h3>
                        <svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="1" y="4" width="22" height="16" rx="2" ry="2"></rect><line x1="1" y1="10" x2="23" y2="10"></line></svg>
                        Ã–deme Bilgileri
                    </h3>
                    <input type="text" placeholder="Kart Ãœzerindeki Ä°sim">
                    <input type="text" placeholder="Kart NumarasÄ±">
                    <div style="display: grid; grid-template-columns: 1fr 1fr; gap: 10px;">
                        <input type="text" placeholder="AA/YY">
                        <input type="text" placeholder="CVV">
                    </div>
                </div>

                <div class="checkout-section">
                    <h3>SipariÅŸ Ã–zeti</h3>
                    <div id="orderSummary"></div>
                </div>

                <button class="checkout-btn" onclick="completeOrder()">SipariÅŸi Tamamla</button>
            </div>
        </div>
    </div>

    <script>
        let products = [
            { id: 1, name: 'Saten Bluz', price: 299, category: 'bluz', image: 'https://images.unsplash.com/photo-1485968579580-b6d095142e6e?w=400', stock: 10 },
            { id: 2, name: 'YÃ¼ksek Bel Pantolon', price: 449, category: 'pantolon', image: 'https://images.unsplash.com/photo-1506629082955-511b1aa562c8?w=400', stock: 8 },
            { id: 3, name: 'Triko Kazak', price: 379, category: 'kazak', image: 'https://images.unsplash.com/photo-1434389677669-e08b4cac3105?w=400', stock: 15 },
            { id: 4, name: 'Mini Etek', price: 259, category: 'etek', image: 'https://images.unsplash.com/photo-1583496661160-fb5886a0aaaa?w=400', stock: 12 },
            { id: 5, name: 'Blazer Ceket', price: 699, category: 'ceket', image: 'https://images.unsplash.com/photo-1591047139829-d91aecb6caea?w=400', stock: 6 },
            { id: 6, name: 'Åžifon Elbise', price: 549, category: 'elbise', image: 'https://images.unsplash.com/photo-1595777457583-95e059d581b8?w=400', stock: 9 },
            { id: 7, name: 'Denim Ceket', price: 429, category: 'ceket', image: 'https://images.unsplash.com/photo-1551028719-00167b16eac5?w=400', stock: 11 },
            { id: 8, name: 'Ã–rme HÄ±rka', price: 349, category: 'hirka', image: 'https://images.unsplash.com/photo-1515886657613-9f3515b0c78f?w=400', stock: 14 }
        ];

        let cart = [];
        let favorites = [];
        let selectedCategory = 'tÃ¼mÃ¼';
        let searchTerm = '';

        const categories = ['tÃ¼mÃ¼', 'bluz', 'pantolon', 'kazak', 'etek', 'ceket', 'elbise', 'hirka'];

        function init() {
            renderCategories();
            renderProducts();
            updateCartBadge();
            updateFavBadge();

            document.getElementById('searchInput').addEventListener('input', function(e) {
                searchTerm = e.target.value;
                renderProducts();
            });

            document.getElementById('adminBtn').addEventListener('click', toggleAdmin);
            document.getElementById('cartBtn').addEventListener('click', toggleCart);
        }

        function renderCategories() {
            const nav = document.getElementById('navCategories');
            nav.innerHTML = categories.map(function(cat) {
                const activeClass = selectedCategory === cat ? 'active' : '';
                return '<button class="' + activeClass + '" onclick="selectCategory(\'' + cat + '\')">' + cat + '</button>';
            }).join('');
        }

        function selectCategory(category) {
            selectedCategory = category;
            renderCategories();
            renderProducts();
        }

        function renderProducts() {
            const grid = document.getElementById('productsGrid');
            const filtered = products.filter(function(p) {
                const matchCategory = selectedCategory === 'tÃ¼mÃ¼' || p.category === selectedCategory;
                const matchSearch = p.name.toLowerCase().includes(searchTerm.toLowerCase());
                return matchCategory && matchSearch;
            });

            const title = selectedCategory === 'tÃ¼mÃ¼' ? 'TÃ¼m ÃœrÃ¼nler' : selectedCategory.charAt(0).toUpperCase() + selectedCategory.slice(1);
            document.getElementById('productsTitle').textContent = title;
            document.getElementById('productCount').textContent = filtered.length + ' Ã¼rÃ¼n';

            grid.innerHTML = filtered.map(function(p) {
                const isFav = favorites.includes(p.id);
                const favFill = isFav ? 'currentColor' : 'none';
                const favClass = isFav ? 'active' : '';
                const isAdmin = document.getElementById('adminPanel').classList.contains('active');
                const deleteBtn = isAdmin ? '<button class="action-btn delete-btn" onclick="deleteProduct(' + p.id + ')"><svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2"><polyline points="3 6 5 6 21 6"></polyline><path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"></path></svg></button>' : '';

                return '<div class="product-card">' +
                    '<div class="product-image">' +
                        '<img src="' + p.image + '" alt="' + p.name + '">' +
                        '<div class="product-actions">' +
                            deleteBtn +
                            '<button class="action-btn ' + favClass + '" onclick="toggleFavorite(' + p.id + ')">' +
                                '<svg width="20" height="20" fill="' + favFill + '" stroke="currentColor" stroke-width="2"><path d="M20.84 4.61a5.5 5.5 0 0 0-7.78 0L12 5.67l-1.06-1.06a5.5 5.5 0 0 0-7.78 7.78l1.06 1.06L12 21.23l7.78-7.78 1.06-1.06a5.5 5.5 0 0 0 0-7.78z"></path></svg>' +
                            '</button>' +
                        '</div>' +
                        '<div class="stock-badge">Stok: ' + p.stock + '</div>' +
                    '</div>' +
                    '<div class="product-info">' +
                        '<div class="product-name">' + p.name + '</div>' +
                        '<div class="product-footer">' +
                            '<div class="product-price">' + p.price + ' TL</div>' +
                            '<button class="add-to-cart" onclick="addToCart(' + p.id + ')">' +
                                '<svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>' +
                            '</button>' +
                        '</div>' +
                    '</div>' +
                '</div>';
            }).join('');
        }

        function addToCart(productId) {
            const product = products.find(function(p) { return p.id === productId; });
            if (!product) return;

            const existingItem = cart.find(function(item) { return item.id === productId; });
            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({
                    id: product.id,
                    name: product.name,
                    price: product.price,
                    image: product.image,
                    quantity: 1
                });
            }

            updateCartBadge();
            renderCart();
        }

        function removeFromCart(productId) {
            cart = cart.filter(function(item) { return item.id !== productId; });
            updateCartBadge();
            renderCart();
        }

        function updateQuantity(productId, delta) {
            const item = cart.find(function(i) { return i.id === productId; });
            if (item) {
                item.quantity += delta;
                if (item.quantity <= 0) {
                    removeFromCart(productId);
                } else {
                    renderCart();
                }
            }
        }

        function toggleFavorite(productId) {
            const index = favorites.indexOf(productId);
            if (index > -1) {
                favorites.splice(index, 1);
            } else {
                favorites.push(productId);
            }
            updateFavBadge();
            renderProducts();
        }

        function addProduct() {
            const name = document.getElementById('productName').value;
            const price = parseFloat(document.getElementById('productPrice').value);
            const category = document.getElementById('productCategory').value;
            const image = document.getElementById('productImage').value;
            const stock = parseInt(document.getElementById('productStock').value);

            if (name && price && image && stock) {
                const newId = products.length > 0 ? Math.max.apply(Math, products.map(function(p) { return p.id; })) + 1 : 1;
                products.push({
                    id: newId,
                    name: name,
                    price: price,
                    category: category,
                    image: image,
                    stock: stock
                });

                document.getElementById('productName').value = '';
                document.getElementById('productPrice').value = '';
                document.getElementById('productImage').value = '';
                document.getElementById('productStock').value = '';

                renderProducts();
                alert('ÃœrÃ¼n baÅŸarÄ±yla eklendi!');
            } else {
                alert('LÃ¼tfen tÃ¼m alanlarÄ± doldurun!');
            }
        }

        function deleteProduct(productId) {
            if (confirm('Bu Ã¼rÃ¼nÃ¼ silmek istediÄŸinize emin misiniz?')) {
                products = products.filter(function(p) { return p.id !== productId; });
                cart = cart.filter(function(item) { return item.id !== productId; });
                renderProducts();
                renderCart();
            }
        }

        function toggleAdmin() {
            const panel = document.getElementById('adminPanel');
            const hero = document.getElementById('heroBanner');
            panel.classList.toggle('active');
            hero.style.display = panel.classList.contains('active') ? 'none' : 'block';
            renderProducts();
        }

        function toggleCart() {
            const sidebar = document.getElementById('cartSidebar');
            sidebar.classList.toggle('active');
            if (sidebar.classList.contains('active')) {
                renderCart();
            }
        }

        function renderCart() {
            const cartItems = document.getElementById('cartItems');
            const cartFooter = document.getElementById('cartFooter');

            if (cart.length === 0) {
                cartItems.innerHTML = '<div class="empty-cart">' +
                    '<svg width="64" height="64" fill="none" stroke="currentColor" stroke-width="2" style="margin: 0 auto 20px;"><circle cx="9" cy="21" r="1"></circle><circle cx="20" cy="21" r="1"></circle><path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"></path></svg>' +
                    '<p>Sepetiniz boÅŸ</p>' +
                    '</div>';
                cartFooter.style.display = 'none';
            } else {
                cartItems.innerHTML = cart.map(function(item) {
                    return '<div class="cart-item">' +
                        '<img src="' + item.image + '" alt="' + item.name + '">' +
                        '<div class="cart-item-info">' +
                            '<div class="cart-item-name">' + item.name + '</div>' +
                            '<div class="cart-item-price">' + item.price + ' TL</div>' +
                            '<div class="quantity-controls">' +
                                '<button class="quantity-btn" onclick="updateQuantity(' + item.id + ', -1)">-</button>' +
                                '<span>' + item.quantity + '</span>' +
                                '<button class="quantity-btn" onclick="updateQuantity(' + item.id + ', 1)">+</button>' +
                                '<button class="remove-btn" onclick="removeFromCart(' + item.id + ')">' +
                                    '<svg width="18" height="18" fill="none" stroke="currentColor" stroke-width="2"><polyline points="3 6 5 6 21 6"></polyline><path d="M19 6v14a2 2 0 0 1-2 2H7a2 2 0 0 1-2-2V6m3 0V4a2 2 0 0 1 2-2h4a2 2 0 0 1 2 2v2"></path></svg>' +
                                '</button>' +
                            '</div>' +
                        '</div>' +
                    '</div>';
                }).join('');

                const total = cart.reduce(function(sum, item) { return sum + item.price * item.quantity; }, 0);
                document.getElementById('cartTotal').textContent = total.toFixed(2) + ' TL';
                cartFooter.style.display = 'block';
            }
        }

        function updateCartBadge() {
            const badge = document.getElementById('cartBadge');
            const total = cart.reduce(function(sum, item) { return sum + item.quantity; }, 0);
            if (total > 0) {
                badge.textContent = total;
                badge.style.display = 'flex';
            } else {
                badge.style.display = 'none';
            }
        }

        function updateFavBadge() {
            const badge = document.getElementById('favBadge');
            if (favorites.length > 0) {
                badge.textContent = favorites.length;
                badge.style.display = 'flex';
            } else {
                badge.style.display = 'none';
            }
        }

        function openCheckout() {
            const modal = document.getElementById('checkoutModal');
            const summary = document.getElementById('orderSummary');

            summary.innerHTML = cart.map(function(item) {
                return '<div class="order-item">' +
                    '<span>' + item.name + ' x' + item.quantity + '</span>' +
                    '<span>' + (item.price * item.quantity).toFixed(2) + ' TL</span>' +
                '</div>';
            }).join('');

            const total = cart.reduce(function(sum, item) { return sum + item.price * item.quantity; }, 0);
            summary.innerHTML += '<div class="order-total">' +
                '<span>Toplam:</span>' +
                '<span>' + total.toFixed(2) + ' TL</span>' +
            '</div>';

            modal.classList.add('active');
            toggleCart();
        }

        function closeCheckout() {
            document.getElementById('checkoutModal').classList.remove('active');
        }

        function completeOrder() {
            alert('SipariÅŸiniz alÄ±ndÄ±! TeÅŸekkÃ¼r ederiz.');
            cart = [];
            updateCartBadge();
            renderCart();
            closeCheckout();
        }

        init();
    </script>
</body>
</html>
