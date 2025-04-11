# crop-recommendation-system-

  <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Crop Recommendation System</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            text-align: center;
            margin: 50px;
        }
        .container {
            max-width: 400px;
            margin: auto;
            padding: 20px;
            border: 1px solid #ccc;
            border-radius: 10px;
            box-shadow: 2px 2px 12px rgba(0,0,0,0.1);
        }
        input, button {
            margin: 10px;
            padding: 10px;
            width: 80%;
        }
    </style>
</head>
<body>
    <div class="container">
        <h2>Crop Recommendation System</h2>
        <label for="ph">Soil pH Level:</label>
        <input type="number" id="ph" placeholder="Enter pH value">
        <label for="nitrogen">Nitrogen Level:</label>
        <input type="number" id="nitrogen" placeholder="Enter Nitrogen value">
        <label for="moisture">Moisture Level:</label>
        <input type="number" id="moisture" placeholder="Enter Moisture %">
        <button onclick="recommendCrop()">Recommend Crop</button>
        <h3 id="result"></h3>
    </div>

    <script>
        function recommendCrop() {
            let ph = parseFloat(document.getElementById('ph').value);
            let nitrogen = parseFloat(document.getElementById('nitrogen').value);
            let moisture = parseFloat(document.getElementById('moisture').value);
            let crop = "";

            if (ph >= 6 && ph <= 7 && nitrogen > 50 && moisture > 30) {
                crop = "Wheat";
            } else if (ph < 6 && nitrogen > 40 && moisture > 40) {
                crop = "Rice";
            } else if (ph > 7 && nitrogen < 50 && moisture < 30) {
                crop = "Maize";
            } else {
                crop = "No suitable crop found. Adjust parameters.";
            }

            document.getElementById('result').innerText = "Recommended Crop: " + crop;
        }
    </script>
</body>
</html>
