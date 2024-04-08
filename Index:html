<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Digital Currency Faucet</title>
<style>
  body {
    margin: 0;
    padding: 0;
    font-family: Arial, sans-serif;
    background: url('background_video.mp4') no-repeat center center fixed;
    background-size: cover;
  }
  .container {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    height: 100vh;
  }
  .wallet-input {
    margin-bottom: 20px;
    display: flex;
    align-items: center;
  }
  .coin-input {
    margin-right: 10px;
    padding: 8px;
    border: 1px solid #ccc;
    border-radius: 5px;
    font-size: 16px;
  }
  .coin-selection {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
  }
  .coin-buttons {
    display: flex;
    justify-content: center;
    margin-bottom: 20px;
  }
  .coin-button {
    margin-right: 10px;
    padding: 8px 12px;
    background-color: rgba(255, 0, 0, 0.7); /* لون أحمر مع طابقة شفافة */
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    transition: background-color 0.3s ease; /* تحويل التغيير في اللون بأنيميشن */
  }
  .coin-button:hover {
    background-color: rgba(255, 0, 0, 0.9); /* لون خلفية زر أحمر مع طابقة شفافة عند التحوي */
  }
  .coin-button:focus {
    background-color: rgba(255, 0, 0, 0.9); /* تغيير لون الخلفية عند النقر لزر العملة */
    outline: none; /* إزالة التأثير الافتراضي للفوكس على الزر */
  }
  .advertisement {
    margin-bottom: 20px;
    position: relative;
  }
  .advertisement p {
    color: #fff;
    font-size: 16px;
    font-weight: bold;
    text-align: center;
    background-color: rgba(0, 0, 0, 0.5); /* طابقة شفافة */
    padding: 10px;
    border-radius: 5px;
  }
  .claim-button {
    padding: 10px 20px;
    background-color: #28a745;
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
    display: none; /* يبدأ بالاختفاء */
  }
  .claim-button:hover {
    background-color: #218838;
  }
  .ads-button {
    padding: 10px 20px;
    background-color: #ff0000; /* لون أحمر */
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    font-size: 16px;
  }
  .ads-button:hover {
    background-color: #cc0000; /* لون أحمر داكن عند التحويل */
  }
  .timer {
    color: #fff;
    font-size: 20px;
    font-weight: bold;
    margin-bottom: 10px;
  }
</style>
</head>
<body>
<div class="container">
  <div class="wallet-input">
    <input type="text" class="coin-input" placeholder="Enter cWallet address">
  </div>
  <div class="coin-buttons">
    <button class="coin-button" onclick="selectCurrency('BTC')">BTC</button>
    <button class="coin-button" onclick="selectCurrency('ETH')">ETH</button>
    <button class="coin-button" onclick="selectCurrency('LTC')">LTC</button>
    <!-- Add more coin buttons as needed -->
  </div>
  <div class="advertisement" id="advertisement">
    <!-- Change the advertisement text -->
    <p style="display: none;" id="advertisementText">Watch ads for 15 seconds.</p>
  </div>
  <!-- Change the button name and color -->
  <button class="ads-button" onclick="startTimer()">Watch Ads</button>
  <!-- Change the button name and color -->
  <button class="claim-button" onclick="claim()">Claim</button>
  <div class="timer" id="timer" style="display: none;"></div>
</div>

<script>
  var countdown; // تعريف المتغير الذي سيحتوي على معرف العد التنازلي

  function startTimer() {
    var claimButton = document.querySelector('.claim-button');
    var advertisementText = document.getElementById('advertisementText');
    var timerElement = document.getElementById('timer');
    var seconds = 15;
    document.querySelector('.ads-button').style.display = 'none'; // يختفي زر المشاهدة بعد النقر عليه
    advertisementText.style.display = 'block'; // يظهر التنبيه بعد النقر على زر المشاهدة
    countdown = setInterval(function() {
      seconds--;
      advertisementText.innerHTML = 'Watch ads for ' + seconds + ' seconds.';
      if (seconds <= 0) {
        clearInterval(countdown);
        advertisementText.style.display = 'none'; // يختفي التنبيه بعد انتهاء المدة
        var claimButton = document.querySelector('.claim-button');
        claimButton.style.display = 'block'; // يظهر زر المطالبة بعد انتهاء المدة
        timerElement.style.display = 'none'; // يختفي عداد الوقت بعد انتهاء المدة
      }
    }, 1000);
    timerElement.innerHTML = 'Please wait 15 seconds before claiming.'; // نص عداد الوقت
    timerElement.style.display = 'block'; // يظهر عداد الوقت
  }

  function selectCurrency(currency) {
    var coinButton = document.getElementById('coinSelect');
    coinButton.value = currency;
    coinButton.innerHTML = currency;
  }

  function claim() {
    clearInterval(countdown); // إيقاف العد التنازلي عند الضغط على زر المطالبة
    alert("Your claim has been successful.");
    setTimeout(function() {
      window.location.reload(); // يقوم بتحديث الصفحة بعد 5 دقائق
    }, 300000); // 5 دقائق بالمللي ثانية (5 * 60 * 1000)
    document.querySelector('.ads-button').style.display = 'block'; // يظهر زر المشاهدة مرة أخرى بعد الطلب
    document.querySelector('.claim-button').style.display = 'none'; // يختفي زر المطالبة بعد الطلب
  }
</script>
</body>
</html>
