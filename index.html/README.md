<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Be My Valentine?</title>
    <style>
        /* CSS: Website ko sundar banane ke liye */
        body {
            font-family: 'Arial', sans-serif;
            background-color: #ffe6e6;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            overflow: hidden;
        }

        .container {
            text-align: center;
            background: white;
            padding: 40px;
            border-radius: 20px;
            box-shadow: 0px 10px 20px rgba(0, 0, 0, 0.1);
        }

        h1 {
            color: #ff4d6d;
            font-size: 2.5rem;
            margin-bottom: 30px;
        }

        .buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            position: relative;
            height: 50px;
        }

        button {
            padding: 12px 30px;
            font-size: 1.2rem;
            border: none;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.2s ease;
        }

        #yesBtn {
            background-color: #ff4d6d;
            color: white;
        }

        #noBtn {
            background-color: #777;
            color: white;
            position: absolute; /* Yeh zaroori hai button ko bhagane ke liye */
            left: 55%;
        }
    </style>
</head>
<body>

    <div class="container">
        <h1 id="question">Will you be my Valentine? 💖</h1>
        
        <div class="buttons">
            <button id="yesBtn" onclick="celebrate()">Yes</button>
            <button id="noBtn" onmouseover="moveButton()" onclick="moveButton()">No</button>
        </div>
    </div>

    <script>
        // JavaScript: Buttons ko chalane ke liye
        
        // 1. Agar koi 'No' par mouse le jaye toh button bhagega
        function moveButton() {
            const noBtn = document.getElementById('noBtn');
            
            // Screen ki width aur height ke mutabik random jagah dundhna
            const x = Math.random() * (window.innerWidth - noBtn.offsetWidth - 50);
            const y = Math.random() * (window.innerHeight - noBtn.offsetHeight - 50);
            
            // Button ki nayi position set karna
            noBtn.style.position = 'absolute';
            noBtn.style.left = x + 'px';
            noBtn.style.top = y + 'px';
        }

        // 2. Agar koi 'Yes' par click kare toh kya ho
        function celebrate() {
            const question = document.getElementById('question');
            const noBtn = document.getElementById('noBtn');
            const yesBtn = document.getElementById('yesBtn');
            
            // Text badal dena
            question.innerHTML = "Yayyy! I knew it! 💖🥰";
            
            // Buttons ko chupa dena
            noBtn.style.display = 'none';
            yesBtn.style.display = 'none';
        }
    </script>

</body>
</html>

