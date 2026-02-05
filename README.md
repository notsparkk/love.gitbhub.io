<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>For My Cutie Manya</title>
    <link href="https://fonts.googleapis.com/css2?family=Great+Vibes&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        /* --- General Settings --- */
        body {
            margin: 0;
            padding: 0;
            background-color: #ffc0cb; /* Pink Background */
            font-family: 'Poppins', sans-serif;
            overflow: hidden; /* Prevents scrollbars on the main body */
            height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            color: #5a2d3b;
        }

        /* --- Falling Hearts Background --- */
        .heart-container {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
            overflow: hidden;
        }

        .heart {
            position: absolute;
            top: -10vh;
            color: #ff4d6d;
            font-size: 1.5rem;
            animation: fall linear infinite;
        }

        @keyframes fall {
            0% { transform: translateY(0) rotate(0deg); opacity: 1; }
            100% { transform: translateY(110vh) rotate(360deg); opacity: 0; }
        }

        /* --- Slide Container --- */
        .slide-container {
            width: 90%;
            max-width: 600px;
            height: 80vh;
            background: rgba(255, 255, 255, 0.85);
            border-radius: 30px;
            box-shadow: 0 10px 40px rgba(163, 21, 61, 0.3);
            position: relative;
            z-index: 10;
            padding: 20px;
            overflow-y: auto; /* Allows scrolling for long text */
            text-align: center;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        /* --- Hide Scrollbar for clean look --- */
        .slide-container::-webkit-scrollbar {
            width: 0px;
            background: transparent;
        }

        /* --- Slides Logic --- */
        .slide {
            display: none;
            width: 100%;
            animation-duration: 1s;
            animation-fill-mode: both;
        }

        .active {
            display: block;
        }

        /* --- Transitions (Different for slides) --- */
        .fade-in { animation-name: fadeIn; }
        .slide-in { animation-name: slideInRight; }
        .zoom-in { animation-name: zoomIn; }
        .rotate-in { animation-name: rotateIn; }

        @keyframes fadeIn { from { opacity: 0; } to { opacity: 1; } }
        @keyframes slideInRight { from { transform: translateX(100%); opacity: 0; } to { transform: translateX(0); opacity: 1; } }
        @keyframes zoomIn { from { transform: scale(0.5); opacity: 0; } to { transform: scale(1); opacity: 1; } }
        @keyframes rotateIn { from { transform: rotate(-10deg); opacity: 0; } to { transform: rotate(0); opacity: 1; } }

        /* --- Typography --- */
        h1 {
            font-family: 'Great Vibes', cursive; /* Fancy Auberge-like font */
            font-size: 2.5rem;
            color: #d63384;
            margin-bottom: 10px;
        }

        .auberge-text {
            font-family: 'Great Vibes', cursive;
            font-size: 1.8rem;
            line-height: 1.4;
            color: #d63384;
        }

        p {
            font-size: 1rem;
            line-height: 1.6;
            margin-bottom: 20px;
            white-space: pre-wrap; /* Preserves your paragraphs */
        }

        /* --- Images --- */
        .photo-grid {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 10px;
            margin-bottom: 20px;
        }

        img {
            max-width: 100%;
            border-radius: 10px;
            border: 4px solid white;
            box-shadow: 0 4px 10px rgba(0,0,0,0.1);
        }

        .shimla-img {
            width: 120px;
            height: 120px;
            object-fit: cover;
        }

        .caption-card {
            background: white;
            padding: 10px;
            border-radius: 10px;
            margin-bottom: 15px;
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
        }

        /* --- Buttons --- */
        .nav-buttons {
            margin-top: auto;
            display: flex;
            justify-content: space-between;
            width: 100%;
            padding-top: 20px;
        }

        button {
            background-color: #ff4d6d;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 20px;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.3s;
            font-family: 'Poppins', sans-serif;
        }

        button:hover {
            background-color: #d6002a;
            transform: scale(1.1);
        }

        /* --- Start Overlay --- */
        #start-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #ffc0cb;
            z-index: 100;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
    </style>
</head>
<body>

    <audio id="bg-music" loop>
        <source src="perfect.mp3" type="audio/mpeg">
    </audio>

    <div class="heart-container" id="hearts"></div>

    <div id="start-overlay">
        <h1>For Manya ❤️</h1>
        <p>Click the button below to start...</p>
        <button onclick="startExperience()">Start Love Story</button>
    </div>

    <div class="slide-container" id="main-container" style="display:none;">
        
        <div class="slide fade-in active">
            <h1>Hey cutieeee 😚</h1>
            <p>This is your man (one and only 🔪🔪🔪🔪🔪🔪).</p>
            <p>I made this thing specially for youuuuuu.</p>
            <p>I hope you like it..........</p>
            <br>
            <div style="font-size: 3rem;">🎁</div>
        </div>

        <div class="slide zoom-in">
            <div class="auberge-text">
                So first of alll, I wanna thank you for being in my life cutieeeee. Aap ke aane pr na bohot si cheezein achiii huiii. I got a good life, got happier and started living like I still had something in me. I just felt all is over for me. But you came to my life and brightened it. <br><br>
                I wanna thank you for all the things youu did for meee Thank you cutieeee 😘😘😘😘. I just want to thank you for all the things you did for me. So lets talk about the last 3 years.
            </div>
        </div>

        <div class="slide slide-in">
            <h1>December 2023</h1>
            <p>So the tale started on 1st December, 2023. Hayyee, That day was so good for the both of us. We started off as a fresh couple things were soo good for the first 5 days.</p>
            <p>Then uk disaster struck and all the things happened. My hand broke 😢 and then all those things happened. But uk you stayed with me and that matters the most to me. I was really happy.</p>
            <p>Fir humari kuchh time tak baat nhi ho paayi and later that Aarush guy also intervened but it was fine. We made it through the first month.</p>
        </div>

        <div class="slide rotate-in">
            <h1>2024: The 10th classss</h1>
            <p style="text-align: left; font-size: 0.9rem;">
                This year started and we didn't talk much iin the first month cuz of uk all the things that had happened. Fir we met on 23rd Jan and yrr, it was so so so good yrr. And jo tumne aakr mere arm ko pakda tha. Hayyee yrr mai itna khush tha uss din. It made my whole year yrr.<br><br>
                Fir sab kuchh normally chlta rha until 18th Feb, Mera haath tut gya 😢. And I coudn't see you for another month. It was too bad for me. Mtlb I used to wait for you everyday, and then finally we met again on 15th March And I was so relieved yrr. It felt like peace again. Fir har din achha chlta tha. Me seeing you, talking to you, making eye contacts sab cheezein bohot achhi thi.<br><br>
                Then came a really good moment. <strong>You kissed me on 25th Aprill !!!!!!!</strong> yrr vo itna pyaaraa tha na Like I always loveed it so muchhhh. But after that came something really bad. You started talking to Malik 😠😠. And tab mujhe itni chidhh hoti thi na I can't even explain it, but I didn't say anything..........
            </p>
        </div>

        <div class="slide zoom-in">
            <h1 style="font-size: 3rem;">The Shimla trip !!!!</h1>
            <div class="photo-grid">
                <img src="shimla1.jpg" class="shimla-img" onerror="this.src='https://via.placeholder.com/150/ffb6c1/fff?text=Shimla1'">
                <img src="shimla2.jpg" class="shimla-img" onerror="this.src='https://via.placeholder.com/150/ffb6c1/fff?text=Shimla2'">
                <img src="shimla3.jpg" class="shimla-img" onerror="this.src='https://via.placeholder.com/150/ffb6c1/fff?text=Shimla3'">
            </div>
            <p style="text-align: left; font-size: 0.9rem;">
                This was too lovely yrr. This was our first trip together and it was lovely. Pehla din bohot achha tha. We reached there. Had some fun. Bohot achha lga. Only downside was that you were still talking to that Malik guy 😒😒.<br><br>
                Anyways Then came the second day, and hayye yrr, you were so sexyyyy. Mast lag rhi thi. We went to the mandir that day, and uk, on the way back you fell twice 😂😂. I picked you up both of the times. Mera chhotta sa bachha ho aap.<br><br>
                Fir came the third day. And that was bilkul peak. Mtlb yrr we were going together while you were holding my arm. Hayee yr, I would do anything to get that feeling again. And it was soo good. At last yrr, you even cried cuz of we were gonna leave. But dw, we'll do another trip sooon.........
            </p>
        </div>

        <div class="slide slide-in">
            <h1>And fir life chlti rhi...</h1>
            <p style="text-align: left; font-size: 0.85rem;">
                We met everyday, and everything went good, especially that cultural part, it was soo soo soo good yrr. I got to see you everyday, and you always looked so hot to me. Mtlb koi ldki itni achii ho vi kese skti hai I coudn't even imagine. We saw each other everyday, Aapko dance krte dekh mai pighal jaata tha. Itni sundar mahila sirf mujhe mile aur kisi ko na mile. You're so only mineeeeeee😘😘😘😘.<br><br>
                Fir ese hi hmara year khtm hua and 2025 started. And we had our first lip kiss on 7th Jan. And it was soo fucking good yrr. Mtlb the first kiss was so good that it still lives as the best memories in my heart. Itni achhi thi voh. Fir baad mei papers aa gye and all. We coudn't talk much but stilll we made it through.<br><br>
                Fir hume firse mile 18th Feb ko and 7th March ko and humne jo sab vi kiya, Tbh it was worth it. My love language is physical touch and I could express my feelings to you. So it was good.<br><br>
                Uske baad many things happened... I would just say that It's all my fault, and as a man I coudn't control my problems. I assure you that esa aage chl kr kbhi nhi hoga. Have faith in me. I'll do everything to make upto you. Fir humne October mei firse baat shuru ki and we did a lot of wrong things. For them too I can assure you ki esa kbhi nhi hoga till our marriage.<br><br>
                Dw, I'll always be there for you. So aap kbhi mat sochna ki mai kbhi aapko chhod kr jaunga. Just know one thing, If I ever say it, It's not who I am, Its someone else. And you have to bring me back. Okieee ???? Bss abhi tak to itna hi hua hai. Baaki hum dekhte hai aage kya hota hai. Jo bhi ho, hum saath rhenge. Hmesha ke liye. We'll have kids and grow old, so take care of yourself, achhe se khana khaya kro and apni dhyan rkha krooooo Okaa 😚.
            </p>
        </div>

        <div class="slide fade-in">
            <h1>My Beautiful Manya</h1>
            
            <div class="caption-card">
                <img src="small.jpg" alt="Childhood" style="height: 150px;" onerror="this.src='https://via.placeholder.com/200/ffb6c1/fff?text=Cutie+Small'">
                <p>This is my cutiee when she was smalllllll 😚😚😚😚😚 !!!!!</p>
            </div>

            <div class="caption-card">
                <img src="class5.jpg" alt="Class 5" style="height: 150px;" onerror="this.src='https://via.placeholder.com/200/ffb6c1/fff?text=Class+5'">
                <p>There is my cute sa bachha in 5th 🥰🥰🥰🥰</p>
            </div>

            <div class="caption-card">
                <img src="beautiful.jpg" alt="Beautiful" style="height: 150px;" onerror="this.src='https://via.placeholder.com/200/ffb6c1/fff?text=So+Beautiful'">
                <p>Oh my cutieee is so so so beeautiful 😍😍😍😍😍😍😍😍😍</p>
            </div>

            <div class="caption-card">
                <img src="diwali.jpg" alt="Diwali" style="height: 150px;" onerror="this.src='https://via.placeholder.com/200/ffb6c1/fff?text=Diwali'">
                <p>My lovely sa bachha on Diwali.. So gorgeoussss 🥵🥵</p>
            </div>
        </div>

        <div class="slide zoom-in">
            <h1>Promises...</h1>
            <p style="text-align: left; font-size: 0.9rem;">
                Haan to mere cutu, at last I just wanna say ki thank you for being with me through this whole timee. You were so good to me and I want you to be the same withme in the future. Aapke jese mujhe kbhi nhi mil skta, aur agr mere life mei koi ldki aane ki try krti hai, I'll throw her away in the ocean. Aapke alawa mere liye koi aur ldki (except my mum) doesn't matter.<br><br>
                And that's all I wanna say. I want ki hum bade ho ek saath, Hmare do bachhe ho, We life a happy life. And we see each other grow together. This is my dream and I hope so yours too. I just want ki aap dusre ldko se dur rho, and listen to me. This is my only wish for you. Bss itna krdo aap, I'll stay with you for eternity.<br><br>
                Chlo I won't waste much of your timee. Aap maze kro okieeee. Bie bie cutieeeee. I love ya bohot bohot bohot saara 😘😘😘😘. Stay happy and just do the two things I said you to doo. Plzzz 🥺🥺🥺🥺.
            </p>
            <h2 class="auberge-text">Love,<br>Rajbir Singh <br><span style="font-size: 0.7em;">(Your one and only man)</span></h2>
        </div>

        <div class="nav-buttons">
            <button onclick="changeSlide(-1)">Back 🔙</button>
            <button onclick="changeSlide(1)">Next ❤️</button>
        </div>
    </div>

    <script>
        let currentSlide = 0;
        const slides = document.querySelectorAll('.slide');

        // Start function to handle Audio + Display
        function startExperience() {
            document.getElementById('start-overlay').style.display = 'none';
            document.getElementById('main-container').style.display = 'flex';
            
            const music = document.getElementById('bg-music');
            music.volume = 0.5; // Set volume to 50%
            music.play().catch(error => {
                console.log("Audio play failed (browser restriction). Interaction needed.");
            });
            
            // Generate Hearts
            createHearts();
        }

        function changeSlide(n) {
            // Hide current slide
            slides[currentSlide].classList.remove('active');
            
            // Calculate next slide
            currentSlide += n;

            // Loop logic (optional, currently stops at end)
            if (currentSlide >= slides.length) {
                currentSlide = slides.length - 1; 
                alert("That's all for now cutieeee! I love you! 😘");
            }
            if (currentSlide < 0) {
                currentSlide = 0;
            }

            // Show new slide
            slides[currentSlide].classList.add('active');
            
            // Scroll to top of the container (for long text slides)
            document.querySelector('.slide-container').scrollTop = 0;
        }

        // JS to create overflowing hearts
        function createHearts() {
            const container = document.getElementById('hearts');
            setInterval(() => {
                const heart = document.createElement('div');
                heart.classList.add('heart');
                heart.innerHTML = '❤️';
                heart.style.left = Math.random() * 100 + 'vw';
                heart.style.animationDuration = Math.random() * 2 + 3 + 's';
                heart.style.fontSize = Math.random() * 20 + 20 + 'px';
                
                container.appendChild(heart);

                // Remove heart after animation to keep browser smooth
                setTimeout(() => {
                    heart.remove();
                }, 5000);
            }, 100); // Create a heart every 100ms
        }
    </script>
</body>
</html>
