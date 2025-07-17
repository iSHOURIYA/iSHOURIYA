<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Shaurya Tayal - GitHub Profile</title>
    <style>
        :root {
            --primary: #0366d6;
            --secondary: #28a745;
            --dark: #24292e;
            --light: #f6f8fa;
            --accent: #d73a49;
            --transition: all 0.3s ease;
        }

        @media (prefers-color-scheme: dark) {
            :root {
                --dark: #f6f8fa;
                --light: #24292e;
            }
        }

        @media (prefers-reduced-motion) {
            * {
                animation: none !important;
                transition: none !important;
            }
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 2rem;
        }

        /* 3D Animated Header */
        .header {
            position: relative;
            height: 100vh;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            perspective: 1000px;
            overflow: hidden;
        }

        .particles {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
        }

        .particle {
            position: absolute;
            border-radius: 50%;
            background: var(--primary);
            opacity: 0.3;
        }

        .name {
            font-size: 5rem;
            font-weight: 700;
            text-align: center;
            transform-style: preserve-3d;
            animation: float 6s ease-in-out infinite;
            text-shadow: 0 5px 15px rgba(0,0,0,0.1);
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            position: relative;
            z-index: 1;
        }

        .title {
            font-size: 2rem;
            margin-top: 1rem;
            animation: fadeIn 2s ease;
            text-align: center;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotateX(0deg) rotateY(0deg); }
            50% { transform: translateY(-20px) rotateX(5deg) rotateY(5deg); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        /* Skills Section */
        .skills-section {
            padding: 4rem 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 3rem;
            font-size: 2.5rem;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 100px;
            height: 4px;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            margin: 0.5rem auto;
            border-radius: 2px;
        }

        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-category {
            background: rgba(255,255,255,0.1);
            backdrop-filter: blur(10px);
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: var(--transition);
        }

        .skill-category:hover {
            transform: translateY(-5px);
        }

        .skill-category h3 {
            margin-bottom: 1.5rem;
            color: var(--primary);
        }

        .skill-item {
            margin-bottom: 1.5rem;
            position: relative;
        }

        .skill-info {
            display: flex;
            justify-content: space-between;
            margin-bottom: 0.5rem;
        }

        .skill-bar {
            height: 10px;
            background-color: #e0e0e0;
            border-radius: 5px;
            overflow: hidden;
        }

        .skill-progress {
            height: 100%;
            background: linear-gradient(90deg, var(--primary), var(--secondary));
            border-radius: 5px;
            transform: translateX(-100%);
            animation: fillBar 1.5s ease forwards;
        }

        @keyframes fillBar {
            to { transform: translateX(0); }
        }

        .skill-tooltip {
            position: absolute;
            top: -40px;
            left: 50%;
            transform: translateX(-50%);
            background: var(--dark);
            color: var(--light);
            padding: 5px 10px;
            border-radius: 5px;
            font-size: 0.8rem;
            opacity: 0;
            pointer-events: none;
            transition: var(--transition);
            white-space: nowrap;
        }

        .skill-item:hover .skill-tooltip {
            opacity: 1;
            top: -45px;
        }

        /* GitHub Stats */
        .stats-section {
            padding: 4rem 0;
            background: rgba(0,0,0,0.02);
        }

        .stats-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .stat-card {
            background: white;
            border-radius: 10px;
            padding: 1.5rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.05);
            text-align: center;
            transition: var(--transition);
        }

        .stat-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.1);
        }

        .stat-icon {
            font-size: 2.5rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .stat-number {
            font-size: 2.5rem;
            font-weight: 700;
            margin-bottom: 0.5rem;
            background: linear-gradient(45deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }

        .stat-label {
            color: #666;
        }

        .contribution-graph {
            margin-top: 3rem;
            display: grid;
            grid-template-columns: repeat(53, 1fr);
            gap: 3px;
        }

        .contribution-cell {
            width: 10px;
            height: 10px;
            background: #ebedf0;
            border-radius: 2px;
            transition: var(--transition);
        }

        .contribution-cell:hover {
            transform: scale(1.5);
        }

        /* Projects Section */
        .projects-section {
            padding: 4rem 0;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            perspective: 1000px;
            height: 300px;
        }

        .project-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.8s;
            transform-style: preserve-3d;
        }

        .project-card:hover .project-card-inner {
            transform: rotateY(180deg);
        }

        .project-card-front, .project-card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            backface-visibility: hidden;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
        }

        .project-card-front {
            background: white;
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .project-card-back {
            background: var(--dark);
            color: var(--light);
            transform: rotateY(180deg);
            padding: 1.5rem;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .project-icon {
            font-size: 3rem;
            margin-bottom: 1rem;
            color: var(--primary);
        }

        .project-title {
            font-size: 1.5rem;
            margin-bottom: 1rem;
        }

        .project-tech {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 0.5rem;
            margin-top: 1rem;
        }

        .tech-badge {
            background: rgba(3, 102, 214, 0.1);
            color: var(--primary);
            padding: 0.3rem 0.8rem;
            border-radius: 20px;
            font-size: 0.8rem;
            transition: var(--transition);
        }

        .tech-badge:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-3px);
        }

        .project-description {
            margin-bottom: 1.5rem;
        }

        .project-links {
            display: flex;
            gap: 1rem;
            justify-content: center;
        }

        .project-link {
            color: var(--light);
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            transition: var(--transition);
        }

        .project-link:hover {
            color: var(--secondary);
        }

        /* Contact Section */
        .contact-section {
            padding: 4rem 0;
            background: rgba(0,0,0,0.02);
        }

        .contact-container {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .contact-methods {
            display: flex;
            flex-wrap: wrap;
            justify-content: center;
            gap: 2rem;
            margin-top: 2rem;
        }

        .contact-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            text-align: center;
            width: 150px;
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            background: white;
            border-radius: 50%;
            margin-bottom: 1rem;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: var(--transition);
        }

        .contact-icon:hover {
            transform: translateY(-5px) scale(1.1);
            background: var(--primary);
        }

        .contact-icon:hover svg {
            fill: white;
        }

        .contact-icon svg {
            width: 30px;
            height: 30px;
            fill: var(--primary);
            transition: var(--transition);
        }

        .contact-label {
            font-weight: 500;
            margin-bottom: 0.5rem;
        }

        .contact-info {
            color: #666;
            text-decoration: none;
            transition: var(--transition);
        }

        .contact-info:hover {
            color: var(--primary);
        }

        .availability {
            margin-top: 1.5rem;
            display: flex;
            align-items: center;
            gap: 0.5rem;
            padding: 0.5rem 1rem;
            background: rgba(40, 167, 69, 0.1);
            border-radius: 20px;
            color: var(--secondary);
        }

        .status-indicator {
            width: 10px;
            height: 10px;
            background: var(--secondary);
            border-radius: 50%;
            animation: pulse 2s infinite;
        }

        @keyframes pulse {
            0% { box-shadow: 0 0 0 0 rgba(40, 167, 69, 0.7); }
            70% { box-shadow: 0 0 0 10px rgba(40, 167, 69, 0); }
            100% { box-shadow: 0 0 0 0 rgba(40, 167, 69, 0); }
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 2rem;
            color: #666;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .name {
                font-size: 3rem;
            }
            
            .title {
                font-size: 1.5rem;
            }
            
            .section-title {
                font-size: 2rem;
            }
            
            .stat-number {
                font-size: 2rem;
            }
            
            .contribution-graph {
                grid-template-columns: repeat(26, 1fr);
            }
        }
    </style>
