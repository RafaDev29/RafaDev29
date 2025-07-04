<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rafael's Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a3e 50%, #2d2d5f 100%);
            color: #ffffff;
            min-height: 100vh;
            position: relative;
            overflow-x: hidden;
        }

        /* Animated background particles */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: 1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #39FF14;
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px) rotate(0deg); opacity: 0.7; }
            50% { transform: translateY(-20px) rotate(180deg); opacity: 1; }
        }

        .container {
            position: relative;
            z-index: 2;
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        .header {
            text-align: center;
            margin-bottom: 3rem;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.3);
        }

        .header h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
            background: linear-gradient(45deg, #39FF14, #00ff88);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: glow 2s ease-in-out infinite alternate;
        }

        @keyframes glow {
            from { filter: drop-shadow(0 0 5px #39FF14); }
            to { filter: drop-shadow(0 0 20px #39FF14); }
        }

        .typing-animation {
            font-size: 1.2rem;
            color: #39FF14;
            margin: 1rem 0;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1rem;
            margin-top: 2rem;
        }

        .social-links a {
            display: inline-block;
            padding: 0.5rem;
            background: rgba(57, 255, 20, 0.1);
            border-radius: 10px;
            transition: all 0.3s ease;
            border: 1px solid rgba(57, 255, 20, 0.3);
        }

        .social-links a:hover {
            background: rgba(57, 255, 20, 0.2);
            transform: translateY(-3px);
            box-shadow: 0 10px 25px rgba(57, 255, 20, 0.3);
        }

        .section {
            margin-bottom: 3rem;
            padding: 2rem;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            backdrop-filter: blur(15px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 8px 32px rgba(0, 0, 0, 0.2);
            transition: all 0.3s ease;
        }

        .section:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 40px rgba(0, 0, 0, 0.3);
        }

        .section h2 {
            text-align: center;
            font-size: 2rem;
            margin-bottom: 2rem;
            color: #39FF14;
            position: relative;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 1rem;
        }

        .section h2::before,
        .section h2::after {
            content: '';
            height: 2px;
            background: linear-gradient(90deg, transparent, #39FF14, transparent);
            flex: 1;
        }

        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 1rem;
            justify-items: center;
        }

        .tech-badge {
            display: inline-block;
            margin: 0.5rem;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .tech-badge:hover {
            transform: scale(1.1);
            filter: brightness(1.2);
        }

        .tech-badge::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.2), transparent);
            transition: left 0.5s;
        }

        .tech-badge:hover::before {
            left: 100%;
        }

        .tech-badge img {
            border-radius: 8px;
            box-shadow: 0 4px 15px rgba(0, 0, 0, 0.2);
        }

        .tools-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(80px, 1fr));
            gap: 2rem;
            align-items: center;
            justify-items: center;
        }

        .tool-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            transition: all 0.3s ease;
            padding: 1rem;
            border-radius: 15px;
            background: rgba(255, 255, 255, 0.05);
        }

        .tool-item:hover {
            transform: translateY(-10px);
            background: rgba(57, 255, 20, 0.1);
            box-shadow: 0 10px 30px rgba(57, 255, 20, 0.2);
        }

        .tool-item img {
            width: 40px;
            height: 40px;
            border-radius: 8px;
            margin-bottom: 0.5rem;
        }

        .tool-name {
            font-size: 0.9rem;
            color: #39FF14;
            font-weight: bold;
        }

        @media (max-width: 768px) {
            .header h1 {
                font-size: 2rem;
            }
            
            .section {
                padding: 1rem;
            }
            
            .tech-grid {
                grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            }
        }
    </style>
