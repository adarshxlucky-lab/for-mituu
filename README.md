# for-mituu
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>A Question for Mituu...</title>
    <style>
        body {
            margin: 0;
            padding: 0;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            /* Base Background: A gentle, cute pink */
            background-color: #ffc0cb; 
            /* Code-Generated Hearts & Dots */
            background-image: 
                url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Cpath d='M50 30 C 60 10, 90 20, 90 45 C 90 70, 50 90, 50 90 C 50 90, 10 70, 10 45 C 10 20, 40 10, 50 30 Z' stroke='%23f38ba888' fill='none' stroke-width='1.5'/%3E%3C/svg%3E"), 
                radial-gradient(#f38ba855 2px, transparent 2px);
            background-size: 200px 200px, 50px 50px;
            background-position: 0 0, 0 0;
            color: #1e1e2e;
            font-family: 'Courier New', Courier, monospace;
            overflow: hidden;
        }
        .container {
            text-align: center;
            position: relative;
            width: 100%;
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            background: rgba(255, 255, 255, 0.9); 
        }
        h1 {
            color: #e60073;
            font-size: 2rem;
            margin-bottom: 2rem;
            padding: 0 20px;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.2);
        }
        .buttons {
            position: relative;
            width: 300px;
            height: 100px;
        }
        button {
            font-family: 'Courier New', Courier, monospace;
            font-size: 1.2rem;
            font-weight: bold;
            padding: 10px 20px;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            transition: 0.1s;
        }
        #yesBtn {
            background-color: #a6e3a1; /* Terminal green */
            color: #1e1e2e;
            position: absolute;
            left: 20px;
        }
        #yesBtn:hover {
            background-color: #94e2d5;
            transform: scale(1.1);
        }
        #noBtn {
            background-color: #f38ba8; /* Terminal red */
            color: #1e1e2e;
            position: absolute;
            right: 20px;
        }
        #successMessage {
            display: none;
            color: #e60073;
            font-size: 1.4rem;
            padding: 20px;
            line-height: 1.6;
            text-shadow: 1px 1px 2px rgba(0,0,0,0.1);
            font-family: 'Arial', sans-serif; /* Making the final message slightly more readable */
            font-weight: bold;
        }
        /* Cute Nickname Floating Messages */
        .cute-msg {
            position: absolute;
            font-size: 0.95rem;
            color: #e60073aa;
            font-style: italic;
            font-weight: bold;
            pointer-events: none;
        }
        .msg1 { top: 8%; left: 8%; }
        .msg2 { top: 8%; right: 8%; }
        .msg3 { top: 22%; left: 4%; }
        .msg4 { top: 22%; right: 4%; }
        .msg5 { bottom: 22%; left: 4%; }
        .msg6 { bottom: 22%; right: 4%; }
        .msg7 { bottom: 8%; left: 8%; }
        .msg8 { bottom: 8%; right: 8%; }
    </style>
</head>
<body>

    <div class="container" id="mainContainer">
        <!-- Floating Nickname Messages -->
        <span class="cute-msg msg1">My kuchupuchu</span>
        <span class="cute-msg msg2">My cutie pie</span>
        <span class="cute-msg msg3">My rasmalai</span>
        <span class="cute-msg msg4">My madam ji</span>
        <span class="cute-msg msg5">Meri jaanuu</span>
        <span class="cute-msg msg6">Merii lugai</span>
        <span class="cute-msg msg7">Merii mommyyy</span>
        <span class="cute-msg msg8">Meri babyy</span>

        <!-- Proposal Question with her name -->
        <h1>Will you be my girlfriend, Mituu? ❤️</h1>
        
        <div class="buttons" id="buttonContainer">
            <button id="yesBtn" onclick="sayYes()"> YES </button>
            <button id="noBtn" onmouseover="moveButton()"> NO </button>
        </div>

        <!-- NEW CUTE SUCCESS MESSAGE -->
        <div id="successMessage">
            System Output: Perfect Match Found! 💖<br><br>
            Mituu, you just made me the happiest person ever. <br>
            I promise to always love you, annoy you, and treat you like my precious Rasmalai. 😘<br><br>
            Take a screenshot and send it to me so I can celebrate! 🎉
        </div>
    </div>

    <script>
        function moveButton() {
            const noBtn = document.getElementById('noBtn');
            const maxX = window.innerWidth - noBtn.offsetWidth - 20;
            const maxY = window.innerHeight - noBtn.offsetHeight - 20;
            const randomX = Math.max(20, Math.floor(Math.random() * maxX));
            const randomY = Math.max(20, Math.floor(Math.random() * maxY));
            
            noBtn.style.position = 'fixed';
            noBtn.style.left = randomX + 'px';
            noBtn.style.top = randomY + 'px';
        }

        function sayYes() {
            document.querySelector('h1').style.display = 'none';
            document.getElementById('buttonContainer').style.display = 'none';
            // Hide all nicknames
            document.querySelectorAll('.cute-msg').forEach(msg => msg.style.display = 'none');
            // Show success message
            document.getElementById('successMessage').style.display = 'block';
        }
        
        // Touch support for mobile phones
        document.getElementById('noBtn').addEventListener('touchstart', function(e) {
            e.preventDefault(); 
            moveButton();
        });
    </script>

</body>
</html>
