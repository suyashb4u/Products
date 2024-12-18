<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Product List</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
            margin-top: 50px;
        }
        .search-container {
            margin-bottom: 20px;
        }
        .search-bar {
            width: 300px;
            padding: 10px;
            font-size: 16px;
            border: 1px solid #ccc;
            border-radius: 5px;
        }
        .product-list {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 20px;
        }
        .product-item {
            width: 200px;
            text-align: center;
            cursor: pointer;
        }
        .product-item img {
            width: 100%;
            border-radius: 8px;
        }
        .product-item h3 {
            font-size: 18px;
            margin-top: 10px;
        }
        .product-item p {
            font-size: 16px;
            color: #555;
        }
    </style>
</head>
<body>

    <h1>Our Products</h1>

    <!-- Search Bar -->
    <div class="search-container">
        <input type="text" id="searchBar" class="search-bar" onkeyup="filterProducts()" placeholder="Search for products...">
    </div>

    <div class="product-list" id="productList">
        <!-- Product 1 -->
        <div class="product-item" data-name="Product 1" onclick="window.location.href='https://affiliate-link-1.com';">
            <img src="https://via.placeholder.com/200" alt="Product 1">
            <h3>Product 1</h3>
            <p>Price: $29.99</p>
        </div>

        <!-- Product 2 -->
        <div class="product-item" data-name="Product 2" onclick="window.location.href='https://affiliate-link-2.com';">
            <img src="https://via.placeholder.com/200" alt="Product 2">
            <h3>Product 2</h3>
            <p>Price: $49.99</p>
        </div>

        <!-- Product 3 -->
        <div class="product-item" data-name="Product 3" onclick="window.location.href='https://affiliate-link-3.com';">
            <img src="https://via.placeholder.com/200" alt="Product 3">
            <h3>Product 3</h3>
            <p>Price: $19.99</p>
        </div>

        <!-- Add more products similarly -->
    </div>

    <script>
        // Function to filter products based on search input
        function filterProducts() {
            var input = document.getElementById('searchBar').value.toLowerCase(); // Get the input value
            var products = document.getElementsByClassName('product-item'); // Get all product items

            // Loop through all products and hide those that don't match the search query
            for (var i = 0; i < products.length; i++) {
                var productName = products[i].getAttribute('data-name').toLowerCase(); // Get the product name
                if (productName.indexOf(input) > -1) {
                    products[i].style.display = ""; // Show the product if it matches
                } else {
                    products[i].style.display = "none"; // Hide the product if it doesn't match
                }
            }
        }
    </script>

</body>
</html>
