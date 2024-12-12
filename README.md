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
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

header {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 1rem;
}

nav ul {
    list-style: none;
    display: flex;
    justify-content: center;
    padding: 0;
}

nav ul li {
    margin: 0 1rem;
}

nav ul li a {
    color: white;
    text-decoration: none;
}

#products, #cart {
    padding: 2rem;
}

#product-list {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    gap: 1rem;
}

.product {
    border: 1px solid #ddd;
    padding: 1rem;
    text-align: center;
}

.product button {
    margin-top: 0.5rem;
    padding: 0.5rem;
    background-color: #4CAF50;
    color: white;
    border: none;
    cursor: pointer;
}

#cart ul {
    list-style: none;
    padding: 0;
}
// Mahsulotlar ro'yxati
const products = [
    { id: 1, name: "Mahsulot 1", price: 50000 },
    { id: 2, name: "Mahsulot 2", price: 75000 },
    { id: 3, name: "Mahsulot 3", price: 120000 },
];

// Savat
let cart = [];

// Mahsulotlarni sahifaga chiqarish
function displayProducts() {
    const productList = document.getElementById("product-list");
    products.forEach((product) => {
        const productDiv = document.createElement("div");
        productDiv.className = "product";
        productDiv.innerHTML = `
            <h3>${product.name}</h3>
            <p>${product.price} so'm</p>
            <button onclick="addToCart(${product.id})">Savatchaga qo'shish</button>
        `;
        productList.appendChild(productDiv);
    });
}

// Mahsulotni savatchaga qo'shish
function addToCart(productId) {
    const product = products.find((p) => p.id === productId);
    cart.push(product);
    updateCart();
}

// Savatchani yangilash
function updateCart() {
    const cartItems = document.getElementById("cart-items");
    const totalPrice = document.getElementById("total-price");
    cartItems.innerHTML = "";
    let total = 0;
    cart.forEach((item, index) => {
        total += item.price;
        const cartItem = document.createElement("li");
        cartItem.innerText = `${item.name} - ${item.price} so'm`;
        cartItems.appendChild(cartItem);
    });
    totalPrice.innerText = total;
}

// Sahifani yuklaganda mahsulotlarni ko'rsatish
document.addEventListener("DOMContentLoaded", () => {
    displayProducts();
});
