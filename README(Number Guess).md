<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Number Guessing Game</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      background: linear-gradient(135deg, #74ebd5, #ACB6E5);
      display: flex;
      justify-content: center;
      align-items: center;
      height: 100vh;
      margin: 0;
    }

    .game-container {
      background: #fff;
      padding: 30px;
      border-radius: 15px;
      box-shadow: 0 8px 16px rgba(0,0,0,0.2);
      text-align: center;
      width: 320px;
    }

    h1 {
      margin-bottom: 20px;
      font-size: 1.8rem;
      color: #333;
    }

    input[type="number"] {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border-radius: 8px;
      border: 1px solid #ccc;
      font-size: 1rem;
      text-align: center;
    }

    button {
      padding: 10px 20px;
      font-size: 1rem;
      border: none;
      border-radius: 8px;
      background: #4CAF50;
      color: white;
      cursor: pointer;
      transition: 0.3s;
    }

    button:hover {
      background: #45a049;
    }

    .message {
      margin-top: 20px;
      font-size: 1rem;
      color: #555;
    }

    .score {
      margin-top: 10px;
      font-size: 0.9rem;
      color: #444;
    }
  </style>
</head>
<body>
  <div class="game-container">
    <h1>Guess the Number 🎯</h1>
    <p>I'm thinking of a number between <b>1 and 100</b></p>

    <input type="number" id="guessInput" placeholder="Enter your guess">
    <button id="guessBtn">Submit Guess</button>
    <button id="restartBtn">Restart</button>

    <p class="message" id="message">Make your first guess!</p>
    <p class="score" id="score">Attempts: 0</p>
  </div>


  <script>
      
      let Attempt = 0;

      
      let randomNumber = Math.floor((Math.random()*100) + 1);

      let button = document.getElementById("guessBtn");
      button.addEventListener("click", function(){
                   
                Attempt++;
               let randomGuess = Number(guessInput.value);

               if (randomNumber === randomGuess) {
                document.getElementById("message").innerHTML = "Congratulations!! Your guess is correct.";
                alert("You have guessed the number in " + Attempt + " attempts");
               }

               else if (randomNumber > randomGuess) {
                document.getElementById("message").innerHTML = "Your guess is very low.";
               }

               else if (randomNumber < randomGuess) {
                document.getElementById("message").innerHTML = "Your guess was high.";
               }

               else {
                document.getElementById("message").innerHTML = "Sorry, You were wrong. Please try again.";
               }

                document.getElementById("score").innerHTML = "Attempts: " + Attempt;    
      });

      let restartButton = document.getElementById("restartBtn");
      restartButton.addEventListener("click", function(){

               Attempt = 0; 
               randomNumber = Math.floor((Math.random() * 100) + 1);

               document.getElementById("guessInput").value = "";
               document.getElementById("message").innerHTML = "Game restarted! Please start guessing again.";
               document.getElementById("score").innerHTML = "Attempts: 0";
      });
  </script>
</body>
</html>