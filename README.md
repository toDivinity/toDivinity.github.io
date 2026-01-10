<body>

    <h2>Mini App</h2>
    <p id="user"></p>

    <button id="btn">Отправить данные боту</button>

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

        // Отправка данных боту
        document.getElementById("btn").onclick = () => {
            const data = {
                id: user.id,
                first_name: user.first_name,
                username: user.username
            };

            // Отправка БОТУ
            tg.sendData(JSON.stringify(data));
        };
    </script>

</body>