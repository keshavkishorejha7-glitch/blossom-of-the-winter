<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Queen Ayushi</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css2?family=Dancing+Script:wght@600;700&family=Poppins:wght@300;400;600&family=Pacifico&display=swap" rel="stylesheet">
    <style>
        :root {
            --rose: #ff4d6d;
            --lavender: #c8b6ff;
            --mint: #b9fbc0;
            --sunshine: #fbf8cc;
        }
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(45deg, #ffafbd, #ffc3a0, #ffafbd);
            background-size: 400% 400%;
            animation: gradientBG 15s ease infinite;
            overflow: hidden;
            margin: 0;
            padding: 0;
            touch-action: manipulation;
        }
        @keyframes gradientBG {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        .slide {
            display: none;
            height: 100vh;
            width: 100vw;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            text-align: center;
            padding: 20px;
            animation: zoomIn 0.6s ease-out;
        }
        .active-slide { display: flex; }
        @keyframes zoomIn {
            from { opacity: 0; transform: scale(1.2); filter: blur(10px); }
            to { opacity: 1; transform: scale(1); filter: blur(0); }
        }

        /* Glassmorphism Card */
        .glass-card {
            background: rgba(255, 255, 255, 0.25);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.3);
            border-radius: 30px;
            padding: 30px;
            box-shadow: 0 8px 32px 0 rgba(31, 38, 135, 0.15);
            max-width: 90%;
            width: 450px;
        }

        /* Photo Slideshow */
        .slideshow-container {
            width: 100%;
            height: 300px;
            position: relative;
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }
        .myPhotos {
            display: none;
            width: 100%;
            height: 100%;
            object-fit: cover;
            animation: fadeEffect 1.5s;
        }
        @keyframes fadeEffect {
            from {opacity: 0.4} to {opacity: 1}
        }

        /* Floating Decorations */
        .floating {
            position: absolute;
            pointer-events: none;
            z-index: 1;
            animation: floatUpDown 6s ease-in-out infinite;
        }
        @keyframes floatUpDown {
            0%, 100% { transform: translateY(0) rotate(0); }
            50% { transform: translateY(-30px) rotate(20deg); }
        }

        .nav-btn {
            background: white;
            color: #ff4d6d;
            padding: 12px 25px;
            border-radius: 50px;
            font-weight: 700;
            box-shadow: 0 4px 15px rgba(0,0,0,0.1);
            transition: 0.3s;
            margin-top: 20px;
            border: none;
            cursor: pointer;
        }
        .nav-btn:hover {
            transform: scale(1.1);
            background: #ff4d6d;
            color: white;
        }

        /* Page Dots */
        .dot-container {
            position: fixed;
            bottom: 20px;
            display: flex;
            gap: 10px;
        }
        .dot {
            width: 10px;
            height: 10px;
            background: rgba(255,255,255,0.5);
            border-radius: 50%;
            transition: 0.3s;
        }
        .active-dot {
            background: white;
            transform: scale(1.4);
        }
    </style>
