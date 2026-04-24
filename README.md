<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Меню кафе</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            max-width: 400px;
            margin: auto;
        }
        h1 {
            color: #444;
        }
        .dish {
            margin-bottom: 15px;
            border-bottom: 1px solid #eee;
            padding-bottom: 10px;
        }
        .dish img {
            max-width: 100%;
            border-radius: 10px;
        }
        button {
            background: #e74c3c;
            color: white;
            padding: 15px;
            font-size: 18px;
            border: none;
            border-radius: 10px;
            width: 100%;
            margin: 20px 0;
            cursor: pointer;
        }
    </style>
</head>
<body>
    <h1>☕ Кафе у Аскара</h1>

    <div class="dish">
        <img src="https://via.placeholder.com/400x200?text=Шорпо" alt="Шорпо">
        <h3>Шорпо — 250 сом</h3>
    </div>
    <div class="dish">
        <img src="https://via.placeholder.com/400x200?text=Плов" alt="Плов">
        <h3>Плов — 350 сом</h3>
    </div>
    <div class="dish">
        <img src="https://via.placeholder.com/400x200?text=Лагман" alt="Лагман">
        <h3>Лагман — 280 сом</h3>
    </div>
    <div class="dish">
        <img src="https://via.placeholder.com/400x200?text=Чай" alt="Чай">
        <h3>Чай — 50 сом</h3>
    </div>

    <button onclick="readMenu()">🔊 Слушать меню</button>

    <script>
        function readMenu() {
            // Берем весь текст на странице (меню)
            let text = document.body.innerText;
            // Заменяем переносы строк на точки, чтобы звучало естественно
            text = text.replace(/\n/g, '. ');
            let utterance = new SpeechSynthesisUtterance(text);
            utterance.lang = 'ru-RU';  // русский язык
            utterance.rate = 0.9;      // скорость
            window.speechSynthesis.speak(utterance);
        }
    </script>
</body>
</html>
