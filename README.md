<!DOCTYPE html>
<html lang="zh-CN">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>极简合约/期货计算器</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <div class="container">
    <h2>合约计算器</h2>
    <label>方向:
      <select id="direction">
        <option value="long">做多</option>
        <option value="short">做空</option>
      </select>
    </label>
    <label>开仓价格: <input type="number" id="entry" step="0.01"></label>
    <label>当前价格: <input type="number" id="current" step="0.01"></label>
    <label>仓位金额(U): <input type="number" id="amount"></label>
    <label>杠杆倍数: <input type="number" id="leverage" value="10"></label>
    <label>止损比例(%): <input type="number" id="stoploss" value="2"></label>
    <label>复利周期(次): <input type="number" id="cycles" value="5"></label>
    <div id="result"></div>
  </div>

  <!-- 底部悬浮按钮 -->
  <div class="bottom-bar">
    <button onclick="calculate()">立即计算</button>
  </div>

  <script src="app.js"></script>
</body>
</html>
