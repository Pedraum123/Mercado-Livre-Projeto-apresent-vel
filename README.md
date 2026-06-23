# Mercado-Livre-Projeto-apresent-vel
Projeto para apresentação para a Professora Thaís, linda Maravilhosa

<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mercado Livre - Análise de Viabilidade</title>
    <style>
        /* --- RESET E VARIÁVEIS --- */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Proxima Nova', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        :root {
            --ml-yellow: #fff159;
            --ml-blue: #3483fa;
            --ml-dark-blue: #2d3277;
            --ml-gray: #ededed;
            --text-color: #333;
            --white: #ffffff;
        }

        html, body {
            height: 100%;
            background-color: var(--ml-gray);
            color: var(--text-color);
        }

        body {
            display: flex;
            flex-direction: column;
        }

        /* --- HEADER --- */
        header {
            background-color: var(--ml-yellow);
            padding: 10px 0;
            box-shadow: 0 1px 3px rgba(0,0,0,0.15);
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
            width: 100%;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            height: 60px;
            gap: 15px;
        }

        .logo {
            font-weight: 900;
            font-size: 24px;
            color: var(--ml-dark-blue);
            text-decoration: none;
            cursor: pointer;
            white-space: nowrap;
            transition: transform 0.2s;
        }

        .logo:hover {
            transform: scale(1.05);
        }

        .search-bar {
            flex-grow: 1;
            display: flex;
            margin: 0 15px;
        }

        .search-bar input {
            width: 100%;
            padding: 10px 15px;
            border: 2px solid transparent;
            border-radius: 4px;
            box-shadow: 0 1px 2px rgba(0,0,0,0.1);
            outline: none;
            transition: box-shadow 0.2s;
        }

        .search-bar input:focus {
            box-shadow: 0 2px 6px rgba(0,0,0,0.15);
            border-color: var(--ml-blue);
        }

        .nav-links {
            display: flex;
            gap: 15px;
            align-items: center;
        }

        .btn-login {
            background-color: transparent;
            border: 2px solid var(--text-color);
            padding: 6px 20px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s;
        }

        .btn-login:hover {
            background-color: var(--text-color);
            color: white;
        }

        .btn-cart {
            background-color: transparent;
            border: none;
            cursor: pointer;
            position: relative;
            display: flex;
            align-items: center;
            gap: 8px;
            font-weight: 600;
            transition: transform 0.2s;
        }

        .btn-cart:hover {
            transform: scale(1.1);
        }

        .cart-icon {
            font-size: 24px;
        }

        .cart-badge {
            position: absolute;
            top: -8px;
            right: -8px;
            background-color: #ff4444;
            color: white;
            border-radius: 50%;
            width: 20px;
            height: 20px;
            font-size: 12px;
            font-weight: bold;
            display: flex;
            justify-content: center;
            align-items: center;
            display: none;
        }

        .cart-badge.active {
            display: flex;
        }

        /* --- MAIN CONTENT --- */
        main {
            flex: 1;
            padding: 30px 0;
        }

        .view {
            display: none;
            animation: fadeIn 0.3s ease;
        }

        .view.active {
            display: block;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(5px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* --- HOME: BANNER E GRID --- */
        .hero-banner {
            background: linear-gradient(135deg, var(--ml-blue), var(--ml-dark-blue));
            color: white;
            padding: 50px;
            border-radius: 8px;
            margin-bottom: 40px;
            text-align: center;
            box-shadow: 0 4px 12px rgba(0,0,0,0.15);
        }

        .hero-banner h1 {
            font-size: 36px;
            margin-bottom: 10px;
        }

        .hero-banner p {
            font-size: 16px;
            opacity: 0.95;
        }

        .section-title {
            font-size: 22px;
            margin-bottom: 20px;
            color: var(--text-color);
            font-weight: 600;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        /* --- PRODUCT CARD --- */
        .product-card {
            background: white;
            border-radius: 8px;
            box-shadow: 0 1px 4px rgba(0,0,0,0.1);
            transition: all 0.3s ease;
            overflow: hidden;
            cursor: pointer;
        }

        .product-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 8px 16px rgba(0,0,0,0.15);
        }

        .product-img {
            height: 150px;
            background: linear-gradient(135deg, #f5f5f5, #e8e8e8);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 50px;
            border-bottom: 3px solid var(--ml-yellow);
            overflow: hidden;
        }

        .product-info {
            padding: 20px;
        }

        .product-price {
            font-size: 18px;
            font-weight: 600;
            color: var(--ml-blue);
            margin-bottom: 8px;
        }

        .product-title {
            font-size: 16px;
            font-weight: 600;
            color: var(--text-color);
            line-height: 1.3;
            margin-bottom: 15px;
            min-height: 32px;
        }

        .product-desc-preview {
            font-size: 13px;
            color: #666;
            line-height: 1.4;
            margin-bottom: 15px;
            max-height: 54px;
            overflow: hidden;
            text-overflow: ellipsis;
            display: -webkit-box;
            -webkit-line-clamp: 2;
            -webkit-box-orient: vertical;
        }

        .btn-add {
            width: 100%;
            padding: 12px;
            background-color: var(--ml-blue);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 0.5px;
        }

        .btn-add:hover {
            background-color: #2968c8;
            transform: scale(1.02);
        }

        .btn-add:active {
            transform: scale(0.98);
        }

        /* --- DETALHES DO PRODUTO --- */
        .detail-container {
            background: white;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
            display: grid;
            grid-template-columns: 1fr 1.5fr;
            gap: 50px;
            animation: slideIn 0.3s ease;
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        .detail-img {
            background: linear-gradient(135deg, #f5f5f5, #e8e8e8);
            height: 350px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 120px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .detail-info {
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }

        .btn-back {
            background: none;
            border: none;
            color: var(--ml-blue);
            cursor: pointer;
            font-size: 14px;
            margin-bottom: 20px;
            display: inline-flex;
            align-items: center;
            gap: 5px;
            transition: all 0.2s;
            width: fit-content;
        }

        .btn-back:hover {
            color: var(--ml-dark-blue);
            transform: translateX(-5px);
        }

        .detail-title {
            font-size: 32px;
            margin-bottom: 15px;
            color: var(--text-color);
            font-weight: 700;
        }

        .price-tag {
            font-size: 24px;
            color: var(--ml-blue);
            margin-bottom: 30px;
            font-weight: 600;
        }

        .detail-desc {
            font-size: 15px;
            line-height: 1.8;
            color: #555;
            margin-bottom: 30px;
            background: #f9f9f9;
            padding: 20px;
            border-radius: 4px;
            border-left: 4px solid var(--ml-yellow);
        }

        .detail-desc strong {
            color: var(--ml-dark-blue);
        }

        .btn-action {
            width: 100%;
            padding: 14px;
            background-color: var(--ml-blue);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            font-size: 16px;
            transition: all 0.3s;
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-top: auto;
        }

        .btn-action:hover {
            background-color: #2968c8;
            box-shadow: 0 4px 12px rgba(52, 131, 250, 0.4);
        }

        /* --- CARRINHO --- */
        .cart-page {
            background: white;
            padding: 40px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .cart-title {
            font-size: 28px;
            margin-bottom: 30px;
            color: var(--text-color);
            font-weight: 700;
        }

        .cart-item {
            display: grid;
            grid-template-columns: 80px 1fr auto;
            gap: 20px;
            padding: 20px;
            border: 1px solid #eee;
            border-radius: 8px;
            margin-bottom: 15px;
            align-items: start;
            transition: all 0.2s;
        }

        .cart-item:hover {
            background-color: #fafafa;
            border-color: var(--ml-yellow);
        }

        .cart-item-icon {
            font-size: 50px;
            text-align: center;
        }

        .cart-item-content h3 {
            font-size: 18px;
            margin-bottom: 8px;
            color: var(--text-color);
        }

        .cart-item-content p {
            font-size: 13px;
            color: #666;
            line-height: 1.6;
            max-height: 80px;
            overflow-y: auto;
        }

        .cart-item-actions {
            display: flex;
            gap: 10px;
            flex-direction: column;
            white-space: nowrap;
        }

        .btn-remove {
            padding: 8px 16px;
            background-color: #ff4444;
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            font-size: 12px;
            transition: all 0.2s;
        }

        .btn-remove:hover {
            background-color: #cc0000;
            transform: scale(1.05);
        }

        .empty-cart {
            text-align: center;
            padding: 60px 20px;
            color: #999;
        }

        .empty-cart-icon {
            font-size: 80px;
            margin-bottom: 20px;
            opacity: 0.5;
        }

        .empty-cart p {
            font-size: 18px;
            margin-bottom: 30px;
        }

        .btn-continue {
            background-color: var(--ml-blue);
            color: white;
            border: none;
            padding: 12px 30px;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            transition: all 0.2s;
        }

        .btn-continue:hover {
            background-color: #2968c8;
        }

        /* --- MODAL LOGIN --- */
        .modal {
            display: none;
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: rgba(0,0,0,0.6);
            z-index: 1000;
            justify-content: center;
            align-items: center;
            animation: fadeIn 0.2s ease;
        }

        .modal.active {
            display: flex;
        }

        .modal-content {
            background: white;
            padding: 40px;
            border-radius: 8px;
            width: 100%;
            max-width: 350px;
            box-shadow: 0 10px 40px rgba(0,0,0,0.3);
            animation: slideUp 0.3s ease;
        }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .modal-header {
            font-size: 24px;
            font-weight: 700;
            margin-bottom: 30px;
            color: var(--text-color);
        }

        .modal-input {
            width: 100%;
            padding: 12px;
            margin-bottom: 15px;
            border: 1px solid #ddd;
            border-radius: 4px;
            font-size: 14px;
            transition: all 0.2s;
        }

        .modal-input:focus {
            outline: none;
            border-color: var(--ml-blue);
            box-shadow: 0 0 0 2px rgba(52, 131, 250, 0.1);
        }

        .modal-btn {
            width: 100%;
            padding: 12px;
            background: var(--ml-blue);
            color: white;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-weight: 600;
            font-size: 14px;
            margin-bottom: 10px;
            transition: all 0.2s;
        }

        .modal-btn:hover {
            background-color: #2968c8;
        }

        .modal-close {
            text-align: center;
            font-size: 12px;
            color: #666;
            cursor: pointer;
            margin-top: 10px;
            transition: all 0.2s;
        }

        .modal-close:hover {
            color: var(--ml-blue);
        }

        /* --- FOOTER --- */
        footer {
            background-color: var(--ml-dark-blue);
            color: white;
            padding: 20px 0;
            margin-top: 50px;
            text-align: center;
            font-size: 14px;
        }

        footer a {
            color: var(--ml-yellow);
            text-decoration: none;
            font-weight: 600;
            transition: all 0.2s;
        }

        footer a:hover {
            text-decoration: underline;
        }

        /* --- CREATORS PAGE --- */
        .creators-container {
            background: white;
            padding: 50px;
            border-radius: 8px;
            box-shadow: 0 2px 8px rgba(0,0,0,0.1);
        }

        .creators-header {
            text-align: center;
            margin-bottom: 50px;
        }

        .creators-header h1 {
            font-size: 36px;
            margin-bottom: 15px;
            color: var(--text-color);
        }

        .creators-header p {
            font-size: 16px;
            color: #666;
            line-height: 1.6;
        }

        .creators-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 30px;
            margin-bottom: 40px;
        }

        .creator-card {
            background: linear-gradient(135deg, #f9f9f9, #f0f0f0);
            padding: 30px;
            border-radius: 8px;
            text-align: center;
            border: 2px solid var(--ml-yellow);
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px rgba(0,0,0,0.08);
        }

        .creator-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 8px 20px rgba(0,0,0,0.15);
            border-color: var(--ml-blue);
        }

        .creator-avatar {
            width: 150px;
            height: 150px;
            margin: 0 auto 20px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid var(--ml-yellow);
            box-shadow: 0 4px 8px rgba(0,0,0,0.1);
        }

        .creator-name {
            font-size: 24px;
            font-weight: 700;
            color: var(--text-color);
            margin-bottom: 10px;
        }

        .creator-role {
            font-size: 14px;
            color: var(--ml-blue);
            font-weight: 600;
            margin-bottom: 15px;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .creator-desc {
            font-size: 14px;
            color: #666;
            line-height: 1.6;
        }

        .creators-footer {
            text-align: center;
            padding: 30px;
            background: linear-gradient(135deg, var(--ml-yellow), #fff);
            border-radius: 8px;
            border-left: 4px solid var(--ml-blue);
        }

        .creators-footer h3 {
            font-size: 20px;
            margin-bottom: 10px;
            color: var(--text-color);
        }

        .creators-footer p {
            font-size: 14px;
            color: #555;
            line-height: 1.6;
        }

        /* --- RESPONSIVO --- */
        @media (max-width: 768px) {
            .navbar {
                flex-wrap: wrap;
                gap: 10px;
            }

            .logo {
                font-size: 20px;
            }

            .search-bar {
                flex-basis: 100%;
                margin: 0;
            }

            .hero-banner {
                padding: 30px 20px;
            }

            .hero-banner h1 {
                font-size: 24px;
            }

            .products-grid {
                grid-template-columns: 1fr;
            }

            .detail-container {
                grid-template-columns: 1fr;
                gap: 30px;
            }

            .detail-img {
                height: 250px;
                font-size: 80px;
            }

            .cart-item {
                grid-template-columns: 60px 1fr;
            }

            .cart-item-icon {
                font-size: 40px;
            }

            .cart-item-actions {
                grid-column: 1 / -1;
                flex-direction: row;
                justify-content: flex-end;
            }
        }
    </style>
</head>
<body>

    <!-- HEADER -->
    <header>
        <div class="container navbar">
            <a class="logo" onclick="showPage('home'); return false;">Mercado Livre</a>
            <div class="search-bar">
                <input type="text" placeholder="Buscar temas do trabalho...">
            </div>
            <div class="nav-links">
                <button class="btn-login" onclick="showPage('creators'); return false;">👥 Créditos</button>
                <button class="btn-login" onclick="openLogin()">Login</button>
                <button class="btn-cart" onclick="showPage('cart'); return false;">
                    <span class="cart-icon">🛒</span>
                    <span class="cart-badge" id="cartCount">0</span>
                </button>
            </div>
        </div>
    </header>

    <!-- MAIN CONTENT -->
    <main class="container">

        <!-- HOME PAGE -->
        <div id="home" class="view active">
            <div class="hero-banner">
                <h1>🏢 Análise de Viabilidade - Mercado Livre</h1>
                <p>Explorar os diferentes aspectos que tornam o Mercado Livre uma empresa viável</p>
            </div>

            <h2 class="section-title">📚 Temas Principais</h2>
            <div class="products-grid">
                <!-- Tema 1: Viabilidade Geral -->
                <div class="product-card" onclick="showProduct('viability-general')">
                    <div class="product-img">📋</div>
                    <div class="product-info">
                        <div class="product-price">Tema 1</div>
                        <div class="product-title">Viabilidade: Tipos e Importância</div>
                        <div class="product-desc-preview">Conheça os diferentes tipos de viabilidade e por que são importantes para análise empresarial...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); showProduct('viability-general')">Ver Detalhes</button>
                    </div>
                </div>

                <!-- Tema 2: Viabilidade Econômica e Financeira -->
                <div class="product-card" onclick="showProduct('viability-economic')">
                    <div class="product-img">💰</div>
                    <div class="product-info">
                        <div class="product-price">Tema 2</div>
                        <div class="product-title">Viabilidade Econômica e Financeira</div>
                        <div class="product-desc-preview">Análise da sustentabilidade financeira, fluxo de caixa e rentabilidade...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); showProduct('viability-economic')">Ver Detalhes</button>
                    </div>
                </div>

                <!-- Tema 3: Viabilidade de Mercado -->
                <div class="product-card" onclick="showProduct('viability-market')">
                    <div class="product-img">🌍</div>
                    <div class="product-info">
                        <div class="product-price">Tema 3</div>
                        <div class="product-title">Viabilidade de Mercado</div>
                        <div class="product-desc-preview">Análise de oportunidades de mercado, demanda, segmentação e posicionamento...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); showProduct('viability-market')">Ver Detalhes</button>
                    </div>
                </div>

                <!-- Tema 4: Viabilidade Ambiental -->
                <div class="product-card" onclick="showProduct('viability-environmental')">
                    <div class="product-img">🌱</div>
                    <div class="product-info">
                        <div class="product-price">Tema 4</div>
                        <div class="product-title">Viabilidade Ambiental e Social</div>
                        <div class="product-desc-preview">Responsabilidade social, sustentabilidade ambiental e impacto comunitário...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); showProduct('viability-environmental')">Ver Detalhes</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- DETAIL PAGE -->
        <div id="product-detail" class="view">
            <button class="btn-back" onclick="showPage('home')">← Voltar para a Loja</button>
            <div class="detail-container">
                <div class="detail-img" id="detail-icon">📦</div>
                <div class="detail-info">
                    <h1 class="detail-title" id="detail-title">Título</h1>
                    <div class="price-tag">Análise Completa</div>
                    <div class="detail-desc" id="detail-desc">Descrição</div>
                    <button class="btn-action" onclick="addCurrentToCart()">➕ Adicionar ao Carrinho de Análise</button>
                </div>
            </div>
        </div>

        <!-- CART PAGE -->
        <div id="cart" class="view">
            <div class="cart-page">
                <h2 class="cart-title">🛒 Carrinho de Análise</h2>
                <div id="cart-items">
                    <div class="empty-cart">
                        <div class="empty-cart-icon">📦</div>
                        <p>Seu carrinho está vazio</p>
                        <button class="btn-continue" onclick="showPage('home')">Voltar à Loja</button>
                    </div>
                </div>
            </div>
        </div>

        <!-- CREATORS PAGE -->
        <div id="creators" class="view">
            <button class="btn-back" onclick="showPage('home')">← Voltar para a Loja</button>
            <div class="creators-container">
                <div class="creators-header">
                    <h1>👥 Criadores deste Projeto</h1>
                    <p>Este trabalho foi desenvolvido com dedicação e comprometimento por um excelente grupo de estudantes.<br>Conheça os responsáveis pela análise da viabilidade do Mercado Livre.</p>
                </div>

                <div class="creators-grid">
                    <!-- Criador 1 -->
                    <div class="creator-card">
                        <img class="creator-avatar" src="pedru.jpeg" alt="Pedro Lucas">
                        <div class="creator-name">Pedro Lucas</div>
                        <div class="creator-role">Co-Autor</div>
                        <div class="creator-desc">Responsável pela pesquisa e análise de viabilidade econômica e financeira do Mercado Livre.</div>
                    </div>

                    <!-- Criador 2 -->
                    <div class="creator-card">
                        <img class="creator-avatar" src="kau.jpeg" alt="Kauê">
                        <div class="creator-name">Kauê</div>
                        <div class="creator-role">Co-Autor</div>
                        <div class="creator-desc">Responsável pela análise de mercado, oportunidades e posicionamento da empresa na América Latina.</div>
                    </div>

                    <!-- Criador 3 -->
                    <div class="creator-card">
                        <img class="creator-avatar" src="jesusa.jpeg" alt="Nicolas Jesus">
                        <div class="creator-name">Nicolas Jesus</div>
                        <div class="creator-role">Co-Autor</div>
                        <div class="creator-desc">Responsável pela viabilidade ambiental, social e desenvolvimento desta plataforma interativa.</div>
                    </div>
                </div>

                <div class="creators-footer">
                    <h3>🎓 Sobre este Projeto</h3>
                    <p>Este trabalho faz parte de uma análise acadêmica completa sobre a viabilidade da empresa Mercado Livre. A plataforma interativa foi desenvolvida para facilitar a apresentação dos temas: Viabilidade Econômica e Financeira, Viabilidade de Mercado, Viabilidade Ambiental e Social, e os Tipos e Importância da Viabilidade Empresarial.</p>
                </div>
            </div>
        </div>

    </main>

    <!-- FOOTER -->
    <div id="login-modal" class="modal">
        <div class="modal-content">
            <div class="modal-header">Acesse sua Conta</div>
            <input type="email" class="modal-input" placeholder="Email">
            <input type="password" class="modal-input" placeholder="Senha">
            <button class="modal-btn" onclick="closeLogin()">Entrar</button>
            <div class="modal-close" onclick="closeLogin()">✕ Fechar</div>
        </div>
    </div>

    <script>
        // --- DADOS DOS PRODUTOS (TEMAS) ---
        const products = {
            'viability-general': {
                title: "Viabilidade: Tipos e Importância",
                icon: "📋",
                desc: `<strong>Conceito:</strong> Viabilidade é a capacidade de uma empresa ser viável, sustentável e lucrativa no longo prazo.<br><br>
                
                <strong>Tipos de Viabilidade:</strong><br>
                • <strong>Viabilidade Econômica:</strong> Capacidade de gerar lucro e retorno sobre investimento<br>
                • <strong>Viabilidade Financeira:</strong> Disponibilidade de capital, fluxo de caixa positivo<br>
                • <strong>Viabilidade de Mercado:</strong> Existência de demanda e oportunidades de negócio<br>
                • <strong>Viabilidade Ambiental:</strong> Sustentabilidade e responsabilidade social<br>
                • <strong>Viabilidade Técnica:</strong> Capacidade de operacionalização e tecnologia<br><br>
                
                <strong>Importância:</strong> A análise de viabilidade é essencial para investidores, gestores e stakeholders entenderem se um negócio pode prosperar e sustentável. Para o Mercado Livre, essa análise é crucial para demonstrar seu posicionamento como empresa líder na América Latina.`
            },

            'viability-economic': {
                title: "Viabilidade Econômica e Financeira",
                icon: "💰",
                desc: `<strong>Análise Econômica do Mercado Livre:</strong><br>
                
                <strong>Receitas:</strong> O Mercado Livre lucra através de:<br>
                • Comissões sobre transações dos vendedores (6-17% dependendo da categoria)<br>
                • Serviços de logística e envios<br>
                • Publicidade e promoções<br>
                • Financiamento e crédito para vendedores<br>
                • Mercado Pago (pagamentos digitais)<br><br>
                
                <strong>Saúde Financeira:</strong><br>
                • ROI (Retorno sobre Investimento): Positivo e crescente<br>
                • Margem de Lucro: Aumentou significativamente em operações de maior escala<br>
                • Fluxo de Caixa: Forte e positivo, permitindo expansão e reinvestimento<br>
                • Dívida: Gerenciada de forma prudente com créditos robustos<br><br>
                
                <strong>Conclusão:</strong> O Mercado Livre demonstrou alta viabilidade econômica e financeira ao se tornar lucrativo e rentável, diferente de muitos concorrentes que dependem de capital de risco contínuo. A diversificação de receitas garante estabilidade financeira.`
            },

            'viability-market': {
                title: "Viabilidade de Mercado",
                icon: "🌍",
                desc: `<strong>Oportunidades de Mercado:</strong><br>
                
                <strong>Tamanho do Mercado:</strong><br>
                • E-commerce em crescimento acelerado na América Latina<br>
                • População de ~650 milhões de pessoas em mercados-alvo (Brasil, Argentina, México, etc.)<br>
                • Penetração de internet crescente em áreas urbanas e semiurbanas<br><br>
                
                <strong>Segmentação de Clientes:</strong><br>
                • Consumidores individuais buscando variedade de produtos<br>
                • PMEs (Pequenas e Médias Empresas) que vendem online<br>
                • Grandes varejistas buscando complementar vendas físicas<br>
                • Mercados verticalizados (autos, eletrônicos, etc.)<br><br>
                
                <strong>Análise Competitiva:</strong><br>
                • Líderes em marketplace na maioria dos países latino-americanos<br>
                • Concorrentes locais e globais (Amazon em alguns mercados)<br>
                • Diferencial: Presença forte, plataforma consolidada, payment gateway próprio<br><br>
                
                <strong>Posicionamento:</strong> O Mercado Livre é o marketplace mais consolidado e confiável da região, com a melhor integração de pagamentos e logística.`
            },

            'viability-environmental': {
                title: "Viabilidade Ambiental e Social",
                icon: "🌱",
                desc: `<strong>Responsabilidade Social:</strong><br>
                
                <strong>Impacto Positivo:</strong><br>
                • Empoderamento de pequenos negócios e empreendedores<br>
                • Criação de oportunidades econômicas para comunidades<br>
                • Geração de empregos diretos e indiretos<br>
                • Acesso a produtos e serviços em áreas remotas<br><br>
                
                <strong>Iniciativas de Sustentabilidade:</strong><br>
                • Programa Sustentabilidade: Incentivo a vendedores ecológicos<br>
                • Redução de embalagens e promoção de embalagens reutilizáveis<br>
                • Investimento em logística de baixa emissão de carbono<br>
                • Educação financeira para vendedores e compradores<br><br>
                
                <strong>Governança Corporativa:</strong><br>
                • Transparência em operações e dados<br>
                • Proteção ao consumidor com políticas claras<br>
                • Combate a fraudes e falsificações<br>
                • Diversidade e inclusão na força de trabalho<br><br>
                
                <strong>Conclusão:</strong> O Mercado Livre demonstra viabilidade ambiental e social ao gerar valor compartilhado para sociedade, vendedores e compradores, enquanto mantém práticas sustentáveis.`
            }
        };

        // --- CARRINHO ---
        let cart = [];
        let currentProduct = null;

        // Mostrar página
        function showPage(pageId) {
            // Esconde todas as views
            document.querySelectorAll('.view').forEach(view => {
                view.classList.remove('active');
            });

            // Mostra a view selecionada
            document.getElementById(pageId).classList.add('active');

            // Atualiza carrinho se ir para cart
            if (pageId === 'cart') {
                updateCartView();
            }

            window.scrollTo(0, 0);
        }

        // Mostrar produto
        function showProduct(productId) {
            const product = products[productId];
            currentProduct = productId;

            document.getElementById('detail-icon').textContent = product.icon;
            document.getElementById('detail-title').textContent = product.title;
            document.getElementById('detail-desc').innerHTML = product.desc;

            showPage('product-detail');
        }

        // Adicionar ao carrinho
        function addCurrentToCart() {
            if (!currentProduct) return;

            const product = products[currentProduct];
            const existingItem = cart.find(item => item.id === currentProduct);

            if (existingItem) {
                existingItem.quantity++;
            } else {
                cart.push({
                    id: currentProduct,
                    title: product.title,
                    icon: product.icon,
                    desc: product.desc,
                    quantity: 1
                });
            }

            updateCartBadge();
            showNotification('✓ Adicionado ao carrinho!');
        }

        // Atualizar badge do carrinho
        function updateCartBadge() {
            const badge = document.getElementById('cartCount');
            const total = cart.reduce((sum, item) => sum + item.quantity, 0);

            if (total > 0) {
                badge.textContent = total;
                badge.classList.add('active');
            } else {
                badge.classList.remove('active');
            }
        }

        // Atualizar view do carrinho
        function updateCartView() {
            const cartItemsDiv = document.getElementById('cart-items');

            if (cart.length === 0) {
                cartItemsDiv.innerHTML = `
                    <div class="empty-cart">
                        <div class="empty-cart-icon">🛒</div>
                        <p>Seu carrinho está vazio</p>
                        <button class="btn-continue" onclick="showPage('home')">Continuar Comprando</button>
                    </div>
                `;
                return;
            }

            let html = '';
            cart.forEach((item, index) => {
                html += `
                    <div class="cart-item">
                        <div class="cart-item-icon">${item.icon}</div>
                        <div class="cart-item-content">
                            <h3>${item.title}</h3>
                            <p>${item.desc}</p>
                        </div>
                        <div class="cart-item-actions">
                            <span style="font-weight: 600; color: var(--ml-blue);">Qtd: ${item.quantity}</span>
                            <button class="btn-remove" onclick="removeFromCart(${index})">Remover</button>
                        </div>
                    </div>
                `;
            });

            cartItemsDiv.innerHTML = html;
        }

        // Remover do carrinho
        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCartBadge();
            updateCartView();
            showNotification('✓ Removido do carrinho');
        }

        // Notificação
        function showNotification(message) {
            // Criar elemento de notificação
            const notification = document.createElement('div');
            notification.style.cssText = `
                position: fixed;
                top: 80px;
                right: 20px;
                background: #4CAF50;
                color: white;
                padding: 15px 25px;
                border-radius: 4px;
                font-weight: 600;
                box-shadow: 0 4px 12px rgba(0,0,0,0.2);
                animation: slideInRight 0.3s ease;
                z-index: 999;
            `;
            notification.textContent = message;
            document.body.appendChild(notification);

            // Remover após 2 segundos
            setTimeout(() => {
                notification.style.animation = 'slideOutRight 0.3s ease';
                setTimeout(() => notification.remove(), 300);
            }, 2000);

            // Adicionar keyframes se não existirem
            if (!document.getElementById('notification-styles')) {
                const style = document.createElement('style');
                style.id = 'notification-styles';
                style.textContent = `
                    @keyframes slideInRight {
                        from { transform: translateX(400px); opacity: 0; }
                        to { transform: translateX(0); opacity: 1; }
                    }
                    @keyframes slideOutRight {
                        from { transform: translateX(0); opacity: 1; }
                        to { transform: translateX(400px); opacity: 0; }
                    }
                `;
                document.head.appendChild(style);
            }
        }

        // Login
        function openLogin() {
            document.getElementById('login-modal').classList.add('active');
        }

        function closeLogin() {
            document.getElementById('login-modal').classList.remove('active');
            showNotification('✓ Bem-vindo!');
        }

        // Fechar modal ao clicar fora
        document.getElementById('login-modal').addEventListener('click', function(e) {
            if (e.target === this) {
                closeLogin();
            }
        });
    </script>

    <!-- FOOTER -->
    <footer>
        <p>© 2026 - Análise de Viabilidade Mercado Livre | Desenvolvido por <a onclick="showPage('creators'); return false;">Pedro Lucas, Kauê e Nicolas Jesus</a></p>
    </footer>

</body>
</html>
