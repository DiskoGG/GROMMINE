<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Розыгрыш Наклеек</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            background: linear-gradient(to bottom right, #3e1a6d, #1a0c3e);
            color: #fff;
            text-align: center;
            padding: 20px;
            box-shadow: inset 0 0 50px rgba(0, 0, 0, 0.5);
        }
        h1 {
            font-size: 2.5em;
            margin-bottom: 15px;
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.7);
        }
        img {
            max-width: 50%;
            height: auto;
            border-radius: 15px;
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.5);
            margin: 15px 0;
        }
        .text-description {
            font-size: 1.2em;
            margin: 15px 0;
            line-height: 1.4;
            max-width: 600px;
            opacity: 0.9;
        }
        .input-container {
            display: flex;
            justify-content: center;
            gap: 15px;
            margin: 15px 0;
            flex-wrap: wrap;
        }
        .input-number {
            padding: 15px;
            border-radius: 5px;
            border: none;
            width: 80px;
            font-size: 1.5em;
            background: rgba(255, 255, 255, 0.2);
            color: #fff;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .input-number:focus {
            outline: none;
            box-shadow: 0 0 10px rgba(255, 255, 255, 0.7);
            transform: scale(1.05);
        }
        .button {
            background-color: #ff5722;
            color: white;
            padding: 12px 20px;
            border: none;
            border-radius: 5px;
            font-size: 1.1em;
            transition: background-color 0.3s, transform 0.2s;
            cursor: pointer;
        }
        .button:hover {
            background-color: #e64a19;
            transform: scale(1.05);
        }
        .tg-button {
            background-color: #0088cc;
            margin-top: 20px;
            font-size: 1.1em;
        }
        .tg-button:hover {
            background-color: #007bb5;
        }
        .winner {
            margin-top: 15px;
            font-size: 2em;
            color: #ffeb3b;
            opacity: 0;
            transition: opacity 0.5s ease-in-out, transform 0.5s ease-in-out;
            transform: translateY(-20px);
        }
        .footer {
            margin-top: 30px;
            font-size: 0.9em;
            color: #ccc;
        }
        .full-text {
            display: none;
            margin-top: 15px;
            max-width: 600px;
            opacity: 0.9;
            transition: max-height 0.3s ease;
        }
        .toggle-button {
            background-color: transparent;
            color: #ffeb3b;
            border: none;
            cursor: pointer;
            font-size: 1em;
            text-decoration: underline;
        }
        .close-button {
            color: red;
            font-size: 1.5em;cursor: pointer;
            position: absolute;
            right: 10px;
            top: 5px;
            }
            </style>
            </head>
            <body>
            <h1>Розыгрыш Наклеек</h1>
            <img src="/storage/emulated/0/Music/img/111.jpg" alt="Розыгрыш Наклеек">
            <a href="https://t.me/@MIFIX" class="telegram-button">Написать по поводу заказа!</a>
            
            <style>
            .telegram-button {
            display: inline-block;
            background-color: #0088cc;
            color: white;
            padding: 10px 15px;
            border-radius: 5px;
            text-decoration: none;
            font-size: 16px;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
            }
            .telegram-button:hover {
            background-color: #0077b3;
            }
            </style>
    <div class="text-description">
    <p>🔥 Он достанется одному из вас! Почти половина наклеек продана, и это крупный розыгрыш! 🔥</p>
    
    <p>Чтобы участвовать, купите эксклюзивную наклейку, и вы автоматически станете участником!</p>
    
    <p>Итоги розыгрыша будут подведены после распродажи всех наклеек. Удачи всем!</p>
    </div>
            <div class="input-container">
            <input type="number" id="minNumber" class="input-number" placeholder="Мин" />
            <input type="number" id="maxNumber" class="input-number" placeholder="Макс" />
            <button id="generateButton" class="button">Сгенерировать победителя</button>
            </div>
            
            <div class="winner" id="winnerNumber"></div>
            
            <div>
            <a href="https://t.me/YDMBeast" target="_blank" class="button tg-button">Присоединиться в TG</a>
            </div>
            
            <footer class="footer">
            &copy; 2023 Розыгрыш Наклеек
            </footer>
            
            <script>
            document.getElementById('generateButton').addEventListener('click', function() {
            const min = parseInt(document.getElementById('minNumber').value);
            const max = parseInt(document.getElementById('maxNumber').value);
            const winnerDisplay = document.getElementById('winnerNumber');
            
            if (!isNaN(min) && !isNaN(max) && min < max) {
            const randomNum = Math.floor(Math.random() * (max - min + 1)) + min;
            winnerDisplay.textContent = `Победитель: ${randomNum}`;
            winnerDisplay.style.opacity = 1;
            winnerDisplay.style.transform = 'translateY(0)';
            
            // Анимация исчезновения
            setTimeout(() => {
            winnerDisplay.style.opacity = 0;
            winnerDisplay.style.transform = 'translateY(-20px)';
            }, 3000);
            
            } else {
            alert("Введите корректные значения!");
            }
            });
            
            // Разворачивание текста
            const toggleDescription = document.getElementById('toggleDescription');
            const fullText = document.getElementById('fullText');
            const closeDescription = document.getElementById('closeDescription');
            
            toggleDescription.addEventListener('click', function() {
            fullText.style.display = "block";
            toggleDescription.style.display = "none";
            });
            
            closeDescription.addEventListener('click', function() {
            fullText.style.display = "none";
            toggleDescription.style.display = "inline";
            });</script>
            </body>
            </html>
            
