<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>WowBall</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            user-select: none;
        }
        
        body {
            background: white;
            overflow: hidden;
            width: 100vw;
            height: 100vh;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        /* МЕНЮ */
        #menuScreen {
            position: fixed;
            width: 100vw;
            height: 100vh;
            background: white;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            z-index: 100;
        }
        
        #title {
            font-size: 64px;
            font-weight: 800;
            color: #333;
            margin-bottom: 40px;
            letter-spacing: -2px;
        }
        
        #playButton {
            padding: 18px 60px;
            font-size: 22px;
            background: #FF9800;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
            box-shadow: 0 6px 20px rgba(255, 152, 0, 0.3);
            margin-top: 30px;
        }
        
        #playButton:hover {
            background: #F57C00;
            transform: translateY(-2px);
            box-shadow: 0 10px 25px rgba(255, 152, 0, 0.4);
        }
        
        #playButton:active {
            transform: translateY(0);
        }
        
        .subtitle {
            font-size: 18px;
            color: #666;
            margin-top: 20px;
            font-weight: 400;
        }
        
        /* ИГРА */
        #gameScreen {
            position: fixed;
            width: 100vw;
            height: 100vh;
            background: white;
            display: none;
            overflow: hidden;
        }
        
        #timer {
            position: absolute;
            top: 25px;
            left: 25px;
            font-size: 24px;
            color: #333;
            font-family: 'Courier New', monospace;
            font-weight: 600;
        }
        
        #player {
            position: absolute;
            background: #444;
            border-radius: 50%;
            box-shadow: 0 4px 15px rgba(0,0,0,0.2);
            transition: transform 0.15s ease-out;
        }
        
        .obstacle {
            position: absolute;
            background: #FF9800;
            border-radius: 6px;
            box-shadow: 0 3px 10px rgba(0,0,0,0.2);
        }
        
        /* ЭКРАН СМЕРТИ */
        #deathScreen {
            position: fixed;
            width: 100vw;
            height: 100vh;
            background: rgba(255,255,255,0.97);
            display: none;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            z-index: 50;
        }
        
        #deathTitle {
            font-size: 42px;
            color: #333;
            margin-bottom: 30px;
            font-weight: 700;
        }
        
        #deathStats {
            font-size: 22px;
            color: #555;
            margin-bottom: 50px;
            text-align: center;
            line-height: 1.6;
        }
        
        .stat-value {
            color: #FF9800;
            font-weight: 700;
        }
        
        .death-buttons {
            display: flex;
            gap: 20px;
        }
        
        .death-button {
            padding: 15px 40px;
            font-size: 18px;
            background: #FF9800;
            color: white;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            font-weight: 600;
            transition: all 0.3s;
        }
        
        .death-button:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 15px rgba(255, 152, 0, 0.3);
        }
        
        #menuButton {
            background: #757575;
        }
        
        #menuButton:hover {
            background: #616161;
            box-shadow: 0 6px 15px rgba(117, 117, 117, 0.3);
        }
        
        /* ЭФФЕКТЫ */
        .player-trail {
            position: absolute;
            background: rgba(68, 68, 68, 0.15);
            border-radius: 50%;
            pointer-events: none;
            z-index: 1;
        }
    </style>
