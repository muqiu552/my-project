
<!DOCTYPE html>
<html lang="zh-CN">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>疯狂星期四</title>
  <style>
    body {
      background: linear-gradient(45deg, #ff6b6b, #ff8e8e);
      height: 100vh;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      overflow: hidden;
      margin: 0;
      font-family: 'Comic Sans MS', cursive;
    }

    .container {
      text-align: center;
    }

    h1 {
      font-size: 3em;
      color: #fff;
      text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.3);
      animation: float 3s ease-in-out infinite;
    }

    .hearts {
      position: fixed;
      top: -20px;
      animation: fall linear forwards;
    }

    @keyframes float {

      0%,
      100% {
        transform: translateY(0);
      }

      50% {
        transform: translateY(-20px);
      }
    }

    @keyframes fall {
      to {
        transform: translateY(105vh);
      }
    }

    .balloon {
      width: 50px;
      height: 70px;
      background: #ff4081;
      border-radius: 50%;
      position: absolute;
      bottom: -100px;
      animation: rise 10s linear infinite;
    }

    @keyframes rise {
      0% {
        transform: translateY(0) rotate(0deg);
        opacity: 1;
      }

      100% {
        transform: translateY(-100vh) rotate(360deg);
        opacity: 0;
      }
    }
  </style>
</head>

<body>
  <div class="container">
    <h1>🎉 疯狂星期四 V我50！！！ </h1>
    <!-- <h2 style="color: #fff;">愿你天天开心，梦想成真！</h2> -->
  </div>

  <audio id="music" loop>
    <source src="https://www.bensound.com/bensound-music/bensound-happyrock.mp3" type="audio/mpeg">
  </audio>

  <script>
    // 创建气球
    function createBalloon() {
      const balloon = document.createElement('div');
      balloon.classList.add('balloon');
      balloon.style.left = Math.random() * 100 + 'vw';
      balloon.style.background = `hsl(${Math.random() * 360}, 70%, 60%)`;
      document.body.appendChild(balloon);

      setTimeout(() => {
        balloon.remove();
      }, 10000);
    }

    // 创建爱心
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('hearts');
      heart.innerHTML = '❤';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.fontSize = Math.random() * 20 + 10 + 'px';
      heart.style.animationDuration = Math.random() * 3 + 2 + 's';
      document.body.appendChild(heart);

      setTimeout(() => {
        heart.remove();
      }, 5000);
    }

    // 播放音乐
    document.body.addEventListener('click', () => {
      document.getElementById('music').play();
    });

    // 定期生成气球和爱心
    setInterval(createBalloon, 1000);
    setInterval(createHeart, 300);

    // 闪烁效果
    const title = document.querySelector('h1');
    setInterval(() => {
      title.style.textShadow = `
                ${Math.random() * 4 - 2}px 
                ${Math.random() * 4 - 2}px 
                4px rgba(0,0,0,0.3)
            `;
    }, 100);
  </script>
</body>

</html>
