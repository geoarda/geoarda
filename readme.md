<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arda - Creative Developer</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;600;800&family=Orbitron:wght@400;700;900&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            background: linear-gradient(135deg, #0c0c0c 0%, #1a1a2e 30%, #16213e 70%, #0f3460 100%);
            min-height: 100vh;
            color: #fff;
            font-family: 'JetBrains Mono', monospace;
            overflow-x: hidden;
            position: relative;
        }
        
        /* Animated Background Particles */
        .particle {
            position: absolute;
            width: 3px;
            height: 3px;
            background: rgba(0, 255, 255, 0.6);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0) scale(1); opacity: 0.4; }
            50% { transform: translateY(-20px) translateX(10px) scale(1.2); opacity: 1; }
        }
        
        /* Matrix-style code rain effect */
        .code-rain {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
            opacity: 0.1;
        }
        
        .code-line {
            position: absolute;
            color: #00ff88;
            font-family: 'JetBrains Mono', monospace;
            font-size: 12px;
            animation: matrixFall 8s linear infinite;
        }
        
        @keyframes matrixFall {
            0% { transform: translateY(-100vh); opacity: 0; }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { transform: translateY(100vh); opacity: 0; }
        }
        
        /* Main container with glassmorphism */
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
            backdrop-filter: blur(20px);
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            margin-top: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }
        
        /* Hero section */
        .hero {
            text-align: center;
            padding: 60px 0;
            position: relative;
        }
        
        .hero h1 {
            font-family: 'Orbitron', monospace;
            font-size: 4rem;
            font-weight: 900;
            background: linear-gradient(45deg, #00ffff, #ff00ff, #ffff00, #00ffff);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: gradientShift 3s ease-in-out infinite, glow 2s ease-in-out infinite alternate;
            margin-bottom: 20px;
            text-shadow: 0 0 50px rgba(0, 255, 255, 0.5);
        }
        
        @keyframes gradientShift {
            0% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
            100% { background-position: 0% 50%; }
        }
        
        @keyframes glow {
            from { filter: drop-shadow(0 0 20px rgba(0, 255, 255, 0.7)); }
            to { filter: drop-shadow(0 0 40px rgba(255, 0, 255, 0.7)); }
        }
        
        .tagline {
            font-size: 1.3rem;
            color: #00ffaa;
            margin-bottom: 30px;
            opacity: 0;
            animation: fadeInUp 1s ease-out 0.5s forwards;
        }
        
        @keyframes fadeInUp {
            from { opacity: 0; transform: translateY(30px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        /* Typing animation for skills */
        .typing-container {
            font-family: 'JetBrains Mono', monospace;
            font-size: 1.1rem;
            height: 30px;
            margin: 20px 0;
        }
        
        .typing-text {
            color: #ffaa00;
            border-right: 2px solid #ffaa00;
            animation: blink 1s infinite;
        }
        
        @keyframes blink {
            50% { border-color: transparent; }
        }
        
        /* Floating tech icons */
        .tech-icons {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin: 40px 0;
        }
        
        .tech-icon {
            width: 80px;
            height: 80px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 20px;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 2rem;
            transition: all 0.3s ease;
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: float 4s ease-in-out infinite;
        }
        
        .tech-icon:nth-child(odd) {
            animation-delay: -2s;
        }
        
        .tech-icon:hover {
            transform: scale(1.2) rotate(10deg);
            box-shadow: 0 10px 30px rgba(0, 255, 255, 0.4);
            background: rgba(0, 255, 255, 0.2);
        }
        
        /* Project cards with neon effect */
        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 30px;
            margin: 60px 0;
        }
        
        .project-card {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 20px;
            padding: 30px;
            border: 1px solid rgba(0, 255, 255, 0.3);
            position: relative;
            overflow: hidden;
            transition: all 0.4s ease;
            backdrop-filter: blur(15px);
        }
        
        .project-card::before {
            content: '';
            position: absolute;
            top: -2px;
            left: -2px;
            right: -2px;
            bottom: -2px;
            background: linear-gradient(45deg, transparent, #00ffff, transparent, #ff00ff, transparent);
            border-radius: 20px;
            z-index: -1;
            animation: borderRotate 4s linear infinite;
            opacity: 0;
            transition: opacity 0.4s ease;
        }
        
        .project-card:hover::before {
            opacity: 1;
        }
        
        @keyframes borderRotate {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        
        .project-card:hover {
            transform: translateY(-10px) scale(1.02);
            box-shadow: 0 20px 40px rgba(0, 255, 255, 0.3);
        }
        
        .project-title {
            font-family: 'Orbitron', monospace;
            font-size: 1.5rem;
            color: #00ffff;
            margin-bottom: 15px;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .project-emoji {
            font-size: 2rem;
            animation: bounce 2s infinite;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
            40% { transform: translateY(-10px); }
            60% { transform: translateY(-5px); }
        }
        
        /* Interactive buttons with cyberpunk style */
        .cyber-button {
            background: linear-gradient(45deg, #00ffff, #ff00ff);
            border: none;
            padding: 12px 30px;
            color: #000;
            font-family: 'Orbitron', monospace;
            font-weight: 700;
            text-decoration: none;
            border-radius: 10px;
            margin: 10px;
            display: inline-block;
            position: relative;
            overflow: hidden;
            transition: all 0.3s ease;
            text-transform: uppercase;
            font-size: 0.9rem;
        }
        
        .cyber-button::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.4), transparent);
            transition: left 0.6s ease;
        }
        
        .cyber-button:hover::before {
            left: 100%;
        }
        
        .cyber-button:hover {
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.8);
            transform: translateY(-2px);
        }
        
        /* Stats section with animated bars */
        .stats {
            margin: 60px 0;
            text-align: center;
        }
        
        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 40px;
        }
        
        .stat-item {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 15px;
            padding: 30px 20px;
            border: 1px solid rgba(0, 255, 255, 0.3);
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }
        
        .stat-item:hover {
            transform: scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 255, 255, 0.2);
        }
        
        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            color: #00ffff;
            display: block;
            margin-bottom: 10px;
        }
        
        /* Contact section with futuristic styling */
        .contact {
            text-align: center;
            margin: 60px 0;
            padding: 40px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        
        .contact-links {
            display: flex;
            justify-content: center;
            gap: 30px;
            margin-top: 30px;
            flex-wrap: wrap;
        }
        
        .contact-link {
            width: 60px;
            height: 60px;
            background: rgba(0, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #00ffff;
            text-decoration: none;
            transition: all 0.4s ease;
            border: 2px solid rgba(0, 255, 255, 0.3);
        }
        
        .contact-link:hover {
            background: #00ffff;
            color: #000;
            transform: scale(1.3) rotate(360deg);
            box-shadow: 0 0 30px rgba(0, 255, 255, 0.8);
        }
        
        /* Mobile responsive */
        @media (max-width: 768px) {
            .hero h1 {
                font-size: 2.5rem;
            }
            
            .container {
                margin: 10px;
                padding: 15px;
            }
            
            .projects {
                grid-template-columns: 1fr;
            }
            
            .tech-icons {
                gap: 15px;
            }
            
            .tech-icon {
                width: 60px;
                height: 60px;
                font-size: 1.5rem;
            }
        }
        
        /* Loading animation */
        .loading-overlay {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: #0c0c0c;
            display: flex;
            align-items: center;
            justify-content: center;
            z-index: 9999;
            animation: fadeOut 2s ease-out 1s forwards;
        }
        
        @keyframes fadeOut {
            to { opacity: 0; pointer-events: none; }
        }
        
        .loader {
            width: 60px;
            height: 60px;
            border: 3px solid rgba(0, 255, 255, 0.3);
            border-top: 3px solid #00ffff;
            border-radius: 50%;
            animation: spin 1s linear infinite;
        }
        
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
    </style>
</head>
<body>
    <div class="loading-overlay">
        <div class="loader"></div>
    </div>
    
    <div class="code-rain" id="codeRain"></div>
    
    <div class="container">
        <div class="hero">
            <h1>ARDA</h1>
            <div class="tagline">17 Yaşında Kodla Dünyayı Değiştiren Genç Developer 🚀</div>
            
            <div class="typing-container">
                <span class="typing-text" id="typingText"></span>
            </div>
            
            <div class="tech-icons">
                <div class="tech-icon">🐍</div>
                <div class="tech-icon">⚛️</div>
                <div class="tech-icon">🟨</div>
                <div class="tech-icon">💎</div>
                <div class="tech-icon">🦀</div>
                <div class="tech-icon">☕</div>
                <div class="tech-icon">🔷</div>
                <div class="tech-icon">🌐</div>
            </div>
        </div>
        
        <div class="projects">
            <div class="project-card">
                <h3 class="project-title">
                    <span class="project-emoji">✅</span>
                    TaskMaster
                </h3>
                <p>Modern ve kullanışlı yapılacaklar listesi! Karanlık mod desteği ve localStorage entegrasyonu ile görevlerinizi takip edin.</p>
                <div>
                    <a href="https://geoarda.github.io/TaskMaster/" class="cyber-button">Canlı Demo</a>
                    <a href="https://github.com/geoarda/TaskMaster" class="cyber-button">GitHub</a>
                </div>
            </div>
            
            <div class="project-card">
                <h3 class="project-title">
                    <span class="project-emoji">🧮</span>
                    CodeCalcPro
                </h3>
                <p>HTML, CSS ve JavaScript ile geliştirilmiş modern hesap makinesi. Renk temaları ve sezgisel arayüz tasarımı.</p>
                <div>
                    <a href="https://geoarda.github.io/CodeCalcPro/" class="cyber-button">Canlı Demo</a>
                    <a href="https://github.com/geoarda/CodeCalcPro" class="cyber-button">GitHub</a>
                </div>
            </div>
            
            <div class="project-card">
                <h3 class="project-title">
                    <span class="project-emoji">🖥️</span>
                    PC Parts Store
                </h3>
                <p>Okul projesi olarak geliştirilen bilgisayar parçası satış sitesi. Basit ve kullanışlı e-ticaret deneyimi.</p>
                <div>
                    <a href="http://bilgisayarparcasisatan.somee.com/" class="cyber-button">Canlı Demo</a>
                </div>
            </div>
        </div>
        
        <div class="stats">
            <h2 style="font-family: 'Orbitron', monospace; font-size: 2.5rem; color: #00ffff; margin-bottom: 30px;">
                📊 Kodlama İstatistikleri
            </h2>
            <div class="stats-grid">
                <div class="stat-item">
                    <span class="stat-number">13+</span>
                    <div>Programlama Dili</div>
                </div>
                <div class="stat-item">
                    <span class="stat-number">5+</span>
                    <div>Tamamlanan Proje</div>
                </div>
                <div class="stat-item">
                    <span class="stat-number">2+</span>
                    <div>Yıllık Deneyim</div>
                </div>
                <div class="stat-item">
                    <span class="stat-number">∞</span>
                    <div>Yaratıcılık Seviyesi</div>
                </div>
            </div>
        </div>
        
        <div class="contact">
            <h2 style="font-family: 'Orbitron', monospace; font-size: 2rem; color: #ff00ff; margin-bottom: 20px;">
                🌐 Benimle İletişime Geç
            </h2>
            <p style="color: #00ffaa; font-size: 1.1rem;">Turn code into creativity, one project at a time.</p>
            
            <div class="contact-links">
                <a href="https://www.linkedin.com/in/arda-a-020bb5380/" class="contact-link">💼</a>
                <a href="https://github.com/geoarda" class="contact-link">🐱</a>
                <a href="mailto:your-email@example.com" class="contact-link">📧</a>
                <a href="#" class="contact-link">💬</a>
            </div>
        </div>
    </div>

    <script>
        // Particle system
        function createParticles() {
            const particleCount = 50;
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + 'vw';
                particle.style.top = Math.random() * 100 + 'vh';
                particle.style.animationDelay = Math.random() * 6 + 's';
                particle.style.animationDuration = (3 + Math.random() * 6) + 's';
                document.body.appendChild(particle);
            }
        }
        
        // Matrix code rain effect
        function createCodeRain() {
            const codeSnippets = [
                'function()', 'const x =', 'if (true)', 'while(i++)', '=> {}', 'async/await', 
                'console.log', 'return;', 'import {', 'export', 'class', 'new Promise',
                'SELECT *', 'FROM', 'WHERE', 'INSERT', 'UPDATE', 'DELETE',
                'git commit', 'git push', 'npm install', 'yarn dev', 'docker run',
                '#!/bin/bash', 'sudo', 'chmod +x', 'ls -la', 'cd ..', 'mkdir'
            ];
            
            const codeRain = document.getElementById('codeRain');
            
            setInterval(() => {
                const codeLine = document.createElement('div');
                codeLine.className = 'code-line';
                codeLine.textContent = codeSnippets[Math.floor(Math.random() * codeSnippets.length)];
                codeLine.style.left = Math.random() * 100 + 'vw';
                codeLine.style.animationDuration = (5 + Math.random() * 5) + 's';
                codeRain.appendChild(codeLine);
                
                // Remove after animation
                setTimeout(() => {
                    if (codeLine.parentNode) {
                        codeLine.parentNode.removeChild(codeLine);
                    }
                }, 10000);
            }, 300);
        }
        
        // Typing animation
        function startTypingAnimation() {
            const texts = [
                'Lua | PHP | JavaScript | Python | Java',
                'C# | C++ | C | Ruby | Go | Rust',
                'Kotlin | TypeScript | React | Node.js',
                'Game Modding & Web Development',
                'Turning Ideas Into Code Magic ✨'
            ];
            
            let textIndex = 0;
            let charIndex = 0;
            let isDeleting = false;
            const typingElement = document.getElementById('typingText');
            
            function type() {
                const currentText = texts[textIndex];
                
                if (isDeleting) {
                    typingElement.textContent = currentText.substring(0, charIndex - 1);
                    charIndex--;
                } else {
                    typingElement.textContent = currentText.substring(0, charIndex + 1);
                    charIndex++;
                }
                
                let typeSpeed = isDeleting ? 50 : 100;
                
                if (!isDeleting && charIndex === currentText.length) {
                    typeSpeed = 2000;
                    isDeleting = true;
                } else if (isDeleting && charIndex === 0) {
                    isDeleting = false;
                    textIndex = (textIndex + 1) % texts.length;
                    typeSpeed = 500;
                }
                
                setTimeout(type, typeSpeed);
            }
            
            type();
        }
        
        // Smooth scroll for internal links
        function smoothScroll() {
            document.querySelectorAll('a[href^="#"]').forEach(anchor => {
                anchor.addEventListener('click', function (e) {
                    e.preventDefault();
                    const target = document.querySelector(this.getAttribute('href'));
                    if (target) {
                        target.scrollIntoView({
                            behavior: 'smooth',
                            block: 'start'
                        });
                    }
                });
            });
        }
        
        // Initialize everything when page loads
        window.addEventListener('load', () => {
            createParticles();
            createCodeRain();
            startTypingAnimation();
            smoothScroll();
        });
        
        // Add mouse trail effect
        document.addEventListener('mousemove', (e) => {
            const trail = document.createElement('div');
            trail.style.position = 'fixed';
            trail.style.width = '4px';
            trail.style.height = '4px';
            trail.style.background = 'rgba(0, 255, 255, 0.6)';
            trail.style.borderRadius = '50%';
            trail.style.pointerEvents = 'none';
            trail.style.left = e.clientX + 'px';
            trail.style.top = e.clientY + 'px';
            trail.style.zIndex = '9998';
            trail.style.animation = 'fadeOut 0.8s ease-out forwards';
            
            document.body.appendChild(trail);
            
            setTimeout(() => {
                if (trail.parentNode) {
                    trail.parentNode.removeChild(trail);
                }
            }, 800);
        });
        
        // Add scroll animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };
        
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '1';
                    entry.target.style.transform = 'translateY(0)';
                }
            });
        }, observerOptions);
        
        // Observe elements for scroll animations
        document.addEventListener('DOMContentLoaded', () => {
            const animateElements = document.querySelectorAll('.project-card, .stat-item');
            animateElements.forEach(el => {
                el.style.opacity = '0';
                el.style.transform = 'translateY(30px)';
                el.style.transition = 'opacity 0.6s ease, transform 0.6s ease';
                observer.observe(el);
            });
        });
    </script>
</body>
</html>
