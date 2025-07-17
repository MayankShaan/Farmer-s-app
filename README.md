# Farmer-s-app
<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>GrainGuard - Moisture Alert</title>
  <link rel="manifest" href="manifest.json">
  <style>
    body {
      font-family: Arial, sans-serif;
      background: #f0f9f0;
      color: #333;
      padding: 20px;
      text-align: center;
    }
    .container {
      max-width: 400px;
      margin: auto;
      background: white;
      padding: 20px;
      border-radius: 12px;
      box-shadow: 0 4px 8px rgba(0,0,0,0.1);
    }
    .moisture {
      font-size: 48px;
      color: #2e7d32;
    }
    .alert {
      color: red;
      font-weight: bold;
    }
    input {
      padding: 10px;
      width: 80%;
      margin: 10px 0;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🌾 GrainGuard</h1>
    <p>Monitor grain storage moisture</p>
    <div class="moisture" id="moistureLevel">--%</div>
    <div id="status"></div>
    <input type="number" id="thresholdInput" placeholder="Set safe limit (default 13%)" />
  </div>  <script>
    const moistureDisplay = document.getElementById('moistureLevel');
    const status = document.getElementById('status');
    const thresholdInput = document.getElementById('thresholdInput');

    let threshold = 13;

    setInterval(() => {
      const simulatedMoisture = Math.floor(Math.random() * 20); // 0 to 19%
      moistureDisplay.textContent = simulatedMoisture + "%";

      const userThreshold = parseFloat(thresholdInput.value);
      if (!isNaN(userThreshold)) threshold = userThreshold;

      if (simulatedMoisture > threshold) {
        status.innerHTML = "⚠️ <span class='alert'>Alert: Moisture too high!</span>";
      } else {
        status.innerHTML = "✅ Safe storage condition.";
      }
    }, 3000);
  </script></body>
</html>
