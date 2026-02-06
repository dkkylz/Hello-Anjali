# Hello-Anjali
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Rose Day My Love</title>
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <style>
        /* This ensures the entire page is a flex container */
        html, body {
            height: 100%;
            margin: 0;
            padding: 0;
        }

        body {
            background-color: #fff5f5;
            display: flex;
            justify-content: center; /* Horizontal Center */
            align-items: center;     /* Vertical Center */
            font-family: 'Georgia', serif;
            text-align: center;
            overflow: hidden;
        }

        .container {
            width: 90%;
            max-width: 500px;
            display: flex;
            flex-direction: column;
            align-items: center; /* Centers items inside the container */
        }

        h1 {
            color: #d63384;
            font-size: 2.5rem;
            margin-bottom: 10px;
        }

        p {
            color: #4a4a4a;
            font-size: 1.2rem;
            line-height: 1.5;
            margin-bottom: 20px;
        }

        #rose-emoji {
            display: none;
            font-size: 100px; /* Big and beautiful */
            margin-bottom: 20px;
            animation: pop 0.6s cubic-bezier(0.175, 0.885, 0.32, 1.275);
        }

        .btn {
            background-color: #ff4d4d;
            color: white;
            border: none;
            padding: 16px 40px;
            font-size: 1.2rem;
            font-weight: bold;
            border-radius: 50px;
            cursor: pointer;
            box-shadow: 0 8px 20px rgba(255, 77, 77, 0.3);
            transition: all 0.3s ease;
        }

        .btn:active {
            transform: scale(0.95);
        }

        @keyframes pop {
            0% { transform: scale(0); }
            100% { transform: scale(1); }
        }
    </style>
</head>
<body>

    <div class="container">
        <div id="rose-emoji">🌹</div>
        
        <h1>Happy Rose Day! 🌹</h1>
        <p>Even though we are miles apart, you are the most beautiful, <br> 
           fragrant rose in the garden of my heart. ✨</p>
        
        <button id="mainButton" class="btn" onclick="celebrate()">Click Here</button>
    </div>

    <audio id="romantic-music" loop>
        <source src="https://www.soundhelix.com/examples/mp3/SoundHelix-Song-1.mp3" type="audio/mpeg">
    </audio>

    <script>
        function celebrate() {
            const music = document.getElementById('romantic-music');
            music.play().catch(e => console.log("Music ready after interaction"));

            // Show emoji and hide button
            document.getElementById('rose-emoji').style.display = 'block';
            document.getElementById('mainButton').style.display = 'none';

            // Confetti Burst
            const end = Date.now() + (3 * 1000);
            const colors = ['#ff4d4d', '#ffffff', '#ff007f'];

            (function frame() {
              confetti({
                particleCount: 3,
                angle: 60,
                spread: 55,
                origin: { x: 0 },
                colors: colors
              });
              confetti({
                particleCount: 3,
                angle: 120,
                spread: 55,
                origin: { x: 1 },
                colors: colors
              });

              if (Date.now() < end) {
                requestAnimationFrame(frame);
              }
            }());
        }
    </script>
</body>
</html>
