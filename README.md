<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Электронный дневник</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            background-color: #f5f5f5;
            margin: 0;
            padding: 20px;
        }
        header {
            text-align: center;
            margin-bottom: 20px;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            border: 1px solid #ddd;
            padding: 8px;
            text-align: left;
        }
        th {
            background-color: #4CAF50;
            color: white;
        }
        form {
            display: flex;
            flex-direction: column;
            width: 300px;
        }
        input[type="text"], input[type="number"], input[type="email"], input[type="password"] {
            padding: 10px;
            margin: 5px 0;
            border: 1px solid #ccc;
            border-radius: 4px;
        }
        input[type="submit"] {
            background-color: #4CAF50;
            color: white;
            padding: 10px;
            border: none;
            border-radius: 4px;
            cursor: pointer;
        }
        input[type="submit"]:hover {
            background-color: #45a049;
        }
        #addStudentForm {
            display: none; /* Изначально скрыто */
        }
    </style>
</head>
<body>
    <header>
        <h1>Электронный дневник</h1>
    </header>
    <main>
        <div id="authForms">
            <h2>Регистрация</h2>
            <form id="registerForm">
                <input type="text" id="regUsername" name="username" required>
                <label for="regEmail">Email:</label>
                <input type="email" id="regEmail" name="email" required>
                <label for="regPassword">Пароль:</label>
                <input type="password" id="regPassword" name="password" required>
                <input type="submit" value="Зарегистрироваться">
            </form>
            <h2>Вход</h2>
            <form id="loginForm">
                <input type="text" id="loginUsername" name="username" required>
                <label for="loginPassword">Пароль:</label>
                <input type="password" id="loginPassword" name="password" required>
                <input type="submit" value="Войти">
            </form>
        </div>
        <table id="studentsTable">
            <thead>
                <tr>
                    <th>Имя</th>
                    <th>Оценки</th>
                </tr>
            </thead>
            <tbody>
                <!-- Данные учеников будут добавлены здесь -->
            </tbody>
        </table>
        <h2>Добавить оценку</h2>
        <form id="addStudentForm">
            <label for="name">Имя ученика:</label>
            <input type="text" id="name" name="name" required>
            <label for="grade">Оценка:</label>
            <input type="number" id="grade" name="grade" required min="1" max="5">
            <input type="submit" value="Добавить">
        </form>
    </main>
      <script type="module">
          import { initializeApp } from 'firebase/app';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
  // TODO: Add SDKs for Firebase products that you want to use
  // https://firebase.google.com/docs/web/setup#available-libraries
  // Your web app's Firebase configuration
  // For Firebase JS SDK v7.20.0 and later, measurementId is optional
  const firebaseConfig = {
    apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
    authDomain: "alexsosh-7c608.firebaseapp.com",
    databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
    projectId: "alexsosh-7c608",
    storageBucket: "alexsosh-7c608.appspot.com",
    messagingSenderId: "540899168475",
    appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
    measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
  // Import the functions you need from the SDKs you need
  import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-app.js";
  import { getAnalytics } from "https://www.gstatic.com/firebasejs/10.12.4/firebase-analytics.js";
 import { initializeApp } from 'firebase/app';
import { getFirestore, collection, getDocs } from 'firebase/firestore/lite';
// Follow this pattern to import other Firebase services
// import { } from 'firebase/<service>';
// TODO: Replace the following with your app's Firebase project configuration
const firebaseConfig = {
 apiKey: "AIzaSyAVy1BVdsVnRkIQB6xRG00f6pmd9WNo97U",
 authDomain: "alexsosh-7c608.firebaseapp.com",
 databaseURL: "https://alexsosh-7c608-default-rtdb.firebaseio.com",
 projectId: "alexsosh-7c608",
 storageBucket: "alexsosh-7c608.appspot.com",
 messagingSenderId: "540899168475",
 appId: "1:540899168475:web:afbeabde1bf0b106dcbcfe",
 measurementId: "G-S45K09RYXW"
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
  };
  // Initialize Firebase
  const app = initializeApp(firebaseConfig);
  const analytics = getAnalytics(app);
};
 </script>
