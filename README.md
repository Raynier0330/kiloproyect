# kiloproyect
<!DOCTYPE html>
<html>

<head>
    <title>Calculadora de Consumo de Kilowatts</title>
    <style>
        body {
            background-color: #d6e9f8; /* Cambio de color de fondo a azul claro */
            font-family: Arial, sans-serif;
        }

        .container {
            width: 400px;
            margin: 100px auto 0; /* Cambio de margen superior para mover el formulario hacia abajo */
            padding: 20px;
            background-color: #ffffff;
            border-radius: 5px;
            box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
        }

        h1 {
            text-align: center;
        }

        form {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        label {
            margin-bottom: 10px;
            font-size: 18px; /* Aumento del tamaño de fuente */
        }

        input[type="number"] {
            padding: 10px;
            width: 100%;
            margin-bottom: 10px;
            font-size: 18px; /* Aumento del tamaño de fuente */
        }

        button {
            padding: 10px;
            width: 100%;
            background-color: #4CAF50;
            color: #ffffff;
            font-weight: bold;
            border: none;
            cursor: pointer;
            transition: background-color 0.3s ease;
            font-size: 18px; /* Aumento del tamaño de fuente */
        }

        button:hover {
            background-color: #45a049;
        }

        #result {
            text-align: center;
            margin-top: 20px;
            font-size: 18px; /* Aumento del tamaño de fuente */
        }
    </style>
</head>

<body>
    <div class="container">
        <h1>Calculadora de Consumo de Kilowatts</h1>
        <form onsubmit="return calculatePrice()">
            <label for="consumo">Consumo de Kilowatts:</label>
            <input type="number" id="consumo" min="0" step="1" required>
            <button type="submit">Calcular Precio</button>
        </form>
        <div id="result"></div>
    </div>

    <script>
        function calculatePrice() {
            var consumo = document.getElementById('consumo').value;
            var precio;

            if (consumo >= 0 && consumo <= 200) {
                precio = 5.55;
            } else if (consumo > 200 && consumo <= 300) {
                precio = 7.88;
            } else if (consumo > 300 && consumo <= 700) {
                precio = 11.46;
            } else {
                precio = 11.68;
            }

            var total = consumo * precio;
            var resultElement = document.getElementById('result');
            resultElement.innerHTML = "El precio a pagar es: $" + total.toFixed(2);
            return false;
        }
    </script>
</body>

</html>
