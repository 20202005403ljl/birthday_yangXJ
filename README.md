<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>化州二中高一官方网站</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=ZCOOL+KuaiLe&family=Ma+Shan+Zheng&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            -webkit-tap-highlight-color: transparent;
        }
        
        body {
            font-family: 'Ma Shan Zheng', cursive;
            overflow-x: hidden;
            background: linear-gradient(135deg, #e0f7fa 0%, #b2ebf2 50%, #80deea 100%);
            background-attachment: fixed;
            color: #333;
            min-height: 100vh;
            touch-action: manipulation;
        }
        
        #particles-js {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            z-index: 0;
            opacity: 0.7;
        }
        
        .container {
            position: relative;
            z-index: 1;
            max-width: 100%;
            margin: 0 auto;
            padding: 1rem;
            text-align: center;
        }
        
        header {
            margin-bottom: 1.5rem;
            padding-top: 1rem;
        }
        
        h1 {
            font-size: 2.2rem;
            margin-bottom: 0.8rem;
            color: #00796b;
            text-shadow: 0 1px 3px rgba(255, 255, 255, 0.8);
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #00695c;
            opacity: 0;
            transform: translateY(15px);
            animation: fadeInUp 0.8s ease forwards 0.5s;
        }
        
        .card-container {
            perspective: 1000px;
            display: flex;
            justify-content: center;
            margin: 1.5rem 0;
            transform-style: preserve-3d;
        }
        
        .card {
            width: 90%;
            max-width: 320px;
            height: 420px;
            position: relative;
            transform-style: preserve-3d;
            transition: transform 0.6s ease;
            cursor: pointer;
        }
        
        .card.flipped {
            transform: rotateY(180deg);
        }
        
        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 15px;
            padding: 1.2rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.1);
            overflow: hidden;
            background: rgba(255, 255, 255, 0.95);
        }
        
        .card-front {
            z-index: 2;
        }
        
        .card-back {
            transform: rotateY(180deg);
            overflow-y: auto;
            -webkit-overflow-scrolling: touch;
        }
        
        .card-back-content {
            height: 100%;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 10px;
        }
        
        .avatar {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid #4dd0e1;
            margin-bottom: 1.2rem;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .wishes {
            margin-top: 1.2rem;
            font-size: 1rem;
            line-height: 1.6;
            color: #333;
            opacity: 0;
            transform: translateY(15px);
            animation: fadeInUp 0.8s ease forwards 1s;
            text-align: center;
            width: 100%;
            padding: 0 10px;
        }
        
        .typing-text {
            font-family: 'ZCOOL KuaiLe', cursive;
            font-size: 1.4rem;
            color: #00796b;
            border-right: 2px solid #4dd0e1;
            white-space: nowrap;
            overflow: hidden;
            margin: 0.8rem auto;
            width: fit-content;
            animation: typing 3s steps(30, end), blink-caret 0.7s step-end infinite;
            text-align: center;
        }
        
        @keyframes typing {
            from { width: 0 }
            to { width: 100% }
        }
        
        @keyframes blink-caret {
            from, to { border-color: transparent }
            50% { border-color: #4dd0e1 }
        }
        
        @keyframes fadeInUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        footer {
            margin-top: 2rem;
            padding: 1rem;
            font-size: 0.8rem;
            color: #00695c;
            opacity: 0.8;
        }
        
        .name-input {
            margin: 1.5rem auto;
            width: 90%;
            max-width: 400px;
            background: rgba(255, 255, 255, 0.9);
            padding: 1.5rem;
            border-radius: 15px;
            box-shadow: 0 3px 10px rgba(0, 0, 0, 0.1);
        }
        
        .name-input h2 {
            color: #00796b;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }
        
        .name-input input {
            width: 100%;
            padding: 12px 15px;
            margin: 8px 0;
            border: 1px solid #b2ebf2;
            border-radius: 25px;
            background: rgba(255, 255, 255, 0.95);
            color: #333;
            font-size: 1rem;
            outline: none;
            transition: all 0.3s;
        }
        
        .name-input input:focus {
            border-color: #4dd0e1;
            box-shadow: 0 0 8px rgba(77, 208, 225, 0.3);
        }
        
        .name-input button {
            background: #4dd0e1;
            color: white;
            border: none;
            padding: 12px 25px;
            margin-top: 15px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 1rem;
            transition: all 0.3s ease;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
            width: 100%;
            max-width: 200px;
        }
        
        .name-input button:active {
            background: #26c6da;
            transform: translateY(1px);
        }
        
        .error-message {
            color: #e53935;
            font-size: 1rem;
            margin-top: 1rem;
            display: none;
        }
        
        /* 倒计时样式 */
        .countdown {
            margin: 2rem auto;
            font-size: 1.5rem;
            color: #00796b;
            text-align: center;
        }
        
        .countdown-number {
            display: inline-block;
            min-width: 2em;
            font-weight: bold;
        }
        
        /* 测试按钮样式 */
        .test-button {
            margin: 1rem auto;
            background: #00796b;
            color: white;
            border: none;
            padding: 10px 20px;
            border-radius: 25px;
            cursor: pointer;
            font-size: 0.9rem;
            transition: all 0.3s;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.1);
        }
        
        .test-button:active {
            transform: translateY(1px);
            background: #00695c;
        }
        
        /* 樱花特效 */
        .sakura {
            position: fixed;
            top: -10%;
            z-index: 999;
            color: #ffb6c1;
            user-select: none;
            pointer-events: none;
            opacity: 0;
            animation: fall linear forwards, sway ease-in-out infinite;
            text-shadow: 0 0 5px rgba(255, 182, 193, 0.5);
            filter: drop-shadow(0 0 3px rgba(255, 182, 193, 0.3));
        }
        
        @keyframes fall {
            0% {
                transform: translateY(-10%) translateX(var(--start-x)) rotate(0deg);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 0.8;
            }
            100% {
                transform: translateY(110vh) translateX(calc(var(--start-x) + var(--sway-distance))) rotate(360deg);
                opacity: 0;
            }
        }
        
        @keyframes sway {
            0%, 100% {
                transform: translateX(0);
            }
            50% {
                transform: translateX(calc(var(--sway-distance) / 2));
            }
        }
    </style>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
</head>
<body>
    <div id="particles-js"></div>
    
    <div class="container">
        <!-- 倒计时显示 -->
        <div id="countdownContainer">
            <div class="countdown">
                <h2>时间沙漏</h2>
                <div>
                    <span id="countdown-days" class="countdown-number">0</span>天
                    <span id="countdown-hours" class="countdown-number">0</span>小时
                    <span id="countdown-minutes" class="countdown-number">0</span>分钟
                </div>
            </div>
            <!-- 测试按钮 -->
            <button class="test-button" onclick="enableTestMode()">测试入口</button>
        </div>
        
        <!-- 名字输入框 - 初始隐藏 -->
        <div class="name-input" id="nameInputContainer" style="display: none;">
            <h2>请输入你的名字</h2>
            <input type="text" id="nameInput" placeholder="请输入你的全名">
            <button onclick="checkName()">查看祝福</button>
            <div class="error-message" id="errorMessage">抱歉，找错人辽~</div>
        </div>
        
        <!-- 祝福内容 - 初始隐藏 -->
        <div id="blessingContainer" style="display: none;">
            <header>
                <h1><span id="friendName">杨晓静</span>同学</h1>
                <p class="subtitle">生日快乐~</p>
            </header>
            
            <div class="card-container">
                <div class="card" id="birthdayCard">
                    <div class="card-front">
                        <img src="yang.jpg" alt="生日照片" class="avatar">
                        <h2 id="dynamicName">杨晓静</h2>
                        <p>CLICK</p>
                    </div>
                    <div class="card-back">
                        <div class="card-back-content">
                            <div class="typing-text" id="typingText">破壳日快乐！杨晓静童鞋！</div>
                            <p style="color: #555; text-align: center; margin-top: 0.8rem; font-size: 0.95rem;">形式主义的话我就不说了</p>
                            <p style="color: #555; text-align: center; margin-top: 0.8rem; font-size: 0.95rem;">想提醒一下上课如果看不见的话</p>
                            <p style="color: #555; text-align: center; margin-top: 0.8rem; font-size: 0.95rem;">尽量戴上眼镜看黑板才行</p>
                            <p style="color: #555; text-align: center; margin-top: 0.8rem; font-size: 0.95rem;">不然度数还会继续升高的</p>
                            <p style="color: #555; text-align: center; margin-top: 0.8rem; font-size: 0.95rem;">by 物理老师</p></div>
                    </div>
                </div>
            </div>
            
            <div class="wishes">
                <p>第一次见有人“明示”</p>
                <p>。k</p>
            </div>
            
            <footer>
                <p>化州二中高一22-23班唯一官方网站（！</p>
            </footer>
        </div>
    </div>
    
    <script src="https://cdn.jsdelivr.net/particles.js/2.0.0/particles.min.js"></script>
    <script>
        // 目标日期 - 2025年3月30日
        const targetDate = new Date('2025-03-30T00:00:00');
        let isBirthday = false;
        let isAnimating = false;
        let testMode = false;
        
        // 启用测试模式
        function enableTestMode() {
            testMode = true;
            document.getElementById('countdownContainer').style.display = 'none';
            document.getElementById('nameInputContainer').style.display = 'block';
        }
        
        // 检查当前日期
        function checkDate() {
            const now = new Date();
            isBirthday = now >= targetDate || testMode;
            
            if (isBirthday && !testMode) {
                document.getElementById('countdownContainer').style.display = 'none';
                document.getElementById('nameInputContainer').style.display = 'block';
            }
        }
        
        // 开始倒计时
        function startCountdown() {
            function updateCountdown() {
                const now = new Date();
                const diff = targetDate - now;
                
                if (diff <= 0) {
                    clearInterval(timer);
                    checkDate();
                    return;
                }
                
                const days = Math.floor(diff / (1000 * 60 * 60 * 24));
                const hours = Math.floor((diff % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((diff % (1000 * 60 * 60)) / (1000 * 60));
                
                document.getElementById('countdown-days').textContent = days;
                document.getElementById('countdown-hours').textContent = hours;
                document.getElementById('countdown-minutes').textContent = minutes;
            }
            
            updateCountdown();
            const timer = setInterval(updateCountdown, 1000);
        }
        
        // 获取URL参数
        function getQueryParam(name) {
            const urlParams = new URLSearchParams(window.location.search);
            return urlParams.get(name);
        }
        
        // 检查名字
        function checkName() {
            const name = document.getElementById('nameInput').value.trim();
            if (name === "杨晓静" || testMode) {
                window.history.pushState({}, '', `?name=${encodeURIComponent(name)}`);
                document.getElementById('nameInputContainer').style.display = 'none';
                document.getElementById('blessingContainer').style.display = 'block';
                initEffects();
                createSakura();
                setTimeout(() => window.scrollTo(0, 1), 100);
            } else {
                document.getElementById('errorMessage').style.display = 'block';
            }
        }
        
        // 初始化页面
        function initPage() {
            checkDate();
            
            if (!isBirthday) {
                startCountdown();
            }
            
            const name = getQueryParam('name');
            if (isBirthday && name === "杨晓静") {
                document.getElementById('nameInputContainer').style.display = 'none';
                document.getElementById('blessingContainer').style.display = 'block';
                initEffects();
                createSakura();
                setTimeout(() => window.scrollTo(0, 1), 100);
            }
            
            document.addEventListener('touchstart', function(){}, {passive: true});
            document.addEventListener('touchmove', function(e) {
                e.preventDefault();
            }, {passive: false});
        }
        
        // 卡片点击处理
        function handleCardClick() {
            if (isAnimating) return;
            isAnimating = true;
            this.classList.toggle('flipped');
            setTimeout(() => isAnimating = false, 600);
        }
        
        // 初始化特效
        function initEffects() {
            particlesJS("particles-js", {
                "particles": {
                    "number": { "value": 40 },
                    "color": { "value": "#4dd0e1" },
                    "shape": { "type": "circle" },
                    "opacity": { "value": 0.5 },
                    "size": { "value": 2.5 },
                    "line_linked": {
                        "enable": true,
                        "distance": 120,
                        "color": "#80deea",
                        "opacity": 0.3,
                        "width": 1
                    },
                    "move": {
                        "enable": true,
                        "speed": 3,
                        "random": true
                    }
                },
                "interactivity": {
                    "events": {
                        "onhover": { "enable": false },
                        "onclick": { "enable": false }
                    }
                }
            });
            
            const card = document.getElementById('birthdayCard');
            card.addEventListener('click', handleCardClick);
            card.addEventListener('touchstart', handleCardClick);
            
            setTimeout(() => {
                document.querySelector('.typing-text').style.animation = 
                    'typing 3s steps(30, end), blink-caret 0.7s step-end infinite';
            }, 1200);
        }

        // 页面加载时初始化
        document.addEventListener('DOMContentLoaded', initPage);
        document.addEventListener('gesturestart', e => e.preventDefault());
    </script>
</body>
</html>
