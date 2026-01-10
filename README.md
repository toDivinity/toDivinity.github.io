<html lang="ru">
<head>
    <meta charset="UTF-8">
    <script src="https://telegram.org/js/telegram-web-app.js"></script>
    <script src="https://cdn.jsdelivr.net/npm/phaser@3/dist/phaser.min.js"></script>
    <script src="src/main.js"></script>
</head>
<style>
            /* Reset CSS: Please avoid making changes here unless you know what you're doing :) */
            *,
            *::before,
            *::after {
                margin: 0;
                padding: 0;
                box-sizing: border-box;
            }
    
            html, body {
                width: 100%;
                height: 100%;
            }
    
            body {
                line-height: 1;
                font-family: Arial, sans-serif;
                background-color: #040218;
            }
    
            ol, ul {
                list-style: none;
            }
    
            img, video {
                max-width: 100%;
                height: auto;
                display: block;
            }
    
            a {
                text-decoration: none;
                color: inherit;
            }
        </style>
<body>

    <p id="user"></p>

    <div id="game-container"></div>
    <script src="./phaser.js"></script>
    <script type="module" src="./src/main.js"></script>

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