</head>
<body>
    <!-- 3D Animated Header -->
    <section class="header" id="header">
        <div class="particles" id="particles"></div>
        <h1 class="name">Shaurya Tayal</h1>
        <p class="title">Aspiring Software Developer</p>
    </section>

    <!-- Skills Section -->
    <section class="skills-section" id="skills">
        <div class="container">
            <h2 class="section-title">Technical Skills</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>Programming Languages</h3>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Python</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="90"></div>
                        </div>
                        <div class="skill-tooltip">5 years experience</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>C++</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="85"></div>
                        </div>
                        <div class="skill-tooltip">4 years experience</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>JavaScript</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="80"></div>
                        </div>
                        <div class="skill-tooltip">3 years experience</div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>Web Development</h3>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Flask</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="85"></div>
                        </div>
                        <div class="skill-tooltip">Used in 5 projects</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>HTML/CSS</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="90"></div>
                        </div>
                        <div class="skill-tooltip">Certified by FreeCodeCamp</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>REST APIs</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="75"></div>
                        </div>
                        <div class="skill-tooltip">3 project implementations</div>
                    </div>
                </div>
                
                <div class="skill-category">
                    <h3>Data & Blockchain</h3>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>MongoDB</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="80"></div>
                        </div>
                        <div class="skill-tooltip">Used in FraudNet.AI</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>HyperLedger</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="85"></div>
                        </div>
                        <div class="skill-tooltip">Quanta Ballet project</div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-info">
                            <span>Machine Learning</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" data-level="75"></div>
                        </div>
                        <div class="skill-tooltip">95% fraud detection accuracy</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- GitHub Stats Section -->
    <section class="stats-section" id="stats">
        <div class="container">
            <h2 class="section-title">GitHub Activity</h2>
            <div class="stats-grid">
                <div class="stat-card">
                    <div class="stat-icon">📊</div>
                    <div class="stat-number" id="repos">25</div>
                    <div class="stat-label">Repositories</div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">⭐</div>
                    <div class="stat-number" id="stars">128</div>
                    <div class="stat-label">Stars</div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">🔀</div>
                    <div class="stat-number" id="forks">42</div>
                    <div class="stat-label">Forks</div>
                </div>
                <div class="stat-card">
                    <div class="stat-icon">🔥</div>
                    <div class="stat-number" id="streak">86</div>
                    <div class="stat-label">Day Streak</div>
                </div>
            </div>
            
            <div class="contribution-graph" id="contributions">
                <!-- Contribution cells will be generated by JS -->
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section class="projects-section" id="projects">
        <div class="container">
            <h2 class="section-title">Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-card-inner">
                        <div class="project-card-front">
                            <div class="project-icon">🔍</div>
                            <h3 class="project-title">FraudNet.AI</h3>
                            <p>Real-time fraud detection system</p>
                            <div class="project-tech">
                                <span class="tech-badge">Python</span>
                                <span class="tech-badge">ML</span>
                                <span class="tech-badge">Blockchain</span>
                            </div>
                        </div>
                        <div class="project-card-back">
                            <p class="project-description">Built a real-time fraud detection system using machine learning and blockchain audit logs achieving 95% detection accuracy on financial datasets.</p>
                            <div class="project-links">
                                <a href="#" class="project-link">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                                    GitHub
                                </a>
                                <a href="#" class="project-link">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2 19l-1.5-1.5 6-6-6-6 1.5-1.5 7.5 7.5-7.5 7.5z"/></svg>
                                    Demo
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-card-inner">
                        <div class="project-card-front">
                            <div class="project-icon">🗳️</div>
                            <h3 class="project-title">Quanta Ballet</h3>
                            <p>Decentralized voting platform</p>
                            <div class="project-tech">
                                <span class="tech-badge">HyperLedger</span>
                                <span class="tech-badge">Solidity</span>
                                <span class="tech-badge">Flask</span>
                            </div>
                        </div>
                        <div class="project-card-back">
                            <p class="project-description">Developed a tamper-proof voting platform with secure smart contract logic for voter validation and result tallying.</p>
                            <div class="project-links">
                                <a href="#" class="project-link">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                                    GitHub
                                </a>
                                <a href="#" class="project-link">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2 19l-1.5-1.5 6-6-6-6 1.5-1.5 7.5 7.5-7.5 7.5z"/></svg>
                                    Demo
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-card-inner">
                        <div class="project-card-front">
                            <div class="project-icon">🚦</div>
                            <h3 class="project-title">Smart Traffic Management</h3>
                            <p>AI-powered traffic control</p>
                            <div class="project-tech">
                                <span class="tech-badge">Python</span>
                                <span class="tech-badge">OpenAI</span>
                                <span class="tech-badge">Sensors</span>
                            </div>
                        </div>
                        <div class="project-card-back">
                            <p class="project-description">Automated traffic light control using real-time camera input and OpenAI model logic, replacing manual intervention.</p>
                            <div class="project-links">
                                <a href="#" class="project-link">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                                    GitHub
                                </a>
                                <a href="#" class="project-link">
                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M12 0c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm-2 19l-1.5-1.5 6-6-6-6 1.5-1.5 7.5 7.5-7.5 7.5z"/></svg>
                                    Demo
                                </a>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section class="contact-section" id="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-container">
                <div class="contact-methods">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 12.713l-11.985-9.713h23.97l-11.985 9.713zm0 2.574l-12-9.725v15.438h24v-15.438l-12 9.725z"/></svg>
                        </div>
                        <span class="contact-label">Email</span>
                        <a href="mailto:shouriyatay1234@gmail.com" class="contact-info">shouriyatay1234@gmail.com</a>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M19 0h-14c-2.761 0-5 2.239-5 5v14c0 2.761 2.239 5 5 5h14c2.762 0 5-2.239 5-5v-14c0-2.761-2.238-5-5-5zm-11 19h-3v-11h3v11zm-1.5-12.268c-.966 0-1.75-.79-1.75-1.764s.784-1.764 1.75-1.764 1.75.79 1.75 1.764-.783 1.764-1.75 1.764zm13.5 12.268h-3v-5.604c0-3.368-4-3.113-4 0v5.604h-3v-11h3v1.765c1.396-2.586 7-2.777 7 2.476v6.759z"/></svg>
                        </div>
                        <span class="contact-label">LinkedIn</span>
                        <a href="https://linkedin.com/in/shaurya_wizard" class="contact-info">shaurya_wizard</a>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z"/></svg>
                        </div>
                        <span class="contact-label">GitHub</span>
                        <a href="https://github.com/ishouriya" class="contact-info">ishouriya</a>
                    </div>
                    
                    <div class="contact-item">
                        <div class="contact-icon">
                            <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path d="M12 2c5.514 0 10 4.486 10 10s-4.486 10-10 10-10-4.486-10-10 4.486-10 10-10zm0-2c-6.627 0-12 5.373-12 12s5.373 12 12 12 12-5.373 12-12-5.373-12-12-12zm6 13h-5v5h-2v-5h-5v-2h5v-5h2v5h5v2z"/></svg>
                        </div>
                        <span class="contact-label">Location</span>
                        <span class="contact-info">Phagwara, Punjab, India</span>
                    </div>
                </div>
                
                <div class="availability">
                    <div class="status-indicator"></div>
                    <span>Available for opportunities</span>
                </div>
            </div>
        </div>
    </section>

    <footer>
        <div class="container">
            <p>© 2025 Shaurya Tayal | Aspiring Software Developer</p>
        </div>
    </footer>

    <script>
        // Create particles for header background
        function createParticles() {
            const particlesContainer = document.getElementById('particles');
            const particleCount = 30;
            
            for (let i = 0; i < particleCount; i++) {
                const particle = document.createElement('div');
                particle.classList.add('particle');
                
                // Random properties
                const size = Math.random() * 20 + 5;
                const posX = Math.random() * 100;
                const posY = Math.random() * 100;
                const delay = Math.random() * 5;
                const duration = Math.random() * 10 + 10;
                
                particle.style.width = `${size}px`;
                particle.style.height = `${size}px`;
                particle.style.left = `${posX}%`;
                particle.style.top = `${posY}%`;
                particle.style.animation = `float ${duration}s ${delay}s infinite ease-in-out`;
                
                particlesContainer.appendChild(particle);
            }
        }
        
        // Initialize progress bars
        function initProgressBars() {
            const progressBars = document.querySelectorAll('.skill-progress');
            progressBars.forEach(bar => {
                const level = bar.getAttribute('data-level');
                bar.style.width = `${level}%`;
            });
        }
        
        // Generate GitHub contribution graph
        function generateContributionGraph() {
            const graph = document.getElementById('contributions');
            const cellCount = 364; // 52 weeks * 7 days
            
            for (let i = 0; i < cellCount; i++) {
                const cell = document.createElement('div');
                cell.classList.add('contribution-cell');
                
                // Random contribution intensity
                const intensity = Math.floor(Math.random() * 5);
                const colors = [
                    '#ebedf0', 
                    '#9be9a8', 
                    '#40c463', 
                    '#30a14e', 
                    '#216e39'
                ];
                
                cell.style.background = colors[intensity];
                graph.appendChild(cell);
            }
        }
        
        // Initialize counters
        function initCounters() {
            const counters = document.querySelectorAll('.stat-number');
            const values = [25, 128, 42, 86]; // Repos, Stars, Forks, Streak
            
            counters.forEach((counter, index) => {
                let current = 0;
                const target = values[index];
                const increment = target / 100;
                
                const updateCounter = () => {
                    if (current < target) {
                        current += increment;
                        counter.textContent = Math.ceil(current);
                        setTimeout(updateCounter, 20);
                    } else {
                        counter.textContent = target;
                    }
                };
                
                updateCounter();
            });
        }
        
        // Initialize everything
        document.addEventListener('DOMContentLoaded', () => {
            createParticles();
            initProgressBars();
            generateContributionGraph();
            initCounters();
            
            // Accessibility: Add keyboard navigation
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Tab') {
                    document.documentElement.classList.add('keyboard-nav');
                }
            });
            
            document.addEventListener('mousedown', () => {
                document.documentElement.classList.remove('keyboard-nav');
            });
        });
    </script>
</body>
</html>
