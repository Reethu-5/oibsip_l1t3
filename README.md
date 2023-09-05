# oibsip_l1t3
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Temperature Converter</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f0f0f0;
        }
        .container {
            max-width: 400px;
            margin: 0 auto;
            text-align: center;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 5px;
            background-color: #fff;
        }
        h1 {
            color: #333;
        }
        label {
            font-weight: bold;
        }
        input[type="number"] {
            width: 100%;
            padding: 8px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
        select {
            width: 100%;
            padding: 8px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 3px;
        }
        button {
            background-color: #007bff;
            color: #fff;
            border: none;
            border-radius: 3px;
            padding: 10px 20px;
            cursor: pointer;
        }
        button:hover {
            background-color: #0056b3;
        }
        #result {
            margin-top: 15px;
            font-size: 1.2em;
        }
    </style>
</head>
<body>
    <div class="container">
        <h1>Temperature Converter</h1>
        <label for="inputTemp">Enter Temperature:</label>
        <input type="number" id="inputTemp" placeholder="Enter temperature">
        <label for="unitSelector">Select Temperature Type:</label>
        <select id="unitSelector">
            <option value="celsius">Celsius</option>
            <option value="fahrenheit">Fahrenheit</option>
        </select>
        <br><br>
        <button onclick="convertTemperature()">Convert</button>
        <br><br>
        <div id="result"></div>
    </div>

    <script>
        function convertTemperature() {
            // Get the input temperature and selected unit
            const inputTemp = parseFloat(document.getElementById("inputTemp").value);
            const unit = document.getElementById("unitSelector").value;

            // Check if the input is a valid number
            if (isNaN(inputTemp)) {
                document.getElementById("result").innerHTML = "Please enter a valid number.";
                return;
            }

            // Determine the temperature type label
            const tempLabel = unit === "celsius" ? "Celsius" : "Fahrenheit";

            // Perform the conversion
            let result;
            if (unit === "celsius") {
                // Convert Celsius to Fahrenheit
                result = (inputTemp * 9/5) + 32;
                document.getElementById("result").innerHTML = `${inputTemp} &deg;${tempLabel} is equal to ${result.toFixed(2)} &deg;Fahrenheit.`;
            } else {
                // Convert Fahrenheit to Celsius
                result = (inputTemp - 32) * 5/9;
                document.getElementById("result").innerHTML = `${inputTemp} &deg;${tempLabel} is equal to ${result.toFixed(2)} &deg;Celsius.`;
            }
        }
    </script>
</body>
</html>
