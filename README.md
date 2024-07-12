<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Food Order Page</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            color: #333;
        }
        .container {
            width: 50%;
            margin: 0 auto;
            background-color: #fff;
            padding: 20px;
            border-radius: 8px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }
        h1 {
            text-align: center;
            color: #ff6600;
        }
        .food-images {
            text-align: center;
            margin-bottom: 20px;
        }
        .food-images img {
            width: 200px;
            height: auto;
            margin: 0 10px;
            border-radius: 8px;
        }
        form {
            display: flex;
            flex-direction: column;
        }
        label {
            margin: 10px 0 5px;
        }
        input, select, textarea {
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 4px;
            margin-bottom: 15px;
        }
        button {
            padding: 10px;
            background-color: #ff6600;
            color: #fff;
            border: none;
            border-radius: 4px;
            cursor: pointer;
            font-size: 16px;
        }
        button:hover {
            background-color: #e55b00;
        }
        .whatsapp-link {
            text-align: center;
            margin-top: 20px;
        }
        .whatsapp-link a {
            color: #25D366;
            font-size: 18px;
            text-decoration: none;
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

            const message = `Order ID: ${orderID}%0APhone: ${phoneNumber}%0AEmail: ${email}%0AAddress: ${address}%0AOrder Details: ${orderDetails}`;

            document.getElementById('order-id').textContent = orderID;
            document.getElementById('whatsapp-link').href = `https://wa.me/971568531596?text=${message}`;
            document.getElementById('order-form').reset();
        }
    </script>
</head>
<body>
    <div class="container">
        <h1>Order Your Jollof Rice</h1>
        <div class="food-images">
            <img src=" https://drive.google.com/file/d/1f-4LbcTB63_IsiRuwomTo8lAmCF5bXwT/view?usp=sharing" alt="Nigerian Jollof Rice">
            <img src=" https://drive.google.com/file/d/1R18MH3Lsm4URurXhFhMbbqHluQBycq7y/view?usp=sharing" alt="Ghanaian Jollof Rice">
        </div>
        <form id="order-form" onsubmit="handleSubmit(event)">
            <label for="phone">Phone Number:</label>
            <input type="tel" id="phone" name="phone" required>
            
            <label for="email">Email:</label>
            <input type="email" id="email" name="email" required>
            
            <label for="address">Address:</label>
            <textarea id="address" name="address" required></textarea>
            
            <label for="order-details">Order Details:</label>
            <textarea id="order-details" name="order-details" required placeholder="Specify Nigerian or Ghanaian Jollof Rice, quantity, etc."></textarea>
            
            <button type="submit">Place Order</button>
        </form>
        <p class="whatsapp-link">
            Your Order ID: <span id="order-id"></span><br>
            <a id="whatsapp-link" href="#" target="_blank">Click here to send your order via WhatsApp</a>
        </p>
        <p>Note: You can place orders between 8am and 12pm. Delivery will be from 2pm onwards.</p>
    </div>
</body>
</html>
![image](https://github.com/user-attachments/assets/eba3e48e-7e32-4b8b-87b0-9aeda32033e9)
