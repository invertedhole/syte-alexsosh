<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Website</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <img src="[images/logo.png" alt="Logo](https://raw.githubusercontent.com/invertedhole/ooalexsosh/main/картинка2.PNG)">
        <h1>Welcome to My Website</h1>
    </header>
    <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="services.html">Services</a>
        <a href="contact.html">Contact</a>
    </nav>
    <div class="content">
        <h2>Home Page</h2>
        <p>This is the home page content.</p>
    </div>
    <footer>
        <p>&copy; 2024 My Website</p>
    </footer>
    <script src="scripts.js"></script>
</body>
</html>
<style>
tabs {
            display: flex;
            list-style: none;
            margin: 0;
            padding: 0;
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
            display: block;overflow: hidden;
    border: none;
    background-color: #8FBC8F;
    body {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
}
header {
    background-color: #333;
    color: white;
    padding: 10px 0;
    text-align: center;
}
nav {
    display: flex;
    justify-content: center;
    background-color: #444;
}
nav a {
    color: white;
    padding: 14px 20px;
    text-decoration: none;
    text-align: center;
}
nav a:hover {
    background-color: #555;
}
.content {
    padding: 20px;
}
footer {
    background-color: #333;
    color: white;
    text-align: center;
    padding: 10px 0;
    position: fixed;
    width: 100%;
    bottom: 0;
}
</style>
    <!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>About Us</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <img src="https://raw.githubusercontent.com/invertedhole/ooalexsosh/main/картинка2.PNG">
        <h1>About Us</h1>
    </header>
    <nav>
          <ul class="tabs">
            <li class="active" data-tab="tab1">О нас</li>
            <li data-tab="tab2">Жизнь школы</li>
            <li data-tab="tab3">Новости</li>
        </ul>
    </nav>
    <div class="content">
        <h2>About Us</h2>
        <p>This is the about us page content.</p>
    </div>
    <footer>
        <p>&copy; 2024 My Website</p>
    </footer>
    <script src="scripts.js"></script>
</body>
</html>
!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Services</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <img src="images/logo.png" alt="Logo">
        <h1>Our Services</h1>
    </header>
    <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="services.html">Services</a>
        <a href="contact.html">Contact</a>
    </nav>
    <div class="content">
        <h2>Services</h2>
        <p>This is the services page content.</p>
    </div>
    <footer>
        <p>&copy; 2024 My Website</p>
    </footer>
    <script src="scripts.js"></script>
</body>
</html>
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Contact Us</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <header>
        <img src="images/logo.png" alt="Logo">
        <h1>Contact Us</h1>
    </header>
    <nav>
        <a href="index.html">Home</a>
        <a href="about.html">About</a>
        <a href="services.html">Services</a>
        <a href="contact.html">Contact</a>
    </nav>
    <div class="content">
        <h2>Contact Us</h2>
        <p>This is the contact page content.</p>
    </div>
    <footer>
        <p>&copy; 2024 My Website</p>
    </footer>
    <script src="scripts.js"></script>
</body>
</html>
<script>
// Simple script to highlight the current page in the navigation menu
document.addEventListener("DOMContentLoaded", function () {
    const currentPath = window.location.pathname;
    const navLinks = document.querySelectorAll("nav a");
    navLinks.forEach(link => {
        if (link.getAttribute("href") === currentPath) {
            link.style.backgroundColor = "#555";
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
        }
    });
});
