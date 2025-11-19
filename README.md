<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Global Money Converter</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 20px;
      background: #f4f4f4;
    }
    .container {
      max-width: 600px;
      background: white;
      padding: 20px;
      margin: auto;
      border-radius: 10px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.2);
    }
    input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 6px;
      border: 1px solid #ccc;
      font-size: 16px;
    }
    button {
      width: 100%;
      padding: 10px;
      background: #007bff;
      color: white;
      border: none;
      border-radius: 6px;
      font-size: 16px;
      cursor: pointer;
    }
    button:hover {
      background: #0056b3;
    }
    .results {
      margin-top: 20px;
    }
    .ad-box {
      width: 100%;
      height: 120px;
      background: #eee;
      border: 1px dashed #bbb;
      display: flex;
      align-items: center;
      justify-content: center;
      border-radius: 8px;
      margin-top: 20px;
      font-size: 14px;
      color: #666;
    }
    .membership-box {
      background: #d7f7d7;
      padding: 15px;
      border-radius: 8px;
      margin-top: 20px;
      border: 1px solid #8cd98c;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>Global Money Value Converter</h1>
    <p>Enter how much money you currently have:</p>
    <input type="number" id="usdInput" placeholder="Enter amount in USD" />
    <button onclick="convertMoney()">Convert</button>

    <div class="results" id="results"></div>

    <div class="ad-box">Ad Space (Insert AdSense Code Here)</div>

    <div class="membership-box">
      <h3>Membership</h3>
      <p>Become a premium member to remove ads and unlock unlimited conversions!</p>
      <button>Join Membership (placeholder)</button>
    </div>
  </div>

  <script>
    const rates = {
      Europe: 0.92,
      UK: 0.79,
      Canada: 1.33,
      Australia: 1.52,
      Mexico: 17.1,
      India: 83.2,
      China: 7.1,
      Japan: 147.3,
      SouthKorea: 1380.5,
      Brazil: 5.6,
      SouthAfrica: 18.9,
      Switzerland: 0.86,
      Sweden: 10.5,
      Norway: 10.8,
      Russia: 93.2,
      Turkey: 33.1,
      SaudiArabia: 3.75,
      UAE: 3.67,
      Singapore: 1.34,
      Philippines: 56.8,
      Indonesia: 15800,
      Vietnam: 24250,
      Egypt: 48.5,
      Thailand: 35.2,
      Malaysia: 4.7,
      Argentina: 850
    };

    function convertMoney() {
      const usd = parseFloat(document.getElementById("usdInput").value);
      const resultsDiv = document.getElementById("results");

      if (isNaN(usd) || usd <= 0) {
        resultsDiv.innerHTML = "<p>Please enter a valid amount.</p>";
        return;
      }

      let html = "<h2>Converted Values</h2>";
      for (const country in rates) {
        html += `<p><strong>${country}:</strong> ${ (usd * rates[country]).toLocaleString() }</p>`;
      }

      resultsDiv.innerHTML = html;
    }
  </script>
</body>
</html>
