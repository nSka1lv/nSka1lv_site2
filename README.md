<html lang="ru">
<head>
  <meta charset="UTF-8">
  <title>Мой IP и время</title>
  <style>
    body {
      background-image: url('[file:///C:/Users/Home/Downloads/background.jpg](https://sun9-46.userapi.com/s/v1/ig2/kXYTYl5fHnO4gq-E8N_x0iKiEhADXvm47u0MqhVyrdxI9UgNBpcWG8OqA86WbZaTp0GgaTjl9QNhIJrAeS7NCODd.jpg?quality=95&as=32x24,48x36,72x55,108x82,160x121,240x182,360x273,480x364,540x409,640x485,720x546,1080x819,1280x970,1440x1092,2560x1941&from=bu&u=JyEO6ttvk6yKTihBBi0RCZ8yK9c94p7N0VDXIJhtXVQ&cs=640x0)')
      color: white;
      font-family: Arial;
      text-align: center;
      padding-top: 100px;
    }
    .box {
      background: #00BFFF;
      padding: 20px;
      border-radius: 15px;
      display: inline-block;
      font-size: 20px;
    }
  </style>
</head>
<body>

  <div class="box">
    <h2>информация о тебе</h2>
    <p>IP адрес: <span id="ip">подожди</span></p>
    <p>дата и время: <span id="time"></span></p>
  </div>

  <script>
    // Время
    function updateTime() {
      const now = new Date();
      document.getElementById("time").textContent =
        now.toLocaleDateString() + " " + now.toLocaleTimeString();
    }
    setInterval(updateTime, 1000);
    updateTime();

    // IP
    fetch("https://api.ipify.org?format=json")
      .then(res => res.json())
      .then(data => {
        document.getElementById("ip").textContent = data.ip;
      });
  </script>

</body>
</html>
