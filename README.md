<!DOCTYPE html>
<html>
<head>
  <title>Funny Flashcards</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    body {
      margin: 0;
      padding: 0;
      height: 100vh;
      width: 100vw;
      overflow: hidden;
      background-color: #98fb98;
    }
    .card {
      position: absolute;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      background-color: #3cb371;
      padding: 1vh;
      border-radius: 2vh;
      font-size: clamp(24px, 18vw, 48px);
      line-height: 1.1;
      text-align: center;
      width: 95vw;
      height: 60vh;
      box-sizing: border-box;
      color: white;
      border: 0.5vh solid #2e8b57;
      box-shadow: 0 0 1vh rgba(0, 0, 0, 0.1);
      display: flex;
      align-items: center;
      justify-content: center;
    }
    #nextBtn {
      position: absolute;
      bottom: 5vh;
      left: 50%;
      transform: translateX(-50%);
      padding: 2vh 4vw;
      font-size: 4vw;
      border: none;
      border-radius: 1vh;
      background-color: #2e8b57;
      color: white;
      cursor: pointer;
    }
    #nextBtn:hover {
      background-color: #228b22;
    }
    @media (orientation: landscape) {
      .card {
        font-size: clamp(20px, 15vw, 40px);
        width: 90vw;
        height: 70vh;
      }
    }
  </style>
</head>
<body>
  <div id="flashcard" class="card"></div>
  <button id="nextBtn" onclick="nextCard()">Next Card</button>

  <script>
    const words = [
      "耳朵", "鼻子", "嘴巴", "身體",
      "春天", "晚上", "時候", "新年", "月亮",
      "開學", "課室", "操場", "放學", "讀書", "寫字",
      "玩耍", "跳舞", "點頭", "說話", "起來", "出來", "休息",
      "高興", "喜歡", "自己",
      "圖畫", "毛衣", "衣服", "糖果", "皮球", "電視",
      "雨點", "蜜蜂", "動物",
      "食物",
      "一起", "再見",
      "顏色", "兒童", "沒有"
    ];
    let currentIndex = 0;

    function showCard() {
      const card = document.getElementById("flashcard");
      if (words.length === 0) {
        card.textContent = "No cards available!";
        return;
      }
      card.style.display = "flex";
      card.textContent = words[currentIndex];
    }

    function nextCard() {
      currentIndex = (currentIndex + 1) % words.length;
      showCard();
    }

    showCard();
  </script>
</body>
</html>
