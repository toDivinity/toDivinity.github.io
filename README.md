<html lang="ru">
<head>
    <meta charset="UTF-8">
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
</head>
<body>

    <p id="user"></p>

    <script>
        const tg = window.Telegram.WebApp;

        // Инициализация
        tg.ready();
        tg.expand();

        // Данные пользователя (авторизация)
        const user = tg.initDataUnsafe.user;

        if (!user) {
            document.getElementById("user").innerText =
                "Откройте приложение через Telegram";
        } else {
            document.getElementById("user").innerText =
                `Вы вошли как: ${user.first_name} (@${user.username ?? "-"})`;
        }

    </script>

</body>
</html>