<!DOCTYPE html>
<html lang="pt">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Venda de Produtos Alimentares - Moçambique</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            color: #333;
        }
        header {
            background-color: #005500;
            color: #fff;
            padding: 1rem;
            text-align: center;
        }
        nav {
            display: flex;
            justify-content: space-around;
            background-color: #007700;
            padding: 0.5rem;
        }
        nav a {
            color: #fff;
            text-decoration: none;
            font-weight: bold;
        }
        .hero {
            text-align: center;
            padding: 2rem;
            background: url('banner.jpg') no-repeat center center/cover;
            color: white;
        }
        .hero h1 {
            font-size: 2.5rem;
        }
        .products {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 1rem;
            padding: 2rem;
        }
        .product {
            background: white;
            border: 1px solid #ddd;
            border-radius: 5px;
            padding: 1rem;
            text-align: center;
        }
        .product img {
            max-width: 100%;
            border-radius: 5px;
        }
        .product button {
            background-color: #007700;
            color: white;
            border: none;
            padding: 0.5rem 1rem;
            cursor: pointer;
            border-radius: 5px;
        }
        .product button:hover {
            background-color: #005500;
        }
        .cart {
            padding: 2rem;
            background-color: #f1f1f1;
            border-top: 1px solid #ddd;
        }
        footer {
            text-align: center;
            padding: 1rem;
            background-color: #005500;
            color: white;
        }
    </style>
    <script>
        let cart = [];

        function addToCart(productName, price) {
            const item = { name: productName, price: price };
            cart.push(item);
            alert(`${productName} foi adicionado ao carrinho.`);
            updateCart();
        }

        function updateCart() {
            const cartSection = document.getElementById('cart-items');
            cartSection.innerHTML = '';
            let total = 0;
            cart.forEach((item, index) => {
                total += item.price;
                cartSection.innerHTML += `<p>${item.name} - ${item.price} MZN <button onclick="removeFromCart(${index})">Remover</button></p>`;
            });
            document.getElementById('total').innerText = `Total: ${total} MZN`;
        }

        function removeFromCart(index) {
            cart.splice(index, 1);
            updateCart();
        }

        function checkout() {
            if (cart.length === 0) {
                alert('O carrinho está vazio. Adicione produtos antes de finalizar a compra.');
                return;
            }
            alert('A integração de pagamento será implementada aqui.');
        }
    </script>
</head>
<body>
    <header>
        <h1>Venda de Produtos Alimentares</h1>
        <p>Os melhores produtos diretamente da África do Sul para Moçambique</p>
    </header>
    <nav>
        <a href="#produtos">Produtos</a>
        <a href="#sobre">Sobre Nós</a>
        <a href="#contato">Contato</a>
    </nav>
    <div class="hero">
        <h1>Produtos Frescos e de Qualidade</h1>
        <p>Descubra uma vasta gama de produtos alimentares.</p>
    </div>
    <section id="produtos" class="products">
        <div class="product">
            <img src="produto1.jpg" alt="Produto 1">
            <h2>Arroz de Qualidade</h2>
            <p>Disponível em sacos de 5kg e 10kg.</p>
            <p><strong>Preço: 500 MZN</strong></p>
            <button onclick="addToCart('Arroz de Qualidade', 500)">Comprar Agora</button>
        </div>
        <div class="product">
            <img src="produto2.jpg" alt="Produto 2">
            <h2>Óleo de Cozinha</h2>
            <p>Óleo vegetal em garrafas de 1L e 5L.</p>
            <p><strong>Preço: 300 MZN</strong></p>
            <button onclick="addToCart('Óleo de Cozinha', 300)">Comprar Agora</button>
        </div>
        <!-- Adicione mais produtos aqui -->
    </section>
    <section id="cart" class="cart">
        <h2>Carrinho de Compras</h2>
        <div id="cart-items"></div>
        <p id="total">Total: 0 MZN</p>
        <button onclick="checkout()">Finalizar Compra</button>
    </section>
    <section id="sobre" style="padding: 2rem; text-align: center;">
        <h2>Sobre Nós</h2>
        <p>Somos uma empresa dedicada a trazer produtos alimentares de alta qualidade da África do Sul para o mercado moçambicano. Garantimos preços acessíveis e um serviço confiável.</p>
    </section>
    <section id="contato" style="padding: 2rem; text-align: center;">
        <h2>Contato</h2>
        <p>Telefone: +258 84 123 4567</p>
        <p>Email: info@produtosalimentares.co.mz</p>
        <p>Endereço: Maputo, Moçambique</p>
    </section>
    <footer>
        <p>&copy; 2024 Venda de Produtos Alimentares. Todos os direitos reservados.</p>
    </footer>
</body>
</html>
