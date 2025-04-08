
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>For My Love ??</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background: linear-gradient(to bottom, #ff69b4, #000);
      color: white;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      height: 100vh;
      text-align: center;
    }

    .question-card {
      background: rgba(0, 0, 0, 0.6);
      border-radius: 20px;
      padding: 40px;
      max-width: 400px;
      box-shadow: 0 0 20px pink;
      animation: fadeIn 1s ease-in-out;
    }

    button {
      padding: 10px 20px;
      margin: 10px;
      font-size: 16px;
      border: none;
      border-radius: 10px;
      cursor: pointer;
      background-color: #ff69b4;
      color: white;
      transition: 0.3s;
    }

    button:hover {
      background-color: #ff1493;
      transform: scale(1.1);
    }

    .shy-message {
      font-size: 24px;
      color: #ffb6c1;
      animation: shyEffect 1s ease-in-out infinite alternate;
    }

    .birthday-message {
      margin-top: 30px;
      font-size: 22px;
      color: #ffccff;
      animation: fadeInUp 2s ease-in-out;
    }

    @keyframes shyEffect {
      from { transform: scale(1); }
      to { transform: scale(1.05); }
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: scale(0.95); }
      to { opacity: 1; transform: scale(1); }
    }

    @keyframes fadeInUp {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .heart {
      position: fixed;
      top: -50px;
      color: pink;
      font-size: 24px;
      animation: fall linear infinite;
      z-index: 0;
    }

    @keyframes fall {
      to {
        transform: translateY(110vh);
      }
    }
  </style>
</head>
<body>
  <div class="question-card" id="questionCard">
    <h2 id="questionText">Hi my love! Ready for a few cute questions? ??</h2>
    <div id="buttons">
      <button onclick="nextQuestion(true)">Yes</button>
      <button onclick="nextQuestion(false)">No</button>
    </div>
  </div>

  <div id="birthdayMessage" class="birthday-message" style="display: none;">
    ?? Happy Birthday Aazeen Ali ??
  </div>

  <script>
    const questions = [
      "Do you like surprises?",
      "Do you like spending time with me?",
      "Do you think about me when I'm not around?",
      "Would you go on a date with me?",
      "Do you love me?"
    ];

    let current = 0;

    function nextQuestion(answer) {
      if (current === 4) {
        if (answer) {
          document.getElementById('questionCard').innerHTML = `
            <h2 class="shy-message">Aww ?? I knew it... Love you too! ?? <br><br>Tumhaari muskurahat meri pehchaan hai,<br>Tum khush raho yehi meri jaan hai. ??</h2>
          `;
        } else {
          document.getElementById('questionCard').innerHTML = `
            <h2 style="color: #ff6f91;">I know you love me... you're just shy! ??<br><br>Jhoot bol kar tum mujh se bach nahi sakti,<br>Dil ka raaz aankhon se chhup nahi sakta. ??</h2>
          `;
        }
        document.getElementById('birthdayMessage').style.display = 'block';
        return;
      }
      current++;
      document.getElementById('questionText').textContent = questions[current];
    }

    // Heart rain effect
    function createHeart() {
      const heart = document.createElement('div');
      heart.classList.add('heart');
      heart.textContent = '??';
      heart.style.left = Math.random() * 100 + 'vw';
      heart.style.animationDuration = (2 + Math.random() * 3) + 's';
      document.body.appendChild(heart);
      setTimeout(() => heart.remove(), 5000);
    }
    setInterval(createHeart, 300);
  </script>
</body>
</html>
