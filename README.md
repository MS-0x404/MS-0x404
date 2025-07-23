<!DOCTYPE html>
<html lang="it">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Matteo - MagicSale GitHub Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@300;400;700&family=Inter:wght@300;400;600;700&display=swap');

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: linear-gradient(135deg, #0f0f23 0%, #1a1a2e 50%, #16213e 100%);
            color: #ffffff;
            overflow-x: hidden;
            min-height: 100vh;
        }

        .container {
            max-width: 800px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* Header animato */
        .header {
            text-align: center;
            margin-bottom: 3rem;
            position: relative;
        }

        .title {
            font-size: 3rem;
            font-weight: 700;
            background: linear-gradient(45deg, #00f5ff, #ff00ff, #00ff00);
            background-size: 300% 300%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 3s ease-in-out infinite;
            margin-bottom: 0.5rem;
        }

        .subtitle {
            font-size: 1.2rem;
            color: #a0a0a0;
            animation: fadeInUp 1s ease-out 0.5s both;
        }

        /* Codice animato */
        .code-container {
            background: rgba(0, 0, 0, 0.6);
            border: 1px solid #333;
            border-radius: 12px;
            padding: 2rem;
            margin: 2rem 0;
            position: relative;
            overflow: hidden;
        }

        .code-header {
            display: flex;
            align-items: center;
            margin-bottom: 1rem;
        }

        .code-dots {
            display: flex;
            gap: 0.5rem;
        }

        .dot {
            width: 12px;
            height: 12px;
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        .dot:nth-child(1) { background: #ff5f56; }
        .dot:nth-child(2) { background: #ffbd2e; animation-delay: 0.5s; }
        .dot:nth-child(3) { background: #27ca3f; animation-delay: 1s; }

        .code {
            font-family: 'JetBrains Mono', monospace;
            font-size: 0.9rem;
            line-height: 1.6;
            overflow: hidden;
        }

        .code-line {
            opacity: 0;
            animation: typewriter 0.5s ease-out forwards;
        }

        .code-line:nth-child(1) { animation-delay: 1s; }
        .code-line:nth-child(2) { animation-delay: 1.2s; }
        .code-line:nth-child(3) { animation-delay: 1.4s; }
        .code-line:nth-child(4) { animation-delay: 1.6s; }
        .code-line:nth-child(5) { animation-delay: 1.8s; }
        .code-line:nth-child(6) { animation-delay: 2s; }
        .code-line:nth-child(7) { animation-delay: 2.2s; }
        .code-line:nth-child(8) { animation-delay: 2.4s; }
        .code-line:nth-child(9) { animation-delay: 2.6s; }
        .code-line:nth-child(10) { animation-delay: 2.8s; }
        .code-line:nth-child(11) { animation-delay: 3s; }

        .keyword { color: #ff79c6; }
        .string { color: #f1fa8c; }
        .comment { color: #6272a4; }
        .number { color: #bd93f9; }
        .function { color: #50fa7b; }

        /* Cards animate */
        .cards-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin: 3rem 0;
        }

        .card {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 16px;
            padding: 2rem;
            text-align: center;
            transition: all 0.3s ease;
            animation: slideInUp 0.8s ease-out both;
        }

        .card:nth-child(1) { animation-delay: 3.5s; }
        .card:nth-child(2) { animation-delay: 3.7s; }

        .card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 245, 255, 0.2);
            border-color: rgba(0, 245, 255, 0.3);
        }

        .card-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            animation: float 3s ease-in-out infinite;
        }

        .card h3 {
            font-size: 1.4rem;
            margin-bottom: 1rem;
            color: #00f5ff;
        }

        /* Quote animata */
        .quote {
            text-align: center;
            margin: 3rem 0;
            padding: 2rem;
            background: linear-gradient(135deg, rgba(0, 245, 255, 0.1), rgba(255, 0, 255, 0.1));
            border-radius: 16px;
            border-left: 4px solid #00f5ff;
            animation: slideInLeft 1s ease-out 4s both;
        }

        .quote-text {
            font-size: 1.3rem;
            font-style: italic;
            margin-bottom: 1rem;
            color: #ffffff;
        }

        .quote-author {
            color: #a0a0a0;
            font-size: 0.9rem;
        }

        /* Contact section */
        .contact {
            text-align: center;
            margin-top: 3rem;
            padding: 2rem;
            background: rgba(0, 0, 0, 0.3);
            border-radius: 16px;
            animation: fadeIn 1s ease-out 4.5s both;
        }

        .email {
            display: inline-block;
            padding: 0.8rem 2rem;
            background: linear-gradient(45deg, #00f5ff, #ff00ff);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            font-weight: 600;
            transition: all 0.3s ease;
            margin-top: 1rem;
        }

        .email:hover {
            transform: scale(1.05);
            box-shadow: 0 10px 25px rgba(0, 245, 255, 0.3);
        }

        /* Particelle di sfondo */
        .particles {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            pointer-events: none;
            z-index: -1;
        }

        .particle {
            position: absolute;
            width: 2px;
            height: 2px;
            background: #00f5ff;
            border-radius: 50%;
            animation: float-particle 15s linear infinite;
        }

        /* Animazioni */
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes typewriter {
            from {
                opacity: 0;
                transform: translateX(-20px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(50px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        @keyframes slideInLeft {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 1; }
            50% { transform: scale(1.2); opacity: 0.7; }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes float-particle {
            0% {
                transform: translateY(100vh) translateX(0);
                opacity: 0;
            }
            10% {
                opacity: 1;
            }
            90% {
                opacity: 1;
            }
            100% {
                transform: translateY(-10vh) translateX(100px);
                opacity: 0;
            }
        }

        /* Responsive */
        @media (max-width: 768px) {
            .title { font-size: 2rem; }
            .container { padding: 1rem; }
            .cards-container { grid-template-columns: 1fr; }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <header class="header">
            <h1 class="title">👋 Ciao! Sono Matteo</h1>
            <p class="subtitle">MagicSale ✨ • Mountain Coder & Security Explorer</p>
        </header>

        <div class="code-container">
            <div class="code-header">
                <div class="code-dots">
                    <div class="dot"></div>
                    <div class="dot"></div>
                    <div class="dot"></div>
                </div>
            </div>
            <div class="code">
                <div class="code-line"><span class="keyword">class</span> <span class="function">Developer</span>:</div>
                <div class="code-line">    <span class="keyword">def</span> <span class="function">__init__</span>(self):</div>
                <div class="code-line">        self.nickname = <span class="string">"MagicSale ✨"</span></div>
                <div class="code-line">        self.age = <span class="number">20</span></div>
                <div class="code-line">        self.location = <span class="string">"🏔️ Tra le montagne e il codice"</span></div>
                <div class="code-line">        self.passions = [</div>
                <div class="code-line">            <span class="string">"Python 🐍"</span>, <span class="string">"Cybersecurity 🔒"</span>,</div>
                <div class="code-line">            <span class="string">"Red Team 🎯"</span>, <span class="string">"Mountain Life 🏔️"</span></div>
                <div class="code-line">        ]</div>
                <div class="code-line">        self.status = <span class="string">"🔄 Debugging life, one line at a time"</span></div>
                <div class="code-line">        <span class="comment"># Always ready for new adventures! 🚀</span></div>
            </div>
        </div>

        <div class="cards-container">
            <div class="card">
                <div class="card-icon">🔒</div>
                <h3>Cybersecurity</h3>
                <p>Esplorando vulnerabilità e sistemi di sicurezza con curiosità e responsabilità etica.</p>
            </div>
            <div class="card">
                <div class="card-icon">🏔️</div>
                <h3>Mountain Coding</h3>
                <p>Le migliori idee nascono tra le vette alpine, dove il codice incontra la natura.</p>
            </div>
        </div>

        <div class="quote">
            <div class="quote-text">
                "Life is like debugging: sometimes you need to climb higher to see the problem from above"
            </div>
            <div class="quote-author">- Me, probabilmente su qualche cima con VSCode aperto</div>
        </div>

        <div class="contact">
            <h3>🤝 Let's Connect & Build Something Amazing</h3>
            <p>Pronto per la prossima avventura nel codice? Facciamo qualcosa di magico insieme!</p>
            <a href="mailto:matteosalis04@ik.me" class="email">📧 Contattami</a>
        </div>
    </div>

    <script>
        // Crea particelle animate di sfondo
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            
            for (let i = 0; i < 50; i++) {
                const particle = document.createElement('div');
                particle.className = 'particle';
                particle.style.left = Math.random() * 100 + '%';
                particle.style.animationDelay = Math.random() * 15 + 's';
                particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
                particlesContainer.appendChild(particle);
            }
        }

        // Effetto di typing per il codice
        function addTypingCursor() {
            const codeLines = document.querySelectorAll('.code-line');
            codeLines.forEach((line, index) => {
                setTimeout(() => {
                    const cursor = document.createElement('span');
                    cursor.textContent = '|';
                    cursor.style.animation = 'blink 1s infinite';
                    cursor.style.color = '#00f5ff';
                    line.appendChild(cursor);
                    
                    setTimeout(() => {
                        cursor.remove();
                    }, 1000);
                }, (index + 1) * 200 + 1000);
            });
        }

        // Inizializza le animazioni
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            addTypingCursor();
        });

        // Aggiunge stile per il cursore lampeggiante
        const style = document.createElement('style');
        style.textContent = `
            @keyframes blink {
                0%, 50% { opacity: 1; }
                51%, 100% { opacity: 0; }
            }
        `;
        document.head.appendChild(style);
    </script>
</body>
</html>
