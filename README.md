<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Developer Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #e4e6ea;
            background: linear-gradient(135deg, #0d1117 0%, #1a1e23 100%);
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header */
        header {
            background: rgba(13, 17, 23, 0.95);
            backdrop-filter: blur(10px);
            position: fixed;
            top: 0;
            width: 100%;
            z-index: 1000;
            border-bottom: 1px solid #21262d;
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 1rem 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: bold;
            color: #58a6ff;
        }

        .nav-links {
            display: flex;
            list-style: none;
            gap: 2rem;
        }

        .nav-links a {
            color: #e4e6ea;
            text-decoration: none;
            transition: color 0.3s ease;
        }

        .nav-links a:hover {
            color: #58a6ff;
        }

        /* Hero Section */
        .hero {
            height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            text-align: center;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(88, 166, 255, 0.1) 0%, transparent 50%);
            animation: pulse 8s ease-in-out infinite;
            z-index: -1;
        }

        @keyframes pulse {
            0%, 100% { transform: scale(1); opacity: 0.5; }
            50% { transform: scale(1.1); opacity: 0.8; }
        }

        .hero-content h1 {
            font-size: 3.5rem;
            margin-bottom: 1rem;
            background: linear-gradient(135deg, #58a6ff, #79c0ff);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: slideInUp 1s ease-out;
        }

        .hero-content .subtitle {
            font-size: 1.2rem;
            margin-bottom: 2rem;
            color: #8b949e;
            animation: slideInUp 1s ease-out 0.2s both;
        }

        .cta-buttons {
            display: flex;
            gap: 1rem;
            justify-content: center;
            flex-wrap: wrap;
            animation: slideInUp 1s ease-out 0.4s both;
        }

        .btn {
            padding: 12px 30px;
            border: none;
            border-radius: 8px;
            text-decoration: none;
            font-weight: bold;
            transition: all 0.3s ease;
            cursor: pointer;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #238636, #2ea043);
            color: white;
        }

        .btn-primary:hover {
            transform: translateY(-2px);
            box-shadow: 0 8px 25px rgba(46, 160, 67, 0.3);
        }

        .btn-secondary {
            background: transparent;
            color: #58a6ff;
            border: 2px solid #58a6ff;
        }

        .btn-secondary:hover {
            background: #58a6ff;
            color: #0d1117;
            transform: translateY(-2px);
        }

        /* Sections */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            font-size: 2.5rem;
            margin-bottom: 3rem;
            color: #58a6ff;
        }

        /* About Section */
        .about {
            background: rgba(21, 26, 33, 0.5);
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 2fr;
            gap: 3rem;
            align-items: center;
        }

        .profile-img {
            width: 300px;
            height: 300px;
            border-radius: 50%;
            background: linear-gradient(135deg, #58a6ff, #79c0ff);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 6rem;
            color: #0d1117;
            margin: 0 auto;
            animation: float 6s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .about-text {
            font-size: 1.1rem;
            line-height: 1.8;
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
            margin-top: 2rem;
        }

        .skill-card {
            background: rgba(33, 38, 45, 0.8);
            padding: 2rem;
            border-radius: 12px;
            border: 1px solid #21262d;
            transition: all 0.3s ease;
            position: relative;
            overflow: hidden;
        }

        .skill-card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(88, 166, 255, 0.1), transparent);
            transition: left 0.5s;
        }

        .skill-card:hover::before {
            left: 100%;
        }

        .skill-card:hover {
            transform: translateY(-5px);
            border-color: #58a6ff;
            box-shadow: 0 10px 30px rgba(88, 166, 255, 0.1);
        }

        .skill-card h3 {
            color: #58a6ff;
            margin-bottom: 1rem;
            font-size: 1.3rem;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .skill-tag {
            background: rgba(88, 166, 255, 0.1);
            color: #58a6ff;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.9rem;
            border: 1px solid rgba(88, 166, 255, 0.3);
        }

        /* Projects Section */
        .projects {
            background: rgba(21, 26, 33, 0.5);
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: rgba(33, 38, 45, 0.9);
            border-radius: 12px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 1px solid #21262d;
            position: relative;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
        }

        .project-header {
            padding: 1.5rem;
            border-bottom: 1px solid #21262d;
        }

        .project-title {
            color: #58a6ff;
            font-size: 1.4rem;
            margin-bottom: 0.5rem;
        }

        .project-desc {
            color: #8b949e;
            line-height: 1.6;
        }

        .project-tech {
            padding: 1rem 1.5rem;
            display: flex;
            flex-wrap: wrap;
            gap: 0.5rem;
        }

        .tech-tag {
            background: rgba(255, 123, 114, 0.1);
            color: #ff7b72;
            padding: 4px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            border: 1px solid rgba(255, 123, 114, 0.3);
        }

        .project-links {
            padding: 1.5rem;
            display: flex;
            gap: 1rem;
        }

        .project-link {
            padding: 8px 16px;
            background: transparent;
            border: 1px solid #58a6ff;
            color: #58a6ff;
            text-decoration: none;
            border-radius: 6px;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }

        .project-link:hover {
            background: #58a6ff;
            color: #0d1117;
        }

        /* Contact Section */
        .contact-content {
            max-width: 600px;
            margin: 0 auto;
            text-align: center;
        }

        .contact-info {
            display: flex;
            justify-content: center;
            gap: 3rem;
            margin-top: 2rem;
            flex-wrap: wrap;
        }

        .contact-item {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 1rem;
        }

        .contact-icon {
            width: 60px;
            height: 60px;
            background: linear-gradient(135deg, #58a6ff, #79c0ff);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 1.5rem;
            color: #0d1117;
        }

        .contact-link {
            color: #58a6ff;
            text-decoration: none;
            font-weight: bold;
            transition: color 0.3s ease;
        }

        .contact-link:hover {
            color: #79c0ff;
        }

        /* Footer */
        footer {
            background: #0d1117;
            padding: 2rem 0;
            text-align: center;
            border-top: 1px solid #21262d;
        }

        .footer-content {
            color: #8b949e;
        }

        /* Animations */
        @keyframes slideInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Responsive Design */
        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hero-content h1 {
                font-size: 2.5rem;
            }

            .about-content {
                grid-template-columns: 1fr;
                text-align: center;
            }

            .cta-buttons {
                flex-direction: column;
                align-items: center;
            }

            .contact-info {
                flex-direction: column;
                gap: 2rem;
            }
        }

        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }

        /* Custom scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }

        ::-webkit-scrollbar-track {
            background: #0d1117;
        }

        ::-webkit-scrollbar-thumb {
            background: #58a6ff;
            border-radius: 4px;
        }

        ::-webkit-scrollbar-thumb:hover {
            background: #79c0ff;
        }
    </style>
</head>
<body>
    <header>
        <nav class="container">
            <div class="logo">DevPortfolio</div>
            <ul class="nav-links">
                <li><a href="#home">Home</a></li>
                <li><a href="#about">About</a></li>
                <li><a href="#skills">Skills</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section id="home" class="hero">
            <div class="hero-content">
                <h1>John Doe</h1>
                <p class="subtitle">Full Stack Developer & Open Source Enthusiast</p>
                <div class="cta-buttons">
                    <a href="#projects" class="btn btn-primary">View My Work</a>
                    <a href="https://github.com/yourusername" class="btn btn-secondary" target="_blank">
                        GitHub Profile →
                    </a>
                </div>
            </div>
        </section>

        <section id="about" class="about">
            <div class="container">
                <h2 class="section-title">About Me</h2>
                <div class="about-content">
                    <div class="profile-img">👨‍💻</div>
                    <div class="about-text">
                        <p>
                            I'm a passionate full-stack developer with over 3 years of experience building 
                            modern web applications. I love creating efficient, scalable solutions and 
                            contributing to open-source projects.
                        </p>
                        <p>
                            When I'm not coding, you can find me exploring new technologies, writing 
                            technical blogs, or collaborating with fellow developers on exciting projects. 
                            I believe in clean code, continuous learning, and the power of community-driven development.
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <section id="skills" class="skills">
            <div class="container">
                <h2 class="section-title">Skills & Technologies</h2>
                <div class="skills-grid">
                    <div class="skill-card">
                        <h3>Frontend Development</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">React</span>
                            <span class="skill-tag">Vue.js</span>
                            <span class="skill-tag">TypeScript</span>
                            <span class="skill-tag">Tailwind CSS</span>
                            <span class="skill-tag">Next.js</span>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3>Backend Development</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">Node.js</span>
                            <span class="skill-tag">Python</span>
                            <span class="skill-tag">Express.js</span>
                            <span class="skill-tag">FastAPI</span>
                            <span class="skill-tag">PostgreSQL</span>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3>DevOps & Tools</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">Docker</span>
                            <span class="skill-tag">AWS</span>
                            <span class="skill-tag">Git</span>
                            <span class="skill-tag">CI/CD</span>
                            <span class="skill-tag">Kubernetes</span>
                        </div>
                    </div>
                    <div class="skill-card">
                        <h3>Mobile & Design</h3>
                        <div class="skill-tags">
                            <span class="skill-tag">React Native</span>
                            <span class="skill-tag">Flutter</span>
                            <span class="skill-tag">Figma</span>
                            <span class="skill-tag">UI/UX</span>
                            <span class="skill-tag">Responsive Design</span>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="projects" class="projects">
            <div class="container">
                <h2 class="section-title">Featured Projects</h2>
                <div class="projects-grid">
                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">E-Commerce Platform</h3>
                            <p class="project-desc">
                                A full-stack e-commerce solution with React frontend, Node.js backend, 
                                and integrated payment processing. Features include user authentication, 
                                product catalog, shopping cart, and admin dashboard.
                            </p>
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                            <span class="tech-tag">Stripe API</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">Task Management App</h3>
                            <p class="project-desc">
                                A collaborative task management application built with Vue.js and Firebase. 
                                Features real-time updates, team collaboration, file attachments, 
                                and progress tracking with beautiful charts.
                            </p>
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">Vue.js</span>
                            <span class="tech-tag">Firebase</span>
                            <span class="tech-tag">Chart.js</span>
                            <span class="tech-tag">PWA</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>

                    <div class="project-card">
                        <div class="project-header">
                            <h3 class="project-title">Weather Dashboard</h3>
                            <p class="project-desc">
                                A responsive weather dashboard that displays current conditions and 
                                forecasts using multiple weather APIs. Features location detection, 
                                interactive maps, and customizable widgets.
                            </p>
                        </div>
                        <div class="project-tech">
                            <span class="tech-tag">JavaScript</span>
                            <span class="tech-tag">Weather API</span>
                            <span class="tech-tag">Leaflet.js</span>
                            <span class="tech-tag">CSS Grid</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="project-link">Live Demo</a>
                            <a href="#" class="project-link">GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>

        <section id="contact" class="contact">
            <div class="container">
                <h2 class="section-title">Get In Touch</h2>
                <div class="contact-content">
                    <p>
                        I'm always interested in new opportunities and collaborations. 
                        Whether you have a project in mind or just want to connect, feel free to reach out!
                    </p>
                    <div class="contact-info">
                        <div class="contact-item">
                            <div class="contact-icon">📧</div>
                            <a href="mailto:john.doe@email.com" class="contact-link">john.doe@email.com</a>
                        </div>
                        <div class="contact-item">
                            <div class="contact-icon">💼</div>
                            <a href="https://linkedin.com/in/johndoe" class="contact-link" target="_blank">LinkedIn</a>
                        </div>
                        <div class="contact-item">
                            <div class="contact-icon">🐙</div>
                            <a href="https://github.com/yourusername" class="contact-link" target="_blank">GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <footer>
        <div class="container">
            <div class="footer-content">
                <p>&copy; 2025 John Doe. Built with passion and lots of coffee ☕</p>
            </div>
        </div>
    </footer>

    <script>
        // Smooth scrolling for navigation links
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

        // Header background on scroll
        window.addEventListener('scroll', () => {
            const header = document.querySelector('header');
            if (window.scrollY > 100) {
                header.style.background = 'rgba(13, 17, 23, 0.98)';
            } else {
                header.style.background = 'rgba(13, 17, 23, 0.95)';
            }
        });

        // Add entrance animations to elements when they come into view
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

        // Observe skill cards and project cards
        document.querySelectorAll('.skill-card, .project-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.6s ease';
            observer.observe(card);
        });

        // Dynamic typing effect for subtitle (optional enhancement)
        const subtitle = document.querySelector('.subtitle');
        const originalText = subtitle.textContent;
        let index = 0;
        
        function typeEffect() {
            if (index <= originalText.length) {
                subtitle.textContent = originalText.slice(0, index) + '|';
                index++;
                setTimeout(typeEffect, 100);
            } else {
                subtitle.textContent = originalText;
            }
        }
        
        // Start typing effect after a delay
        setTimeout(typeEffect, 1000);
    </script>
</body>
</html>
