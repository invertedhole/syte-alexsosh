<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Мой сайт</title>
    <style>
       /* Базовый стиль для всего сайта */
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #FFFFF0;
        }

       
        /* Стиль для вкладок */
        .tabs {
            display: flex;
            list-style: none;
            margin: 0;
            padding: 0;
             overflow: hidden;
    border: none;
    background-color: #8FBC8F;
        }

        .tabs li {
            flex: 1;
            text-align: center;
            border-bottom: 2px solid transparent;
            cursor: pointer;
            padding: 10px;
        }

        .tabs li.active {
            border-bottom: 2px solid #007bff;
        }

        /* Стиль для контента вкладок */
        .tab-content {
            display: none;
            padding: 20px;
        }

        .tab-content.active {
            display: block;
        }
    </style>
</head>
<body>
    <header>
        <!-- Заголовок сайта -->
        <h1></h1>
<p><img src="/C:Users\User\Desktop\картинка2.jpg." width="300" height="200"><img src="/C:Users\User\Desktop\картинка2.png." width="1200" height="200">
    </header>
    <main>
        <!-- Основное содержимое сайта -->
        <ul class="tabs">
            <li class="active" data-tab="tab1">О нас</li>
            <li data-tab="tab2">Жизнь школы</li>
            <li data-tab="tab3">Новости</li>
        </ul>
        <div id="tab1" class="tab-content active">
            <p>Контактные данные
<p>Директор:+7 990 077 2103
<p>Отдел кадров +7 990 058 1933</p>
          </div>
           <div id="tab2" class="tab-content">
            <p></head>
<body>

<div class="tab">
    <button class="tablinks" onclick="openCity(event, 'Первый звонок 2024')" id="defaultOpen">Первый звонок 2024</button>
    <button class="tablinks" onclick="openCity(event, 'Выпуск 2024')">Выпуск 2024</button>
</div>

<div id="Первый звонок 2024" class="tabcontent">
    <h3>дзынь</h3>
    <p>дзынь.</p>
</div>

<div id="Выпуск 2024" class="tabcontent">
    <h3>(=(=(=</h3>
    <p>Выпуск 2024</p>
<style>
body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}

/* Стили для вкладки */
.tab {
    overflow: hidden;
    border: none;
    background-color: #f1f1f1;
}

/* Стили для кнопок вкладки */
.tab button {
    background-color: #f1f1f1;
    float: left;
    border: none;
    outline: none;
    cursor: pointer;
    padding: 14px 16px;
    transition: background-color 0.5s ease;
}

/* Стили для активной кнопки */
.tab button.active {
    background-color: #ccc;
}

/* Стили для контента вкладки */
.tabcontent {
    display: none;
    padding: 6px 12px;
}

/* Стили для активного контента вкладки */
.tabcontent.active {
    display: block;
    animation: fadeIn 0.5s ease;
}

/* CSS-анимация для активного контента вкладки */
@keyframes fadeIn {
    from {opacity: 0;}
    to {opacity: 1;}
}

/* Стили для изменения цвета кнопок при наведении */
.tab button:hover {
    background-color: #ddd;
}

/* Стили для активной кнопки при наведении */
.tab button.active:hover {
    background-color: #ccc;
}
</style>
<script>
    function openCity(evt, cityName) {
        var i, tabcontent, tablinks;
        tabcontent = document.getElementsByClassName("tabcontent");
        for (i = 0; i < tabcontent.length; i++) {
            tabcontent[i].style.display = "none";
        }
        tablinks = document.getElementsByClassName("tablinks");
        for (i = 0; i < tablinks.length; i++) {
            tablinks[i].className = tablinks[i].className.replace(" active", "");
        }
        document.getElementById(cityName).style.display = "block";
        evt.currentTarget.className += " active";
    }

    // Открыть первую вкладку по умолчанию
    document.getElementById("defaultOpen").click();
</script>
</div>
</body></p>
           <ul class="tabs">
        </div>
        <div id="tab3" class="tab-content">
            <p>Контент вкладки 3</p>
        </div>
    </main>
    <footer>
        <!-- Нижняя часть сайта -->
        <p>&copy; 2024  сайт  ГБУ ОО ЗО "Алексеевская СОШ"</p>
    </footer>

    <script>
        // JavaScript для управления вкладками
        const tabs = document.querySelectorAll('.tabs li');
        const tabContents = document.querySelectorAll('.tab-content');

        tabs.forEach(tab => {
            tab.addEventListener('click', () => {
                const targetTab = tab.dataset.tab;
                const targetContent = document.getElementById(targetTab);

                tabs.forEach(tab => {
                    tab.classList.remove('active');
                });

                tabContents.forEach(content => {
                    content.classList.remove('active');
                });

                tab.classList.add('active');
                targetContent.classList.add('active');
            });
        });
    </script>
</body>
</html>
