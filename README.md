<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Happy Birthday Best Friend! 🐼💕</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Comic Sans MS', cursive, sans-serif;
            background: linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%);
            min-height: 100vh;
            overflow-x: hidden;
        }

        .page {
            display: none;
            min-height: 100vh;
            padding: 20px;
            position: relative;
        }

        .page.active {
            display: block;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        /* Navigation */
        .nav-bar {
            position: fixed;
            top: 0;
            left: 0;
            right: 0;
            background: rgba(255, 255, 255, 0.95);
            backdrop-filter: blur(10px);
            padding: 10px 0;
            z-index: 1000;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        }

        .nav-container {
            max-width: 1200px;
            margin: 0 auto;
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 10px;
            padding: 0 20px;
        }

        .nav-btn {
            background: linear-gradient(45deg, #ff6b6b, #ee5a6f);
            color: white;
            border: none;
            padding: 8px 16px;
            border-radius: 25px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-size: 0.9rem;
            font-weight: bold;
        }

        .nav-btn:hover, .nav-btn.active {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            background: linear-gradient(45deg, #ee5a6f, #ff6b6b);
        }

        /* Countdown Page */
        .countdown-container {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            min-height: 100vh;
            text-align: center;
        }

        .countdown-title {
            font-size: 3rem;
            color: #2c3e50;
            margin-bottom: 50px;
            animation: pulse 2s infinite;
        }

        .countdown-number {
            font-size: 15rem;
            font-weight: bold;
            color: #e74c3c;
            text-shadow: 5px 5px 10px rgba(0,0,0,0.3);
            animation: countdownPulse 1s ease-in-out;
        }

        .countdown-message {
            font-size: 2rem;
            color: #2c3e50;
            margin-top: 30px;
            opacity: 0;
            animation: fadeInUp 0.5s ease-out 0.5s forwards;
        }

        .start-btn {
            background: linear-gradient(45deg, #4ecdc4, #44a08d);
            color: white;
            border: none;
            padding: 20px 40px;
            font-size: 1.5rem;
            border-radius: 50px;
            cursor: pointer;
            margin-top: 30px;
            animation: bounce 2s infinite;
            box-shadow: 0 10px 30px rgba(0,0,0,0.2);
        }

        @keyframes countdownPulse {
            0% { transform: scale(0.8); opacity: 0; }
            50% { transform: scale(1.2); opacity: 1; }
            100% { transform: scale(1); opacity: 1; }
        }

        @keyframes fadeInUp {
            0% { opacity: 0; transform: translateY(30px); }
            100% { opacity: 1; transform: translateY(0); }
        }

        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }

        /* Main Birthday Page */
        .header {
            text-align: center;
            margin: 80px 0 50px 0;
            animation: bounceIn 2s ease-out;
        }

        .main-title {
            font-size: 3.5rem;
            color: #2c3e50;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            margin-bottom: 20px;
            animation: rainbow 3s linear infinite;
        }

        @keyframes rainbow {
            0% { color: #ff6b6b; }
            16% { color: #4ecdc4; }
            33% { color: #45b7d1; }
            50% { color: #96ceb4; }
            66% { color: #ffeaa7; }
            83% { color: #dda0dd; }
            100% { color: #ff6b6b; }
        }

        .subtitle {
            font-size: 1.8rem;
            color: #34495e;
            margin-bottom: 30px;
        }

        .panda-container {
            display: flex;
            justify-content: center;
            margin: 30px 0;
            animation: float 3s ease-in-out infinite;
        }

        .panda {
            font-size: 8rem;
            animation: bounce 2s infinite;
            cursor: pointer;
            transition: transform 0.3s ease;
        }

        .panda:hover {
            transform: scale(1.2);
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        @keyframes bounceIn {
            0% { opacity: 0; transform: scale(0.3); }
            50% { opacity: 1; transform: scale(1.05); }
            70% { transform: scale(0.9); }
            100% { opacity: 1; transform: scale(1); }
        }

        /* Hearts animation */
        .hearts-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .heart {
            position: absolute;
            font-size: 2rem;
            color: #e74c3c;
            animation: heartFloat 4s linear infinite;
        }

        @keyframes heartFloat {
            0% {
                transform: translateY(100vh) rotate(0deg);
                opacity: 1;
            }
            100% {
                transform: translateY(-100px) rotate(360deg);
                opacity: 0;
            }
        }


        /* Photos Page */
        .photos-container {
            margin-top: 80px;
            padding: 40px 20px;
        }

        .photos-title {
            text-align: center;
            font-size: 3rem;
            color: #2c3e50;
            margin-bottom: 50px;
            animation: fadeIn 2s ease-in;
        }

        .photos-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-bottom: 50px;
        }

        .photo-frame {
            background: white;
            padding: 20px;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
            transition: transform 0.3s ease;
            animation: slideInUp 1s ease-out;
        }

        .photo-frame:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0,0,0,0.2);
        }

        .photo-placeholder {
            width: 100%;
            height: 250px;
            background: linear-gradient(135deg, #ffeaa7, #fab1a0);
            border-radius: 15px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 4rem;
            margin-bottom: 15px;
            position: relative;
            overflow: hidden;
        }

        .photo-placeholder::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255,255,255,0.3), transparent);
            animation: shine 3s infinite;
        }

        @keyframes shine {
            0% { transform: translateX(-100%) translateY(-100%) rotate(45deg); }
            100% { transform: translateX(100%) translateY(100%) rotate(45deg); }
        }

        .photo-caption {
            text-align: center;
            font-size: 1.2rem;
            color: #2c3e50;
            font-weight: bold;
        }

        .upload-section {
            text-align: center;
            background: rgba(255, 255, 255, 0.9);
            padding: 40px;
            border-radius: 20px;
            margin: 30px 0;
        }

        .upload-btn {
            background: linear-gradient(45deg, #6c5ce7, #a29bfe);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.3rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }

        .upload-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.3);
        }

        /* Interactive elements */
        .birthday-cake {
            text-align: center;
            font-size: 6rem;
            margin: 40px 0;
            animation: pulse 2s infinite;
            cursor: pointer;
        }

        @keyframes pulse {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        .interactive-section {
            text-align: center;
            margin: 40px 0;
            position: relative;
            z-index: 2;
        }

        .birthday-button {
            background: linear-gradient(45deg, #ff6b6b, #ee5a6f);
            color: white;
            border: none;
            padding: 15px 30px;
            font-size: 1.3rem;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.3s ease;
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
            margin: 10px;
        }

        .birthday-button:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(0,0,0,0.3);
        }

        .message-popup {
            display: none;
            position: fixed;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
            background: white;
            padding: 30px;
            border-radius: 20px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.3);
            z-index: 1000;
            text-align: center;
            max-width: 400px;
        }

        .close-popup {
            position: absolute;
            top: 10px;
            right: 15px;
            background: none;
            border: none;
            font-size: 1.5rem;
            cursor: pointer;
        }

        .footer {
            text-align: center;
            margin-top: 50px;
            font-size: 1.5rem;
            color: #2c3e50;
            animation: fadeIn 3s ease-in;
            position: relative;
            z-index: 2;
        }
        #nav{
            visibility: hidden;
            transition: transform 0.8s ease-out;
        }

        @keyframes fadeIn {
            0% { opacity: 0; }
            100% { opacity: 1; }
        }

        /* Mobile responsiveness */
        @media (max-width: 768px) {
            .nav-container {
                flex-direction: row;
                align-items: center;
            }
            
            .nav-btn {
                font-size: 0.8rem;
                padding: 6px 12px;
            }
            
            .main-title { font-size: 2.5rem; }
            .subtitle { font-size: 1.4rem; }
            .panda { font-size: 6rem; }
            .wish-text { font-size: 1.2rem; }
            .birthday-cake { font-size: 4rem; }
            .countdown-number { font-size: 10rem; }
            .countdown-title { font-size: 2rem; }
            
            .photos-grid {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="hearts-container" id="heartsContainer"></div>
    
    <!-- Navigation -->
    <nav class="nav-bar" id="nav">
        <div class="nav-container">
            <button class="nav-btn" onclick="showPage('birthday')">🎉 Birthday</button>
            <button class="nav-btn" onclick="showPage('photos')">📸 Photos</button>
            <button class="nav-btn" onclick="showPage('memories')">💭 Memories</button>
        </div>
    </nav>

    <!-- Countdown Page -->
    <div class="page active" id="countdown">
        <div class="countdown-container">
            <h1 class="countdown-title">🎂 Birthday Countdown! 🎂</h1>
            <div class="countdown-number" id="countdownNumber">10</div>
            <div class="countdown-message" id="countdownMessage">Get ready for something amazing...</div>
            <button class="start-btn" onclick="startCountdown()" id="startBtn">Start Countdown! 🚀</button>
        </div>
    </div>

    <!-- Birthday Page -->
    <div class="page" id="birthday">
        <div class="container">
            <header class="header">
                <h1 class="main-title">🎉 HAPPY BIRTHDAY 🎉</h1>
                <p class="subtitle">To My Amazing Best Friend!</p>
                
                <div class="panda-container">
                    <div class="panda" onclick="pandaClick()">🐼</div>
                </div>
            </header>

            <div class="birthday-cake" onclick="cakeClick()">🎂</div>

            <div class="interactive-section">
                <button class="birthday-button" onclick="showMessage('surprise')">🎁 Birthday Surprise!</button>
                <button class="birthday-button" onclick="showMessage('memory')">💭 Special Memory</button>
                <button class="birthday-button" onclick="showMessage('wish')">⭐ Make a Wish!</button>
            </div>
        </div>
    </div>

    
    <!-- Photos Page -->
    <div class="page" id="photos">
        <div class="container">
            <div class="photos-container">
                <h1 class="photos-title">📸 Our Amazing Memories 📸</h1>
                
                <div class="photos-grid">
                    <div class="photo-frame">
                        <div class="photo-placeholder"><img src="D:\code with 2g\gvproject\gvproject\one.jpeg"></div>
                        <div class="photo-caption">Best Friends Forever</div>
                    </div>
                    <div class="photo-frame">
                        <div class="photo-placeholder"><img src="D:\code with 2g\gvproject\gvproject\two.jpeg"></div>
                        <div class="photo-caption">Birthday Celebrations</div>
                    </div>
                    <div class="photo-frame">
                        <div class="photo-placeholder"><img src="D:\code with 2g\gvproject\gvproject\three.jpeg"></div>
                        <div class="photo-caption">Special Moments</div>
                    </div>
                    <div class="photo-frame">
                        <div class="photo-placeholder"><img src="D:\code with 2g\gvproject\gvproject\four.jpeg"></div>
                        <div class="photo-caption">Fun Times Together</div>
                    </div>
                    <div class="photo-frame">
                        <div class="photo-placeholder"><img src="D:\code with 2g\gvproject\gvproject\five.jpeg"></div>
                        <div class="photo-caption">Happy Days</div>
                    </div>
                    <div class="photo-frame">
                        <div class="photo-placeholder"><img src="D:\code with 2g\gvproject\gvproject\six.jpeg"></div>
                        <div class="photo-caption">Friendship Goals</div>
                    </div>
                </div>           
            </div>
        </div>
    </div>

    <!-- Memories Page -->
    <div class="page" id="memories">
        <div class="container">
            <div style="margin-top: 80px;">
                <section class="wishes-section">
                    <h2 style="text-align: center; font-size: 2.5rem; margin-bottom: 30px; color: #2c3e50;">💭 Special Memories 💭</h2>
                    <div class="wish-text">
                        🌈 Remember when we first met? I knew right away you were going to be someone special in my life!
                        <br><br>
                        🎭 All those times we've laughed until our stomachs hurt, cried during movies, and stayed up way too late talking about everything and nothing...
                        <br><br>
                        🎢 Our adventures together - from spontaneous trips to quiet moments at home - every single one has been a treasure!
                        <br><br>
                        🌟 You've been there through thick and thin, always knowing exactly what to say to make everything better. That's what makes you so incredibly special!
                        <br><br>
                        💝 Here's to all the memories we've made and all the amazing ones still to come! Our friendship is truly one of a kind! 🐼💕
                    </div>
                </section>
            </div>
        </div>
    </div>

    <footer class="footer">
        <p>🐼💕 With all my love and best wishes! 💕🐼</p>
        <p>Happy Birthday, Best Friend! 🎉</p>
    </footer>

    <div class="message-popup" id="messagePopup">
        <button class="close-popup" onclick="closePopup()">&times;</button>
        <div id="popupContent"></div>
    </div>

    <script>
        let currentPage = 'countdown';
        let countdownActive = false;
        
        // Show page function
        function showPage(pageId) {
            // Hide all pages
            document.querySelectorAll('.page').forEach(page => {
                page.classList.remove('active');
            });
            
            // Show selected page
            document.getElementById(pageId).classList.add('active');
            
            // Update navigation
            document.querySelectorAll('.nav-btn').forEach(btn => {
                btn.classList.remove('active');
            });
            event.target.classList.add('active');
            
            currentPage = pageId;
        }

        // Countdown function
        function startCountdown() {
            if (countdownActive) return;
            
            countdownActive = true;
            const startBtn = document.getElementById('startBtn');
            const numberEl = document.getElementById('countdownNumber');
            const messageEl = document.getElementById('countdownMessage');
            const nav=document.getElementById('nav');
            
            startBtn.style.display = 'none';
            
            let count = 10;
            
            const countInterval = setInterval(() => {
                numberEl.textContent = count;
                numberEl.style.animation = 'none';
                setTimeout(() => {
                    numberEl.style.animation = 'countdownPulse 1s ease-in-out';
                }, 10);
                
                // Special messages for certain numbers
                if (count === 5) {
                    messageEl.textContent = "Almost there! 🎈";
                    messageEl.style.animation = 'none';
                    setTimeout(() => {
                        messageEl.style.animation = 'fadeInUp 0.5s ease-out forwards';
                    }, 10);
                } else if (count === 3) {
                    messageEl.textContent = "Get ready to celebrate! 🎉";
                    messageEl.style.animation = 'none';
                    setTimeout(() => {
                        messageEl.style.animation = 'fadeInUp 0.5s ease-out forwards';
                    }, 10);
                } else if (count === 1) {
                    messageEl.textContent = "Here we go! 🚀";
                    messageEl.style.animation = 'none';
                    setTimeout(() => {
                        messageEl.style.animation = 'fadeInUp 0.5s ease-out forwards';
                    }, 10);
                }
                
                count--;
                
                if (count < 0) {
                    clearInterval(countInterval);
                    numberEl.textContent = "🎉";
                    numberEl.style.fontSize = "10rem";
                    messageEl.textContent = "HAPPY BIRTHDAY! 🎂🎈";
                    nav.style.visibility = "visible";
        
                    nav.style.transform = "scale(1)";

                    
                    // Create celebration effect
                    for(let i = 0; i < 20; i++) {
                        setTimeout(() => createHeart(), i * 100);
                    }
                    
                    // Auto-navigate to birthday page after 3 seconds
                    setTimeout(() => {
                        showPage('birthday');
                        document.querySelector('[onclick="showPage(\'birthday\')"]').classList.add('active');
                    }, 3000);
                }
            }, 1000);
        }

        // Create floating hearts
        function createHeart() {
            const heart = document.createElement('div');
            heart.className = 'heart';
            heart.innerHTML = '💕';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 3 + 2) + 's';
            heart.style.fontSize = (Math.random() * 1 + 1) + 'rem';
            
            document.getElementById('heartsContainer').appendChild(heart);
            
            setTimeout(() => {
                heart.remove();
            }, 5000);
        }

        // Create hearts continuously
        setInterval(createHeart, 800);

        // Panda click interaction
        function pandaClick() {
            const panda = document.querySelector('.panda');
            panda.style.transform = 'scale(1.5) rotate(360deg)';
            setTimeout(() => {
                panda.style.transform = 'scale(1) rotate(0deg)';
            }, 500);
            
            // Create explosion of hearts
            for(let i = 0; i < 10; i++) {
                setTimeout(() => createHeart(), i * 100);
            }
        }

        // Cake click interaction
        function cakeClick() {
            const cake = document.querySelector('.birthday-cake');
            cake.innerHTML = '🎂✨';
            setTimeout(() => {
                cake.innerHTML = '🎂';
            }, 1000);
            
            // Play birthday sound effect (visual feedback)
            document.body.style.background = 'linear-gradient(135deg, #ffd700 0%, #ffb347 50%, #ff6b6b 100%)';
            setTimeout(() => {
                document.body.style.background = 'linear-gradient(135deg, #ff9a9e 0%, #fecfef 50%, #fecfef 100%)';
            }, 1000);
        }

        // Show popup messages
        function showMessage(type) {
            const popup = document.getElementById('messagePopup');
            const content = document.getElementById('popupContent');
            
            const messages = {
                surprise: `
                    <h3>🎁 Your Birthday Surprise! 🎁</h3>
                    <p>🌟 You're getting a virtual panda hug! 🤗🐼</p>
                    <p>💕 And a promise for a real celebration soon! 🎉</p>
                    <div style="font-size: 3rem; margin: 20px 0;">🐼🤗💕</div>
                `,
                memory: `
                    <h3>💭 A Special Memory 💭</h3>
                    <p>🌈 Remember all the times we've laughed until our stomachs hurt?</p>
                    <p>🐼 You're like a panda - rare, precious, and always making me smile!</p>
                    <p>💝 Here's to making many more beautiful memories together!</p>
                `,
                wish: `
                    <h3>⭐ Make a Birthday Wish! ⭐</h3>
                    <p>🕯️ Close your eyes and make a wish...</p>
                    <p>🌟 I hope all your dreams come true this year!</p>
                    <p>🐼💕 You deserve all the happiness in the world!</p>
                    <div style="font-size: 2rem; margin: 15px 0;">✨🌟⭐</div>
                `,
                upload: `
                    <h3>📸 Upload Your Photos! 📸</h3>
                    <p>🌟 Share your favorite memories with us!</p>
                    <p>💕 Add photos of our adventures, celebrations, and special moments!</p>
                    <p>🐼 This is where all our beautiful memories will live forever!</p>
                    <div style="font-size: 2rem; margin: 15px 0;">📷💝🎉</div>
                `
            };
            
            content.innerHTML = messages[type];
            popup.style.display = 'block';
        }

        // Close popup
        function closePopup() {
            document.getElementById('messagePopup').style.display = 'none';
        }

        // Close popup when clicking outside
        window.onclick = function(event) {
            const popup = document.getElementById('messagePopup');
            if (event.target === popup) {
                popup.style.display = 'none';
            }
        }

        // Add some sparkle effects on scroll
        window.addEventListener('scroll', function() {
            const scrolled = window.pageYOffset;
            const parallax = scrolled * 0.5;
            
            document.querySelector('.hearts-container').style.transform = `translateY(${parallax}px)`;
        });

        // Initialize navigation
        document.addEventListener('DOMContentLoaded', function() {
            document.querySelector('.nav-btn').classList.add('active');
        });
    </script>
</body>
</html>
