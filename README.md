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
                <label for="regUsername">Имя пользователя:</label>
                <input type="text" id="regUsername" name="username" required>
                <label for="regEmail">Email:</label>
                <input type="email" id="regEmail" name="email" required>
                <label for="regPassword">Пароль:</label>
                <input type="password" id="regPassword" name="password" required>
                <input type="submit" value="Зарегистрироваться">
            </form>
            <h2>Вход</h2>
            <form id="loginForm">
                <label for="loginUsername">Имя пользователя:</label>
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
    // Import the functions you need from the SDKs
    import { initializeApp } from "https://www.gstatic.com/firebasejs/9.9.0/firebase-app.js";
    import { getAuth, createUserWithEmailAndPassword, signInWithEmailAndPassword } from "https://www.gstatic.com/firebasejs/9.9.0/firebase-auth.js";
    import { getFirestore, collection, addDoc, getDocs, query, where } from "https://www.gstatic.com/firebasejs/9.9.0/firebase-firestore.js";
    // Your web app's Firebase configuration
    const firebaseConfig = {
      apiKey: "AIzaSyA6lScjtjt5q2tIPtS7oOfpfFTNUzcP_Vw",
 authDomain: "user-1bfb3.firebaseapp.com",
 databaseURL: "https://user-1bfb3-default-rtdb.europe-west1.firebasedatabase.app",
 ProjectID: "user-1bfb3",
 Корзина для хранения: "user-1bfb3.appspot.com",
 messagingSenderId: "202312075024",
 AppID: "1:202312075024: web: 15751f1725984416354795",
 Идентификатор измерения: "G-N6R5HHDR7E"
    };
    // Initialize Firebase
    const app = initializeApp(firebaseConfig);
    const auth = getAuth();
    const db = getFirestore(app);
    const registerForm = document.getElementById('registerForm');
    const loginForm = document.getElementById('loginForm');
    const addStudentForm = document.getElementById('addStudentForm');
    const authForms = document.getElementById('authForms');
    const studentsTable = document.getElementById('studentsTable').querySelector('tbody');
    let currentUser = null;
    async function updateUI() {
        if (currentUser) {
            authForms.style.display = 'none';
            addStudentForm.style.display = currentUser.role === 'admin' ? 'flex' : 'none';
        } else {
            authForms.style.display = 'block';
            addStudentForm.style.display = 'none';
        }
        await updateStudentTable();
    }
    async function updateStudentTable() {
        const studentsCol = collection(db, 'students');
        const studentSnapshot = await getDocs(studentsCol);
        const studentsList = studentSnapshot.docs.map(doc => doc.data()); 
        studentsTable.innerHTML = '';
        studentsList.forEach(student => {
            const row = document.createElement('tr');
            const nameCell = document.createElement('td');
            const gradeCell = document.createElement('td');
            nameCell.textContent = student.name;
            gradeCell.textContent = student.grade;
            row.appendChild(nameCell);
            row.appendChild(gradeCell);
            studentsTable.appendChild(row);
        });
    }
    registerForm.addEventListener('submit', async function(event) {
        event.preventDefault();
        const username = event.target.username.value.trim();
        const email = event.target.email.value.trim();
        const password = event.target.password.value.trim();
        try {
            await createUserWithEmailAndPassword(auth, email, password);
            const isFirstUser = (await getDocs(collection(db, 'users'))).empty;
            await addDoc(collection(db, 'users'), { username, email, role: isFirstUser ? 'admin' : 'user' });
            alert('Регистрация выполнена');
            currentUser = { username, role: isFirstUser ? 'admin' : 'user' };
            updateUI();
        } catch (error) {
            alert(`Ошибка регистрации: ${error.message}`);
        }
    });
    loginForm.addEventListener('submit', async function(event) {
        event.preventDefault();
        const username = event.target.username.value.trim();
        const password = event.target.password.value.trim();
        try {
            await signInWithEmailAndPassword(auth, username, password);
            const userQuery = query(collection(db, 'users'), where('username', '==', username));
            const querySnapshot = await getDocs(userQuery);
            if (querySnapshot.empty) {
                alert('Неверное имя пользователя или пароль');
                return;
            }
            const userData = querySnapshot.docs[0].data();
            currentUser = { username, role: userData.role };
            alert('Вход выполнен');
            updateUI();
        } catch (error) {
            alert(`Ошибка входа: ${error.message}`);
        }
    });
    addStudentForm.addEventListener('submit', async function(event) {
        event.preventDefault();
        if (!currentUser || currentUser.role !== 'admin') {
            alert('У вас нет прав для добавления оценки');
            return;
        }
        const name = event.target.name.value.trim();
        const grade = parseInt(event.target.grade.value.trim(), 10);
        try {
            await addDoc(collection(db, 'students'), { name, grade });
            alert('Оценка добавлена');
            await updateStudentTable();
        } catch (error) {
            alert(`Ошибка добавления оценки: ${error.message}`);
        }
    });
    // Initialize UI on page load
    updateUI();
</script>
