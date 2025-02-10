
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Тетрис</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #000;
            position: relative; /* Добавлено для позиционирования кнопки */
        }

        .game-container {
            position: relative;
            background-color: #222;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 20px rgba(255, 255, 255, 0.5);
            width: 400px;
            height: 600px;
            display: flex;
            flex-direction: column;
            align-items: center;
            z-index: 1; /* Убедитесь, что контейнер находится ниже кнопки */
        }

        canvas {
            border: 2px solid #fff;
            background-color: #000;
        }

        .controls {
            display: flex;
            justify-content: space-between;
            width: 100%;
            margin-top: 20px;
        }

        .control-row {
            display: flex;
            justify-content: center;
            align-items: center;
        }

        button {
            width: 50px;
            height: 50px;
            font-size: 24px;
            background-color: #444;
            color: white;
            border: 2px solid white; /* Белая обводка */
            border-radius: 50%;
            margin: 0 5px;
            cursor: pointer;
            transition: background-color 0.3s, transform 0.2s; /* Добавлено для эффекта нажатия */
            outline: none; /* Убираем стандартный обвод кнопки */
        }

        button:hover {
            background-color: #666;
        }

        button:active {
            transform: scale(0.95); /* Эффект нажатия */
        }

        .rotate-button {
            background-color: #f39c12;
        }

        .rotate-button:hover {
            background-color: #e67e22;
        }

        .down-button {
            background-color: #e74c3c;
        }

        .down-button:hover {
            background-color: #c0392b;
        }

        .next-container {
            margin-top: 20px;
            background-color: #333;
            padding: 10px;
            border-radius: 5px;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.3);
            text-align: center;
        }

        .next-title {
            color: white;
            margin-bottom: 5px;
        }

        /* Стили для модального окна */
        .modal {
            display: none; /* Скрыто по умолчанию */
            position: fixed;
            z-index: 1;
            left: 0;
            top: 0;
            width: 100%;
            height: 100%;
            overflow: auto;
            background-color: rgb(0,0,0);
            background-color: rgba(0,0,0,0.4); /* Черный с прозрачностью */
            padding-top: 60px;
        }

        .modal-content {
            background-color: #fefefe;
            margin: 5% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 500px;
            border-radius: 10px;
        }

        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }

        /* Стили для кнопки правил */
        #rulesButton {
            position: absolute; /* Позиционирование кнопки */
            top: 20px; /* Отступ сверху */
            right: 0; /* Кнопка на самом краю справа */
            margin-right: 20px; /* Увеличен отступ справа для перемещения кнопки еще правее */
            font-size: 24px; /* Размер шрифта для восклицательного знака */
            width: 50px;
            height: 50px;
            background-color: #f39c12; /* Цвет кнопки */
            border-radius: 50%; /* Кнопка круглая */
            border: none; /* Убираем обводку */
            color: white; /* Цвет текста */
            cursor: pointer; /* Курсор при наведении */
            transition: background-color 0.3s; /* Плавный переход цвета */
            z-index: 2; /* Убедитесь, что кнопка выше контейнера игры */
        }

        #rulesButton:hover {
            background-color: #e67e22; /* Цвет при наведении */
        }
    </style>
