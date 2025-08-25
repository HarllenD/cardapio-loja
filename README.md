<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MEN'S BARBERSHOP - Bar & Bebidas</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Inter:wght@300;400;500&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            background: #0a0a0a;
            font-family: 'Inter', sans-serif;
            color: #ffffff;
            overflow-x: hidden;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            position: relative;
        }

        /* Background decorative elements */
        .bg-decoration {
            position: absolute;
            width: 300px;
            height: 300px;
            border-radius: 50%;
            opacity: 0.1;
            z-index: 0;
        }

        .bg-decoration.red {
            background: radial-gradient(circle, #ff4757 0%, transparent 70%);
            top: 100px;
            right: -150px;
        }

        .bg-decoration.blue {
            background: radial-gradient(circle, #3742fa 0%, transparent 70%);
            top: 800px;
            left: -150px;
        }

        .bg-decoration.green {
            background: radial-gradient(circle, #2ed573 0%, transparent 70%);
            top: 1400px;
            right: -100px;
        }

        .header {
            text-align: center;
            padding: 60px 20px 40px;
            position: relative;
            z-index: 2;
        }

        .logo {
            width: 300px;
            height: 150px;
            margin: 0 auto 30px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 10px;
        }

        .logo img {
            width: 100%;
            height: 100%;
            object-fit: contain;
        }

        .title {
            font-family: 'Playfair Display', serif;
            font-size: 2.8em;
            font-weight: 700;
            letter-spacing: 8px;
            margin-bottom: 10px;
            color: #d4af37;
            text-transform: uppercase;
        }

        .subtitle {
            font-size: 1.1em;
            letter-spacing: 3px;
            color: #888;
            text-transform: uppercase;
        }

        .menu-section {
            padding: 0 20px;
            margin-bottom: 60px;
            position: relative;
            z-index: 2;
        }

        .section-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.8em;
            font-weight: 700;
            color: #ffffff;
            text-transform: uppercase;
            letter-spacing: 4px;
            margin-bottom: 30px;
            text-align: center;
            position: relative;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 50%;
            transform: translateX(-50%);
            width: 60px;
            height: 2px;
            background: #d4af37;
        }

        .menu-item {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            margin-bottom: 35px;
            padding: 25px;
            background: rgba(255, 255, 255, 0.02);
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.08);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .menu-item::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(212, 175, 55, 0.1), transparent);
            transition: all 0.8s ease;
        }

        .menu-item:hover::before {
            left: 100%;
        }

        .menu-item:hover {
            transform: translateY(-2px);
            border-color: rgba(212, 175, 55, 0.3);
            background: rgba(255, 255, 255, 0.05);
        }

        .item-info {
            flex: 1;
            padding-right: 20px;
        }

        .item-name {
            font-family: 'Playfair Display', serif;
            font-size: 1.3em;
            font-weight: 700;
            color: #ff4757;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 8px;
        }

        .item-description {
            font-size: 0.95em;
            color: #bbb;
            line-height: 1.5;
            font-style: italic;
        }

        .item-price {
            font-family: 'Playfair Display', serif;
            font-size: 1.4em;
            font-weight: 700;
            color: #d4af37;
            white-space: nowrap;
        }

        .price-currency {
            font-size: 0.8em;
            color: #999;
        }

        /* Seções específicas com decorações */
        .cervejas-premium {
            position: relative;
        }

        .cervejas-premium::before {
            content: '🍺';
            position: absolute;
            top: -10px;
            right: 20px;
            font-size: 3em;
            opacity: 0.1;
        }

        .cervejas-nacionais {
            position: relative;
        }

        .cervejas-nacionais::before {
            content: '🍻';
            position: absolute;
            top: -10px;
            right: 20px;
            font-size: 3em;
            opacity: 0.1;
        }

        .refrigerantes {
            position: relative;
        }

        .refrigerantes::before {
            content: '🥤';
            position: absolute;
            top: -10px;
            right: 20px;
            font-size: 3em;
            opacity: 0.1;
        }

        .bebidas {
            position: relative;
        }

        .bebidas::before {
            content: '💧';
            position: absolute;
            top: -10px;
            right: 20px;
            font-size: 3em;
            opacity: 0.1;
        }

        /* Destaque especial para produtos premium */
        .premium-item {
            border-left: 4px solid #d4af37;
            background: rgba(212, 175, 55, 0.05);
        }

        .premium-item .item-name {
            color: #d4af37;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .title {
                font-size: 2.2em;
                letter-spacing: 4px;
            }
            
            .menu-item {
                flex-direction: column;
                align-items: flex-start;
            }
            
            .item-info {
                padding-right: 0;
                margin-bottom: 15px;
            }
            
            .item-price {
                align-self: flex-end;
            }
        }

        /* Animações */
        .menu-item {
            opacity: 0;
            transform: translateY(20px);
            animation: fadeInUp 0.6s ease forwards;
        }

        .menu-item:nth-child(1) { animation-delay: 0.1s; }
        .menu-item:nth-child(2) { animation-delay: 0.2s; }
        .menu-item:nth-child(3) { animation-delay: 0.3s; }
        .menu-item:nth-child(4) { animation-delay: 0.4s; }
        .menu-item:nth-child(5) { animation-delay: 0.5s; }
        .menu-item:nth-child(6) { animation-delay: 0.6s; }

        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .footer {
            text-align: center;
            padding: 40px 20px;
            color: #666;
            font-style: italic;
            border-top: 1px solid rgba(255, 255, 255, 0.1);
        }
    </style>
