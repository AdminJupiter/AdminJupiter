<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>3D GitHub Profile</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #0f0c29, #302b63, #24243e);
            color: #fff;
            min-height: 100vh;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 20px;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            width: 100%;
            padding: 20px;
        }
        
        .profile-card {
            background: rgba(255, 255, 255, 0.06);
            border-radius: 20px;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            padding: 40px;
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.3);
            text-align: center;
            margin-bottom: 40px;
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) rotateX(0) rotateY(0); }
            33% { transform: translateY(-10px) rotateX(2deg) rotateY(2deg); }
            66% { transform: translateY(10px) rotateX(-2deg) rotateY(-2deg); }
        }
        
        .profile-img {
            width: 150px;
            height: 150px;
            border-radius: 50%;
            object-fit: cover;
            border: 3px solid #7e3fce;
            box-shadow: 0 0 25px #7e3fce;
            margin: 0 auto 20px;
            transform: translateZ(30px);
            transition: transform 0.5s;
        }
        
        .profile-img:hover {
            transform: translateZ(50px) scale(1.05);
        }
        
        h1 {
            font-size: 2.8rem;
            margin-bottom: 10px;
            background: linear-gradient(45deg, #ff6b6b, #7e3fce, #4ecdc4);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            transform: translateZ(20px);
        }
        
        h2 {
            font-size: 1.5rem;
            margin-bottom: 25px;
            color: #d8d8d8;
            transform: translateZ(15px);
        }
        
        .typing-text {
            font-size: 1.3rem;
            margin-bottom: 30px;
            min-height: 40px;
            color: #a3a3ff;
            transform: translateZ(10px);
        }
        
        .stats-container {
            display: flex;
            justify-content: space-around;
            flex-wrap: wrap;
            gap: 20px;
            margin: 30px 0;
        }
        
        .stat-box {
            background: rgba(126, 63, 206, 0.2);
            border-radius: 15px;
            padding: 20px;
            min-width: 200px;
            transform-style: preserve-3d;
            transform: translateZ(15px);
            transition: transform 0.3s;
        }
        
        .stat-box:hover {
            transform: translateZ(25px) scale(1.05);
        }
        
        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            color: #7e3fce;
            margin-bottom: 5px;
        }
        
        .stat-label {
            font-size: 1rem;
            color: #b0b0b0;
        }
        
        .tech-stack {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 15px;
            margin: 40px 0;
        }
        
        .tech-icon {
            font-size: 3rem;
            color: #7e3fce;
            transition: all 0.3s;
            transform: translateZ(10px);
        }
        
        .tech-icon:hover {
            color: #ff6b6b;
            transform: translateZ(30px) scale(1.2);
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 30px;
        }
        
        .social-btn {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.5rem;
            text-decoration: none;
            transition: all 0.3s;
            transform: translateZ(10px);
        }
        
        .social-btn:hover {
            transform: translateZ(30px) scale(1.1) rotate(5deg);
        }
        
        .youtube { background: #FF0000; }
        .instagram { background: linear-gradient(45deg, #f09433, #e6683c, #dc2743, #cc2366, #bc1888); }
        .twitch { background: #9146FF; }
        .discord { background: #5865F2; }
        .gmail { background: #EA4335; }
        .linkedin { background: #0A66C2; }
        
        .snake-animation {
            width: 100%;
            height: 100px;
            margin: 40px 0;
            position: relative;
            overflow: hidden;
            border-radius: 10px;
        }
        
        .snake-path {
            position: absolute;
            width: 100%;
            height: 100%;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 10px;
        }
        
        .snake {
            position: absolute;
            width: 40px;
            height: 40px;
            background: linear-gradient(45deg, #ff6b6b, #7e3fce);
            border-radius: 50%;
            filter: blur(5px);
            animation: snakeMove 8s linear infinite;
        }
        
        @keyframes snakeMove {
            0% { left: -40px; top: 10px; }
            25% { left: calc(100% - 40px); top: 10px; }
            50% { left: calc(100% - 40px); top: calc(100% - 50px); }
            75% { left: -40px; top: calc(100% - 50px); }
            100% { left: -40px; top: 10px; }
        }
        
        .pulse {
            display: block;
            width: 20px;
            height: 20px;
            background: #7e3fce;
            border-radius: 50%;
            margin: 0 auto;
            box-shadow: 0 0 0 rgba(126, 63, 206, 0.4);
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(126, 63, 206, 0.7); }
            70% { transform: scale(1); box-shadow: 0 0 0 15px rgba(126, 63, 206, 0); }
            100% { transform: scale(0.95); box-shadow: 0 0 0 0 rgba(126, 63, 206, 0); }
        }
        
        @media (max-width: 768px) {
            .profile-card {
                padding: 25px;
            }
            
            h1 {
                font-size: 2.2rem;
            }
            
            .stats-container {
                flex-direction: column;
                align-items: center;
            }
            
            .stat-box {
                width: 100%;
                max-width: 300px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <div class="profile-card">
            <img src="https://images.unsplash.com/photo-1535713875002-d1d0cf377fde?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=200&q=80" alt="Profile Image" class="profile-img">
            
            <h1>John Anderson</h1>
            <h2>Full Stack Developer from San Francisco</h2>
            
            <div class="typing-text" id="typing-text">
                <span>Creating digital experiences that matter</span>
            </div>
            
            <div class="pulse"></div>
            
            <div class="stats-container">
                <div class="stat-box">
                    <div class="stat-number">152</div>
                    <div class="stat-label">Repositories</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">3.2k</div>
                    <div class="stat-label">Commits</div>
                </div>
                <div class="stat-box">
                    <div class="stat-number">48</div>
                    <div class="stat-label">Projects</div>
                </div>
            </div>
            
            <div class="tech-stack">
                <i class="tech-icon fab fa-js"></i>
                <i class="tech-icon fab fa-react"></i>
                <i class="tech-icon fab fa-node-js"></i>
                <i class="tech-icon fab fa-python"></i>
                <i class="tech-icon fab fa-html5"></i>
                <i class="tech-icon fab fa-css3-alt"></i>
            </div>
            
            <div class="social-links">
                <a href="#" class="social-btn youtube"><i class="fab fa-youtube"></i></a>
                <a href="#" class="social-btn instagram"><i class="fab fa-instagram"></i></a>
                <a href="#" class="social-btn twitch"><i class="fab fa-twitch"></i></a>
                <a href="#" class="social-btn discord"><i class="fab fa-discord"></i></a>
                <a href="#" class="social-btn gmail"><i class="far fa-envelope"></i></a>
                <a href="#" class="social-btn linkedin"><i class="fab fa-linkedin-in"></i></a>
            </div>
        </div>
        
        <div class="snake-animation">
            <div class="snake-path"></div>
            <div class="snake"></div>
        </div>
    </div>

    <script>
        
        const texts = [
            "Creating digital experiences that matter",
            "Coding with passion and purpose",
            "Transforming ideas into reality",
            "Building the future, one line at a time"
        ];
        
        let textIndex = 0;
        const typingElement = document.getElementById('typing-text');
        
        function changeText() {
            typingElement.style.opacity = 0;
            
            setTimeout(() => {
                textIndex = (textIndex + 1) % texts.length;
                typingElement.textContent = texts[textIndex];
                typingElement.style.opacity = 1;
            }, 1000);
        }
        
        setInterval(changeText, 4000);
        
        
        document.addEventListener('mousemove', (e) => {
            const moveX = (e.clientX - window.innerWidth / 2) / 25;
            const moveY = (e.clientY - window.innerHeight / 2) / 25;
            
            const profileCard = document.querySelector('.profile-card');
            profileCard.style.transform = `translateY(${moveY}px) translateX(${moveX}px) rotateX(${moveY/2}deg) rotateY(${moveX/2}deg)`;
        });
    </script>
</body>
</html>