</head>
<body>
    <button id="rulesButton">!</button> <!-- Кнопка для показа правил с восклицательным знаком -->
    <div class="game-container">
        <canvas id="tetris" width="240" height="360"></canvas>
        <div class="next-container">
            <div class="next-title">Следующая фигура:</div>
            <canvas id="nextPiece" width="80" height="80"></canvas>
        </div>
        <div class="controls">
            <div class="control-row">
                <button id="left">←</button>
                <button class="rotate-button" id="rotate">↑</button>
                <button id="right">→</button>
            </div>
            <div class="control-row">
                <button class="down-button" id="down">↓</button>
            </div>
        </div>
    </div>

    <!-- Модальное окно для правил -->
    <div id="rulesModal" class="modal">
        <div class="modal-content">
            <span class="close">&times;</span>
            <h2>Правила игры</h2>
            <p>Цель игры - управлять падающими фигурами и заполнять горизонтальные ряды.</p>
            <p>Когда ряд полностью заполняется, он исчезает, и вы получаете очки.</p>
            <p>Игра заканчивается, когда фигуры достигают верхней части игрового поля.</p>
            <p>Управление:</p>
            <ul>
                <li>← - Двигать фигуру влево</li>
                <li>→ - Двигать фигуру вправо</li>
                <li>↑ - Повернуть фигуру</li>
                <li>↓ - Ускорить падение фигуры</li>
            </ul>
        </div>
    </div>

    <script>
        const canvas = document.getElementById('tetris');
        const context = canvas.getContext('2d');
        context.scale(20, 20);

        const nextCanvas = document.getElementById('nextPiece');
        const nextContext = nextCanvas.getContext('2d');
        nextContext.scale(10, 10);

        let board = Array.from({ length: 18 }, () => Array(12).fill(0));
        let pieces = 'IJLOSTZ';
        let currentPiece = null;
        let nextPiece = null;
        let dropInterval = 1000;
        let lastTime = 0;

        function drawBoard() {
            context.clearRect(0, 0, canvas.width, canvas.height);
            board.forEach((row, y) => {
                row.forEach((value, x) => {
                    if (value === 1) {
                        context.fillStyle = 'white';
                        context.fillRect(x, y, 1, 1);
                    } else if (value === 2) {
                        context.fillStyle = 'red'; // Цвет для мигающего ряда
                        context.fillRect(x, y, 1, 1);
                    }
                });
            });
            drawGrid();
        }

        function drawGrid() {
            context.strokeStyle = 'rgba(255, 255, 255, 0.3)';
            context.lineWidth = 0.05;

            for (let x = 0; x < 12; x++) {
                context.beginPath();
                context.moveTo(x, 0);
                context.lineTo(x, 18);
                context.stroke();
            }

            for (let y = 0; y < 18; y++) {
                context.beginPath();
                context.moveTo(0, y);
                context.lineTo(12, y);
                context.stroke();
            }
        }

        function drawPiece(piece, ctx) {
            piece.shape.forEach((row, y) => {
                row.forEach((value, x) => {
                    if (value) {
                        ctx.fillStyle = piece.color;
                        ctx.fillRect(piece.x + x, piece.y + y, 1, 1);
                    }
                });
            });
        }

        function createPiece(type) {
            const pieces = {
                I: { shape: [[1, 1, 1, 1]], color: 'cyan' },
                J: { shape: [[1, 0, 0], [1, 1, 1]], color: 'blue' },
                L: { shape: [[0, 0, 1], [1, 1, 1]], color: 'orange' },
                O: { shape: [[1, 1], [1, 1]], color: 'yellow' },
                S: { shape: [[0, 1, 1], [1, 1, 0]], color: 'green' },
                T: { shape: [[0, 1, 0], [1, 1, 1]], color: 'purple' },
                Z: { shape: [[1, 1, 0], [0, 1, 1]], color: 'red' },
            };
            return { ...pieces[type], x: 5, y: 0 };
        }

        function resetGame() {
            board = Array.from({ length: 18 }, () => Array(12).fill(0));
            currentPiece = createPiece(pieces[Math.floor(Math.random() * pieces.length)]);
            nextPiece = createPiece(pieces[Math.floor(Math.random() * pieces.length)]);
            drawBoard();
            drawPiece(currentPiece, context);
            drawNextPiece();
        }

        function drawNextPiece() {
            nextContext.clearRect(0, 0, nextCanvas.width, nextCanvas.height);
            drawPiece(nextPiece, nextContext);
        }

        function collide() {
            for (let y = 0; y < currentPiece.shape.length; y++) {
                for (let x = 0; x < currentPiece.shape[y].length; x++) {
                    if (currentPiece.shape[y][x] && (board[currentPiece.y + y] && board[currentPiece.y + y][currentPiece.x + x]) !== 0) {
                        return true;
                    }
                }
            }
            return false;
        }

        function merge() {
            currentPiece.shape.forEach((row, y) => {
                row.forEach((value, x) => {
                    if (value) {
                        board[currentPiece.y + y][currentPiece.x + x] = 1;
                    }
                });
            });
        }

        function removeFullRows() {
            let rowsToRemove = [];
            board.forEach((row, y) => {
                if (row.every(value => value !== 0)) {
                    rowsToRemove.push(y);
                }
            });

            rowsToRemove.forEach(row => {
                setTimeout(() => {
                    for (let x = 0; x < 12; x++) {
                        board[row][x] = 2; // Используем значение 2 для обозначения мигающего ряда
                    }
                    drawBoard(); // Перерисовываем доску

                    setTimeout(() => {
                        board.splice(row, 1);
                        board.unshift(Array(12).fill(0)); // Добавляем пустую строку сверху
                        drawBoard(); // Перерисовываем доску после удаления
                    }, 500); // Задержка перед удалением ряда
                }, 500); // Задержка перед началом мигания
            });
        }

        function drop() {
            currentPiece.y++;
            if (collide()) {
                currentPiece.y--;
                merge();
                removeFullRows(); // Удаляем заполненные ряды
                currentPiece = nextPiece; // Переключаем текущую фигуру на следующую
                nextPiece = createPiece(pieces[Math.floor(Math.random() * pieces.length)]); // Генерируем новую следующую фигуру
                drawNextPiece(); // Обновляем экран следующей фигуры
                if (collide()) {
                    alert('Игра окончена!');
                    resetGame();
                }
            }
        }

        function update(time = 0) {
            if (time - lastTime > dropInterval) {
                drop();
                lastTime = time;
            }
            drawBoard();
            drawPiece(currentPiece, context);
            requestAnimationFrame(update);
        }

        document.getElementById('left').addEventListener('click', () => {
            currentPiece.x--;
            if (collide()) currentPiece.x++;
        });

        document.getElementById('right').addEventListener('click', () => {
            currentPiece.x++;
            if (collide()) currentPiece.x--;
        });

        document.getElementById('rotate').addEventListener('click', () => {
            const temp = currentPiece.shape;
            currentPiece.shape = temp[0].map((_, index) => temp.map(row => row[index])).reverse();
            if (collide()) currentPiece.shape = temp;
        });

        document.getElementById('down').addEventListener('click', drop);

        // Обработка нажатия на кнопку "Правила"
        const rulesButton = document.getElementById('rulesButton');
        const rulesModal = document.getElementById('rulesModal');
        const closeModal = document.getElementsByClassName('close')[0];

        rulesButton.onclick = function() {
            rulesModal.style.display = "block";
        }

        closeModal.onclick = function() {
            rulesModal.style.display = "none";
        }

        window.onclick = function(event) {
            if (event.target === rulesModal) {
                rulesModal.style.display = "none";
            }
        }

        resetGame();
        update();
    </script>
</body>
</html>
