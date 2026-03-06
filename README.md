# -Khabir-
<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>HBD Mas Khabir</title>
    <style>
        :root {
            --deep-blue: #1a2a6c;
            --soft-blue: #b21f1f; /* transition accent */
            --sky-blue: #4a90e2;
            --white: #ffffff;
        }

        body, html {
            margin: 0;
            padding: 0;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: radial-gradient(circle, #0f2027, #203a43, #2c5364);
            color: var(--white);
            height: 100vh;
            overflow: hidden;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        /* Watermark */
        .watermark {
            position: fixed;
            bottom: 10px;
            right: 10px;
            opacity: 0.5;
            font-size: 12px;
            z-index: 100;
        }

        /* Background Elements */
        .floating-heart {
            position: absolute;
            color: rgba(74, 144, 226, 0.6);
            pointer-events: none;
            animation: move Up 4s linear infinite;
        }

        @keyframes moveUp {
            0% { transform: translateY(100vh) scale(0); opacity: 1; }
            100% { transform: translateY(-10vh) scale(1.5); opacity: 0; }
        }

        /* Container */
        .container {
            text-align: center;
            z-index: 10;
            width: 85%;
            max-width: 500px;
            padding: 20px;
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

        .cover h1 { font-size: 1.5rem; margin-bottom: 10px; }
        .date { font-size: 1.2rem; color: var(--sky-blue); margin-bottom: 20px; }
        .time { font-family: monospace; font-size: 1.1rem; margin-bottom: 30px; }

        /* Button Open */
        .open-btn {
            background: var(--sky-blue);
            color: white;
            border: none;
            padding: 15px 30px;
            border-radius: 50px;
            font-size: 1rem;
            cursor: pointer;
            transition: 0.3s;
            box-shadow: 0 5px 15px rgba(74, 144, 226, 0.4);
        }

        .open-btn:hover { transform: scale(1.1); background: #357abd; }

        /* Message Overlay */
        #message-overlay {
            display: none;
            position: fixed;
            top: 0; left: 0; width: 100%; height: 100%;
            background: rgba(0, 10, 30, 0.95);
            z-index: 100;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            padding: 20px;
            box-sizing: border-box;
            overflow-y: auto;
        }

        .typing-text {
            font-size: 1rem;
            line-height: 1.8;
            max-width: 600px;
            white-space: pre-wrap;
            text-align: left;
            color: #e0e0e0;
        }

        .flower-icon {
            color: var(--sky-blue);
            font-size: 2rem;
            margin-bottom: 20px;
        }

        .hidden { display: none; }
    </style>
</head>
<body>

    <div class="watermark">Created by Salwa 🤍</div>

    <div class="container" id="main-card">
        <div class="cover">
            <div style="font-size: 40px; margin-bottom: 10px;">🎂</div>
            <div id="greeting" style="margin-bottom: 15px; line-height: 1.5;">
                Hello Mas Khabir<br>
                你的专属信息中心已在线 🖤<br>
                请准备接收 Salwa 的爱心数据包 💌
            </div>
            <div class="date">2026年3月7日, 星期六</div>
            <div class="time" id="clock">00:00:00</div>
            <button class="open-btn" onclick="openMessage()">💙 点我</button>
        </div>
    </div>

    <div id="message-overlay">
        <div class="flower-icon">🦋❄️💠</div>
        <div class="typing-text" id="typewriter"></div>
        <button class="open-btn" id="close-btn" style="margin-top: 30px; display: none;" onclick="location.reload()">Back ↩</button>
    </div>

    <script>
        // Update Time
        function updateClock() {
            const now = new Date();
            document.getElementById('clock').innerText = now.toLocaleTimeString();
        }
        setInterval(updateClock, 1000);
        updateClock();

        // Heart Rain Effect
        function createHeart() {
            const heart = document.createElement('div');
            heart.classList.add('floating-heart');
            heart.innerHTML = Math.random() > 0.5 ? '💙' : '❄️';
            heart.style.left = Math.random() * 100 + 'vw';
            heart.style.animationDuration = (Math.random() * 2 + 3) + 's';
            document.body.appendChild(heart);
            setTimeout(() => heart.remove(), 5000);
        }
        setInterval(createHeart, 400);

        // Typewriter Effect
        const message = `亲爱的 Mas Khabir：

今天是你的生日，我想写一封小小的信给你。

谢谢你一直以来那么努力地生活，也那么认真地承担自己的责任。
在我心里，你是一个让我觉得很安心、很可靠的人。

有时候我在想，世界上有这么多人，
但能遇见你，对我来说真的很特别。

希望未来的日子里，
不管你走到哪里，做什么事情，
都能顺顺利利，平平安安，也越来越幸福。

如果有一天你觉得累了，
请记得，还有一个人一直在为你加油，支持你。

最后，
生日快乐，Mas Khabir。
希望你的每一年，都比上一年更幸福。

你的baby, Salwa🤍`;

        function openMessage() {
            document.getElementById('message-overlay').style.display = 'flex';
            let i = 0;
            const speed = 50; // typing speed in ms
            const target = document.getElementById('typewriter');
            
            function type() {
                if (i < message.length) {
                    target.innerHTML += message.charAt(i);
                    i++;
                    setTimeout(type, speed);
                } else {
                    document.getElementById('close-btn').style.display = 'block';
                }
            }
            type();
        }
    </script>
</body>
</html>
