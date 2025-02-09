# Giftilic
Putujuća Čestitka
<!DOCTYPE html>
<html lang="sr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Putujuća čestitka</title>
    <style>
        body {
            font-family: 'Arial', sans-serif;
            text-align: center;
            background: linear-gradient(to right, #ffecd2, #fcb69f);
            padding: 20px;
            color: #333;
        }
        .container {
            background: white;
            max-width: 600px;
            margin: 20px auto;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
        }
        img {
            width: 100px;
            margin-bottom: 10px;
        }
        h1 {
            color: #d9534f;
        }
        p {
            font-size: 16px;
            margin-bottom: 20px;
        }
        textarea {
            width: 100%;
            height: 100px;
            padding: 10px;
            border: 1px solid #ccc;
            border-radius: 5px;
            font-size: 16px;
        }
        button {
            padding: 10px 20px;
            font-size: 16px;
            background-color: #28a745;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            margin-top: 10px;
        }
        button:hover {
            background-color: #218838;
        }
        #messageDisplay {
            margin-top: 20px;
            font-size: 18px;
            color: #555;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div class="container">
        <img src="logo.png" alt="Logo čestitke">
        <h1>Putujuća čestitka</h1>
        <p>Ova čestitka putuje od osobe do osobe, noseći lepe želje i poruke. 
            Upisivanjem teksta, ostavljate poruku sledećem primaocu. 
            Zajedno gradimo lanac radosti!</p>

        <textarea id="messageInput" placeholder="Napišite svoju čestitku ovde..."></textarea><br>
        <button onclick="saveMessage()">Sačuvaj poruku</button>

        <div id="messageDisplay"></div>
    </div>

    <script>
        function saveMessage() {
            let message = document.getElementById("messageInput").value;
            localStorage.setItem("putujucaCestitka", message);
            displayMessage();
        }

        function displayMessage() {
            let savedMessage = localStorage.getItem("putujucaCestitka");
            if (savedMessage) {
                document.getElementById("messageDisplay").innerHTML = "Poruka: " + savedMessage;
            }
        }

        window.onload = displayMessage;
    </script>

</body>
</html>