</head>
<body>
    <!-- МЕНЮ -->
    <div id="menuScreen">
        <div id="title">WowBall</div>
        <button id="playButton">ИГРАТЬ</button>
        <div class="subtitle">Избегай оранжевых препятствий</div>
    </div>
    
    <!-- ИГРА -->
    <div id="gameScreen">
        <div id="timer">0.000с</div>
        <div id="player"></div>
    </div>
    
    <!-- ЭКРАН СМЕРТИ -->
    <div id="deathScreen">
        <div id="deathTitle">Игра окончена</div>
        <div id="deathStats">
            Время: <span id="finalTime" class="stat-value">0.000</span>с<br>
            Уровень: <span id="finalLevel" class="stat-value">1</span><br>
            Препятствий: <span id="finalObstacles" class="stat-value">0</span>
        </div>
        <div class="death-buttons">
            <button class="death-button" id="restartButton">Ещё раз</button>
            <button class="death-button" id="menuButton">Меню</button>
        </div>
    </div>

    <script>
        // ЭЛЕМЕНТЫ
        const menuScreen = document.getElementById('menuScreen');
        const gameScreen = document.getElementById('gameScreen');
        const playButton = document.getElementById('playButton');
        const player = document.getElementById('player');
        const timerDisplay = document.getElementById('timer');
        const deathScreen = document.getElementById('deathScreen');
        const finalTimeDisplay = document.getElementById('finalTime');
        const finalLevelDisplay = document.getElementById('finalLevel');
        const finalObstaclesDisplay = document.getElementById('finalObstacles');
        const restartButton = document.getElementById('restartButton');
        const menuButton = document.getElementById('menuButton');
        
        // НАСТРОЙКИ ИГРЫ
        const PLAYER_RADIUS = 22;
        const PLAYER_HITBOX_REDUCTION = 0.70;
        const OBSTACLE_HITBOX_REDUCTION = 0.85;
        let gameTime = 0;
        let gameRunning = false;
        let obstacles = [];
        let playerSpeed = 5;
        let obstacleSpeed = 3.5;
        let obstacleSpawnTime = 1.0; // Чуть быстрее в начале
        let lastSpawnTime = 0;
        let obstaclesPassed = 0;
        let level = 1;
        let mouseX = window.innerWidth / 2;
        let mouseY = window.innerHeight / 2;
        let lastTrailTime = 0;
        
        // РАЗМЕР ИГРОКА
        player.style.width = PLAYER_RADIUS * 2 + 'px';
        player.style.height = PLAYER_RADIUS * 2 + 'px';
        
        // СОЗДАНИЕ СЛЕДА
        function createTrail(x, y) {
            const trail = document.createElement('div');
            trail.className = 'player-trail';
            trail.style.left = (x - PLAYER_RADIUS/2) + 'px';
            trail.style.top = (y - PLAYER_RADIUS/2) + 'px';
            trail.style.width = PLAYER_RADIUS + 'px';
            trail.style.height = PLAYER_RADIUS + 'px';
            gameScreen.appendChild(trail);
            
            setTimeout(() => {
                trail.style.opacity = '0';
                trail.style.transition = 'opacity 0.6s';
                setTimeout(() => trail.remove(), 600);
            }, 100);
        }
        
        // СОЗДАНИЕ ПРЕПЯТСТВИЯ
        function createObstacle() {
            const types = ['stick', 'square', 'bar', 'rectangle'];
            const type = types[Math.floor(Math.random() * types.length)];
            
            const obstacle = document.createElement('div');
            obstacle.className = 'obstacle';
            
            let width, height;
            
            switch(type) {
                case 'stick':
                    width = 12 + Math.random() * 10;
                    height = 60 + Math.random() * 80;
                    break;
                case 'square':
                    width = height = 35 + Math.random() * 25;
                    break;
                case 'bar':
                    width = 100 + Math.random() * 60;
                    height = 15 + Math.random() * 10;
                    break;
                case 'rectangle':
                    width = 40 + Math.random() * 30;
                    height = 25 + Math.random() * 20;
                    break;
            }
            
            obstacle.style.width = width + 'px';
            obstacle.style.height = height + 'px';
            
            // Позиция сверху с проходом
            const gapWidth = 100 + Math.random() * 80;
            const gapX = Math.random() * (window.innerWidth - gapWidth - width);
            
            // Распределяем препятствия так, чтобы оставался проход
            let xPos;
            if (Math.random() > 0.5) {
                xPos = Math.random() * gapX;
            } else {
                xPos = gapX + gapWidth + Math.random() * (window.innerWidth - gapX - gapWidth - width);
            }
            
            obstacle.style.left = xPos + 'px';
            obstacle.style.top = '-100px';
            
            // Иногда добавляем вращение
            if (Math.random() > 0.7) {
                const rotation = Math.random() * 45 - 22.5;
                obstacle.style.transform = `rotate(${rotation}deg)`;
            }
            
            gameScreen.appendChild(obstacle);
            
            obstacles.push({
                element: obstacle,
                x: xPos,
                y: -100,
                width: width,
                height: height,
                speed: obstacleSpeed * (0.9 + Math.random() * 0.2),
                rotation: parseFloat(obstacle.style.transform?.replace('rotate(', '')?.replace('deg)', '')) || 0
            });
            
            obstaclesPassed++;
            
            // ЧУТЬ чаще второе препятствие
            if (Math.random() > 0.5 && obstaclesPassed > 3 && gameTime > 8) {
                setTimeout(() => {
                    if (gameRunning && obstacles.length < 8) {
                        createObstacle();
                    }
                }, 200 + Math.random() * 300);
            }
        }
        
        // ОБНОВЛЕНИЕ ИГРОКА
        function updatePlayer() {
            const currentX = parseFloat(player.style.left) || window.innerWidth / 2;
            const currentY = parseFloat(player.style.top) || window.innerHeight / 2;
            
            const dx = mouseX - currentX;
            const dy = mouseY - currentY;
            
            const moveSpeed = playerSpeed * 0.06;
            player.style.left = (currentX + dx * moveSpeed) + 'px';
            player.style.top = (currentY + dy * moveSpeed) + 'px';
            
            // Границы экрана
            player.style.left = Math.max(0, Math.min(window.innerWidth - PLAYER_RADIUS*2, parseFloat(player.style.left))) + 'px';
            player.style.top = Math.max(0, Math.min(window.innerHeight - PLAYER_RADIUS*2, parseFloat(player.style.top))) + 'px';
            
            // След
            if (Date.now() - lastTrailTime > 40) {
                createTrail(currentX + PLAYER_RADIUS, currentY + PLAYER_RADIUS);
                lastTrailTime = Date.now();
            }
        }
        
        // ОБНОВЛЕНИЕ ПРЕПЯТСТВИЙ
        function updateObstacles(deltaTime) {
            for (let i = obstacles.length - 1; i >= 0; i--) {
                const obs = obstacles[i];
                obs.y += obs.speed;
                obs.element.style.top = obs.y + 'px';
                
                // Медленное вращение
                if (obs.rotation !== 0) {
                    obs.rotation += 0.5;
                    obs.element.style.transform = `rotate(${obs.rotation}deg)`;
                }
                
                // Проверка столкновения
                const playerRect = {
                    left: parseFloat(player.style.left) + PLAYER_RADIUS * (1 - PLAYER_HITBOX_REDUCTION),
                    right: parseFloat(player.style.left) + PLAYER_RADIUS * 2 - PLAYER_RADIUS * (1 - PLAYER_HITBOX_REDUCTION),
                    top: parseFloat(player.style.top) + PLAYER_RADIUS * (1 - PLAYER_HITBOX_REDUCTION),
                    bottom: parseFloat(player.style.top) + PLAYER_RADIUS * 2 - PLAYER_RADIUS * (1 - PLAYER_HITBOX_REDUCTION)
                };
                
                const obsHitboxWidth = obs.width * OBSTACLE_HITBOX_REDUCTION;
                const obsHitboxHeight = obs.height * OBSTACLE_HITBOX_REDUCTION;
                const obsHitboxX = obs.x + (obs.width - obsHitboxWidth) / 2;
                const obsHitboxY = obs.y + (obs.height - obsHitboxHeight) / 2;
                
                const obsHitboxRect = {
                    left: obsHitboxX,
                    right: obsHitboxX + obsHitboxWidth,
                    top: obsHitboxY,
                    bottom: obsHitboxY + obsHitboxHeight
                };
                
                if (checkCollision(playerRect, obsHitboxRect)) {
                    endGame();
                    return;
                }
                
                // Удаление за экраном
                if (obs.y > window.innerHeight) {
                    obs.element.remove();
                    obstacles.splice(i, 1);
                }
            }
        }
        
        // ПРОВЕРКА СТОЛКНОВЕНИЯ
        function checkCollision(rect1, rect2) {
            return !(rect1.right < rect2.left || 
                     rect1.left > rect2.right || 
                     rect1.bottom < rect2.top || 
                     rect1.top > rect2.bottom);
        }
        
        // ИГРОВОЙ ЦИКЛ
        let lastTime = 0;
        function gameLoop(currentTime) {
            if (!gameRunning) return;
            
            const deltaTime = (currentTime - lastTime) / 1000;
            lastTime = currentTime;
            
            // Обновление времени
            gameTime += deltaTime;
            timerDisplay.textContent = gameTime.toFixed(3) + 'с';
            
            // Увеличение уровня каждые 7 секунд
            const newLevel = Math.floor(gameTime / 7) + 1;
            if (newLevel > level) {
                level = newLevel;
                // ЧУТЬ больше ускорение
                obstacleSpeed = 3.5 + level * 0.45;
                playerSpeed = 5 + level * 0.3;
            }
            
            // Обновление игрока
            updatePlayer();
            
            // Спавн препятствий - ЧУТЬ БОЛЬШЕ
            lastSpawnTime += deltaTime;
            if (lastSpawnTime > obstacleSpawnTime) {
                // ЧУТЬ больше препятствий на экране
                if (obstacles.length < 7) {
                    createObstacle();
                }
                lastSpawnTime = 0;
                
                // ЧУТЬ быстрее спавн
                obstacleSpawnTime = Math.max(0.6, 1.0 / (level * 0.45));
                
                // После 10 секунд - ЧУТЬ быстрее
                if (gameTime > 10) {
                    obstacleSpawnTime = Math.max(0.5, obstacleSpawnTime);
                }
                
                // После 30 секунд - ЧУТЬ быстрее
                if (gameTime > 30) {
                    obstacleSpawnTime = Math.max(0.4, obstacleSpawnTime);
                }
                
                // После 60 секунд - ЧУТЬ быстрее
                if (gameTime > 60) {
                    obstacleSpawnTime = Math.max(0.35, obstacleSpawnTime);
                }
                
                // После 100 секунд - ЧУТЬ быстрее
                if (gameTime > 100) {
                    obstacleSpawnTime = Math.max(0.3, obstacleSpawnTime);
                }
            }
            
            // Обновление препятствий
            updateObstacles(deltaTime);
            
            requestAnimationFrame(gameLoop);
        }
        
        // НАЧАЛО ИГРЫ
        function startGame() {
            // Сброс
            gameTime = 0;
            obstacles.forEach(obs => obs.element.remove());
            obstacles = [];
            obstaclesPassed = 0;
            level = 1;
            obstacleSpeed = 3.5;
            playerSpeed = 5;
            obstacleSpawnTime = 1.0;
            lastSpawnTime = 0;
            
            // Позиция игрока
            mouseX = window.innerWidth / 2;
            mouseY = window.innerHeight / 2;
            player.style.left = (window.innerWidth / 2 - PLAYER_RADIUS) + 'px';
            player.style.top = (window.innerHeight / 2 - PLAYER_RADIUS) + 'px';
            
            // Запуск игры
            gameRunning = true;
            deathScreen.style.display = 'none';
            gameScreen.style.display = 'block';
            
            lastTime = performance.now();
            requestAnimationFrame(gameLoop);
        }
        
        // КОНЕЦ ИГРЫ
        function endGame() {
            gameRunning = false;
            
            // Статистика
            finalTimeDisplay.textContent = gameTime.toFixed(3);
            finalLevelDisplay.textContent = level;
            finalObstaclesDisplay.textContent = obstaclesPassed;
            
            // Показываем экран смерти
            setTimeout(() => {
                deathScreen.style.display = 'flex';
            }, 700);
        }
        
        // УПРАВЛЕНИЕ
        document.addEventListener('mousemove', (e) => {
            mouseX = e.clientX;
            mouseY = e.clientY;
        });
        
        document.addEventListener('touchmove', (e) => {
            e.preventDefault();
            mouseX = e.touches[0].clientX;
            mouseY = e.touches[0].clientY;
        }, { passive: false });
        
        // КНОПКИ
        playButton.addEventListener('click', () => {
            menuScreen.style.display = 'none';
            startGame();
        });
        
        restartButton.addEventListener('click', () => {
            deathScreen.style.display = 'none';
            startGame();
        });
        
        menuButton.addEventListener('click', () => {
            deathScreen.style.display = 'none';
            menuScreen.style.display = 'flex';
        });
        
        // АДАПТАЦИЯ К РАЗМЕРУ ЭКРАНА
        window.addEventListener('resize', () => {
            if (gameRunning) {
                player.style.left = Math.max(0, Math.min(window.innerWidth - PLAYER_RADIUS*2, parseFloat(player.style.left))) + 'px';
                player.style.top = Math.max(0, Math.min(window.innerHeight - PLAYER_RADIUS*2, parseFloat(player.style.top))) + 'px';
            }
        });
        
        // ЗАГРУЗКА
        timerDisplay.textContent = "0.000с";
    </script>
</body>
</html>
