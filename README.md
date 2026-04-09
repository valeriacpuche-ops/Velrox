<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Velrox | Tienda Oficial</title>
    <style>
        :root {
            --bg-crema: #f9f5f0;
            --oro-rosa: #b76e79;
            --texto: #4a4a4a;
            --blanco: #ffffff;
        }

        body {
            font-family: 'Segoe UI', sans-serif;
            background-color: var(--bg-crema);
            color: var(--texto);
            margin: 0;
            padding: 0;
        }

        /* HEADER ESTILO ATENEA */
        header {
            background: var(--blanco);
            padding: 15px 0;
            text-align: center;
            border-bottom: 1px solid #e0e0e0;
            position: sticky;
            top: 0;
            z-index: 100;
        }

        .logo {
            font-size: 28px;
            letter-spacing: 6px;
            font-weight: 300;
            color: var(--oro-rosa);
            margin: 0;
        }

        /* CARRITO */
        .cart-icon {
            position: absolute;
            right: 20px;
            top: 20px;
            cursor: pointer;
            font-size: 20px;
        }

        /* GRID DE PRODUCTOS (2 Columnas como en tu imagen) */
        .container {
            max-width: 1000px;
            margin: 20px auto;
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 15px;
            padding: 10px;
        }

        .product-card {
            background: var(--blanco);
            border: 1px solid #eee;
            padding-bottom: 15px;
            position: relative;
        }

        .img-placeholder {
            background-color: #f4f4f4;
            width: 100%;
            aspect-ratio: 1/1.1;
            display: flex;
            align-items: center;
            justify-content: center;
            color: #ccc;
            font-size: 12px;
        }

        .product-info {
            padding: 10px;
        }

        .product-info h3 {
            font-size: 13px;
            text-transform: uppercase;
            margin: 5px 0;
            font-weight: 500;
        }

        .price {
            font-size: 15px;
            color: #888;
            margin-bottom: 10px;
        }

        .add-btn {
            background: var(--blanco);
            border: 1px solid #ddd;
            border-radius: 50%;
            width: 35px;
            height: 35px;
            position: absolute;
            bottom: 50px;
            right: 15px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        /* MODAL CARRITO / PAGO */
        #checkout-modal {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0,0,0,0.5);
            justify-content: center;
            align-items: center;
        }

        .modal-content {
            background: white;
            padding: 30px;
            border-radius: 10px;
            width: 90%;
            max-width: 400px;
            text-align: center;
        }

        .pay-btn {
            background: var(--oro-rosa);
            color: white;
            border: none;
            padding: 10px 20px;
            width: 100%;
            margin-top: 15px;
            cursor: pointer;
        }
    </style>
</head>
<body>

    <header>
        <div class="logo">VELROX</div>
        <div class="cart-icon" onclick="openCheckout()">🛒 <span id="count">0</span></div>
    </header>

    <div class="container">
        <div class="product-card">
            <div class="img-placeholder">IMAGEN PRODUCTO</div>
            <button class="add-btn" onclick="add(14000)">🛒</button>
            <div class="product-info">
                [span_0](start_span)<h3>Labial 2 en 1 Contorno</h3>[span_0](end_span)
                [span_1](start_span)<p class="price">$14.000</p>[span_1](end_span)
            </div>
        </div>

        <div class="product-card">
            <div class="img-placeholder">IMAGEN PRODUCTO</div>
            <button class="add-btn" onclick="add(15000)">🛒</button>
            <div class="product-info">
                [span_2](start_span)<h3>Serum Retinol</h3>[span_2](end_span)
                [span_3](start_span)<p class="price">$15.000</p>[span_3](end_span)
            </div>
        </div>

        <div class="product-card">
            <div class="img-placeholder">IMAGEN PRODUCTO</div>
            <button class="add-btn" onclick="add(3000)">🛒</button>
            <div class="product-info">
                [span_4](start_span)<h3>Colágeno de Ojeras</h3>[span_4](end_span)
                [span_5](start_span)<p class="price">$3.000</p>[span_5](end_span)
            </div>
        </div>

        <div class="product-card">
            <div class="img-placeholder">IMAGEN PRODUCTO</div>
            <button class="add-btn" onclick="add(25000)">🛒</button>
            <div class="product-info">
                [span_6](start_span)<h3>Kit Brochas Profesionales</h3>[span_6](end_span)
                [span_7](start_span)<p class="price">$25.000</p>[span_7](end_span)
            </div>
        </div>
    </div>

    <div id="checkout-modal">
        <div class="modal-content">
            <h2>Finalizar Compra</h2>
            <p>Total a pagar: <strong id="total-pay">$0</strong></p>
            <hr>
            <p>Método de Pago: <strong>Transferencia Bancaria / WhatsApp</strong></p>
            <button class="pay-btn" onclick="alert('Pedido enviado a Velrox!')">Confirmar Pedido</button>
            <button style="background:none; border:none; color:red; margin-top:10px; cursor:pointer;" onclick="closeCheckout()">Cerrar</button>
        </div>
    </div>

    <script>
        let total = 0;
        let items = 0;

        function add(price) {
            total += price;
            items++;
            document.getElementById('count').innerText = items;
            alert("Producto añadido!");
        }

        function openCheckout() {
            document.getElementById('total-pay').innerText = "$" + total;
            document.getElementById('checkout-modal').style.display = 'flex';
        }

        function closeCheckout() {
            document.getElementById('checkout-modal').style.display = 'none';
        }
    </script>
</body>
</html>
