<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Agent X: Operation Iron Curtain</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #2c3e50;
            color: white;
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            flex-direction: column;
        }

        h1 {
            font-size: 3rem;
            text-align: center;
            margin-bottom: 30px;
        }

        button {
            padding: 10px 20px;
            font-size: 1.5rem;
            color: #fff;
            background-color: #e74c3c;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: background-color 0.3s;
        }

        button:hover {
            background-color: #c0392b;
        }

        .game-container {
            text-align: center;
            display: none;
        }

        .game-message {
            font-size: 1.5rem;
            margin-top: 20px;
        }

        .game-result {
            font-size: 2rem;
            font-weight: bold;
        }

        .game-result.success {
            color: #27ae60;
        }

        .game-result.failure {
            color: #e74c3c;
        }
    </style>
</head>
<body>

    <h1>Agent X: Operation Iron Curtain</h1>
    <button id="startBtn">Start Mission</button>

    <div class="game-container">
        <p class="game-message" id="message">You have been assigned a covert mission in the heart of the Cold War. Are you ready to begin?</p>
        <button id="nextBtn">Next Step</button>
    </div>

    <script>
        document.getElementById('startBtn').addEventListener('click', function() {
            document.getElementById('startBtn').style.display = 'none';
            document.querySelector('.game-container').style.display = 'block';
        });

        document.getElementById('nextBtn').addEventListener('click', function() {
            let message = document.getElementById('message');
            let result = document.createElement('p');
            result.classList.add('game-result');
            let randomOutcome = Math.random();

            if (randomOutcome > 0.5) {
                message.textContent = "Mission Successful! You've infiltrated the enemy camp.";
                result.textContent = "Victory!";
                result.classList.add('success');
            } else {
                message.textContent = "Mission Failed! You were caught by the enemy agents.";
                result.textContent = "Failure!";
                result.classList.add('failure');
            }

            document.querySelector('.game-container').appendChild(result);
            document.getElementById('nextBtn').disabled = true;  // Disable the button after the result
        });
    </script>
</body>
</html>
