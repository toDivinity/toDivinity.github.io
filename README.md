# toDivinity.github.io
<!DOCTYPE html>
<html lang="ru">
<head>
    <meta charset="UTF-8">
    <title>Mini App</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
</head>
<body>
    <h2>🚀 Telegram Mini App</h2>
    <button id="btn">Отправить данные боту</button>

    <script>
        const tg = window.Telegram.WebApp;
        tg.ready();

        document.getElementById("btn").onclick = () => {
            tg.sendData(JSON.stringify({
                action: "test",
                value: 42
            }));
        };
    </script>
</body>
</html>