</head>
<body>
    <div class="particles"></div>
    
    <div class="container">
        <div class="header">
            <h1>¡Hola 👋, Soy Rafael!</h1>
            <div class="typing-animation">
                <img src="https://readme-typing-svg.herokuapp.com?font=ROBOT&size=25&color=39FF14&background=000000&center=true&vCenter=true&width=590&lines=%3E+Bienvenido+a+mi+Portafolio+en+GitHub...!" alt="Typing SVG">
            </div>
            
            <h2>¡Contáctame! <img src="https://media.giphy.com/media/iY8CRBdQXODJSCERIr/giphy.gif" width="30px"></h2>
            
            <div class="social-links">
                <a href="https://www.linkedin.com/in/rafael-andres-rossel-galarza-47b8bb214/" target="_blank">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="LinkedIn" height="30" width="40">
                </a>
                <a href="https://www.instagram.com/rafael_rossel_galarza/" target="_blank">
                    <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/instagram.svg" alt="Instagram" height="30" width="40">
                </a>
                <a href="https://gitlab.com/rosselgalarzarafael" target="_blank">
                    <img alt="GitLab" src="https://img.icons8.com/color/48/000000/gitlab.png" height="30" width="40">
                </a>
            </div>
        </div>

        <div class="section">
            <h2>¡Lenguajes de Programación! <img src="https://media.giphy.com/media/HwBlFQZFcAoUcPHZdX/giphy.gif" width="45px"></h2>
            <div class="tech-grid">
                <div class="tech-badge">
                    <img alt="JavaScript" src="https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black">
                </div>
                <div class="tech-badge">
                    <img alt="Python" src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="TypeScript" src="https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="PHP" src="https://img.shields.io/badge/PHP-777BB4?style=for-the-badge&logo=php&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="Java" src="https://img.shields.io/badge/Java-ED8B00?style=for-the-badge&logo=java&logoColor=white">
                </div>
            </div>
        </div>

        <div class="section">
            <h2>¡Frontend! <img src="https://media.giphy.com/media/HwBlFQZFcAoUcPHZdX/giphy.gif" width="45px"></h2>
            <div class="tech-grid">
                <div class="tech-badge">
                    <img alt="React" src="https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="Vue.js" src="https://img.shields.io/badge/Vue.js-4FC08D?style=for-the-badge&logo=vue.js&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="Astro" src="https://img.shields.io/badge/Astro-000000?style=for-the-badge&logo=astro&logoColor=white">
                </div>
            </div>
        </div>

        <div class="section">
            <h2>¡Backend! <img src="https://media.giphy.com/media/HwBlFQZFcAoUcPHZdX/giphy.gif" width="45px"></h2>
            <div class="tech-grid">
                <div class="tech-badge">
                    <img alt="Express.js" src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="Node.js" src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=node.js&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="NestJS" src="https://img.shields.io/badge/NestJS-E0234E?style=for-the-badge&logo=nestjs&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="Spring Boot" src="https://img.shields.io/badge/Spring_Boot-6DB33F?style=for-the-badge&logo=spring-boot&logoColor=white">
                </div>
            </div>
        </div>

        <div class="section">
            <h2>¡Bases de Datos! <img src="https://media.giphy.com/media/HwBlFQZFcAoUcPHZdX/giphy.gif" width="45px"></h2>
            <div class="tech-grid">
                <div class="tech-badge">
                    <img alt="SQL Server" src="https://img.shields.io/badge/SQL_Server-CC2927?style=for-the-badge&logo=microsoft-sql-server&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="MySQL" src="https://img.shields.io/badge/MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="MongoDB" src="https://img.shields.io/badge/MongoDB-47A248?style=for-the-badge&logo=mongodb&logoColor=white">
                </div>
                <div class="tech-badge">
                    <img alt="PostgreSQL" src="https://img.shields.io/badge/PostgreSQL-336791?style=for-the-badge&logo=postgresql&logoColor=white">
                </div>
            </div>
        </div>

        <div class="section">
            <h2>¡DevOps & Herramientas! <img src="https://media.giphy.com/media/iDaCeaKrHhUI1I8e2b/giphy.gif" width="45px"></h2>
            <div class="tools-grid">
                <div class="tool-item">
                    <img src="https://img.shields.io/badge/Ubuntu-E95420?style=for-the-badge&logo=ubuntu&logoColor=white" alt="Ubuntu">
                    <span class="tool-name">Ubuntu</span>
                </div>
                <div class="tool-item">
                    <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/docker/docker-original-wordmark.svg" alt="Docker">
                    <span class="tool-name">Docker</span>
                </div>
                <div class="tool-item">
                    <img src="https://img.shields.io/badge/PM2-2B037A?style=for-the-badge&logo=pm2&logoColor=white" alt="PM2">
                    <span class="tool-name">PM2</span>
                </div>
                <div class="tool-item">
                    <img src="https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazon-aws&logoColor=white" alt="AWS">
                    <span class="tool-name">AWS</span>
                </div>
            </div>
        </div>
    </div>

    <script>
        // Create animated particles
        function createParticles() {
            const particlesContainer = document.querySelector('.particles');
            const particleCount = 50;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.top = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (Math.random() * 3 + 3) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Initialize particles when page loads
        document.addEventListener('DOMContentLoaded', createParticles);

        // Add smooth scrolling and hover effects
        document.querySelectorAll('.tech-badge').forEach(badge => {
            badge.addEventListener('mouseenter', function() {
                this.style.transform = 'scale(1.05) rotate(2deg)';
            });
            
            badge.addEventListener('mouseleave', function() {
                this.style.transform = 'scale(1) rotate(0deg)';
            });
        });
    </script>
</body>
</html>