</head>
<body>

    <div id="decorations"></div>

    <!-- Page 1: Welcome -->
    <div id="slide1" class="slide active-slide">
        <div class="glass-card">
            <h1 class="text-5xl font-[Pacifico] text-white mb-6 drop-shadow-lg">Hello Ayushi!</h1>
            <p class="text-white text-lg font-medium">I built a little world just for you. Shall we explore?</p>
            <button class="nav-btn" onclick="nextSlide(2)">Enter Our World 💖</button>
        </div>
    </div>

    <!-- Page 2: The Slideshow (Her Beauty) -->
    <div id="slide2" class="slide">
        <h2 class="text-3xl font-[Dancing+Script] text-white mb-6 font-bold">The Prettiest Face I Know...</h2>
        <div class="glass-card">
            <div class="slideshow-container">
                <!-- Replace these src URLs with actual photos of Ayushi -->
                <img src="https://images.unsplash.com/photo-1517841905240-472988babdf9?auto=format&fit=crop&w=400&q=80" class="myPhotos">
                <img src="https://images.unsplash.com/photo-1524504388940-b1c1722653e1?auto=format&fit=crop&w=400&q=80" class="myPhotos">
                <img src="https://images.unsplash.com/photo-1494790108377-be9c29b29330?auto=format&fit=crop&w=400&q=80" class="myPhotos">
            </div>
            <p class="mt-4 text-white italic">"Every time I see you, I fall in love all over again."</p>
            <button class="nav-btn" onclick="nextSlide(3)">Keep Going ✨</button>
        </div>
    </div>

    <!-- Page 3: Feelings Timeline -->
    <div id="slide3" class="slide">
        <div class="glass-card text-left">
            <h2 class="text-3xl font-[Dancing+Script] text-white mb-6 text-center font-bold">Why I Love You</h2>
            <div class="space-y-4 text-white">
                <div class="flex items-center gap-3">
                    <i class="fas fa-heart text-red-400"></i>
                    <span>Your Smile: It brightens my darkest days.</span>
                </div>
                <div class="flex items-center gap-3">
                    <i class="fas fa-star text-yellow-300"></i>
                    <span>Your Soul: You are the kindest person I've met.</span>
                </div>
                <div class="flex items-center gap-3">
                    <i class="fas fa-music text-blue-300"></i>
                    <span>Your Voice: It's my favorite melody.</span>
                </div>
                <div class="flex items-center gap-3">
                    <i class="fas fa-sun text-orange-300"></i>
                    <span>Your Presence: Everything feels right with you.</span>
                </div>
            </div>
            <button class="nav-btn w-full mt-8" onclick="nextSlide(4)">One More Thing... 🌙</button>
        </div>
    </div>

    <!-- Page 4: Interactive Memory -->
    <div id="slide4" class="slide">
        <div class="glass-card">
            <i class="fas fa-envelope-open-text text-5xl text-white mb-6"></i>
            <h2 class="text-2xl font-bold text-white mb-4">A Secret Note</h2>
            <p class="text-white italic leading-relaxed">
                "Ayushi, sometimes I might be difficult, but please never doubt my love for you. You aren't just my girlfriend, you're my best friend and my home."
            </p>
            <button class="nav-btn" onclick="nextSlide(5)">Almost there... 🦋</button>
        </div>
    </div>

    <!-- Page 5: Our Future -->
    <div id="slide5" class="slide">
        <h2 class="text-4xl font-[Pacifico] text-white mb-10">To Our Future...</h2>
        <div class="flex gap-4">
            <div class="glass-card w-40 text-white">
                <i class="fas fa-plane text-3xl mb-2"></i>
                <p>Travel Together</p>
            </div>
            <div class="glass-card w-40 text-white">
                <i class="fas fa-home text-3xl mb-2"></i>
                <p>Grow Together</p>
            </div>
        </div>
        <button class="nav-btn mt-12" onclick="nextSlide(6)">The Big Question 💎</button>
    </div>

    <!-- Page 6: Forgiveness/Promise -->
    <div id="slide6" class="slide">
        <div class="glass-card">
            <h2 class="text-3xl font-bold text-white mb-6">Forever?</h2>
            <p class="text-white mb-8">I promise to love you more than yesterday and less than tomorrow.</p>
            <div class="flex flex-col gap-4">
                <button class="bg-white text-[#ff4d6d] py-3 rounded-full font-bold text-xl shadow-lg" onclick="celebrate()">Yes, Forever ❤️</button>
                <button id="no-btn" class="bg-transparent border border-white text-white py-2 rounded-full text-sm" onmouseover="moveNo()">Not today</button>
            </div>
            <div id="final-msg" class="hidden mt-8 animate-bounce text-2xl text-white font-[Pacifico]">
                I Love You, Ayushi! ♾️
            </div>
        </div>
    </div>

    <div class="dot-container">
        <div class="dot active-dot" id="dot1"></div>
        <div class="dot" id="dot2"></div>
        <div class="dot" id="dot3"></div>
        <div class="dot" id="dot4"></div>
        <div class="dot" id="dot5"></div>
        <div class="dot" id="dot6"></div>
    </div>

    <script>
        let currentSlide = 1;
        
        // Photo Slideshow Logic
        let photoIndex = 0;
        function showPhotos() {
            let i;
            let photos = document.getElementsByClassName("myPhotos");
            for (i = 0; i < photos.length; i++) {
                photos[i].style.display = "none";  
            }
            photoIndex++;
            if (photoIndex > photos.length) {photoIndex = 1}    
            photos[photoIndex-1].style.display = "block";  
            setTimeout(showPhotos, 3000); 
        }
        showPhotos();

        // Slide Navigation
        function nextSlide(n) {
            document.getElementById('slide' + currentSlide).classList.remove('active-slide');
            document.getElementById('dot' + currentSlide).classList.remove('active-dot');
            
            currentSlide = n;
            
            document.getElementById('slide' + currentSlide).classList.add('active-slide');
            document.getElementById('dot' + currentSlide).classList.add('active-dot');
        }

        // Floating Decor
        const decorIcons = ['❤️', '💖', '🌸', '✨', '💎', '🌹'];
        function createDecor() {
            const el = document.createElement('div');
            el.className = 'floating';
            el.innerHTML = decorIcons[Math.floor(Math.random() * decorIcons.length)];
            el.style.left = Math.random() * 100 + 'vw';
            el.style.top = Math.random() * 100 + 'vh';
            el.style.fontSize = (Math.random() * 20 + 20) + 'px';
            el.style.opacity = Math.random();
            document.getElementById('decorations').appendChild(el);
        }
        for(let i=0; i<15; i++) createDecor();

        // Forgiveness Logic
        function moveNo() {
            const btn = document.getElementById('no-btn');
            btn.style.position = 'fixed';
            btn.style.left = Math.random() * (window.innerWidth - 100) + 'px';
            btn.style.top = Math.random() * (window.innerHeight - 50) + 'px';
        }

        function celebrate() {
            document.getElementById('final-msg').classList.remove('hidden');
            document.getElementById('no-btn').style.display = 'none';
            // Burst of decorations
            for(let i=0; i<30; i++) {
                setTimeout(createDecor, i * 100);
            }
        }
    </script>
</body>
</html>
