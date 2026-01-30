<!DOCTYPE html>
<html lang="sq">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>ProGamingTech - Paisje Gaming Premium</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: #0f0f1a;
            color: #f0f0f0;
            line-height: 1.6;
        }

        header {
            background: linear-gradient(135deg, #1a1a2e 0%, #16213e 100%);
            padding: 1.5rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            display: flex;
            align-items: center;
            gap: 15px;
        }

        .logo i {
            font-size: 2.5rem;
            color: #6c63ff;
        }

        .logo h1 {
            font-size: 1.8rem;
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            font-weight: 800;
        }

        nav ul {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        nav a {
            color: #f0f0f0;
            text-decoration: none;
            font-weight: 600;
            transition: color 0.3s;
            font-size: 1.1rem;
        }

        nav a:hover {
            color: #6c63ff;
        }

        .cart-icon {
            position: relative;
            cursor: pointer;
            font-size: 1.5rem;
            color: #6c63ff;
        }

        .cart-count {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: #ff6b9d;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            font-size: 0.8rem;
            font-weight: bold;
        }

        .hero {
            background: linear-gradient(rgba(15, 15, 26, 0.9), rgba(22, 33, 62, 0.9)), url('https://images.unsplash.com/photo-1593305841991-05c297ba4575?ixlib=rb-4.0.3&auto=format&fit=crop&w=1200&q=80');
            background-size: cover;
            background-position: center;
            padding: 5rem 5%;
            text-align: center;
            margin-bottom: 3rem;
        }

        .hero h2 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .hero p {
            font-size: 1.2rem;
            max-width: 700px;
            margin: 0 auto 2rem;
            color: #d0d0e0;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 5%;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.2rem;
            position: relative;
        }

        .section-title:after {
            content: '';
            display: block;
            width: 80px;
            height: 4px;
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            margin: 10px auto;
            border-radius: 2px;
        }

        .category-filter {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 1rem;
            margin-bottom: 2.5rem;
        }

        .category-btn {
            padding: 0.6rem 1.5rem;
            background: #1a1a2e;
            border: 2px solid #262640;
            border-radius: 30px;
            color: #f0f0f0;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .category-btn:hover, .category-btn.active {
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            border-color: transparent;
        }

        .products {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
            gap: 2.5rem;
            margin-bottom: 4rem;
        }

        .product-card {
            background: #1a1a2e;
            border-radius: 12px;
            overflow: hidden;
            transition: transform 0.3s, box-shadow 0.3s;
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.3);
            display: flex;
            flex-direction: column;
        }

        .product-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(108, 99, 255, 0.25);
        }

        .product-image {
            height: 220px;
            width: 100%;
            object-fit: cover;
            border-bottom: 3px solid #6c63ff;
        }

        .product-info {
            padding: 1.5rem;
            flex-grow: 1;
            display: flex;
            flex-direction: column;
        }

        .product-title {
            font-size: 1.3rem;
            margin-bottom: 0.5rem;
            color: #f0f0f0;
            min-height: 3.5rem;
        }

        .product-description {
            color: #b0b0c0;
            margin-bottom: 1rem;
            font-size: 0.95rem;
            flex-grow: 1;
        }

        .product-price {
            font-size: 1.6rem;
            font-weight: 700;
            color: #6c63ff;
            margin-bottom: 1.2rem;
        }

        .buy-btn {
            display: block;
            width: 100%;
            padding: 12px;
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            text-decoration: none;
            margin-top: auto;
        }

        .buy-btn:hover {
            background: linear-gradient(to right, #5a52d5, #e55a8a);
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.4);
        }

        .buy-btn i {
            margin-right: 8px;
        }

        /* Modal Styling */
        .modal-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: rgba(0, 0, 0, 0.8);
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 1000;
            opacity: 0;
            visibility: hidden;
            transition: opacity 0.3s, visibility 0.3s;
        }

        .modal-overlay.active {
            opacity: 1;
            visibility: visible;
        }

        .modal {
            background: #1a1a2e;
            border-radius: 15px;
            width: 90%;
            max-width: 800px;
            max-height: 90vh;
            overflow-y: auto;
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.5);
            transform: translateY(-20px);
            transition: transform 0.3s;
        }

        .modal-overlay.active .modal {
            transform: translateY(0);
        }

        .modal-header {
            padding: 1.5rem 2rem;
            border-bottom: 2px solid #262640;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        .modal-title {
            font-size: 1.8rem;
            color: #6c63ff;
        }

        .close-btn {
            background: none;
            border: none;
            color: #f0f0f0;
            font-size: 1.8rem;
            cursor: pointer;
            transition: color 0.3s;
        }

        .close-btn:hover {
            color: #ff6b9d;
        }

        .modal-body {
            padding: 2rem;
        }

        /* Cart Styling */
        .cart-items {
            margin-bottom: 2rem;
        }

        .cart-item {
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 1rem;
            border-bottom: 1px solid #262640;
        }

        .cart-item-info {
            display: flex;
            align-items: center;
            gap: 1rem;
        }

        .cart-item-image {
            width: 80px;
            height: 80px;
            object-fit: cover;
            border-radius: 8px;
            border: 2px solid #6c63ff;
        }

        .cart-item-name {
            font-weight: 600;
            font-size: 1.1rem;
        }

        .cart-item-price {
            color: #6c63ff;
            font-weight: 700;
        }

        .cart-item-quantity {
            display: flex;
            align-items: center;
            gap: 0.5rem;
        }

        .quantity-btn {
            background: #262640;
            border: none;
            color: #f0f0f0;
            width: 30px;
            height: 30px;
            border-radius: 50%;
            cursor: pointer;
            font-weight: bold;
            transition: background 0.3s;
        }

        .quantity-btn:hover {
            background: #6c63ff;
        }

        .quantity-value {
            font-weight: 600;
            min-width: 30px;
            text-align: center;
        }

        .remove-item {
            background: #ff3b3b;
            color: white;
            border: none;
            border-radius: 5px;
            padding: 5px 10px;
            cursor: pointer;
            transition: background 0.3s;
        }

        .remove-item:hover {
            background: #ff0000;
        }

        .cart-summary {
            background: #262640;
            border-radius: 10px;
            padding: 1.5rem;
            margin-bottom: 1.5rem;
        }

        .summary-row {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.8rem;
            font-size: 1.1rem;
        }

        .total-row {
            font-size: 1.4rem;
            font-weight: 700;
            color: #6c63ff;
            border-top: 2px solid #6c63ff;
            padding-top: 1rem;
            margin-top: 1rem;
        }

        .checkout-btn {
            display: block;
            width: 100%;
            padding: 15px;
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            color: white;
            border: none;
            border-radius: 8px;
            font-size: 1.2rem;
            font-weight: 700;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
            text-decoration: none;
        }

        .checkout-btn:hover {
            background: linear-gradient(to right, #5a52d5, #e55a8a);
            box-shadow: 0 5px 20px rgba(108, 99, 255, 0.5);
        }

        /* Payment Form Styling */
        .payment-form {
            display: none;
        }

        .payment-form.active {
            display: block;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #b0b0c0;
        }

        .form-input {
            width: 100%;
            padding: 12px 15px;
            background: #262640;
            border: 2px solid #363650;
            border-radius: 8px;
            color: #f0f0f0;
            font-size: 1rem;
            transition: border-color 0.3s;
        }

        .form-input:focus {
            border-color: #6c63ff;
            outline: none;
        }

        .form-row {
            display: flex;
            gap: 1rem;
        }

        .form-row .form-group {
            flex: 1;
        }

        .payment-methods {
            display: flex;
            gap: 1rem;
            margin-bottom: 1.5rem;
        }

        .payment-method {
            flex: 1;
            text-align: center;
            padding: 1rem;
            background: #262640;
            border-radius: 8px;
            cursor: pointer;
            transition: all 0.3s;
            border: 2px solid transparent;
        }

        .payment-method:hover {
            background: #2d2d4a;
        }

        .payment-method.active {
            border-color: #6c63ff;
            background: #2d2d4a;
        }

        .payment-method i {
            font-size: 2rem;
            margin-bottom: 0.5rem;
            color: #6c63ff;
        }

        .back-to-cart {
            background: #363650;
            color: #f0f0f0;
            border: none;
            border-radius: 8px;
            padding: 10px 20px;
            cursor: pointer;
            font-weight: 600;
            transition: background 0.3s;
            margin-right: 1rem;
        }

        .back-to-cart:hover {
            background: #6c63ff;
        }

        .submit-payment {
            background: linear-gradient(to right, #6c63ff, #ff6b9d);
            color: white;
            border: none;
            border-radius: 8px;
            padding: 12px 30px;
            font-size: 1.1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .submit-payment:hover {
            background: linear-gradient(to right, #5a52d5, #e55a8a);
            box-shadow: 0 5px 15px rgba(108, 99, 255, 0.4);
        }

        .form-actions {
            display: flex;
            justify-content: flex-end;
            margin-top: 2rem;
        }

        footer {
            background: #1a1a2e;
            padding: 3rem 5% 2rem;
            margin-top: 4rem;
            border-top: 3px solid #6c63ff;
        }

        .footer-content {
            display: flex;
            flex-wrap: wrap;
            justify-content: space-between;
            gap: 2rem;
            margin-bottom: 2rem;
        }

        .footer-column {
            flex: 1;
            min-width: 250px;
        }

        .footer-column h3 {
            color: #6c63ff;
            margin-bottom: 1.2rem;
            font-size: 1.3rem;
        }

        .footer-column p, .footer-column a {
            color: #b0b0c0;
            margin-bottom: 0.8rem;
            display: block;
            text-decoration: none;
            transition: color 0.3s;
        }

        .footer-column a:hover {
            color: #6c63ff;
        }

        .social-icons {
            display: flex;
            gap: 1rem;
            margin-top: 1rem;
        }

        .social-icons a {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            background: #262640;
            border-radius: 50%;
            color: #f0f0f0;
            font-size: 1.2rem;
            transition: all 0.3s;
        }

        .social-icons a:hover {
            background: #6c63ff;
            transform: translateY(-3px);
        }

        .copyright {
            text-align: center;
            padding-top: 2rem;
            border-top: 1px solid #262640;
            color: #8888a0;
            font-size: 0.9rem;
        }

        .notification {
            position: fixed;
            bottom: 20px;
            right: 20px;
            background: #1a1a2e;
            color: white;
            padding: 1rem 1.5rem;
            border-radius: 8px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
            border-left: 4px solid #6c63ff;
            transform: translateX(150%);
            transition: transform 0.5s;
            z-index: 1000;
            max-width: 300px;
        }

        .notification.show {
            transform: translateX(0);
        }

        .success-message {
            display: none;
            text-align: center;
            padding: 3rem 2rem;
        }

        .success-message.active {
            display: block;
        }

        .success-icon {
            font-size: 4rem;
            color: #4CAF50;
            margin-bottom: 1.5rem;
        }

        .product-category {
            font-size: 0.85rem;
            color: #ff6b9d;
            font-weight: 600;
            margin-bottom: 0.5rem;
            text-transform: uppercase;
        }

        @media (max-width: 768px) {
            header {
                flex-direction: column;
                gap: 1rem;
                padding: 1rem 5%;
            }
            
            nav ul {
                flex-wrap: wrap;
                justify-content: center;
                gap: 1rem;
            }
            
            .hero h2 {
                font-size: 2.2rem;
            }
            
            .hero p {
                font-size: 1rem;
            }
            
            .products {
                grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            }
            
            .cart-item {
                flex-direction: column;
                align-items: flex-start;
                gap: 1rem;
            }
            
            .cart-item-info {
                width: 100%;
            }
            
            .form-row {
                flex-direction: column;
                gap: 0;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="logo">
            <i class="fas fa-gamepad"></i>
            <h1>ProGamingTech</h1>
        </div>
        <nav>
            <ul>
                <li><a href="#"><i class="fas fa-home"></i> Kryefaqja</a></li>
                <li><a href="#products"><i class="fas fa-headset"></i> Produktet</a></li>
                <li><a href="#"><i class="fas fa-info-circle"></i> Rreth Nesh</a></li>
                <li><a href="#"><i class="fas fa-phone"></i> Kontakt</a></li>
            </ul>
        </nav>
        <div class="cart-icon" id="cartIcon">
            <i class="fas fa-shopping-cart"></i>
            <span class="cart-count" id="cartCount">0</span>
        </div>
    </header>

    <section class="hero">
        <div class="container">
            <h2>Paisje Gaming të Niveltit Më të Lartë</h2>
            <p>Zbuloni koleksionin tonë të paisjeve gaming me cilësi premium për një përvojë lojërash të përsosur. Performanca ekstreme, dizajn ergonomik dhe qëndrueshmëri e provuar.</p>
        </div>
    </section>

    <main class="container">
        <h2 class="section-title" id="products">Produktet Tona</h2>
        
        <div class="category-filter">
            <button class="category-btn active" data-category="all">Të Gjitha</button>
            <button class="category-btn" data-category="periferike">Periferike</button>
            <button class="category-btn" data-category="monitor">Monitorë</button>
            <button class="category-btn" data-category="komponente">Komponente</button>
            <button class="category-btn" data-category="aksesore">Aksesore</button>
            <button class="category-btn" data-category="karrige">Karrige Gaming</button>
        </div>
        
        <div class="products">
            <!-- PRODUKTET E VJETRA -->
            
            <!-- Produkti 1 -->
            <div class="product-card" data-id="1" data-name="Mouse Gaming RGB Pro-X" data-price="49.99" data-image="https://images.unsplash.com/photo-1542291026-7eec264c27ff?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="periferike">
                <img src="https://m.media-amazon.com/images/I/61mLJPSwyGL._AC_UF1000,1000_QL80_.jpg" alt="Mouse Gaming RGB" class="product-image">
                <div class="product-info">
                    <div class="product-category">Periferike</div>
                    <h3 class="product-title">Mouse Gaming RGB Pro-X</h3>
                    <p class="product-description">Mouse me sensor 16000 DPI, 8 butona të programueshëm, iluminim RGB dhe design ergonomik për lojëra të gjata.</p>
                    <div class="product-price">49.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 2 -->
            <div class="product-card" data-id="2" data-name="Tastierë Mekanike Thunder K7" data-price="89.99" data-image="https://images.unsplash.com/photo-1600086827875-7a8d42d7c9a9?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="periferike">
                <img src="https://aztechonline.com/cache/large/product/5986/EnbOGRcpkAbtlTQd4aPbSYHJNS2IT79zdjB2ituY.png" alt="Tastierë Mekanike" class="product-image">
                <div class="product-info">
                    <div class="product-category">Periferike</div>
                    <h3 class="product-title">Tastierë Mekanike Thunder K7</h3>
                    <p class="product-description">Tastierë mekanike me çelsha RGB, anti-ghosting, kushinë doreze dhe butona multimediale. Përgjigje e shpejtë për gaming kompetitiv.</p>
                    <div class="product-price">89.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 3 -->
            <div class="product-card" data-id="3" data-name="Kufje Gaming Sonic 7.1" data-price="79.99" data-image="https://images.unsplash.com/photo-1585298721221-4652e5d5e61c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="periferike">
                <img src="https://e-baa.com/new/public/uploads/all/U7ClTvM9fesmJF1W8GWBHCTCTGv89NeMrnXjHMKB.webp" alt="Kufje Gaming 7.1" class="product-image">
                <div class="product-info">
                    <div class="product-category">Periferike</div>
                    <h3 class="product-title">Kufje Gaming Sonic 7.1</h3>
                    <p class="product-description">Kufje me audio surround 7.1, mikrofon me anulim të zhurmës, ndjeshmëri e lartë dhe mbështjellës të rehatshëm për veshët.</p>
                    <div class="product-price">79.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 4 -->
            <div class="product-card" data-id="4" data-name="Monitor Gaming 27\" 144Hz" data-price="329.99" data-image="https://images.unsplash.com/photo-1591799264318-7e6ef8ddb7ea?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="monitor">
                <img src="https://assets.shpresa.al/shop/2023/06/b4b3e29d-cng3684-b-2.jpg" alt="Monitor Gaming 144Hz" class="product-image">
                <div class="product-info">
                    <div class="product-category">Monitorë</div>
                    <h3 class="product-title">Monitor Gaming 27" 144Hz</h3>
                    <p class="product-description">Monitor 27 inç me shpejtësi rifreskimi 144Hz, kohë përgjigjeje 1ms, rezolucion QHD dhe teknologji AMD FreeSync për imazhe të qeta.</p>
                    <div class="product-price">329.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 5 -->
            <div class="product-card" data-id="5" data-name="Karrige Gaming Elite Pro" data-price="199.99" data-image="https://images.unsplash.com/photo-1593640408182-31c70c8268f5?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="karrige">
                <img src="https://buzistore.com/wp-content/uploads/nc/s-mjqaafwwmi/product_images/o/096/bc6c67eff7022cc082f593d42fb3f213-hi__82863.jpg" alt="Karrige Gaming" class="product-image">
                <div class="product-info">
                    <div class="product-category">Karrige Gaming</div>
                    <h3 class="product-title">Karrige Gaming Elite Pro</h3>
                    <p class="product-description">Karrige gaming ergonomike me mbështetje për kokë dhe bel, rrotullime 360°, lartësi e rregullueshme dhe materiale të cilësisë së lartë.</p>
                    <div class="product-price">199.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 6 -->
            <div class="product-card" data-id="6" data-name="Tablet Gaming X-Pad" data-price="199.99" data-image="https://images.unsplash.com/photo-1600003263720-95b45a4035d5?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="periferike">
                <img src="https://mynexttablet.com/wp-content/uploads/2023/12/samsung-s9-fortnite.jpg" alt="Tablet Gaming" class="product-image">
                <div class="product-info">
                    <div class="product-category">Periferike</div>
                    <h3 class="product-title">Tablet Gaming X-Pad</h3>
                    <p class="product-description">Tablet me saktësi të lartë për lojëra, sipërfaqe e madhe, butona të programueshëm dhe ndërfaqe USB me shpejtësi të lartë.</p>
                    <div class="product-price">199.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- PRODUKTET E REJA -->
            
            <!-- Produkti 7 -->
            <div class="product-card" data-id="7" data-name="RTX 4090 Gaming GPU" data-price="1799.99" data-image="https://images.unsplash.com/photo-1591488320449-011701bb6704?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="komponente">
                <img src="https://images.unsplash.com/photo-1591488320449-011701bb6704?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="RTX 4090 GPU" class="product-image">
                <div class="product-info">
                    <div class="product-category">Komponente</div>
                    <h3 class="product-title">RTX 4090 Gaming GPU</h3>
                    <p class="product-description">Kartë grafike NVIDIA RTX 4090 me 24GB VRAM, ray tracing dhe DLSS 3.0 për performancë ekstreme në lojërat 4K.</p>
                    <div class="product-price">1799.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 8 -->
            <div class="product-card" data-id="8" data-name="SSD NVMe 2TB Ultra" data-price="149.99" data-image="https://images.unsplash.com/photo-1591798454113-023d737d1fcc?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="komponente">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcR_LbA87hkeKccuBoayAplU7W6erlNwWdQ-6A&s" alt="SSD NVMe 2TB" class="product-image">
                <div class="product-info">
                    <div class="product-category">Komponente</div>
                    <h3 class="product-title">wireless controller</h3>
                    <p class="product-description">Një wireless controller sjell liri totale në lojë, dizajn ergonomik dhe reagim të shpejtë për një eksperiencë lojërash pa kufij, pa kabllo dhe pa vonesa. </p>
                    <div class="product-price">149.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 9 -->
            <div class="product-card" data-id="9" data-name="Webcam 4K Streaming" data-price="129.99" data-image="https://images.unsplash.com/photo-1614680376573-df3480f0c6ff?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="aksesore">
                <img src="https://m.media-amazon.com/images/I/61WQr6U3mwL._AC_UF894,1000_QL80_.jpg" alt="Webcam 4K" class="product-image">
                <div class="product-info">
                    <div class="product-category">Aksesore</div>
                    <h3 class="product-title">Webcam 4K Streaming</h3>
                    <p class="product-description">Webcam 4K me mikrofon stereo integruar, autofokus dhe teknologji HDR për transmetime me cilësi të lartë.</p>
                    <div class="product-price">129.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 10 -->
            <div class="product-card" data-id="10" data-name="Monitor Ultrawide 34\"" data-price="699.99" data-image="https://images.unsplash.com/photo-1541140532154-b024d705b90a?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="monitor">
                <img src="https://i.rtings.com/assets/pages/I3j8zFmb/best-uw-gaming-monitors-20230802-medium.jpg?format=auto" alt="Monitor Ultrawide" class="product-image">
                <div class="product-info">
                    <div class="product-category">Monitorë</div>
                    <h3 class="product-title">Monitor Ultrawide 34"</h3>
                    <p class="product-description">Monitor ultrawide 34 inç me rezolucion 3440x1440, refresh rate 144Hz dhe teknologji HDR400 për përvojë gaming immersive.</p>
                    <div class="product-price">699.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 11 -->
            <div class="product-card" data-id="11" data-name="Mousepad RGB XXL" data-price="34.99" data-image="https://images.unsplash.com/photo-1611077541490-2f015dc7c3c9?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="aksesore">
                <img src="https://media.ldlc.com/r1600/ld/products/00/05/60/21/LD0005602103_2.jpg" alt="Mousepad RGB" class="product-image">
                <div class="product-info">
                    <div class="product-category">Aksesore</div>
                    <h3 class="product-title">Mousepad RGB XXL</h3>
                    <p class="product-description">Mousepad RGB XXL me sipërfaqe të lëmuar, iluminim RGB me 16.8 milion ngjyra dhe kontroll të plotë të ndriçimit.</p>
                    <div class="product-price">34.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
            
            <!-- Produkti 12 -->
            <div class="product-card" data-id="12" data-name="Sistem PC Gaming Pro" data-price="2499.99" data-image="https://images.unsplash.com/photo-1550745165-9bc0b252726f?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" data-category="komponente">
                <img src="https://computerpro.al/wp-content/uploads/2025/10/GAMING-PC-COMPUTER-PRO.webp" alt="PC Gaming" class="product-image">
                <div class="product-info">
                    <div class="product-category">Komponente</div>
                    <h3 class="product-title">Sistem PC Gaming Pro</h3>
                    <p class="product-description">Sistem i plotë PC gaming me procesor Intel i9, RTX 4080, 32GB RAM, 2TB SSD dhe ftohje me ujë RGB.</p>
                    <div class="product-price">1499.99€</div>
                    <button class="buy-btn add-to-cart"><i class="fas fa-cart-plus"></i> Shto në Shportë</button>
                </div>
            </div>
        </div>
    </main>

    <!-- Modal për Shportën dhe Pagesën -->
    <div class="modal-overlay" id="cartModal">
        <div class="modal">
            <div class="modal-header">
                <h2 class="modal-title" id="modalTitle">Shporta e Blerjeve</h2>
                <button class="close-btn" id="closeModal">&times;</button>
            </div>
            <div class="modal-body">
                <!-- Shporta e Blerjeve -->
                <div id="cartContent">
                    <div class="cart-items" id="cartItemsContainer">
                        <!-- Produktet në shportë do të shtohen këtu nga JavaScript -->
                    </div>
                    
                    <div class="cart-summary">
                        <div class="summary-row">
                            <span>Nëntotal:</span>
                            <span id="subtotal">0.00€</span>
                        </div>
                        <div class="summary-row">
                            <span>Transporti:</span>
                            <span id="shipping">5.00€</span>
                        </div>
                        <div class="summary-row total-row">
                            <span>Total:</span>
                            <span id="total">0.00€</span>
                        </div>
                    </div>
                    
                    <button class="checkout-btn" id="checkoutBtn">
                        <i class="fas fa-credit-card"></i> Vazhdo në Pagesë
                    </button>
                </div>
                
                <!-- Forma e Pagesës -->
                <div class="payment-form" id="paymentForm">
                    <div class="payment-methods">
                        <div class="payment-method active" data-method="card">
                            <i class="fas fa-credit-card"></i>
                            <div>Kartë Bankare</div>
                        </div>
                        <div class="payment-method" data-method="paypal">
                            <i class="fab fa-paypal"></i>
                            <div>PayPal</div>
                        </div>
                        <div class="payment-method" data-method="cash">
                            <i class="fas fa-money-bill-wave"></i>
                            <div>Para në Dorë</div>
                        </div>
                    </div>
                    
                    <form id="paymentFormContent">
                        <div class="form-group">
                            <label class="form-label" for="cardName">Emri në Kartë</label>
                            <input type="text" id="cardName" class="form-input" placeholder="Shembull: Agim Krasniqi" required>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="cardNumber">Numri i Kartës</label>
                            <input type="text" id="cardNumber" class="form-input" placeholder="1234 5678 9012 3456" maxlength="19" required>
                        </div>
                        
                        <div class="form-row">
                            <div class="form-group">
                                <label class="form-label" for="expiryDate">Data e Skadencës</label>
                                <input type="text" id="expiryDate" class="form-input" placeholder="MM/YY" maxlength="5" required>
                            </div>
                            <div class="form-group">
                                <label class="form-label" for="cvv">CVV</label>
                                <input type="text" id="cvv" class="form-input" placeholder="123" maxlength="3" required>
                            </div>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="email">Email për Faturën</label>
                            <input type="email" id="email" class="form-input" placeholder="shembull@email.com" required>
                        </div>
                        
                        <div class="form-group">
                            <label class="form-label" for="address">Adresa e Dërgesës</label>
                            <textarea id="address" class="form-input" rows="3" placeholder="Shkruani adresën tuaj të plotë" required></textarea>
                        </div>
                        
                        <div class="form-actions">
                            <button type="button" class="back-to-cart" id="backToCart">
                                <i class="fas fa-arrow-left"></i> Kthehu në Shportë
                            </button>
                            <button type="submit" class="submit-payment">
                                <i class="fas fa-lock"></i> Konfirmo Pagesën
                            </button>
                        </div>
                    </form>
                </div>
                
                <!-- Mesazhi i Suksesit pas Pagesës -->
                <div class="success-message" id="successMessage">
                    <div class="success-icon">
                        <i class="fas fa-check-circle"></i>
                    </div>
                    <h2>Pagesa u Krye me Sukses!</h2>
                    <p>Faleminderit për blerjen tuaj. Një email konfirmimi është dërguar në adresën tuaj.</p>
                    <p>Porosia juaj do të dërgohet brenda 2-3 ditëve pune.</p>
                    <button class="checkout-btn" id="closeAfterPayment">
                        <i class="fas fa-home"></i> Kthehu në Faqen Kryesore
                    </button>
                </div>
            </div>
        </div>
    </div>

    <footer>
        <div class="footer-content">
            <div class="footer-column">
                <h3>ProGamingTech</h3>
                <p>Dyqani më i mirë për paisje gaming në rajon. Ne ofrojmë produktet më të fundit dhe me cilësinë më të lartë për të gjithë gamers.</p>
                <div class="social-icons">
                    <a href="#"><i class="fab fa-facebook-f"></i></a>
                    <a href="#"><i class="fab fa-instagram"></i></a>
                    <a href="#"><i class="fab fa-twitter"></i></a>
                    <a href="#"><i class="fab fa-youtube"></i></a>
                </div>
            </div>
            
            <div class="footer-column">
                <h3>Lidhje të Shpejta</h3>
                <a href="#">Kryefaqja</a>
                <a href="#products">Produktet</a>
                <a href="#">Rreth Nesh</a>
                <a href="#">Kontakt</a>
            </div>
            
            <div class="footer-column">
                <h3>Na Kontaktoni</h3>
                <p><i class="fas fa-phone"></i> +355 68 222 3333</p>
                <p><i class="fas fa-envelope"></i> info@progamingtech.github.io</p>
            </div>
        </div>
        
        <div class="copyright">
            <p>&copy; 2023 ProGamingTech. Të gjitha të drejtat e rezervuara.</p>
        </div>
    </footer>

    <div class="notification" id="notification">
        <p id="notificationText"><strong>Produkti u shtua në shportë!</strong></p>
    </div>

    <script>
        // Variabla globale
        let cart = [];
        const shippingCost = 5.00;
        
        // Elementet DOM
        const cartIcon = document.getElementById('cartIcon');
        const cartCount = document.getElementById('cartCount');
        const cartModal = document.getElementById('cartModal');
        const closeModal = document.getElementById('closeModal');
        const cartItemsContainer = document.getElementById('cartItemsContainer');
        const subtotalElement = document.getElementById('subtotal');
        const totalElement = document.getElementById('total');
        const checkoutBtn = document.getElementById('checkoutBtn');
        const backToCart = document.getElementById('backToCart');
        const cartContent = document.getElementById('cartContent');
        const paymentForm = document.getElementById('paymentForm');
        const paymentFormContent = document.getElementById('paymentFormContent');
        const successMessage = document.getElementById('successMessage');
        const closeAfterPayment = document.getElementById('closeAfterPayment');
        const modalTitle = document.getElementById('modalTitle');
        const notification = document.getElementById('notification');
        const notificationText = document.getElementById('notificationText');
        const categoryButtons = document.querySelectorAll('.category-btn');
        const productCards = document.querySelectorAll('.product-card');
        
        // Butonat e metodave të pagesës
        const paymentMethods = document.querySelectorAll('.payment-method');
        
        // Ngarko shportën nga localStorage nëse ekziston
        function loadCartFromStorage() {
            const savedCart = localStorage.getItem('proGamingTechCart');
            if (savedCart) {
                cart = JSON.parse(savedCart);
                updateCartUI();
            }
        }
        
        // Ruaj shportën në localStorage
        function saveCartToStorage() {
            localStorage.setItem('proGamingTechCart', JSON.stringify(cart));
        }
        
        // Shto produkt në shportë
        function addToCart(productId, productName, productPrice, productImage) {
            // Kontrollo nëse produkti ekziston tashmë në shportë
            const existingProductIndex = cart.findIndex(item => item.id === productId);
            
            if (existingProductIndex !== -1) {
                // Rrit sasinë nëse produkti ekziston
                cart[existingProductIndex].quantity += 1;
            } else {
                // Shto produkt të ri në shportë
                cart.push({
                    id: productId,
                    name: productName,
                    price: parseFloat(productPrice),
                    image: productImage,
                    quantity: 1
                });
            }
            
            // Përditëso UI dhe ruaj
            updateCartUI();
            saveCartToStorage();
            
            // Shfaq njoftim
            showNotification(`${productName} u shtua në shportë!`);
        }
        
        // Hiq produkt nga shporta
        function removeFromCart(productId) {
            cart = cart.filter(item => item.id !== productId);
            updateCartUI();
            saveCartToStorage();
            showNotification('Produkti u hoq nga shporta.');
        }
        
        // Përditëso sasinë e produktit
        function updateQuantity(productId, newQuantity) {
            if (newQuantity < 1) {
                removeFromCart(productId);
                return;
            }
            
            const productIndex = cart.findIndex(item => item.id === productId);
            if (productIndex !== -1) {
                cart[productIndex].quantity = newQuantity;
                updateCartUI();
                saveCartToStorage();
            }
        }
        
        // Llogarit totalin
        function calculateTotal() {
            let subtotal = 0;
            cart.forEach(item => {
                subtotal += item.price * item.quantity;
            });
            
            const total = subtotal + shippingCost;
            
            return {
                subtotal: subtotal.toFixed(2),
                total: total.toFixed(2)
            };
        }
        
        // Përditëso shfaqjen e shportës
        function updateCartUI() {
            // Përditëso numrin e produkteve në ikonën e shportës
            const totalItems = cart.reduce((sum, item) => sum + item.quantity, 0);
            cartCount.textContent = totalItems;
            
            // Përditëso listën e produkteve në shportë
            cartItemsContainer.innerHTML = '';
            
            if (cart.length === 0) {
                cartItemsContainer.innerHTML = '<p style="text-align: center; color: #b0b0c0;">Shporta juaj është e zbrazët.</p>';
                checkoutBtn.style.display = 'none';
            } else {
                checkoutBtn.style.display = 'block';
                
                cart.forEach(item => {
                    const cartItemElement = document.createElement('div');
                    cartItemElement.className = 'cart-item';
                    cartItemElement.innerHTML = `
                        <div class="cart-item-info">
                            <img src="${item.image}" alt="${item.name}" class="cart-item-image">
                            <div>
                                <div class="cart-item-name">${item.name}</div>
                                <div class="cart-item-price">${item.price.toFixed(2)}€</div>
                            </div>
                        </div>
                        <div class="cart-item-quantity">
                            <button class="quantity-btn minus" data-id="${item.id}">-</button>
                            <span class="quantity-value">${item.quantity}</span>
                            <button class="quantity-btn plus" data-id="${item.id}">+</button>
                        </div>
                        <button class="remove-item" data-id="${item.id}">Hiq</button>
                    `;
                    cartItemsContainer.appendChild(cartItemElement);
                });
            }
            
            // Përditëso çmimet
            const totals = calculateTotal();
            subtotalElement.textContent = `${totals.subtotal}€`;
            totalElement.textContent = `${totals.total}€`;
        }
        
        // Shfaq njoftimin
        function showNotification(message) {
            notificationText.innerHTML = `<strong>${message}</strong>`;
            notification.classList.add('show');
            
            setTimeout(() => {
                notification.classList.remove('show');
            }, 3000);
        }
        
        // Reset formën e pagesës
        function resetPaymentForm() {
            document.getElementById('paymentFormContent').reset();
            document.querySelector('.payment-method[data-method="card"]').classList.add('active');
            document.querySelectorAll('.payment-method:not([data-method="card"])').forEach(method => {
                method.classList.remove('active');
            });
        }
        
        // Filtro produktet sipas kategorisë
        function filterProducts(category) {
            productCards.forEach(card => {
                const cardCategory = card.getAttribute('data-category');
                
                if (category === 'all' || cardCategory === category) {
                    card.style.display = 'flex';
                } else {
                    card.style.display = 'none';
                }
            });
            
            // Përditëso butonat e kategorive
            categoryButtons.forEach(btn => {
                if (btn.getAttribute('data-category') === category) {
                    btn.classList.add('active');
                } else {
                    btn.classList.remove('active');
                }
            });
        }
        
        // Vëre listen për ngjarje
        document.addEventListener('DOMContentLoaded', () => {
            // Ngarko shportën nga localStorage
            loadCartFromStorage();
            
            // Shto produkt në shportë kur klikohet butoni "Shto në Shportë"
            document.querySelectorAll('.add-to-cart').forEach(button => {
                button.addEventListener('click', function() {
                    const productCard = this.closest('.product-card');
                    const productId = productCard.getAttribute('data-id');
                    const productName = productCard.getAttribute('data-name');
                    const productPrice = productCard.getAttribute('data-price');
                    const productImage = productCard.getAttribute('data-image');
                    
                    addToCart(productId, productName, productPrice, productImage);
                });
            });
            
            // Filtro produktet sipas kategorisë
            categoryButtons.forEach(button => {
                button.addEventListener('click', function() {
                    const category = this.getAttribute('data-category');
                    filterProducts(category);
                });
            });
            
            // Hap modal-in e shportës
            cartIcon.addEventListener('click', () => {
                cartModal.classList.add('active');
                modalTitle.textContent = 'Shporta e Blerjeve';
                cartContent.style.display = 'block';
                paymentForm.classList.remove('active');
                successMessage.classList.remove('active');
                resetPaymentForm();
            });
            
            // Mbylle modal-in
            closeModal.addEventListener('click', () => {
                cartModal.classList.remove('active');
            });
            
            // Mbylle modal-in kur klikohet jashtë
            cartModal.addEventListener('click', (e) => {
                if (e.target === cartModal) {
                    cartModal.classList.remove('active');
                }
            });
            
            // Mbylle modal-in pas pagesës së suksesshme
            closeAfterPayment.addEventListener('click', () => {
                cartModal.classList.remove('active');
                cart = [];
                updateCartUI();
                saveCartToStorage();
            });
            
            // Përpunoni ndryshimin e sasisë dhe heqjen e produkteve (përdorim delegimin e ngjarjeve)
            cartItemsContainer.addEventListener('click', (e) => {
                const target = e.target;
                
                // Rritja e sasisë
                if (target.classList.contains('plus')) {
                    const productId = target.getAttribute('data-id');
                    const product = cart.find(item => item.id === productId);
                    if (product) {
                        updateQuantity(productId, product.quantity + 1);
                    }
                }
                
                // Zbritja e sasisë
                if (target.classList.contains('minus')) {
                    const productId = target.getAttribute('data-id');
                    const product = cart.find(item => item.id === productId);
                    if (product) {
                        updateQuantity(productId, product.quantity - 1);
                    }
                }
                
                // Heqja e produktit
                if (target.classList.contains('remove-item')) {
                    const productId = target.getAttribute('data-id');
                    removeFromCart(productId);
                }
            });
            
            // Vazhdo në pagesë
            checkoutBtn.addEventListener('click', () => {
                if (cart.length === 0) return;
                
                modalTitle.textContent = 'Pagesa';
                cartContent.style.display = 'none';
                paymentForm.classList.add('active');
                successMessage.classList.remove('active');
            });
            
            // Kthehu në shportë nga faqja e pagesës
            backToCart.addEventListener('click', () => {
                modalTitle.textContent = 'Shporta e Blerjeve';
                cartContent.style.display = 'block';
                paymentForm.classList.remove('active');
                successMessage.classList.remove('active');
            });
            
            // Ndrysho metodën e pagesës
            paymentMethods.forEach(method => {
                method.addEventListener('click', () => {
                    paymentMethods.forEach(m => m.classList.remove('active'));
                    method.classList.add('active');
                });
            });
            
            // Formati i numrit të kartës
            document.getElementById('cardNumber').addEventListener('input', function(e) {
                let value = e.target.value.replace(/\s+/g, '').replace(/[^0-9]/gi, '');
                let formatted = '';
                
                for (let i = 0; i < value.length; i++) {
                    if (i > 0 && i % 4 === 0) {
                        formatted += ' ';
                    }
                    formatted += value[i];
                }
                
                e.target.value = formatted;
            });
            
            // Formati i datës së skadencës
            document.getElementById('expiryDate').addEventListener('input', function(e) {
                let value = e.target.value.replace(/\D/g, '');
                
                if (value.length >= 2) {
                    value = value.substring(0, 2) + '/' + value.substring(2, 4);
                }
                
                e.target.value = value;
            });
            
            // Formati i CVV
            document.getElementById('cvv').addEventListener('input', function(e) {
                e.target.value = e.target.value.replace(/\D/g, '').substring(0, 3);
            });
            
            // Përpunoni pagesën
            paymentFormContent.addEventListener('submit', (e) => {
                e.preventDefault();
                
                // Merr metodën e zgjedhur të pagesës
                const selectedMethod = document.querySelector('.payment-method.active').getAttribute('data-method');
                
                // Validimi i thjeshtë
                const cardName = document.getElementById('cardName').value;
                const cardNumber = document.getElementById('cardNumber').value;
                const expiryDate = document.getElementById('expiryDate').value;
                const cvv = document.getElementById('cvv').value;
                const email = document.getElementById('email').value;
                const address = document.getElementById('address').value;
                
                if (!cardName || !cardNumber || !expiryDate || !cvv || !email || !address) {
                    showNotification('Ju lutem plotësoni të gjitha fushat e kërkuara.');
                    return;
                }
                
                if (cardNumber.replace(/\s/g, '').length !== 16) {
                    showNotification('Numri i kartës duhet të ketë 16 shifra.');
                    return;
                }
                
                if (cvv.length !== 3) {
                    showNotification('CVV duhet të ketë 3 shifra.');
                    return;
                }
                
                // Simuloni pagesën e suksesshme
                setTimeout(() => {
                    modalTitle.textContent = 'Pagesa u Krye me Sukses';
                    paymentForm.classList.remove('active');
                    successMessage.classList.add('active');
                    
                    // Këtu në një sistem real do të dërgonim të dhënat në server
                    console.log('Pagesa u krye me sukses:');
                    console.log('Metoda e pagesës:', selectedMethod);
                    console.log('Totali:', totalElement.textContent);
                    console.log('Produktet:', cart);
                    console.log('Email:', email);
                    console.log('Adresa:', address);
                }, 1000);
            });
        });
    </script>
</body>
</html>
