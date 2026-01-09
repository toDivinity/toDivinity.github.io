<!DOCTYPE html>
<html lang="ru">
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
