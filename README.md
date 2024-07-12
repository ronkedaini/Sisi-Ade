<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Food Order Page</title>
    <link href="https://stackpath.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet">
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            color: #333;
            position: relative;
        }
        .container {
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        .food-images {
            text-align: center;
            margin-bottom: 20px;
        }
        .food-item {
            margin-bottom: 20px;
        }
        .food-images img {
            width: 200px;
            height: auto;
            margin: 0 10px;
            border-radius: 8px;
        }
        .watermark {
            position: absolute;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            font-size: 80px;
            color: lightgrey;
            opacity: 0.3;
            white-space: nowrap;
            z-index: -1;
        }
    </style>
    <script>
        function generateOrderID() {
            return 'ORD' + Math.floor(Math.random() * 1000000);
        }
        
        function handleSubmit(event) {
            event.preventDefault();
            const orderID = generateOrderID();
            const phoneNumber = document.getElementById('phone').value;
            const email = document.getElementById('email').value;
            const address = document.getElementById('address').value;
            const orderDetails = document.getElementById('order-details').value;
            const paymentStatus = document.getElementById('payment-status').checked ? 'Paid' : 'Not Paid';

            const message = `Order ID: ${orderID}%0APhone: ${phoneNumber}%0AEmail: ${email}%0AAddress: ${address}%0AOrder Details: ${orderDetails}%0APayment Status: ${paymentStatus}`;

            document.getElementById('order-id').textContent = orderID;
            document.getElementById('whatsapp-link').href = `https://wa.me/2348053773962?text=${message}`;
            document.getElementById('order-form').reset();
        }
    </script>
</head>
<body>
    <div class="container mt-5">
        <h1 class="text-center text-warning">Complete the form to order your African dishes</h1>
        <div class="row mb-4 text-center food-images">
            <div class="col food-item">
                <img src="https://c.ndtvimg.com/2020-06/4v9oqcn_jollof-rice_625x300_15_June_20.jpg" alt="Nigerian Jollof Rice" class="img-fluid rounded">
                <p>Nigerian Jollof Rice</p>
            </div>
            <div class="col food-item">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTol7StrFPD-HxZUOnZ3uSUfrWShUPhhLOsdg&s" alt="Ghanaian Jollof Rice" class="img-fluid rounded">
                <p>Ghanaian Jollof Rice</p>
            </div>
            <div class="col food-item">
                <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSsH8WHCSBvBWhXvj95zDayI8lVdlNZgPjFIQ&s" alt="Fried Rice" class="img-fluid rounded">
                <p>Fried Rice</p>
            </div>
            <div class="col food-item">
                <img src="https://i.ytimg.com/vi/LnfeYXsFi2Y/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDNZcmWUDIJXTfzqmoQKzA_qzS_BQ" alt="Yam with Egg Sauce" class="img-fluid rounded">
                <p>Yam with Egg Sauce</p>
            </div>
        </div>
        <form id="order-form" onsubmit="handleSubmit(event)">
            <div class="form-group">
                <label for="phone">Phone Number:</label>
                <input type="tel" id="phone" name="phone" class="form-control" required>
            </div>
            <div class="form-group">
                <label for="email">Email:</label>
                <input type="email" id="email" name="email" class="form-control" required>
            </div>
            <div class="form-group">
                <label for="address">Address:</label>
                <textarea id="address" name="address" class="form-control" required></textarea>
            </div>
            <div class="form-group">
                <label for="order-details">Order Details:</label>
                <textarea id="order-details" name="order-details" class="form-control" required placeholder="Specify Nigerian or Ghanaian Jollof Rice, quantity, etc."></textarea>
            </div>
            <div class="form-group form-check">
                <input type="checkbox" id="payment-status" name="payment-status" class="form-check-input">
                <label for="payment-status" class="form-check-label">I have paid</label>
            </div>
            <button type="submit" class="btn btn-warning btn-block">Place Order</button>
        </form>
        <p class="text-center mt-4">
            Your Order ID: <span id="order-id"></span><br>
            <a id="whatsapp-link" href="#" target="_blank" class="text-success">Click here to send your order via WhatsApp and attach payment receipt</a>
        </p>
        <p class="text-center">Pay to Test bank, Account name is Adeoti, account number is 123456789.</p>
        <p class="text-center">Note: You can place orders between 8am and 12pm. Delivery will be from 2pm onwards.</p>
    </div>
    <div class="watermark">Sisi Ade's Kitchen</div>
</body>
</html>
