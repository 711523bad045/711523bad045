<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Rajesh N - Full Stack Developer</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #667eea;
            --secondary: #764ba2;
            --dark-bg: #0a0a1a;
            --card-bg: rgba(20, 20, 40, 0.8);
            --text-primary: #ffffff;
            --text-secondary: #a0a0c0;
            --accent: #61dafb;
        }

        body {
            font-family: 'Inter', 'Segoe UI', system-ui, -apple-system, sans-serif;
            background: linear-gradient(135deg, #0a0a1a 0%, #1a1a3e 100%);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1400px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            background: radial-gradient(circle at 30% 50%, rgba(102, 126, 234, 0.15), transparent 50%),
                        radial-gradient(circle at 70% 50%, rgba(118, 75, 162, 0.15), transparent 50%);
            animation: pulse 8s ease-in-out infinite;
        }

        @keyframes pulse {
            0%, 100% { opacity: 0.5; }
            50% { opacity: 1; }
        }

        .hero-content {
            text-align: center;
            position: relative;
            z-index: 1;
            padding: 60px 20px;
        }

        .hero-title {
            font-size: clamp(3rem, 8vw, 6rem);
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 20px;
            line-height: 1.2;
        }

        .hero-subtitle {
            font-size: clamp(1.2rem, 3vw, 1.8rem);
            color: var(--text-secondary);
            margin-bottom: 30px;
            font-weight: 300;
        }

        .hero-description {
            font-size: 1.1rem;
            color: var(--text-secondary);
            max-width: 700px;
            margin: 0 auto 40px;
            line-height: 1.8;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            justify-content: center;
            flex-wrap: wrap;
            margin-bottom: 40px;
        }

        .btn {
            padding: 14px 32px;
            border-radius: 50px;
            text-decoration: none;
            font-weight: 600;
            transition: all 0.3s ease;
            display: inline-block;
            font-size: 1rem;
        }

        .btn-primary {
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            color: white;
            box-shadow: 0 4px 15px rgba(102, 126, 234, 0.4);
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 6px 25px rgba(102, 126, 234, 0.6);
        }

        .btn-outline {
            border: 2px solid var(--primary);
            color: var(--primary);
            background: transparent;
        }

        .btn-outline:hover {
            background: var(--primary);
            color: white;
        }

        .social-links {
            display: flex;
            gap: 15px;
            justify-content: center;
            margin-top: 30px;
        }

        .social-link {
            width: 50px;
            height: 50px;
            border-radius: 50%;
            background: var(--card-bg);
            border: 1px solid rgba(102, 126, 234, 0.3);
            display: flex;
            align-items: center;
            justify-content: center;
            transition: all 0.3s ease;
            text-decoration: none;
            color: var(--primary);
            font-weight: 600;
        }

        .social-link:hover {
            background: var(--primary);
            color: white;
            transform: translateY(-5px);
            box-shadow: 0 5px 20px rgba(102, 126, 234, 0.4);
        }

        /* Stats Section */
        .stats {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
            gap: 30px;
            padding: 80px 0;
            max-width: 1000px;
            margin: 0 auto;
        }

        .stat-card {
            text-align: center;
            padding: 30px;
            background: var(--card-bg);
            border-radius: 15px;
            border: 1px solid rgba(102, 126, 234, 0.2);
            transition: all 0.3s ease;
        }

        .stat-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .stat-number {
            font-size: 3rem;
            font-weight: 800;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .stat-label {
            color: var(--text-secondary);
            margin-top: 10px;
            font-size: 1rem;
        }

        /* Section Styles */
        .section {
            padding: 100px 0;
        }

        .section-header {
            text-align: center;
            margin-bottom: 60px;
        }

        .section-title {
            font-size: clamp(2.5rem, 5vw, 3.5rem);
            font-weight: 700;
            margin-bottom: 15px;
            background: linear-gradient(135deg, var(--primary), var(--secondary));
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
        }

        .section-subtitle {
            color: var(--text-secondary);
            font-size: 1.1rem;
            max-width: 600px;
            margin: 0 auto;
        }

        /* Projects Grid */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(500px, 1fr));
            gap: 40px;
        }

        .project-card {
            background: var(--card-bg);
            border-radius: 20px;
            padding: 40px;
            border: 1px solid rgba(102, 126, 234, 0.2);
            transition: all 0.4s ease;
            position: relative;
            overflow: hidden;
        }

        .project-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, rgba(102, 126, 234, 0.1), rgba(118, 75, 162, 0.1));
            opacity: 0;
            transition: opacity 0.4s ease;
        }

        .project-card:hover {
            transform: translateY(-10px);
            border-color: var(--primary);
            box-shadow: 0 20px 50px rgba(102, 126, 234, 0.3);
        }

        .project-card:hover::before {
            opacity: 1;
        }

        .project-content {
            position: relative;
            z-index: 1;
        }

        .project-header {
            margin-bottom: 20px;
        }

        .project-title {
            font-size: 1.8rem;
            font-weight: 700;
            margin-bottom: 10px;
            color: var(--text-primary);
        }

        .project-subtitle {
            color: var(--text-secondary);
            font-size: 1.1rem;
            font-weight: 500;
        }

        .tech-stack {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin: 20px 0;
        }

        .tech-badge {
            padding: 8px 16px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 600;
            background: rgba(102, 126, 234, 0.2);
            color: var(--accent);
            border: 1px solid rgba(102, 126, 234, 0.3);
        }

        .project-description {
            color: var(--text-secondary);
            line-height: 1.8;
            margin-bottom: 20px;
        }

        .project-features {
            list-style: none;
            margin: 20px 0;
        }

        .project-features li {
            padding: 10px 0;
            padding-left: 30px;
            position: relative;
            color: var(--text-secondary);
        }

        .project-features li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--primary);
            font-weight: bold;
            font-size: 1.2rem;
        }

        .project-links {
            display: flex;
            gap: 15px;
            margin-top: 25px;
        }

        .project-link {
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 600;
            font-size: 0.9rem;
            transition: all 0.3s ease;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .project-link-primary {
            background: var(--primary);
            color: white;
        }

        .project-link-primary:hover {
            background: var(--secondary);
            transform: translateX(5px);
        }

        /* Experience Timeline */
        .timeline {
            max-width: 900px;
            margin: 0 auto;
        }

        .timeline-item {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            border-left: 4px solid var(--primary);
            margin-bottom: 30px;
            transition: all 0.3s ease;
        }

        .timeline-item:hover {
            transform: translateX(10px);
            border-color: var(--secondary);
        }

        .timeline-date {
            color: var(--primary);
            font-weight: 600;
            margin-bottom: 10px;
        }

        .timeline-title {
            font-size: 1.5rem;
            font-weight: 700;
            margin-bottom: 10px;
        }

        .timeline-description {
            color: var(--text-secondary);
            line-height: 1.8;
        }

        /* Skills Grid */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            max-width: 1200px;
            margin: 0 auto;
        }

        .skill-category {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            border: 1px solid rgba(102, 126, 234, 0.2);
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .skill-category h3 {
            color: var(--primary);
            font-size: 1.5rem;
            margin-bottom: 20px;
            font-weight: 700;
        }

        .skill-list {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
        }

        .skill-tag {
            padding: 8px 16px;
            background: rgba(102, 126, 234, 0.1);
            border: 1px solid rgba(102, 126, 234, 0.3);
            border-radius: 20px;
            color: var(--text-primary);
            font-size: 0.9rem;
        }

        /* Contact Section */
        .contact-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            max-width: 1000px;
            margin: 0 auto;
        }

        .contact-card {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            text-align: center;
            border: 1px solid rgba(102, 126, 234, 0.2);
            transition: all 0.3s ease;
        }

        .contact-card:hover {
            border-color: var(--primary);
            transform: translateY(-5px);
        }

        .contact-icon {
            font-size: 2.5rem;
            margin-bottom: 15px;
        }

        .contact-label {
            color: var(--text-secondary);
            margin-bottom: 10px;
            font-size: 0.9rem;
            text-transform: uppercase;
            letter-spacing: 1px;
        }

        .contact-value {
            color: var(--primary);
            font-size: 1.1rem;
            font-weight: 600;
            text-decoration: none;
            display: block;
        }

        .contact-value:hover {
            color: var(--secondary);
        }

        /* Footer */
        footer {
            background: var(--card-bg);
            padding: 40px 20px;
            text-align: center;
            border-top: 1px solid rgba(102, 126, 234, 0.2);
            margin-top: 100px;
        }

        .footer-text {
            color: var(--text-secondary);
        }

        /* Responsive */
        @media (max-width: 768px) {
            .projects-grid {
                grid-template-columns: 1fr;
            }

            .stats {
                grid-template-columns: repeat(2, 1fr);
            }

            .hero-title {
                font-size: 3rem;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .btn {
                width: 100%;
                max-width: 300px;
            }
        }

        /* Smooth Scroll */
        html {
            scroll-behavior: smooth;
        }

        /* Animations */
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

        .fade-in-up {
            animation: fadeInUp 0.6s ease-out;
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="container">
            <div class="hero-content fade-in-up">
                <h1 class="hero-title">Rajesh N</h1>
                <p class="hero-subtitle">Full Stack Developer | AI Enthusiast | Competitive Programmer</p>
                <p class="hero-description">
                    Pre-final year student specializing in AI & Data Science, building production-ready applications 
                    with 2 years of consistent coding and 6+ delivered client projects.
                </p>
                <div class="cta-buttons">
                    <a href="#projects" class="btn btn-primary">View My Work</a>
                    <a href="#contact" class="btn btn-outline">Get In Touch</a>
                </div>
                <div class="social-links">
                    <a href="https://github.com/711523bad045" target="_blank" class="social-link" title="GitHub">GH</a>
                    <a href="https://linkedin.com/in/rajesh-n-4922622a6" target="_blank" class="social-link" title="LinkedIn">LI</a>
                    <a href="https://leetcode.com/u/rajeshkit/" target="_blank" class="social-link" title="LeetCode">LC</a>
                    <a href="https://www.codechef.com/users/kit27ad45" target="_blank" class="social-link" title="CodeChef">CC</a>
                    <a href="mailto:kit27.ad45@gmail.com" class="social-link" title="Email">✉</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Stats Section -->
    <div class="container">
        <div class="stats">
            <div class="stat-card fade-in-up">
                <div class="stat-number">1000+</div>
                <div class="stat-label">Problems Solved</div>
            </div>
            <div class="stat-card fade-in-up">
                <div class="stat-number">6+</div>
                <div class="stat-label">Client Projects</div>
            </div>
            <div class="stat-card fade-in-up">
                <div class="stat-number">2</div>
                <div class="stat-label">Years Coding</div>
            </div>
            <div class="stat-card fade-in-up">
                <div class="stat-number">7.71</div>
                <div class="stat-label">CGPA</div>
            </div>
        </div>
    </div>

    <!-- Projects Section -->
    <section id="projects" class="section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Featured Projects</h2>
                <p class="section-subtitle">Production-ready applications built with modern technologies</p>
            </div>

            <div class="projects-grid">
                <!-- TNPSC Learning Hub -->
                <div class="project-card">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">TNPSC Learning Hub</h3>
                            <p class="project-subtitle">Government Exam Preparation Platform</p>
                        </div>

                        <div class="tech-stack">
                            <span class="tech-badge">React.js</span>
                            <span class="tech-badge">Node.js</span>
                            <span class="tech-badge">MySQL</span>
                            <span class="tech-badge">REST API</span>
                        </div>

                        <p class="project-description">
                            Full-stack learning platform featuring comprehensive exam preparation tools, 
                            user authentication, video lectures, and progress tracking systems.
                        </p>

                        <ul class="project-features">
                            <li>Secure JWT-based authentication system</li>
                            <li>RESTful API architecture for scalable data management</li>
                            <li>Real-time progress tracking and analytics</li>
                            <li>Responsive design optimized for all devices</li>
                            <li>Video lecture integration with buffering optimization</li>
                        </ul>

                        <div class="project-links">
                            <a href="#contact" class="project-link project-link-primary">View Details →</a>
                        </div>
                    </div>
                </div>

                <!-- Employee Management System -->
                <div class="project-card">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">Employee Management System</h3>
                            <p class="project-subtitle">Enterprise-Grade EMS Solution</p>
                        </div>

                        <div class="tech-stack">
                            <span class="tech-badge">Python</span>
                            <span class="tech-badge">JavaScript</span>
                            <span class="tech-badge">MySQL</span>
                            <span class="tech-badge">JWT</span>
                        </div>

                        <p class="project-description">
                            Production-ready employee management system replacing traditional Excel workflows 
                            with modern, secure, and efficient digital solutions.
                        </p>

                        <ul class="project-features">
                            <li>Complete CRUD operations for employee data</li>
                            <li>Role-based access control (RBAC) system</li>
                            <li>Secure JWT authentication and authorization</li>
                            <li>Advanced task tracking and assignment features</li>
                            <li>Automated reporting and analytics dashboard</li>
                        </ul>

                        <div class="project-links">
                            <a href="#contact" class="project-link project-link-primary">View Details →</a>
                        </div>
                    </div>
                </div>

                <!-- AI Knowledge Assistant -->
                <div class="project-card">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">AI Knowledge Assistant</h3>
                            <p class="project-subtitle">Intelligent Study Companion</p>
                        </div>

                        <div class="tech-stack">
                            <span class="tech-badge">React.js</span>
                            <span class="tech-badge">Python</span>
                            <span class="tech-badge">FastAPI</span>
                            <span class="tech-badge">AI/ML</span>
                            <span class="tech-badge">NLP</span>
                        </div>

                        <p class="project-description">
                            Advanced AI-powered knowledge assistant leveraging natural language processing 
                            and machine learning for intelligent Q&A and contextual understanding.
                        </p>

                        <ul class="project-features">
                            <li>GPT integration for intelligent responses</li>
                            <li>Context-aware conversation management</li>
                            <li>Natural language processing capabilities</li>
                            <li>User authentication and personalization</li>
                            <li>Async FastAPI backend for optimal performance</li>
                            <li>Modern React UI with hooks and state management</li>
                        </ul>

                        <div class="project-links">
                            <a href="https://github.com/711523bad045/AI-Knowledge-Assistant" target="_blank" class="project-link project-link-primary">View Repository →</a>
                        </div>
                    </div>
                </div>

                <!-- Company Intelligence AI -->
                <div class="project-card">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">Company Intelligence AI</h3>
                            <p class="project-subtitle">Business Intelligence Automation</p>
                        </div>

                        <div class="tech-stack">
                            <span class="tech-badge">Python</span>
                            <span class="tech-badge">HTML5</span>
                            <span class="tech-badge">BeautifulSoup</span>
                            <span class="tech-badge">Selenium</span>
                            <span class="tech-badge">NLP</span>
                        </div>

                        <p class="project-description">
                            Automated company intelligence gathering system using web scraping, NLP, 
                            and AI to extract comprehensive business insights from company domains.
                        </p>

                        <ul class="project-features">
                            <li>Automated web scraping and data aggregation</li>
                            <li>AI-powered data extraction and categorization</li>
                            <li>Company profile generation and analysis</li>
                            <li>Market positioning and competitive insights</li>
                            <li>Personnel identification and org mapping</li>
                            <li>Ethical scraping of public information only</li>
                        </ul>

                        <div class="project-links">
                            <a href="https://github.com/711523bad045/Company_intelligence-Ai" target="_blank" class="project-link project-link-primary">View Repository →</a>
                        </div>
                    </div>
                </div>

                <!-- Dynamic School Website -->
                <div class="project-card">
                    <div class="project-content">
                        <div class="project-header">
                            <h3 class="project-title">Dynamic School Website</h3>
                            <p class="project-subtitle">Interactive Educational Portal</p>
                        </div>

                        <div class="tech-stack">
                            <span class="tech-badge">HTML5</span>
                            <span class="tech-badge">CSS3</span>
                            <span class="tech-badge">JavaScript</span>
                            <span class="tech-badge">Local Storage</span>
                        </div>

                        <p class="project-description">
                            Fully responsive multi-page school website with dynamic features, user authentication, 
                            and comprehensive information architecture for admissions and curriculum.
                        </p>

                        <ul class="project-features">
                            <li>Clean, modern UI with structured navigation</li>
                            <li>Login and signup functionality using Local Storage</li>
                            <li>Dynamic sections for curriculum and facilities</li>
                            <li>Fully responsive across all device sizes</li>
                            <li>Interactive forms with client-side validation</li>
                        </ul>

                        <div class="project-links">
                            <a href="#contact" class="project-link project-link-primary">View Details →</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="section" style="background: rgba(10, 10, 26, 0.5);">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Experience</h2>
                <p class="section-subtitle">Professional development journey</p>
            </div>

            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-date">June 2025 - Present</div>
                    <h3 class="timeline-title">Freelance Full Stack Developer</h3>
                    <div class="timeline-description">
                        <p style="margin-bottom: 10px;">Coimbatore, India (Remote)</p>
                        <ul style="margin-left: 20px; color: var(--text-secondary); line-height: 1.8;">
                            <li>Delivered 6+ production-ready full-stack web applications for real clients</li>
                            <li>Collaborated with senior developer (10+ years IT experience) on enterprise projects</li>
                            <li>Managed end-to-end development lifecycle from requirements to deployment</li>
                            <li>Implemented modern tech stacks including React, Node.js, Python, and MySQL</li>
                            <li>Ensured code quality, scalability, and optimal performance across all projects</li>
                        </ul>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="timeline-date">2023 - 2027</div>
                    <h3 class="timeline-title">B.Tech in AI & Data Science</h3>
                    <div class="timeline-description">
                        <p style="margin-bottom: 10px;">KIT - Kalaignarkarunanidhi Institute of Technology</p>
                        <p style="color: var(--text-secondary);">Current CGPA: 7.71/10.0 | Pre-Final Year</p>
                        <p style="color: var(--text-secondary); margin-top: 10px;">
                            Coursework: Data Science, Computer Networks, Operating Systems, Database Management Systems, 
                            Machine Learning, Deep Learning, Artificial Intelligence
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Technical Skills</h2>
                <p class="section-subtitle">Technologies and tools I work with</p>
            </div>

            <div class="skills-grid">
                <div class="skill-category">
                    <h3>Programming Languages</h3>
                    <div class="skill-list">
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">C</span>
                        <span class="skill-tag">Java</span>
                        <span class="skill-tag">SQL</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Frontend Development</h3>
                    <div class="skill-list">
                        <span class="skill-tag">React.js</span>
                        <span class="skill-tag">HTML5</span>
                        <span class="skill-tag">CSS3</span>
                        <span class="skill-tag">JavaScript (ES6+)</span>
                        <span class="skill-tag">Responsive Design</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Backend Development</h3>
                    <div class="skill-list">
                        <span class="skill-tag">Node.js</span>
                        <span class="skill-tag">Python</span>
                        <span class="skill-tag">Flask</span>
                        <span class="skill-tag">FastAPI</span>
                        <span class="skill-tag">REST APIs</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Databases</h3>
                    <div class="skill-list">
                        <span class="skill-tag">MySQL</span>
                        <span class="skill-tag">MongoDB</span>
                        <span class="skill-tag">Database Design</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>AI & Machine Learning</h3>
                    <div class="skill-list">
                        <span class="skill-tag">Machine Learning</span>
                        <span class="skill-tag">NLP</span>
                        <span class="skill-tag">Deep Learning</span>
                        <span class="skill-tag">Data Analysis</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Tools & Technologies</h3>
                    <div class="skill-list">
                        <span class="skill-tag">Git</span>
                        <span class="skill-tag">GitHub</span>
                        <span class="skill-tag">Postman</span>
                        <span class="skill-tag">VS Code</span>
                        <span class="skill-tag">JWT</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Competitive Programming</h3>
                    <div class="skill-list">
                        <span class="skill-tag">LeetCode (1600 rating)</span>
                        <span class="skill-tag">CodeChef (2★)</span>
                        <span class="skill-tag">DSA</span>
                        <span class="skill-tag">Problem Solving</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>Other Skills</h3>
                    <div class="skill-list">
                        <span class="skill-tag">Data Structures</span>
                        <span class="skill-tag">Algorithms</span>
                        <span class="skill-tag">OOP</span>
                        <span class="skill-tag">Web Scraping</span>
                        <span class="skill-tag">API Development</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Achievements Section -->
    <section class="section" style="background: rgba(10, 10, 26, 0.5);">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Achievements</h2>
                <p class="section-subtitle">Milestones and recognition</p>
            </div>

            <div class="skills-grid">
                <div class="skill-category">
                    <h3>🏆 Competitive Programming</h3>
                    <div class="timeline-description">
                        <ul style="margin-left: 20px; color: var(--text-secondary); line-height: 1.8;">
                            <li><strong>LeetCode:</strong> Max rating 1600 | 300+ problems | Top 23.6% globally</li>
                            <li><strong>CodeChef:</strong> 2★ rating (1450) | 500+ problems solved | Global rank 38,915</li>
                            <li><strong>CodeForces:</strong> 30+ problems solved</li>
                            <li><strong>Coding Ninjas:</strong> 50+ problems solved</li>
                        </ul>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>🎯 Awards & Recognition</h3>
                    <div class="timeline-description">
                        <ul style="margin-left: 20px; color: var(--text-secondary); line-height: 1.8;">
                            <li>2nd Prize in Debugging Competition at KPR College</li>
                            <li>GitHub Achievement for highest project contributions (2nd year)</li>
                            <li>Published research paper in Scopus: "CNN-LSTM Based Cloudburst Warning System"</li>
                        </ul>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>📜 Certifications</h3>
                    <div class="timeline-description">
                        <ul style="margin-left: 20px; color: var(--text-secondary); line-height: 1.8;">
                            <li>6+ Coursera certifications (AI, AWS, UX Design)</li>
                            <li>3+ Infosys Springboard certifications</li>
                            <li>NPTEL Soft Skills Development</li>
                            <li>Various technical internships and workshops</li>
                        </ul>
                    </div>
                </div>

                <div class="skill-category">
                    <h3>🤝 Community Involvement</h3>
                    <div class="timeline-description">
                        <ul style="margin-left: 20px; color: var(--text-secondary); line-height: 1.8;">
                            <li>Mentored 20+ first-year students in coding fundamentals</li>
                            <li>Blood donor with 5+ donations</li>
                            <li>Active participant in college workshops and events</li>
                            <li>Open-source contributor</li>
                        </ul>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section">
        <div class="container">
            <div class="section-header">
                <h2 class="section-title">Get In Touch</h2>
                <p class="section-subtitle">Open to opportunities, collaborations, and interesting projects</p>
            </div>

            <div class="contact-grid">
                <div class="contact-card">
                    <div class="contact-icon">📧</div>
                    <div class="contact-label">Email</div>
                    <a href="mailto:kit27.ad45@gmail.com" class="contact-value">kit27.ad45@gmail.com</a>
                </div>

                <div class="contact-card">
                    <div class="contact-icon">📱</div>
                    <div class="contact-label">Phone</div>
                    <a href="tel:+919751247267" class="contact-value">+91 9751247267</a>
                </div>

                <div class="contact-card">
                    <div class="contact-icon">💼</div>
                    <div class="contact-label">LinkedIn</div>
                    <a href="https://linkedin.com/in/rajesh-n-4922622a6" target="_blank" class="contact-value">Connect with me</a>
                </div>

                <div class="contact-card">
                    <div class="contact-icon">💻</div>
                    <div class="contact-label">GitHub</div>
                    <a href="https://github.com/711523bad045" target="_blank" class="contact-value">View my code</a>
                </div>
            </div>

            <div style="text-align: center; margin-top: 50px;">
                <p style="color: var(--text-secondary); font-size: 1.1rem; margin-bottom: 20px;">
                    📍 Based in Coimbatore, Tamil Nadu, India
                </p>
                <p style="color: var(--primary); font-size: 1.2rem; font-weight: 600;">
                    Currently open for Full-time positions, Internships, and Freelance projects
                </p>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <p class="footer-text">© 2025 Rajesh N. All rights reserved.</p>
            <p class="footer-text" style="margin-top: 10px; font-size: 0.9rem;">
                Built with passion, powered by code ☕
            </p>
        </div>
    </footer>

    <script>
        // Smooth scroll
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

        // Intersection Observer for animations
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -50px 0px'
        };

        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = '0';
                    entry.target.style.transform = 'translateY(30px)';
                    setTimeout(() => {
                        entry.target.style.transition = 'all 0.6s ease-out';
                        entry.target.style.opacity = '1';
                        entry.target.style.transform = 'translateY(0)';
                    }, 100);
                    observer.unobserve(entry.target);
                }
            });
        }, observerOptions);

        // Observe all cards and sections
        document.querySelectorAll('.project-card, .skill-category, .timeline-item, .stat-card, .contact-card').forEach(el => {
            observer.observe(el);
        });

        // Add parallax effect to hero
        window.addEventListener('scroll', () => {
            const scrolled = window.pageYOffset;
            const hero = document.querySelector('.hero-content');
            if (hero && scrolled < window.innerHeight) {
                hero.style.transform = `translateY(${scrolled * 0.5}px)`;
                hero.style.opacity = 1 - (scrolled / window.innerHeight);
            }
        });
    </script>
</body>
</html
