# Arzon-tovarlar
<!DOCTYPE html>
<html lang="uz">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Online Do'kon</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <header>
        <h1>Online Do'kon</h1>
        <nav>
            <ul>
                <li><a href="#products">Mahsulotlar</a></li>
                <li><a href="#cart">Savat</a></li>
                <li><a href="#contact">Aloqa</a></li>
            </ul>
        </nav>
    </header>
    <main>
        <section id="products">
            <h2>Mahsulotlar</h2>
            <div id="product-list">
                <!-- Mahsulotlar dinamik ravishda qo'shiladi -->
            </div>
        </section>
        <section id="cart">
            <h2>Savat</h2>
            <ul id="cart-items"></ul>
            <p>Umumiy narx: <span id="total-price">0</span> so'm</p>
            <button id="checkout">Buyurtma qilish</button>
        </section>
    </main>
    <footer>
        <p>&copy; 2024 Online Do'kon. Barcha huquqlar himoyalangan.</p>
    </footer>
    <script src="script.js"></script>
</body>
</html>
