<!DOCTYPE html>
<html lang="tr">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ROI Hesaplayıcı</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 0;
      padding: 0;
    }

    .container {
      display: flex;
      justify-content: center;
      align-items: center;
      height: 80px;
    }

    .table {
      width: 200px;
      height: 100%;
      text-align: center;
      display: table;
      background-color: #f9f9f9;
      border: 1px solid #ccc;
      font-size: 1.2em;
    }

    .cell {
      display: table-cell;
      vertical-align: middle;
      color: #333;
    }

    .green-bold {
      color: green;
      font-weight: bold;
    }

    .divider {
      width: 2px;
      height: 60%;
      background-color: #ccc;
    }
  </style>
</head>
<body>
  <div class="container">
    <div class="table">
      <div class="cell">ROI: <span id="roi" class="green-bold"></span></div>
    </div>
    <div class="divider"></div>
    <div class="table">
      <div class="cell">Proje Gün Sayısı: <span id="days" class="green-bold"></span></div>
    </div>
  </div>

  <script>
    const roiStartDate = new Date("2024-01-01");
    const daysStartDate = new Date("2024-02-15");
    const roiDailyIncrease = 2;
    const today = new Date();

    const roiDiffDays = Math.floor((today - roiStartDate) / (1000 * 60 * 60 * 24));
    const daysDiffDays = Math.floor((today - daysStartDate) / (1000 * 60 * 60 * 24));

    const roi = roiDailyIncrease * (roiDiffDays + 1);
    const daysCount = daysDiffDays + 1;

    document.getElementById("roi").textContent = roi + "%";
    document.getElementById("days").textContent = daysCount + " gün";
  </script>
</body>
</html>