</head>
<body>
    <div class="bg-decoration red"></div>
    <div class="bg-decoration blue"></div>
    <div class="bg-decoration green"></div>

    <div class="container">
        <div class="header">
            <div class="logo">
                <svg width="300" height="150" viewBox="0 0 300 150" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <!-- Fundo preto -->
                    <rect width="300" height="150" fill="#000000"/>
                    
                    <!-- MEN'S -->
                    <text x="150" y="80" text-anchor="middle" fill="white" font-family="serif" font-size="32" font-weight="400" letter-spacing="8px">MEN'S</text>
                    
                    <!-- Elemento decorativo -->
                    <polygon points="250,20 270,30 260,50" fill="white"/>
                    
                    <!-- BARBERSHOP -->
                    <text x="150" y="115" text-anchor="middle" fill="white" font-family="serif" font-size="12" font-weight="300" letter-spacing="6px">B A R B E R S H O P</text>
                </svg>
            </div>
            <h1 class="title" style="display: none;">MEN'S BARBERSHOP</h1>
            <p class="subtitle">Bebidas Selecionadas</p>
        </div>

        <div class="menu-section cervejas-premium">
            <h2 class="section-title">Cervejas Premium</h2>
            
            <div class="menu-item premium-item">
                <div class="item-info">
                    <div class="item-name">Heineken Long Neck</div>
                    <div class="item-description">Cerveja premium holandesa, 330ml, sabor único e refrescante</div>
                </div>
                <div class="item-price">12,<span class="price-currency">00 R$</span></div>
            </div>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Heineken Lata</div>
                    <div class="item-description">Cerveza clara dorada con espuma generosa, 269ml</div>
                </div>
                <div class="item-price">6,<span class="price-currency">00 R$</span></div>
            </div>
        </div>

        <div class="menu-section cervejas-nacionais">
            <h2 class="section-title">Cervejas Artesanais</h2>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Eisenbahn</div>
                    <div class="item-description">Cerveza alemã tradicional con lúpulo seleccionado e malte especial</div>
                </div>
                <div class="item-price">8,<span class="price-currency">00 R$</span></div>
            </div>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Spaten</div>
                    <div class="item-description">Tradicional cerveja alemã, sabor equilibrado e marcante</div>
                </div>
                <div class="item-price">8,<span class="price-currency">00 R$</span></div>
            </div>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Budweiser</div>
                    <div class="item-description">Cerveza americana clásica, sabor suave e refrescante</div>
                </div>
                <div class="item-price">8,<span class="price-currency">00 R$</span></div>
            </div>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Amstel</div>
                    <div class="item-description">Cerveja holandesa premium, sabor puro e cristalino</div>
                </div>
                <div class="item-price">8,<span class="price-currency">00 R$</span></div>
            </div>
        </div>

        <div class="menu-section refrigerantes">
            <h2 class="section-title">Refrigerantes</h2>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Coca-Cola</div>
                    <div class="item-description">Refrigerante clásico, 350ml, sabor original inconfundível</div>
                </div>
                <div class="item-price">6,<span class="price-currency">00 R$</span></div>
            </div>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Guaraná Antarctica</div>
                    <div class="item-description">Sabor brasileiro autêntico, 350ml, fruta da Amazônia</div>
                </div>
                <div class="item-price">6,<span class="price-currency">00 R$</span></div>
            </div>
        </div>

        <div class="menu-section bebidas">
            <h2 class="section-title">Água</h2>
            
            <div class="menu-item">
                <div class="item-info">
                    <div class="item-name">Água Mineral</div>
                    <div class="item-description">Água pura e cristalina, gelada na temperatura ideal</div>
                </div>
                <div class="item-price">2,<span class="price-currency">50 R$</span></div>
            </div>
        </div>

        <div class="footer">
            <p>Todas as bebidas servidas geladas • Qualidade premium sempre</p>
        </div>
    </div>

    <script>
        // Efeito paralaxe suave nos elementos decorativos
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const decorations = document.querySelectorAll('.bg-decoration');
            
            decorations.forEach((decoration, index) => {
                const speed = 0.2 + (index * 0.1);
                decoration.style.transform = `translateY(${scrolled * speed}px)`;
            });
        });

        // Animação de entrada mais suave
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, {
            threshold: 0.1
        });

        document.querySelectorAll('.menu-item').forEach(item => {
            observer.observe(item);
        });
    </script>
</body>
</html>
