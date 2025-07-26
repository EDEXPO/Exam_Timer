<!DOCTYPE html>
<html>
<head>
  <style>
    .vertical-center {
      margin: 0;
      position: absolute;
      top: 50%;
      -ms-transform: translateY(-50%);
      transform: translateY(-50%);
    }

    .button {
      border: none;
      color: white;
      position: absolute;
      left: 50%;
      top: 70%;
      text-align: center;
      text-decoration: none;
      display: inline-block;
      font-size: 16px;
      margin: 4px 2px;
      cursor: pointer;
      transform: translateX(-50%);
      padding: 15px 30px;
      background-color: #4CAF50;
      border-radius: 5px;
    }

    body {
      background-color: lightblue;
    }

    h1 {
      font-size: 250px;
      color: white;
      text-align: center;
    }

    p {
      font-family: verdana;
      font-size: 20px;
      text-align: center;
    }

    .timer {
      font-size: 40px;
      color: white;
      text-align: center;
      margin-top: 50px;
    }
  </style>
</head>
<body>

  <h1>Exam Timer</h1>
  <p>To help Students and Teachers.</p>

  <div class="button">
    <button class="button" onclick="startCountdown()">Start Test</button>
  </div>

  <div class="timer" id="timer">Time Remaining: 00:00</div>

  <script>
    let countdown;
    let timeRemaining = 10 * 60; // Set time in seconds (10 minutes)
    
    function startCountdown() {
      document.body.style.backgroundColor = 'red'; // Change background color when button is clicked

      countdown = setInterval(function() {
        let minutes = Math.floor(timeRemaining / 60);
        let seconds = timeRemaining % 60;
        if (seconds < 10) seconds = "0" + seconds;
        document.getElementById('timer').innerText = `Time Remaining: ${minutes}:${seconds}`;

        timeRemaining--;

        if (timeRemaining < 0) {
          clearInterval(countdown);
          document.getElementById('timer').innerText = "Time's up!";
        }
      }, 1000);
    }
  </script>

</body>
</html>
