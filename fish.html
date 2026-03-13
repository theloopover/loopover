<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Classic Snake</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #1a1a1a;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            color: #ececec;
        }

        .game-container {
            position: relative;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .header {
            width: 400px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            margin-bottom: 12px;
        }

        #score {
            font-size: 24px;
            font-weight: bold;
            color: #4CAF50;
            letter-spacing: 1px;
        }

        canvas {
            background-color: #242424;
            border-radius: 8px;
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.5);
        }

        #overlay {
            position: absolute;
            top: 46px; /* Offsets below the header */
            left: 0;
            width: 400px;
            height: 400px;
            background: rgba(26, 26, 26, 0.85);
            border-radius: 8px;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
            z-index: 10;
        }

        #overlay h2 {
            margin: 0 0 10px 0;
            font-size: 28px;
            color: #fff;
        }

        #overlay p {
            margin: 0;
            font-size: 16px;
            color: #aaa;
        }

        .hidden {
            display: none !important;
        }
    </style>
</head>
<body>

    <div class="game-container">
        <div class="header">
            <div id="score">SCORE: 0</div>
        </div>
        
        <canvas id="gameCanvas" width="400" height="400"></canvas>
        
        <div id="overlay">
            <h2 id="overlay-title">SNAKE</h2>
            <p>Press <strong>Arrows</strong> or <strong>WASD</strong> to Start</p>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('gameCanvas');
        const ctx = canvas.getContext('2d');
        const scoreElement = document.getElementById('score');
        const overlay = document.getElementById('overlay');
        const overlayTitle = document.getElementById('overlay-title');

        // Game settings
        const grid = 20;
        let fps = 10; // Controls snake speed
        let score = 0;
        let isPlaying = false;
        let gameLoopTimeout;

        // Snake setup
        let snake = {
            x: 160,
            y: 160,
            dx: grid,
            dy: 0,
            cells: [],
            maxCells: 4
        };

        // Food setup
        let food = {
            x: 320,
            y: 320
        };

        // Random integer generator for food placement
        function getRandomInt(min, max) {
            return Math.floor(Math.random() * (max - min)) + min;
        }

        function resetGame() {
            snake.x = 160;
            snake.y = 160;
            snake.cells = [];
            snake.maxCells = 4;
            snake.dx = grid;
            snake.dy = 0;
            score = 0;
            scoreElement.innerText = `SCORE: ${score}`;
            placeFood();
        }

        function placeFood() {
            food.x = getRandomInt(0, 20) * grid;
            food.y = getRandomInt(0, 20) * grid;
            
            // Ensure food doesn't spawn inside the snake
            snake.cells.forEach(cell => {
                if (cell.x === food.x && cell.y === food.y) {
                    placeFood();
                }
            });
        }

        function loop() {
            if (!isPlaying) return;

            gameLoopTimeout = setTimeout(() => {
                requestAnimationFrame(loop);
            }, 1000 / fps);

            ctx.clearRect(0, 0, canvas.width, canvas.height);

            // Move snake
            snake.x += snake.dx;
            snake.y += snake.dy;

            // Wall wrapping (Cross borders)
            if (snake.x < 0) {
                snake.x = canvas.width - grid;
            } else if (snake.x >= canvas.width) {
                snake.x = 0;
            }
            if (snake.y < 0) {
                snake.y = canvas.height - grid;
            } else if (snake.y >= canvas.height) {
                snake.y = 0;
            }

            // Keep track of where snake has been
            snake.cells.unshift({ x: snake.x, y: snake.y });

            // Remove tail as it moves forward
            if (snake.cells.length > snake.maxCells) {
                snake.cells.pop();
            }

            // Draw food
            ctx.fillStyle = '#ff4757'; // Modern flat red
            ctx.beginPath();
            ctx.arc(food.x + grid / 2, food.y + grid / 2, grid / 2 - 2, 0, Math.PI * 2);
            ctx.fill();

            // Draw snake
            ctx.fillStyle = '#4CAF50'; // Modern flat green
            snake.cells.forEach(function (cell, index) {
                // Make the head slightly different/rounded
                if (index === 0) {
                    ctx.fillStyle = '#45a049'; 
                } else {
                    ctx.fillStyle = '#4CAF50';
                }
                
                // Draw cells slightly smaller than grid to show gaps (minimalist style)
                ctx.fillRect(cell.x + 1, cell.y + 1, grid - 2, grid - 2);

                // Collision detection with self
                for (let i = index + 1; i < snake.cells.length; i++) {
                    if (cell.x === snake.cells[i].x && cell.y === snake.cells[i].y) {
                        gameOver();
                    }
                }
            });

            // Food collision
            if (snake.x === food.x && snake.y === food.y) {
                snake.maxCells++;
                score += 10;
                scoreElement.innerText = `SCORE: ${score}`;
                placeFood();
            }
        }

        function startGame() {
            if (!isPlaying) {
                overlay.classList.add('hidden');
                isPlaying = true;
                resetGame();
                requestAnimationFrame(loop);
            }
        }

        function gameOver() {
            isPlaying = false;
            clearTimeout(gameLoopTimeout);
            overlayTitle.innerText = "GAME OVER";
            overlay.classList.remove('hidden');
        }

        // Listen to keyboard events to move the snake
        document.addEventListener('keydown', function (e) {
            // Prevent default scrolling for arrow keys and space
            if(["ArrowUp","ArrowDown","ArrowLeft","ArrowRight"," "].indexOf(e.key) > -1) {
                e.preventDefault();
            }

            const key = e.key.toLowerCase();

            // Left: left arrow or 'a'
            if ((key === 'arrowleft' || key === 'a') && snake.dx === 0) {
                snake.dx = -grid;
                snake.dy = 0;
                startGame();
            }
            // Up: up arrow or 'w'
            else if ((key === 'arrowup' || key === 'w') && snake.dy === 0) {
                snake.dy = -grid;
                snake.dx = 0;
                startGame();
            }
            // Right: right arrow or 'd'
            else if ((key === 'arrowright' || key === 'd') && snake.dx === 0) {
                snake.dx = grid;
                snake.dy = 0;
                startGame();
            }
            // Down: down arrow or 's'
            else if ((key === 'arrowdown' || key === 's') && snake.dy === 0) {
                snake.dy = grid;
                snake.dx = 0;
                startGame();
            }
        });
    </script>
</body>
</html>
