<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Detalhes do Tema - Mercado Livre</title>
    <style>
        :root {
            --ml-yellow: #fff159;
            --ml-blue: #3483fa;
            --ml-dark-blue: #2d3277;
            --ml-gray: #ededed;
            --text-color: #333;
            --white: #ffffff;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
        }

        html, body {
            min-height: 100%;
            background-color: var(--ml-gray);
            color: var(--text-color);
        }

        body {
            display: flex;
            flex-direction: column;
        }

        header {
            background-color: var(--ml-yellow);
            padding: 15px 0;
            box-shadow: 0 1px 4px rgba(0,0,0,0.12);
        }

        .container {
            width: min(1200px, calc(100% - 40px));
            margin: 0 auto;
        }

        .navbar {
            display: flex;
            justify-content: space-between;
            align-items: center;
            gap: 16px;
        }

        .logo {
            font-size: 24px;
            font-weight: 900;
            color: var(--ml-dark-blue);
            text-decoration: none;
            cursor: pointer;
        }

        .btn-back {
            display: inline-flex;
            align-items: center;
            gap: 8px;
            margin: 25px 0;
            padding: 12px 18px;
            border: 2px solid var(--ml-blue);
            background: white;
            color: var(--ml-blue);
            border-radius: 8px;
            cursor: pointer;
            text-decoration: none;
            font-weight: 700;
        }

        .detail-page {
            padding: 40px 0 80px;
        }

        .detail-card {
            background: white;
            border-radius: 18px;
            box-shadow: 0 12px 30px rgba(0,0,0,0.08);
            display: grid;
            grid-template-columns: 1fr;
            gap: 24px;
            padding: 40px;
        }

        .detail-media {
            width: 100%;
            min-height: 220px;
            border-radius: 16px;
            overflow: hidden;
            background: #f5f5f5;
            box-shadow: inset 0 0 0 1px rgba(0,0,0,0.05);
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 16px;
            flex-wrap: wrap;
        }

        .detail-media img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            display: block;
        }

        .detail-media .multi-img {
            width: calc(50% - 8px);
            height: 220px;
            object-fit: cover;
            display: block;
            margin: 0;
            border-radius: 10px;
        }

        /* imagem de logo no detalhe (ex.: info-what-is) */
        .detail-media .logo-img {
            height: 140px;
            max-width: 320px;
            width: auto;
            display: block;
            margin: 0 auto;
            object-fit: contain;
            background: transparent;
            border-radius: 6px;
        }

        /* classe para imagens grandes (ex.: serviçosML.webp) */
        .detail-media .large-img {
            width: auto;
            height: 700px; /* reduzido para 700px */
            max-width: 90%;
            margin: 0 auto;
        }

        .detail-desc {
            font-size: 20px;
            line-height: 1.9;
            color: #333;
        }

        @media (max-width: 700px) {
            .detail-media {
                padding: 12px;
            }
            .detail-media .multi-img {
                width: 100%;
                max-width: 420px;
                height: 220px;
                margin: 0 auto;
            }
            .detail-media .large-img {
                height: 420px; /* reduz em telas menores */
                max-width: 100%;
            }
            .detail-media .logo-img {
                height: 100px;
                max-width: 220px;
            }
            .detail-card {
                grid-template-columns: 1fr;
            }
        }

        .detail-chart {
            width: 100%;
            margin: 24px 0 8px;
            display: grid;
            gap: 14px;
        }

        .detail-chart-row {
            display: grid;
            gap: 8px;
        }

        .detail-chart-row span {
            display: flex;
            justify-content: space-between;
            color: #4d4d4d;
            font-size: 14px;
        }

        .detail-chart-bar {
            height: 14px;
            background: #eef4ff;
            border-radius: 999px;
            overflow: hidden;
        }

        .detail-chart-bar-inner {
            height: 100%;
            background: linear-gradient(90deg, var(--ml-blue), var(--ml-dark-blue));
        }

        .detail-info {
            display: flex;
            flex-direction: column;
            gap: 22px;
        }

        .detail-info h1 {
            font-size: 34px;
            color: var(--text-color);
            line-height: 1.1;
        }

        .detail-price {
            font-size: 24px;
            color: var(--ml-blue);
            font-weight: 700;
        }

        .detail-desc {
            background: #f9f9f9;
            border-left: 5px solid var(--ml-yellow);
            padding: 24px;
            border-radius: 12px;
            line-height: 1.8;
            color: #444;
        }

        .detail-brand-logos {
            display: flex;
            flex-wrap: wrap;
            gap: 14px;
            align-items: center;
            margin: 16px 0 4px;
        }

        .detail-brand-logos img {
            height: 220px;
            width: auto;
            max-width: 260px;
            border-radius: 10px;
            background: white;
            padding: 8px;
            box-shadow: 0 4px 16px rgba(0,0,0,0.08);
        }

        .btn-action {
            width: fit-content;
            padding: 16px 26px;
            border: none;
            border-radius: 10px;
            background-color: var(--ml-blue);
            color: white;
            cursor: pointer;
            font-size: 16px;
            font-weight: 700;
            transition: transform 0.2s ease, background-color 0.2s ease;
        }

        .btn-action:hover {
            background-color: #2968c8;
            transform: translateY(-1px);
        }

        .suggestions {
            margin-top: 40px;
            display: grid;
            gap: 18px;
        }

        .suggestion-card {
            background: white;
            border-radius: 14px;
            padding: 24px;
            box-shadow: 0 8px 22px rgba(0,0,0,0.06);
        }

        .suggestion-card h3 {
            margin-bottom: 12px;
            color: var(--ml-dark-blue);
        }

        .suggestion-card p {
            color: #555;
            line-height: 1.7;
        }

        footer {
            margin-top: auto;
            padding: 18px 0;
            text-align: center;
            background: var(--ml-dark-blue);
            color: white;
            font-size: 14px;
        }

        @media (max-width: 900px) {
            .detail-card {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <header>
        <div class="container navbar">
            <a class="logo" href="Site2.html">Mercado Livre</a>
            <a class="btn-back" href="Site2.html">← Voltar para a Loja</a>
        </div>
    </header>

    <main class="container detail-page">
        <div class="btn-back-wrapper">
            <a class="btn-back" href="Site2.html">← Voltar para a Loja</a>
        </div>

        <div class="detail-card">
            <div class="detail-info">
                <h1 id="detail-title"></h1>
                <div class="detail-brand-logos" id="detail-brand-logos"></div>
                <div class="detail-price" id="detail-price"></div>
                <div class="detail-chart" id="detail-chart"></div>
                <div class="detail-media" id="detail-media"></div>
                <div class="detail-desc" id="detail-desc">Carregando conteúdo...</div>
                <button class="btn-action" id="detail-add" onclick="addCurrentToCart()">➕ Adicionar ao Carrinho</button>
            </div>
        </div>

        
    </main>

    <footer>
        © 2026 - Detalhes do Tema | Mercado Livre
    </footer>

    <script>
        const products = {
            'viability-general': {
                title: 'Viabilidade: Tipos e Importância',
                icon: 'logo',
                image: 'images/logo.png',
                price: 'R$ 129,90',
                desc: `<strong>Conceito:</strong> Viabilidade é a capacidade de um projeto ou empresa de gerar resultados consistentes, sustentáveis e lucrativos ao longo do tempo.<br><br>
                <strong>Como aplicar ao Mercado Livre:</strong><br>
                • O marketplace hoje combina várias frentes de receita e precisa provar que todos funcionam juntas.<br>
                • Analisar viabilidade envolve verificar se há demanda, receita, recursos técnicos e sustentabilidade ambiental.<br><br>
                <strong>Principais tipos:</strong><br>
                • <strong>Viabilidade Econômica:</strong> O Mercado Livre deve apresentar lucro e retorno sobre o investimento.<br>
                • <strong>Viabilidade Financeira:</strong> A empresa depende de fluxo de caixa saudável e capital suficiente para crescer.<br>
                • <strong>Viabilidade de Mercado:</strong> Precisa haver clientes dispostos a comprar e vendedores dispostos a ofertar.<br>
                • <strong>Viabilidade Ambiental:</strong> Projetos de sustentabilidade, embalagens e logística devem ser viáveis para o futuro.<br>
                • <strong>Viabilidade Técnica:</strong> A plataforma deve funcionar de forma estável, segura e escalável para milhões de usuários.<br><br>
                <strong>Por quê é importante?</strong><br>
                Porque apresenta se o negócio é viável em todas as dimensões necessárias, não apenas se vende bem hoje, mas se pode se manter forte amanhã.`
            },
            'viability-economic': {
                title: 'Viabilidade Econômica e Financeira',
                icon: '💰',
                price: 'R$ 139,90',
                desc: `<strong>Fontes de receita:</strong><br>
                • Taxas de venda cobradas dos vendedores<br>
                • Receitas por publicidade em anúncios e destaque de produtos<br>
                • Serviços financeiros do Mercado Pago<br>
                • Soluções de crédito para vendedores e compradores<br><br>
                <strong>Custo e margem:</strong><br>
                • A maior parte do lucro vem da combinação entre marketplace e serviços financeiros.<br>
                • Investimentos em logística e tecnologia são altos, mas geram ganhos de eficiência com escala.<br><br>
                <strong>Indicadores de saúde:</strong><br>
                • Fluxo de caixa positivo garante continuidade operacional.<br>
                • Margem operacional melhora conforme a base de usuários cresce.<br>
                • Controle de custos de frete e devolução é essencial para manter competitividade.<br><br>
                <strong>Conclusão:</strong><br>
                O Mercado Livre constrói viabilidade econômica ao equilibrar receitas diversificadas com investimentos estratégicos em tecnologia e logística.`
            },
            'viability-market': {
                title: 'Viabilidade de Mercado',
                icon: '🌍',
                price: 'R$ 149,90',
                desc: `<strong>Ambiente de mercado:</strong><br>
                • A América Latina tem forte potencial de crescimento para comércio eletrônico.<br>
                • O Mercado Livre aproveita mercados grandes como Brasil, México e Argentina.<br><br>
                <strong>Demanda:</strong><br>
                • Consumidores buscam variedade, preço competitivo e facilidade de pagamento.<br>
                • Pequenos e médios lojistas usam a plataforma para alcançar clientes sem precisar de loja própria.<br><br>
                <strong>Competição:</strong><br>
                • Concorrentes incluem Amazon, Shopee e marketplaces locais.<br>
                • O diferencial do Mercado Livre é a integração com Mercado Pago e Mercado Envios.<br><br>
                <strong>Força da marca:</strong><br>
                • Alto reconhecimento na região e confiança do consumidor são ativos valiosos.<br>
                • O ecossistema completo aumenta a competitividade e fortalece a viabilidade de mercado.`
            },
            'viability-environmental': {
                title: 'Viabilidade Ambiental e Social',
                icon: '🌱',
                price: 'R$ 159,90',
                desc: `<strong>Impacto social:</strong><br>
                • O Mercado Livre conecta vendedores locais a clientes de toda a região.<br>
                • Pequenos negócios ganham visibilidade e faturamento sem investimento em tecnologia própria.<br><br>
                <strong>Sustentabilidade:</strong><br>
                • Programas de redução de embalagens e logística mais limpa ajudam a diminuir emissões.<br>
                • A plataforma investe em práticas que tornam o ciclo de comércio mais sustentável.<br><br>
                <strong>Engajamento:</strong><br>
                • Incentivo a vendedores com boas práticas e produtos sustentáveis.<br>
                • Políticas de proteção ao consumidor ajudam a manter confiança e reputação.<br><br>
                <strong>Resultado:</strong><br>
                A viabilidade ambiental e social reforça que o modelo de negócios do Mercado Livre não só gera lucro, mas também impacto positivo para a região.`
            },
            'info-what-is': {
                title: 'O que é o Mercado Livre?',
                icon: '❓',
                images: ['images/logo.png'],
                price: 'R$ 129,90',
                desc: `<strong>Definição:</strong><br>
                O Mercado Livre é um marketplace que conecta compradores e vendedores com um sistema integrado de pagamento e envio.<br><br>
                <strong>Funções principais:</strong><br>
                • Vendas de produtos novos e usados<br>
                • Ferramentas para gestão de anúncios e reputação<br>
                • Solução de pagamento digital com Mercado Pago<br>
                • Logística integrada via Mercado Envios<br><br>
                <strong>Benefício:</strong><br>
                Ele torna mais fácil vender online, dá mais segurança ao comprador e centraliza todas as etapas de uma transação em uma só plataforma.`
            },
            'info-headquarters': {
                title: 'Sede e Criador',
                icon: 'logo',
                images: ['images/fundador.webp', 'images/sede.webp'],
                price: 'R$ 89,90',
                desc: `<strong>Origem:</strong><br>
                Fundado em 1999 por Marcos Galperin em Buenos Aires, o Mercado Livre cresceu rapidamente para se tornar o maior player de e-commerce da região.<br><br>
                <strong>Sede:</strong><br>
                A sede principal fica na Argentina, com escritórios estratégicos em São Paulo, México e outras capitais.<br><br>
                <strong>Papel do criador:</strong><br>
                Galperin trouxe a ideia de marketplace para a América Latina e liderou o modelo de expansão por inovação em pagamentos e logística.`
            },
            'info-services': {
                title: 'Serviços Principais',
                icon: 'logo',
                images: ['images/serviçosML.webp'],
                price: 'R$ 159,90',
                desc: `<strong>Mercado Livre:</strong><br>
                Plataforma de compra e venda que oferece catálogo amplo e opções de entrega.<br><br>
                <strong>Mercado Pago:</strong><br>
                Solução de pagamento digital usada tanto dentro quanto fora do marketplace.<br><br>
                <strong>Mercado Envios:</strong><br>
                Serviço de logística que simplifica o despacho, rastreamento e entrega de produtos.<br><br>
                <strong>Outros serviços:</strong><br>
                • Mercado Crédito para financiamento<br>
                • Ferramentas de gestão e análise para vendedores.<br><br>
                <strong>Mercado Shops:</strong><br>
                Mercado Shops permite que lojistas criem sua loja online própria, integrada ao marketplace, com controle de branding, catálogo e meios de pagamento via Mercado Pago, além de sincronização de estoque e vendas.<br><br>
                <strong>Mercado Ads (Publicidades):</strong><br>
                Mercado Ads oferece formatos de anúncios para aumentar visibilidade dos produtos dentro e fora da plataforma — anúncios patrocinados em resultados de busca, display e campanhas segmentadas — com relatórios e otimização por conversão.<br><br>
                Esses serviços deixam a operação mais completa e atraente para usuários e lojistas.`,
            },
            'info-transport': {
                title: 'Como funciona o transporte',
                icon: '🚚',
                price: 'R$ 109,90',
                desc: `<strong>Fluxo logístico:</strong><br>
                • O vendedor prepara e despacha o pedido.<br>
                • O pacote é recolhido ou deixado em um ponto de envio.<br>
                • O produto passa por centros de distribuição e transporte parceiro.<br>
                • O cliente acompanha o rastreamento online até a entrega.<br><br>
                <strong>Vantagens:</strong><br>
                • Rastreabilidade completa<br>
                • Opções de entrega expressa ou econômica<br>
                • Melhor integração entre vendedor, transportadora e comprador.<br><br>
                Esse processo garante que a logística funcione bem para compras em toda a América Latina.`
            },
            'info-purpose': {
                title: 'Para que serve',
                icon: '🎯',
                price: 'R$ 99,90',
                desc: `<strong>Objetivo principal:</strong><br>
                Permitir que qualquer pessoa compre e venda produtos online de forma simples e segura.<br><br>
                <strong>Para quem serve:</strong><br>
                • Consumidores que querem comparar preços e métodos de pagamento<br>
                • Pequenos e médios vendedores que precisam de uma vitrine digital<br>
                • Grandes empresas que buscam maior alcance sem abrir loja física.<br><br>
                <strong>Impacto:</strong><br>
                O Mercado Livre serve para ampliar o acesso ao comércio eletrônico e fortalecer o ecossistema de vendas na região.`
            },
            'info-companies': {
                title: 'Empresas e marcas que usam',
                icon: '🏷️',
                price: 'R$ 139,90',
                desc: `<strong>Quem vende:</strong><br>
                • Grandes marcas como Samsung, LG, Nike e Adidas<br>
                • Pequenos comerciantes e artesãos locais<br>
                • Lojas de eletrônicos, moda, beleza, casa e construção<br><br>
                <strong>Por que usam:</strong><br>
                • Alcance rápido a milhares de clientes<br>
                • Pagamentos e logística integrados<br>
                • Ferramentas de divulgação e análise de vendas<br><br>
                O Mercado Livre é popular porque dá visibilidade a vendedores de todos os tamanhos e acelera a expansão do negócio online.`
            },
            'info-ai': {
                title: 'Uso de Inteligência Artificial',
                icon: '🤖',
                price: 'R$ 119,90',
                desc: `<strong>Visão geral:</strong><br>
                O Mercado Livre aplica Inteligência Artificial em várias camadas para melhorar experiência do usuário, aumentar a eficiência operacional e reforçar a segurança da plataforma.<br><br>
                <strong>Principais aplicações:</strong><br>
                • Recomendação e personalização: modelos que sugerem produtos, ofertas e categorias com base em histórico de navegação, compras e comportamento em tempo real.<br>
                • Busca e entendimento de intenção: sistemas de NLP e rankeamento que corrigem consultas, expandem termos e ordenam resultados por relevância contextual.<br>
                • Detecção de fraudes e risco: modelos em tempo real que identificam transações suspeitas, padrões anômalos e anúncios potencialmente fraudulentos.<br>
                • Otimização de preços e conversão: algoritmos que suportam promoções, recomendações de preço dinâmico e testes A/B para melhorar vendas.<br>
                • Logística e roteirização: previsões de demanda, alocação inteligente de estoque e planejamento de rotas que reduzem custos e prazos de entrega.<br>
                • Atendimento automatizado: chatbots e assistentes virtuais que resolvem dúvidas comuns e encaminham casos complexos para agentes humanos.<br>
                • Classificação e moderação de conteúdo: visão computacional para analisar imagens de produtos, categorizar anúncios e detectar conteúdo indevido.<br><br>
                <strong>Infraestrutura e boas práticas:</strong><br>
                • Pipelines de dados e ML para treinamento batch e inferência em tempo real, com monitoramento de desempenho e retraining contínuo.<br>
                • Experimentação (A/B testing), métricas de negócio integradas e governança de modelos para garantir qualidade e robustez.<br>
                • Uso de ambientes multi-cloud e on-premises, com atenção a privacidade e conformidade no tratamento de dados.<br><br>
                <strong>Benefícios:</strong><br>
                A IA permite personalizar a jornada de compra, aumentar a conversão, reduzir fraudes e otimizar operações logísticas, mantendo a confiança e segurança dos usuários.`
            },
            'info-value': {
                title: 'Valor e avaliação',
                icon: '💵',
                price: 'R$ 179,90',
                desc: `<strong>Valor de mercado:</strong><br>
                O Mercado Livre é uma das empresas de tecnologia mais valiosas da América Latina, com valuation em dezenas de bilhões de dólares.<br><br>
                <strong>Por que importa:</strong><br>
                • Mostra confiança de investidores na capacidade de crescimento<br>
                • Indica estabilidade financeira e potencial de expansão<br>
                • Ajuda a atrair talentos e parcerias estratégicas.<br><br>
                Esse valor reflete a posição de liderança da empresa e seu impacto no comércio eletrônico regional.`
            },
            'info-infrastructure': {
                title: 'Servidores e infraestrutura',
                icon: '☁️',
                price: 'R$ 149,90',
                brandLogos: ['images/Amazon_Web_Services-Logo.wine.webp', 'images/google-cloud-logo-1.webp'],
                desc: `<strong>Arquitetura:</strong><br>
                O Mercado Livre usa uma estratégia <strong>multi-cloud</strong>, dependendo principalmente da <strong>AWS (Amazon Web Services)</strong> e da <strong>Google Cloud</strong>.<br><br>
                <strong>AWS:</strong><br>
                É o principal provedor de nuvem da empresa, utilizada para armazenar dados, processar transações (como as 900 milhões de requisições por minuto), executar machine learning para detecção de fraudes e gerenciar a infraestrutura de automação industrial via AWS Outposts.<br>
                <br>
                <strong>Google Cloud:</strong><br>
                É utilizada para rodar o sistema de gestão SAP S/4HANA e em projetos específicos de inteligência artificial, analytics e infraestrutura multi-cloud.<br><br>
                <strong>Segurança:</strong><br>
                • Proteção de dados do cliente<br>
                • Sistemas redundantes para evitar quedas<br>
                • Monitoramento constante de desempenho<br><br>
                <strong>Resultado:</strong><br>
                Essa infraestrutura permite lidar com picos de acesso, carregar páginas rapidamente e manter a plataforma segura e estável.`
            },
            /* info-shops and info-ads consolidated into info-services */
            'info-countries': {
                title: 'Usuários em todos os países',
                icon: '🌎',
                price: 'R$ 199,90',
                desc: `<strong>Base de usuários por país:</strong><br>
                • Brasil: 95 milhões<br>
                • Argentina: 24 milhões<br>
                • México: 72 milhões<br>
                • Colômbia: 30 milhões<br>
                • Chile: 12 milhões<br>
                • Uruguai: 6 milhões<br>
                • Peru: 18 milhões<br>
                • Venezuela: 8 milhões<br>
                • Equador: 6 milhões<br>
                • Paraguai: 3 milhões<br>
                • Bolívia: 4 milhões<br>
                • Costa Rica: 2,4 milhões<br>
                • Guatemala: 2,8 milhões<br>
                • Panamá: 1,1 milhão<br>
                • El Salvador: 1,7 milhão<br>
                • Honduras: 1,8 milhão<br>
                • República Dominicana: 2,9 milhões<br>
                • Nicarágua: 1,2 milhão<br><br>
                <strong>O que isso significa:</strong><br>
                Uma base de usuários ampla torna o Mercado Livre uma plataforma muito valiosa para vendedores e anunciantes, com potencial de crescimento em cada país.<br><br>
                <strong>Impacto regional:</strong><br>
                Esses números mostram que o Mercado Livre não é apenas forte no Brasil, mas relevante em toda a América Latina, adaptando-se a diferentes mercados e necessidades locais.`
            }
        };

        let currentProduct = null;
        const detailMedia = document.getElementById('detail-media');
        const detailChart = document.getElementById('detail-chart');
        const detailTitle = document.getElementById('detail-title');
        const detailBrandLogos = document.getElementById('detail-brand-logos');
        const detailPrice = document.getElementById('detail-price');
        const detailDesc = document.getElementById('detail-desc');
        const addButton = document.getElementById('detail-add');
        const defaultDetailImage = 'data:image/svg+xml,%3Csvg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 600 360%22%3E%3Crect width=%22600%22 height=%22360%22 fill=%22%23f5f5f5%22/%3E%3Ctext x=%2250%25%22 y=%2250%25%22 dominant-baseline=%22middle%22 text-anchor=%22middle%22 font-family=%22Arial%22 font-size=%2232%22 fill=%22222%22%3EDetalhe%3C/text%3E%3C/svg%3E';

        function getQueryParam(name) {
            const params = new URLSearchParams(window.location.search);
            return params.get(name);
        }

        function loadProduct() {
            const productId = getQueryParam('product');
            if (!productId || !products[productId]) {
                detailTitle.textContent = 'Produto inválido';
                detailDesc.innerHTML = 'Nenhum produto encontrado. Volte para a loja e selecione um item válido.';
                detailPrice.textContent = '';
                addButton.style.display = 'none';
                return;
            }

            const product = products[productId];
            currentProduct = productId;
            detailTitle.textContent = product.title;
            detailPrice.textContent = `Preço: ${product.price}`;
            detailDesc.innerHTML = product.desc;
            const noImageProducts = ['info-companies', 'info-purpose', 'info-value', 'info-infrastructure', 'info-ai'];
            if (noImageProducts.includes(productId)) {
                document.getElementById('detail-brand-logos').innerHTML = '';
                detailMedia.innerHTML = '';
            } else {
                if (product.brandLogos && product.brandLogos.length) {
                    document.getElementById('detail-brand-logos').innerHTML = product.brandLogos.map(src => `<img src="${src}" alt="Logo">`).join('');
                } else {
                    document.getElementById('detail-brand-logos').innerHTML = '';
                }
                if (product.images && product.images.length) {
                    const imgClass = productId === 'info-services'
                        ? 'multi-img large-img'
                        : (productId === 'info-what-is' ? 'multi-img logo-img' : 'multi-img');
                    detailMedia.innerHTML = product.images.map(src => `<img class="${imgClass}" src="${src}" alt="${product.title}">`).join('');
                } else {
                    detailMedia.innerHTML = `<img src="${product.image || defaultDetailImage}" alt="${product.title}">`;
                }
            }
            if (productId === 'info-countries') {
                detailChart.innerHTML = `
                    <div class="detail-chart-row">
                        <span><strong>Brasil</strong><strong>95 mi</strong></span>
                        <div class="detail-chart-bar"><div class="detail-chart-bar-inner" style="width: 100%;"></div></div>
                    </div>
                    <div class="detail-chart-row">
                        <span><strong>México</strong><strong>72 mi</strong></span>
                        <div class="detail-chart-bar"><div class="detail-chart-bar-inner" style="width: 76%;"></div></div>
                    </div>
                    <div class="detail-chart-row">
                        <span><strong>Colômbia</strong><strong>30 mi</strong></span>
                        <div class="detail-chart-bar"><div class="detail-chart-bar-inner" style="width: 32%;"></div></div>
                    </div>
                    <div class="detail-chart-row">
                        <span><strong>Argentina</strong><strong>24 mi</strong></span>
                        <div class="detail-chart-bar"><div class="detail-chart-bar-inner" style="width: 25%;"></div></div>
                    </div>
                    <div class="detail-chart-row">
                        <span><strong>Chile</strong><strong>12 mi</strong></span>
                        <div class="detail-chart-bar"><div class="detail-chart-bar-inner" style="width: 13%;"></div></div>
                    </div>
                `;
            } else {
                detailChart.innerHTML = '';
            }
        }

        function addCurrentToCart() {
            if (!currentProduct) return;
            const storageKey = 'site2_cart';
            const saved = JSON.parse(localStorage.getItem(storageKey) || '[]');
            const existing = saved.find(item => item.id === currentProduct);
            if (existing) {
                existing.quantity += 1;
            } else {
                saved.push({ id: currentProduct, title: products[currentProduct].title, quantity: 1 });
            }
            localStorage.setItem(storageKey, JSON.stringify(saved));
            showNotification('✓ Adicionado ao carrinho!');
        }

        function showNotification(message) {
            const notification = document.createElement('div');
            notification.style.cssText = 'position: fixed; top: 25px; right: 25px; background: #4CAF50; color: white; padding: 14px 22px; border-radius: 10px; font-weight: 700; box-shadow: 0 6px 22px rgba(0,0,0,0.2); z-index: 1000;';
            notification.textContent = message;
            document.body.appendChild(notification);
            setTimeout(() => {
                notification.remove();
            }, 1800);
        }

        loadProduct();
    </script>
</body>
</html>


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

        .visual-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
            gap: 24px;
            margin-bottom: 32px;
        }

        .visual-card {
            background: white;
            border-radius: 18px;
            padding: 24px;
            box-shadow: 0 10px 25px rgba(0,0,0,0.08);
            overflow: hidden;
        }

        .visual-card h3 {
            font-size: 20px;
            margin-bottom: 16px;
            color: var(--ml-dark-blue);
        }

        .visual-card p {
            font-size: 15px;
            line-height: 1.75;
            color: #4a4a4a;
        }

        .logo-box {
            display: flex;
            align-items: center;
            gap: 18px;
            background: linear-gradient(135deg, #fffaf1, #f7f4c3);
            border-radius: 16px;
            padding: 20px;
            margin-bottom: 18px;
        }

        .logo-box img {
            max-width: 120px;
            height: auto;
        }

        .logo-box strong {
            font-size: 18px;
            color: var(--ml-dark-blue);
        }

        .stats-list {
            display: grid;
            gap: 14px;
            margin-top: 14px;
        }

        .stats-item {
            background: #f8f9ff;
            padding: 14px 16px;
            border-radius: 12px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            color: var(--ml-dark-blue);
            font-weight: 600;
        }

        .country-details {
            display: none;
            margin-top: 18px;
            padding: 18px 16px;
            border-radius: 14px;
            background: #f7fbff;
            border: 1px solid rgba(52, 131, 250, 0.16);
        }

        .country-details.active {
            display: block;
        }

        .country-details h4 {
            font-size: 16px;
            margin-bottom: 12px;
            color: var(--ml-dark-blue);
        }

        .country-details p {
            font-size: 14px;
            color: #4a4a4a;
            line-height: 1.7;
            margin-bottom: 10px;
        }

        .country-details ul {
            padding-left: 18px;
            margin-top: 8px;
            color: #4a4a4a;
            line-height: 1.7;
        }

        .country-details li {
            margin-bottom: 8px;
        }

        .btn-secondary {
            width: 100%;
            padding: 12px;
            background-color: #f0f4ff;
            color: var(--ml-blue);
            border: 2px solid var(--ml-blue);
            border-radius: 6px;
            cursor: pointer;
            font-weight: 700;
            transition: all 0.3s ease;
            margin-top: 18px;
        }

        .btn-secondary:hover {
            background-color: var(--ml-blue);
            color: white;
        }

        .chart-card {
            display: grid;
            gap: 14px;
        }

        .chart-bar {
            background: #eef4ff;
            border-radius: 999px;
            overflow: hidden;
            height: 14px;
        }

        .chart-bar-inner {
            height: 100%;
            background: linear-gradient(90deg, var(--ml-blue), var(--ml-dark-blue));
        }

        .chart-labels {
            display: flex;
            justify-content: space-between;
            font-size: 13px;
            color: #5a5a5a;
            margin-top: 6px;
        }

        .detail-price {
            font-size: 20px;
            color: var(--ml-blue);
            font-weight: 700;
            margin-bottom: 20px;
        }

        .products-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
            gap: 20px;
            margin-bottom: 40px;
        }

        .info-section {
            margin-bottom: 40px;
        }

        .info-section .section-title {
            display: flex;
            align-items: center;
            gap: 12px;
        }

        .info-summary {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
            gap: 20px;
            margin-bottom: 30px;
        }

        .summary-card {
            background: linear-gradient(135deg, rgba(52, 131, 250, 0.12), rgba(255, 241, 89, 0.15));
            border: 1px solid rgba(52, 131, 250, 0.12);
            border-radius: 16px;
            padding: 22px;
            min-height: 140px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .summary-card:hover {
            transform: translateY(-4px);
            box-shadow: 0 12px 26px rgba(0,0,0,0.12);
        }

        .summary-icon {
            width: 42px;
            height: 42px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 12px;
            background: var(--ml-blue);
            color: white;
            font-size: 18px;
            margin-bottom: 14px;
        }

        .summary-card h3,
        .summary-card p {
            color: var(--ml-dark-blue);
        }

        .summary-card h3 {
            font-size: 18px;
            margin-bottom: 10px;
        }

        .info-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
            gap: 24px;
        }

        .info-card {
            background: white;
            border-radius: 18px;
            padding: 42px;
            min-height: 280px;
            box-shadow: 0 12px 30px rgba(0,0,0,0.11);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            overflow: hidden;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            gap: 28px;
        }

        .info-card:hover {
            transform: translateY(-8px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.18);
        }

        .info-card-icon {
            width: 72px;
            height: 72px;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            border-radius: 20px;
            background: var(--ml-yellow);
            overflow: hidden;
            margin-bottom: 0;
        }

        .info-card-icon img {
            width: 58px;
            height: 58px;
            object-fit: contain;
        }

        .info-card h3 {
            font-size: 22px;
            margin-bottom: 12px;
            color: var(--ml-dark-blue);
        }

        .info-card p,
        .info-card ul {
            font-size: 18px;
            color: #333;
            line-height: 1.9;
        }

        .info-card ul {
            padding-left: 18px;
            margin-top: 10px;
        }

        .info-card li {
            margin-bottom: 8px;
        }

        .info-price {
            display: inline-flex;
            align-items: center;
            justify-content: center;
            margin-top: 20px;
            padding: 10px 16px;
            background-color: #1b6e3c;
            color: var(--ml-yellow);
            font-weight: 700;
            border-radius: 999px;
            width: fit-content;
            box-shadow: inset 0 0 0 1px rgba(0,0,0,0.06);
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

            <div class="visual-grid">
                <div class="visual-card">
                    <div class="logo-box">
                        <img src="images/logo.png" alt="Logo Mercado Livre">
                        <div>
                            <strong>Mercado Livre</strong>
                            <p>Fundado em 1999, líder de e-commerce na América Latina.</p>
                        </div>
                    </div>
                    <div class="stats-list">
                        <div class="stats-item"><span>Ano de início</span><strong>1999</strong></div>
                        <div class="stats-item"><span>Presença</span><strong>18 países</strong></div>
                        <div class="stats-item"><span>Valor estimado</span><strong>~US$ 90 bi</strong></div>
                        <div class="stats-item"><span>Crescimento anual</span><strong>+25% média</strong></div>
                    </div>
                </div>
                <div class="visual-card chart-card">
                    <h3>Gráfico de Crescimento</h3>
                    <div>
                        <div class="chart-bar"><div class="chart-bar-inner" style="width: 40%;"></div></div>
                        <div class="chart-labels"><span>2018</span><span>R$ 30 bi</span></div>
                    </div>
                    <div>
                        <div class="chart-bar"><div class="chart-bar-inner" style="width: 60%;"></div></div>
                        <div class="chart-labels"><span>2020</span><span>R$ 55 bi</span></div>
                    </div>
                    <div>
                        <div class="chart-bar"><div class="chart-bar-inner" style="width: 85%;"></div></div>
                        <div class="chart-labels"><span>2023</span><span>R$ 95 bi</span></div>
                    </div>
                </div>
                <div class="visual-card product-card">
                    <h3>Usuários por país</h3>
                    <div class="stats-list">
                        <div class="stats-item"><span>Brasil</span><strong>95 milhões</strong></div>
                        <div class="stats-item"><span>Argentina</span><strong>24 milhões</strong></div>
                        <div class="stats-item"><span>México</span><strong>72 milhões</strong></div>
                        <div class="stats-item"><span>Colômbia</span><strong>30 milhões</strong></div>
                        <div class="stats-item"><span>Chile</span><strong>12 milhões</strong></div>
                    </div>
                    <button type="button" class="btn-add" onclick="event.stopPropagation(); navigateToDetail('info-countries')">Ver detalhes</button>
                </div>
            </div>

            <h2 class="section-title">📚 Temas Principais</h2>
            <div class="products-grid">
                <!-- Tema 1: Viabilidade Geral -->
                <div class="product-card" onclick="navigateToDetail('viability-general')">
                    <div class="product-img">📋</div>
                    <div class="product-info">
                        <div class="product-price">Tema 1</div>
                        <div class="product-title">Viabilidade: Tipos e Importância</div>
                        <div class="product-desc-preview">Conheça os diferentes tipos de viabilidade e por que são importantes para análise empresarial...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); navigateToDetail('viability-general')">Ver Detalhes</button>
                    </div>
                </div>

                <!-- Tema 2: Viabilidade Econômica e Financeira -->
                <div class="product-card" onclick="navigateToDetail('viability-economic')">
                    <div class="product-img">💰</div>
                    <div class="product-info">
                        <div class="product-price">Tema 2</div>
                        <div class="product-title">Viabilidade Econômica e Financeira</div>
                        <div class="product-desc-preview">Análise da sustentabilidade financeira, fluxo de caixa e rentabilidade...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); navigateToDetail('viability-economic')">Ver Detalhes</button>
                    </div>
                </div>

                <!-- Tema 3: Viabilidade de Mercado -->
                <div class="product-card" onclick="navigateToDetail('viability-market')">
                    <div class="product-img">🌍</div>
                    <div class="product-info">
                        <div class="product-price">Tema 3</div>
                        <div class="product-title">Viabilidade de Mercado</div>
                        <div class="product-desc-preview">Análise de oportunidades de mercado, demanda, segmentação e posicionamento...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); navigateToDetail('viability-market')">Ver Detalhes</button>
                    </div>
                </div>

                <!-- Tema 4: Viabilidade Ambiental -->
                <div class="product-card" onclick="navigateToDetail('viability-environmental')">
                    <div class="product-img">🌱</div>
                    <div class="product-info">
                        <div class="product-price">Tema 4</div>
                        <div class="product-title">Viabilidade Ambiental e Social</div>
                        <div class="product-desc-preview">Responsabilidade social, sustentabilidade ambiental e impacto comunitário...</div>
                        <button class="btn-add" onclick="event.stopPropagation(); navigateToDetail('viability-environmental')">Ver Detalhes</button>
                    </div>
                </div>
            </div>

            <div class="info-section">
                <h2 class="section-title">📌 Mercado Livre em Destaque</h2>
                <div class="info-summary">
                    <div class="summary-card">
                        <span class="summary-icon">🏢</span>
                        <h3>Visão geral rápida</h3>
                        <p>Maior marketplace da América Latina, com marketplace, pagamentos e logística integrados para consumidores e vendedores.</p>
                    </div>
                    <div class="summary-card">
                        <span class="summary-icon">🌍</span>
                        <h3>Pilares da operação</h3>
                        <p>Marketplace, Mercado Pago e Mercado Envios formam o ecossistema principal que garante vendas, pagamentos e entregas.</p>
                    </div>
                    <div class="summary-card">
                        <span class="summary-icon">🤖</span>
                        <h3>IA e inovação</h3>
                        <p>Uso de inteligência artificial em busca, recomendações, prevenção de fraudes e atendimento para melhorar a experiência do usuário.</p>
                    </div>
                </div>

                <div class="info-grid">
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>O que é</h3>
                        <p>Entenda o marketplace, funcionalidades e benefícios do Mercado Livre.</p>
                        <span class="info-price">R$ 129,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-what-is')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Sede</h3>
                        <p>Origem, fundador e presença global do Mercado Livre na América Latina.</p>
                        <span class="info-price">R$ 89,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-headquarters')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Serviços</h3>
                        <p>Conheça Mercado Pago, Mercado Envios e outros serviços que ampliam a plataforma.</p>
                        <span class="info-price">R$ 159,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-services')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Transporte</h3>
                        <p>Veja como a logística e o rastreamento suportam entregas rápidas e confiáveis.</p>
                        <span class="info-price">R$ 109,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-transport')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Propósito</h3>
                        <p>Descubra a missão do Mercado Livre e o impacto para compradores e vendedores.</p>
                        <span class="info-price">R$ 99,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-purpose')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Marcas</h3>
                        <p>Marcas e empresas que usam a plataforma para expandir presença e vendas.</p>
                        <span class="info-price">R$ 139,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-companies')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>IA</h3>
                        <p>Saiba como a inteligência artificial melhora recomendações e segurança.</p>
                        <span class="info-price">R$ 119,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-ai')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Valor</h3>
                        <p>Entenda o valor da empresa e sua posição como líder no comércio eletrônico.</p>
                        <span class="info-price">R$ 179,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-value')">Ver detalhes</button>
                    </div>
                    <div class="info-card">
                        <span class="info-card-icon"><img src="images/logo.png" alt="Logo Mercado Livre"></span>
                        <h3>Infraestrutura</h3>
                        <p>Infraestrutura em nuvem, servidores e segurança por trás da plataforma.</p>
                        <span class="info-price">R$ 149,90</span>
                        <button class="btn-add" onclick="navigateToDetail('info-infrastructure')">Ver detalhes</button>
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
                    <div class="detail-price" id="detail-price"></div>
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
                        <img class="creator-avatar" src="images/pedru.jpeg" alt="Pedro Lucas">
                        <div class="creator-name">Pedro Lucas</div>
                        <div class="creator-role">Co-Autor</div>
                        <div class="creator-desc">Responsável pela pesquisa e análise de viabilidade econômica e financeira do Mercado Livre.</div>
                    </div>

                    <!-- Criador 2 -->
                    <div class="creator-card">
                        <img class="creator-avatar" src="images/kau.jpeg" alt="Kauê">
                        <div class="creator-name">Kauê</div>
                        <div class="creator-role">Co-Autor</div>
                        <div class="creator-desc">Responsável pela análise de mercado, oportunidades e posicionamento da empresa na América Latina.</div>
                    </div>

                    <!-- Criador 3 -->
                    <div class="creator-card">
                        <img class="creator-avatar" src="images/jesusa.jpeg" alt="Nicolas Jesus">
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
            },
            'info-what-is': {
                title: "O que é o Mercado Livre?",
                icon: "❓",
                price: "R$ 129,90",
                desc: `<strong>Visão detalhada:</strong><br>
                O Mercado Livre é um marketplace que integra compradores e vendedores em um mesmo ecossistema digital. Além de permitir a venda de produtos novos e usados, oferece ferramentas de pagamento, crédito e logística para facilitar toda a operação.<br><br>
                <strong>Diferenciais:</strong><br>
                • Catálogo variado de milhões de produtos<br>
                • Interface acessível para pessoas e empresas<br>
                • Sistema de reputação para vendedores e compradores<br><br>
                <strong>Por que é importante?</strong><br>
                Porque permite que empresas e consumidores realizem transações seguras, com prazos de entrega e pagamentos mais transparentes, ampliando o acesso ao comércio eletrônico na região.`
            },
            'info-headquarters': {
                title: "Sede e Criador",
                icon: "📍",
                price: "R$ 89,90",
                desc: `<strong>Fundação:</strong><br>
                Criado em 1999 por Marcos Galperin, o Mercado Livre nasceu em Buenos Aires e cresceu rapidamente na América Latina.<br><br>
                <strong>Sede:</strong><br>
                A sede principal fica em Buenos Aires, Argentina, mas a empresa mantém escritórios estratégicos em São Paulo, México e outras capitais regionais.<br><br>
                <strong>Criador:</strong><br>
                Marcos Galperin é um empreendedor argentino formado em economia que já passou por Stanford e trouxe o conceito de marketplace para a América Latina.`
            },
            'info-services': {
                title: "Serviços Principais",
                icon: "🛒",
                price: "R$ 159,90",
                desc: `<strong>Ecossistema de serviços:</strong><br>
                O Mercado Livre não é apenas um site de vendas. Ele oferece soluções que transformam a experiência de compra e venda.<br><br>
                <strong>Mercado Pago:</strong><br>
                Permite pagamentos online, transferências, carteira digital e parcelamentos.<br><br>
                <strong>Mercado Envios:</strong><br>
                Cuida da operação logística, envio e rastreamento de pedidos em parceria com transportadoras.<br><br>
                <strong>Mercado Crédito:</strong><br>
                Disponibiliza crédito para vendedores expandirem o negócio e para consumidores comprarem com mais facilidade.<br><br>
                <strong>Mercado Ads:</strong><br>
                Oferece anúncios e campanhas para aumentar a visibilidade de produtos e vendas.`
            },
            'info-transport': {
                title: "Como funciona o transporte",
                icon: "🚚",
                price: "R$ 109,90",
                desc: `<strong>Funcionalidade do Mercado Envios:</strong><br>
                O serviço conecta vendedores, centros de distribuição e transportadoras, criando uma rede logística que permite entregas rápidas e rastreáveis.<br><br>
                <strong>Passos:</strong><br>
                1. O vendedor prepara o pedido.<br>
                2. O produto é coletado ou entregue em um ponto de envio.<br>
                3. A mercadoria segue para o centro de distribuição.<br>
                4. O cliente recebe o código de rastreamento e acompanha a entrega.<br><br>
                <strong>Vantagens:</strong><br>
                • Melhor visibilidade do pedido<br>
                • Redução de erros de entrega<br>
                • Opção de retirada em pontos físicos ou entrega em casa.`
            },
            'info-purpose': {
                title: "Para que serve",
                icon: "🎯",
                price: "R$ 99,90",
                desc: `<strong>Objetivo principal:</strong><br>
                Facilitar o comércio eletrônico para qualquer pessoa ou empresa, oferecendo um ambiente seguro, confiável e com recursos completos para vender e comprar online.<br><br>
                <strong>Uso principal:</strong><br>
                • Compradores: encontrar produtos com várias opções de preço e frete<br>
                • Vendedores: abrir lojas online sem precisar investir em um site próprio<br>
                • Empreendedores: alcançar clientes em toda a região com baixo custo operacional.<br><br>
                <strong>Impacto:</strong><br>
                Torna o comércio mais acessível e competitivo, ajudando empresas de todos os tamanhos a crescerem no digital.`
            },
            'info-companies': {
                title: "Empresas e marcas que usam",
                icon: "🏷️",
                price: "R$ 139,90",
                desc: `<strong>Quem vende no Mercado Livre:</strong><br>
                Grandes marcas, lojas tradicionais e pequenas empresas utilizam a plataforma para alcançar clientes de forma rápida e escalável.<br><br>
                <strong>Exemplos de usuários:</strong><br>
                • Samsung, LG, Sony, Nike, Adidas<br>
                • Lojas de eletrônicos, moda, esportes, beleza, casa e construção<br>
                • Vendedores locais e artesãos<br><br>
                <strong>Por que confiam:</strong><br>
                O marketplace oferece confiança, logística integrada e milhões de visitantes por mês, aumentando significativamente o alcance das vendas.`
            },
            'info-ai': {
                title: "Uso de Inteligência Artificial",
                icon: "🤖",
                price: "R$ 119,90",
                desc: `<strong>Como a IA é usada:</strong><br>
                O Mercado Livre aplica inteligência artificial em várias etapas da jornada do cliente para melhorar eficiência e segurança.<br><br>
                <strong>Principais aplicações:</strong><br>
                • Recomendação de produtos personalizada<br>
                • Busca inteligente com correção de termos<br>
                • Prevenção de fraudes em pagamentos e anúncios<br>
                • Atendimento automatizado com chatbots<br>
                • Análise de dados para tomada de decisão e ofertas inteligentes.<br><br>
                <strong>Benefícios:</strong><br>
                Aumenta a conversão, reduz erros e entrega uma experiência de compra mais rápida e personalizada.`
            },
            'info-value': {
                title: "Valor e avaliação",
                icon: "💵",
                price: "R$ 179,90",
                desc: `<strong>Avaliação de mercado:</strong><br>
                O Mercado Livre é uma das empresas de tecnologia mais valiosas da América Latina, com valor de mercado superior a dezenas de bilhões de dólares.<br><br>
                <strong>Importância financeira:</strong><br>
                • Crescimento constante das receitas<br>
                • Valorização em bolsas internacionais<br>
                • Alta confiança de investidores e analistas.<br><br>
                <strong>Por que isso importa:</strong><br>
                Um valor de mercado alto demonstra estabilidade, capacidade de crescimento e relevância no setor de e-commerce.`
            },
            'info-infrastructure': {
                title: "Servidores e infraestrutura",
                icon: "☁️",
                price: "R$ 149,90",
                desc: `<strong>Arquitetura tecnológica:</strong><br>
                O Mercado Livre utiliza uma infraestrutura híbrida que combina nuvem pública e data centers próprios, garantindo alta disponibilidade e escalabilidade.<br><br>
                <strong>Componentes principais:</strong><br>
                • Computação em nuvem para aplicativos e análise de dados<br>
                • Data centers regionais para reduzir latência<br>
                • Sistemas redundantes para manter a plataforma no ar<br>
                • Segurança e proteção de dados dos usuários.<br><br>
                <strong>Por que é relevante:</strong><br>
                Uma boa infraestrutura permite lidar com picos de tráfego, oferecer serviços rápidos e proteger as transações dos clientes.`
            },
            'info-countries': {
                title: "Usuários em todos os países",
                icon: "🌎",
                price: "R$ 199,90",
                desc: `<strong>Base de usuários por país:</strong><br>
                • Brasil: 95 milhões<br>
                • Argentina: 24 milhões<br>
                • México: 72 milhões<br>
                • Colômbia: 30 milhões<br>
                • Chile: 12 milhões<br>
                • Uruguai: 6 milhões<br>
                • Peru: 18 milhões<br>
                • Venezuela: 8 milhões<br>
                • Equador: 6 milhões<br>
                • Paraguai: 3 milhões<br>
                • Bolívia: 4 milhões<br>
                • Costa Rica: 2,4 milhões<br>
                • Guatemala: 2,8 milhões<br>
                • Panamá: 1,1 milhão<br>
                • El Salvador: 1,7 milhão<br>
                • Honduras: 1,8 milhão<br>
                • República Dominicana: 2,9 milhões<br>
                • Nicarágua: 1,2 milhão<br><br>
                <strong>Importância dos dados:</strong><br>
                Estes números mostram a abrangência do Mercado Livre na América Latina, com forte presença em mercados grandes como Brasil e México, além de crescimento constante em países menores. A base de usuários reforça o papel da empresa como líder regional no comércio eletrônico e no uso de serviços conectados como Mercado Pago e Mercado Envios.`
            }
        };

        // --- CARRINHO ---
        let cart = [];
        let currentProduct = null;

        function navigateToDetail(productId) {
            window.location.href = 'Site2-detail.html?product=' + encodeURIComponent(productId);
        }

        // Mostrar página
        function toggleCountryDetails() {
            const details = document.getElementById('country-details');
            const button = details.previousElementSibling;
            details.classList.toggle('active');
            button.textContent = details.classList.contains('active') ? 'Ocultar detalhes' : 'Ver todos';
        }

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

            window.requestAnimationFrame(() => window.scrollTo(0, 0));
        }

        // Mostrar produto
        function showProduct(productId) {
            const product = products[productId];
            currentProduct = productId;

            document.getElementById('detail-icon').textContent = product.icon;
            document.getElementById('detail-title').textContent = product.title;
            document.getElementById('detail-desc').innerHTML = product.desc;
            document.getElementById('detail-price').textContent = product.price ? `Preço: ${product.price}` : '';

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
