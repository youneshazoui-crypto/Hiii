<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Sis! 🎂</title>
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; }
        body {
            font-family: 'Comic Sans MS', cursive;
            background: linear-gradient(45deg, #ffecd2, #fcb69f, #a8edea, #fed6e3);
            background-size: 400% 400%;
            animation: gradientShift 12s ease infinite;
            color: #2c3e50;
            line-height: 1.8;
            min-height: 100vh;
        }
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        .container { max-width: 800px; margin: 0 auto; padding: 30px 20px; text-align: center; }
        h1 {
            font-size: 3.5rem; color: #e74c3c; margin-bottom: 10px;
            text-shadow: 3px 3px 8px rgba(0,0,0,0.3); animation: bounce 2s infinite;
        }
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-25px); }
            60% { transform: translateY(-12px); }
        }
        .subtitle { font-size: 1.6rem; color: #8e44ad; margin-bottom: 40px; }
        .emojis { font-size: 3rem; margin: 20px 0; animation: float 3s ease-in-out infinite; }
        @keyframes float { 0%, 100% { transform: translateY(0); } 50% { transform: translateY(-15px); } }
        
        .message-box {
            background: rgba(255,255,255,0.95); margin: 30px auto; padding: 35px;
            border-radius: 25px; box-shadow: 0 20px 40px rgba(0,0,0,0.15);
            max-width: 700px; backdrop-filter: blur(10px);
        }
        .message-box h2 { 
            color: #e74c3c; font-size: 2rem; margin-bottom: 20px;
            text-decoration: underline wavy #f39c12;
        }
        .message { 
            font-size: 1.4rem; margin-bottom: 25px; 
            text-align: left; padding: 20px; background: #fff; 
            border-left: 6px solid #f39c12; border-radius: 10px;
        }
        
        .final-photo {
            margin: 40px auto; max-width: 400px; border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.2); border: 8px solid #ff9a9e;
        }
        .final-photo img { width: 100%; height: auto; border-radius: 12px; }
        
        button {
            background: linear-gradient(45deg, #f39c12, #e67e22); color: white;
            border: none; padding: 15px 35px; font-size: 1.2rem; border-radius: 35px;
            cursor: pointer; margin: 15px; font-family: inherit; font-weight: bold;
            transition: all 0.3s;
        }
        button:hover { transform: translateY(-5px); box-shadow: 0 12px 25px rgba(0,0,0,0.2); }
        
        #confetti { position: fixed; top: 0; left: 0; pointer-events: none; z-index: 100; }
        @media (max-width: 600px) { h1 { font-size: 2.5rem; } .message { font-size: 1.2rem; } }
    </style>
</head>
<body>
    <canvas id="confetti"></canvas>
    
    <div class="container">
        <h1>Happy Birthday [Sis Name]! 🎉</h1>
        <div class="subtitle">To the BEST sister ever! 🌟</div>
        <div class="emojis">🎂🎈🎁✨🥳🎊</div>

        <!-- Message 1 -->
        <div class="message-box">
            <h2>🎮 Why You're Amazing:</h2>
            <div class="message">
                Sis, you're not just my sister - you're my gaming partner, 
                late-night snack buddy, and the only one who gets my weird jokes! 
                You've been there through every silly fight and epic win. 
                Here's to MANY more years of chaos together! 😎
            </div>
        </div>

        <!-- Message 2 -->
        <div class="message-box">
            <h2>💖 Favorite Memories:</h2>
            <div class="message">
                Remember when we stayed up all night watching cartoons? 
                Or when we made the worst cookies ever but ate them anyway? 
                Those are my favorite days. You make life so much fun!
            </div>
        </div>

        <!-- Message 3 -->
        <div class="message-box">
            <h2>🎁 Birthday Wish:</h2>
            <div class="message">
                This year I wish you get everything that makes you smile - 
                good grades, fun adventures, and all the snacks you can eat! 
                You're going to CRUSH this year! 🚀
            </div>
            <div style="text-align: center; font-size: 1.8rem; color: #e74c3c; margin-top: 20px;">
                Love you LOTS, [Your Name] ❤️
            </div>
        </div>

        <!-- YOUR PHOTO GOES HERE -->
        <div class="message-box">
            <h2 style="color: #e74c3c;">🎨 Special Picture for You:</h2>
            <div class="final-photo">
                <!-- PASTE YOUR PHOTO LINK HERE: -->
                <img src="https://i.imgur.com/i3FJC8W.jpg" alt="Special sister pic">
            </div>
            <p style="margin-top: 15px; font-style: italic;">[Photo description - "Our fave memory!" or whatever fits 😊]</p>
        </div>

        <button onclick="partyTime()">🎊 START BIRTHDAY PARTY! 🎊</button>
    </div>

    <script>
        // Simple confetti
        const canvas = document.getElementById('confetti');
        const ctx = canvas.getContext('2d');
        canvas.width = window.innerWidth; canvas.height = window.innerHeight;
        
        function makeConfetti() {
            for(let i = 0; i < 100; i++) {
                setTimeout(() => {
                    const x = Math.random() * canvas.width;
                    const size = Math.random() * 10 + 5;
                    ctx.fillStyle = `hsl(${Math.random()*360}, 70%, 60%)`;
                    ctx.fillRect(x, 0, size, size);
                }, i * 20);
            }
        }
        setInterval(makeConfetti, 3000);

        // Party explosion
        function partyTime() {
            const emojis = ['🎉','🎊','🎈','🎂','✨','🌟','🎁','🥳','🎵','💖'];
            for(let i = 0; i < 50; i++) {
                setTimeout(() => {
                    const div = document.createElement('div');
                    div.textContent = emojis[Math.floor(Math.random()*emojis.length)];
                    div.style.cssText = `
                        position: fixed; left: ${Math.random()*90}vw; top: 100vh;
                        font-size: ${Math.random()*3+2}rem; pointer-events: none;
                        animation: explode 3s ease-out forwards; z-index: 999;
                    `;
                    document.body.appendChild(div);
                    setTimeout(() => div.remove(), 3000);
                }, i * 50);
            }
            alert('🎉 HAPPY BIRTHDAY SIS! 🎉\n\nHave the BEST day ever! 🥰');
        }

        // CSS for explosion
        const style = document.createElement('style');
        style.textContent = `
            @keyframes explode {
                to { transform: translateY(-120vh) rotate(720deg); opacity: 0; }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>

