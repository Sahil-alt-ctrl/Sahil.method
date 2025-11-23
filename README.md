<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Will You Be My Valentine?</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            background-color: #ffe4e6;
            font-family: 'Arial', sans-serif;
            flex-direction: column;
            overflow: hidden;
        }
        .container { text-align: center; }
        h1 { font-size: 2rem; color: #be185d; margin-bottom: 20px; padding: 0 20px; }
        img { width: 200px; border-radius: 10px; margin-bottom: 20px; }
        .buttons { display: flex; gap: 15px; justify-content: center; flex-wrap: wrap; }
        #yesBtn { background-color: #22c55e; color: white; border: none; padding: 15px 32px; font-size: 16px; font-weight: bold; border-radius: 8px; cursor: pointer; }
        #noBtn { background-color: #ef4444; color: white; border: none; padding: 15px 32px; font-size: 16px; font-weight: bold; border-radius: 8px; cursor: pointer; }
        #success { display: none; flex-direction: column; align-items: center; }
    </style>
</head>
<body>
    <div class="container">
        <div id="question-box">
            <img src="https://media.tenor.com/h5jR_iU96MAAAAAi/bear-kawaii.gif" alt="Cute Bear">
            <h1>Will you go out with me?</h1>
            <div class="buttons">
                <button id="yesBtn" onclick="sayYes()">Yes</button>
                <button id="noBtn" onclick="hoverNo()">No</button>
            </div>
        </div>
        <div id="success">
            <img src="https://media.tenor.com/gUiu1zyxfzYAAAAi/bear-kiss-bear-kisses.gif" alt="Bear Kiss">
            <h1>Yay! I love you! ❤️</h1>
        </div>
    </div>
    <script>
        let yesSize = 16;
        let clickCount = 0;
        const phrases = ["No", "Are you sure?", "Really?", "Please?", "Heartless!", "Don't do this!"];

        function hoverNo() {
            clickCount++;
            yesSize += 20;
            document.getElementById("yesBtn").style.fontSize = yesSize + "px";
            let phrase = phrases[Math.min(clickCount, phrases.length - 1)];
            document.getElementById("noBtn").innerText = phrase;
        }

        function sayYes() {
            document.getElementById("question-box").style.display = "none";
            document.getElementById("success").style.display = "flex";
        }
    </script>
</body>
</html>

