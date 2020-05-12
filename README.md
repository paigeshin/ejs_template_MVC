# ejs_template

제일 많이 쓰던 것이여서 자세한 설명은 생략 

- installation

```jsx
app.set('view engine', 'ejs');
app.set('views', 'views');
```

- import

```jsx
<%- include('includes/head.ejs') %>
```

- key value, loop

```jsx
<%- include('includes/head.ejs') %>
    <link rel="stylesheet" href="/css/product.css">
</head>

<body>
    <%- include('includes/navigation.ejs') %>

    <main>
        <% if (prods.length > 0) { %>
            <div class="grid">
                <% for (let product of prods) { %>
                    <article class="card product-item">
                        <header class="card__header">
                            <h1 class="product__title"><%= product.title %></h1>
                        </header>
                        <div class="card__image">
                            <img src="data:image/jpeg;base64,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"
                                alt="A Book">
                        </div>
                        <div class="card__content">
                            <h2 class="product__price">$19.99</h2>
                            <p class="product__description">A very interesting book about so many even more interesting things!</p>
                        </div>
                        <div class="card__actions">
                            <button class="btn">Add to Cart</button>
                        </div>
                    </article>
                <% } %>
            </div>
        <% } else { %>
            <h1>No Products Found!</h1>
        <% } %>
    </main>
<%- include('includes/end.ejs') %>
```

