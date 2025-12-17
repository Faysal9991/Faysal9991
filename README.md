<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Faysal - Flutter Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: #fff;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }

        header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
        }

        .name {
            font-size: 3.5rem;
            font-weight: bold;
            margin-bottom: 10px;
            text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
            animation: fadeInDown 1s ease;
        }

        .title {
            font-size: 1.5rem;
            opacity: 0.9;
            margin-bottom: 30px;
            animation: fadeInUp 1s ease 0.2s backwards;
        }

        .stats {
            display: flex;
            justify-content: center;
            gap: 40px;
            flex-wrap: wrap;
            animation: fadeIn 1s ease 0.4s backwards;
        }

        .stat-card {
            background: rgba(255, 255, 255, 0.15);
            backdrop-filter: blur(10px);
            padding: 20px 30px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }

        .stat-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.3);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: bold;
            display: block;
        }

        .stat-label {
            font-size: 0.9rem;
            opacity: 0.8;
            margin-top: 5px;
        }

        .section {
            background: rgba(255, 255, 255, 0.1);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin-bottom: 30px;
            border: 1px solid rgba(255, 255, 255, 0.2);
            animation: slideIn 0.8s ease;
        }

        .section-title {
            font-size: 2rem;
            margin-bottom: 30px;
            position: relative;
            display: inline-block;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: -10px;
            left: 0;
            width: 50%;
            height: 3px;
            background: #ffd700;
            border-radius: 2px;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }

        .skill-card {
            background: rgba(255, 255, 255, 0.1);
            padding: 20px;
            border-radius: 12px;
            border-left: 4px solid #ffd700;
            transition: all 0.3s ease;
        }

        .skill-card:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateX(10px);
        }

        .skill-title {
            font-size: 1.2rem;
            font-weight: bold;
            margin-bottom: 10px;
            color: #ffd700;
        }

        .skill-items {
            font-size: 0.95rem;
            line-height: 1.6;
            opacity: 0.9;
        }

        .projects {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
        }

        .project-card {
            background: linear-gradient(135deg, rgba(255,255,255,0.15), rgba(255,255,255,0.05));
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(255, 255, 255, 0.3);
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255,255,255,0.2), transparent);
            transition: left 0.5s ease;
        }

        .project-card:hover::before {
            left: 100%;
        }

        .project-card:hover {
            transform: scale(1.05);
            box-shadow: 0 20px 50px rgba(0,0,0,0.4);
        }

        .project-name {
            font-size: 1.5rem;
            font-weight: bold;
            margin-bottom: 10px;
            color: #ffd700;
        }

        .project-desc {
            font-size: 0.95rem;
            line-height: 1.6;
            opacity: 0.9;
            margin-bottom: 15px;
        }

        .project-stats {
            display: flex;
            gap: 15px;
            font-size: 0.85rem;
        }

        .badge {
            background: rgba(255, 215, 0, 0.2);
            padding: 5px 12px;
            border-radius: 20px;
            border: 1px solid #ffd700;
        }

        .cta-section {
            text-align: center;
            padding: 60px 20px;
        }

        .cta-buttons {
            display: flex;
            justify-content: center;
            gap: 20px;
            flex-wrap: wrap;
            margin-top: 30px;
        }

        .btn {
            padding: 15px 40px;
            border-radius: 50px;
            font-size: 1.1rem;
            font-weight: bold;
            text-decoration: none;
            transition: all 0.3s ease;
            border: 2px solid #fff;
            display: inline-block;
        }

        .btn-primary {
            background: #ffd700;
            color: #667eea;
            border-color: #ffd700;
        }

        .btn-primary:hover {
            background: #fff;
            transform: translateY(-5px);
            box-shadow: 0 10px 30px rgba(255, 215, 0, 0.5);
        }

        .btn-secondary {
            background: transparent;
            color: #fff;
        }

        .btn-secondary:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }

        @keyframes fadeInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
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

        @keyframes fadeIn {
            from {
                opacity: 0;
            }
            to {
                opacity: 1;
            }
        }

        @keyframes slideIn {
            from {
                opacity: 0;
                transform: translateX(-50px);
            }
            to {
                opacity: 1;
                transform: translateX(0);
            }
        }

        @media (max-width: 768px) {
            .name {
                font-size: 2.5rem;
            }
            
            .title {
                font-size: 1.2rem;
            }
            
            .stats {
                gap: 20px;
            }
            
            .section {
                padding: 25px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <h1 class="name">S M TANVIR HASAN FAYSAL</h1>
            <p class="title">Senior Flutter & Dart Developer | Mobile Architecture Expert</p>
            
            <div class="stats">
                <div class="stat-card">
                    <span class="stat-number">3.5+</span>
                    <span class="stat-label">Years Experience</span>
                </div>
                <div class="stat-card">
                    <span class="stat-number">10K+</span>
                    <span class="stat-label">Active Users</span>
                </div>
                <div class="stat-card">
                    <span class="stat-number">4.7+</span>
                    <span class="stat-label">App Store Rating</span>
                </div>
                <div class="stat-card">
                    <span class="stat-number">7+</span>
                    <span class="stat-label">Production Apps</span>
                </div>
            </div>
        </header>

        <div class="section">
            <h2 class="section-title">🚀 Expertise</h2>
            <div class="skills-grid">
                <div class="skill-card">
                    <div class="skill-title">Mobile Development</div>
                    <div class="skill-items">Flutter & Dart<br>Android & iOS Native<br>Custom Animations<br>Adaptive UI Design</div>
                </div>
                <div class="skill-card">
                    <div class="skill-title">State Management</div>
                    <div class="skill-items">GetX<br>Riverpod<br>Provider<br>BLoC Pattern</div>
                </div>
                <div class="skill-card">
                    <div class="skill-title">Backend & Database</div>
                    <div class="skill-items">Firebase Ecosystem<br>Node.js & Express<br>MongoDB<br>RESTful APIs</div>
                </div>
                <div class="skill-card">
                    <div class="skill-title">Real-Time Features</div>
                    <div class="skill-items">WebRTC Audio/Video<br>Socket.IO Chat<br>Push Notifications<br>Live Updates</div>
                </div>
                <div class="skill-card">
                    <div class="skill-title">Architecture</div>
                    <div class="skill-items">Clean Architecture<br>MVVM & MVC<br>Dependency Injection<br>Design Patterns</div>
                </div>
                <div class="skill-card">
                    <div class="skill-title">DevOps & Testing</div>
                    <div class="skill-items">CI/CD Pipelines<br>Unit & Integration Tests<br>Fastlane Deployment<br>Git Workflows</div>
                </div>
            </div>
        </div>

        <div class="section">
            <h2 class="section-title">💼 Featured Projects</h2>
            <div class="projects">
                <div class="project-card">
                    <div class="project-name">My Akij Takaful</div>
                    <div class="project-desc">Sharia-compliant insurance platform enabling policy management, claims processing, and premium payments with seamless user experience.</div>
                    <div class="project-stats">
                        <span class="badge">10K+ Downloads</span>
                        <span class="badge">Android & iOS</span>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-name">Bini FinTech</div>
                    <div class="project-desc">Cross-platform banking app with mutual-fund trading, DPS, FDPS, and Sanchayapatra purchases. OAuth2 secured with PCI DSS compliance.</div>
                    <div class="project-stats">
                        <span class="badge">100+ Downloads</span>
                        <span class="badge">Multi-locale</span>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-name">Akij Fair Value</div>
                    <div class="project-desc">E-commerce platform with integrated Stripe & bKash payments, real-time chat, and optimized checkout flow reducing latency by 30%.</div>
                    <div class="project-stats">
                        <span class="badge">100+ Downloads</span>
                        <span class="badge">4.7+ Rating</span>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-name">Market Audit</div>
                    <div class="project-desc">Real-time market survey and competitor analysis tool with customizable templates and offline support for businesses.</div>
                    <div class="project-stats">
                        <span class="badge">Android</span>
                        <span class="badge">Offline-First</span>
                    </div>
                </div>
            </div>
        </div>

        <div class="cta-section">
            <h2 class="section-title">Let's Build Something Amazing</h2>
            <p style="font-size: 1.1rem; opacity: 0.9; margin-top: 20px;">Ready to transform your mobile app idea into reality?</p>
            <div class="cta-buttons">
                <a href="https://github.com/yourusername" class="btn btn-primary">View GitHub</a>
                <a href="https://linkedin.com/in/yourprofile" class="btn btn-secondary">Connect on LinkedIn</a>
                <a href="mailto:faysaltanvir991@gmail.com" class="btn btn-secondary">Get In Touch</a>
            </div>
        </div>
    </div>
</body>
</html>
