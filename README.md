<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Your Name - Portfolio</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
            line-height: 1.6;
            color: #e0e0e0;
            background: #121212;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header */
        header {
            padding: 60px 0;
            text-align: center;
            border-bottom: 1px solid #333;
        }
        
        .profile-image {
            width: 120px;
            height: 120px;
            border-radius: 50%;
            margin: 0 auto 30px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            color: white;
            font-weight: bold;
        }
        
        h1 {
            font-size: 3rem;
            font-weight: 700;
            margin-bottom: 20px;
            color: #ffffff;
        }
        
        .subtitle {
            font-size: 1.2rem;
            color: #b0b0b0;
            max-width: 600px;
            margin: 0 auto;
            line-height: 1.7;
        }
        
        /* Navigation */
        nav {
            padding: 30px 0;
            text-align: center;
            border-bottom: 1px solid #333;
            position: sticky;
            top: 0;
            background: rgba(18, 18, 18, 0.95);
            backdrop-filter: blur(10px);
            z-index: 100;
        }
        
        nav ul {
            list-style: none;
            display: flex;
            justify-content: center;
            gap: 40px;
        }
        
        nav a {
            text-decoration: none;
            color: #ffffff;
            font-weight: 500;
            transition: color 0.3s ease;
            position: relative;
        }
        
        nav a:hover {
            color: #667eea;
        }
        
        nav a::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: #667eea;
            transition: width 0.3s ease;
        }
        
        nav a:hover::after {
            width: 100%;
        }
        
        /* Sections */
        section {
            padding: 80px 0;
        }
        
        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 50px;
            color: #ffffff;
            position: relative;
        }
        
        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            margin: 20px auto;
            border-radius: 2px;
        }
        
        /* About Section */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 60px;
            align-items: center;
        }
        
        .about-text {
            font-size: 1.1rem;
            color: #c0c0c0;
            line-height: 1.8;
        }
        
        .skills {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .skill-item {
            background: #2a2a2a;
            padding: 15px 20px;
            border-radius: 10px;
            text-align: center;
            font-weight: 500;
            transition: transform 0.3s ease, box-shadow 0.3s ease;
            color: #ffffff;
        }
        
        .skill-item:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(0,0,0,0.1);
        }
        
        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            gap: 40px;
        }
        
        .project-card {
            background: #1e1e1e;
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px rgba(0,0,0,0.3);
            transition: transform 0.3s ease, box-shadow 0.3s ease;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(0,0,0,0.4);
        }
        
        .project-image {
            height: 200px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            display: flex;
            align-items: center;
            justify-content: center;
            font-size: 48px;
            color: white;
        }
        
        .project-content {
            padding: 30px;
        }
        
        .project-title {
            font-size: 1.5rem;
            font-weight: 600;
            margin-bottom: 15px;
            color: #2c3e50;
        }
        
        .project-description {
            color: #666;
            margin-bottom: 20px;
            line-height: 1.6;
        }
        
        .project-tech {
            display: flex;
            flex-wrap: wrap;
            gap: 10px;
            margin-bottom: 20px;
        }
        
        .tech-tag {
            background: #e3f2fd;
            color: #1976d2;
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.85rem;
            font-weight: 500;
        }
        
        .project-links {
            display: flex;
            gap: 15px;
        }
        
        .btn {
            display: inline-block;
            padding: 10px 20px;
            border-radius: 25px;
            text-decoration: none;
            font-weight: 500;
            transition: all 0.3s ease;
            border: 2px solid transparent;
        }
        
        .btn-primary {
            background: linear-gradient(135deg, #667eea, #764ba2);
            color: white;
        }
        
        .btn-outline {
            border-color: #667eea;
            color: #667eea;
        }
        
        .btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(0,0,0,0.2);
        }
        
        /* Contact Section */
        .contact {
            background: #f8f9fa;
        }
        
        .contact-content {
            text-align: center;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .contact-info {
            display: flex;
            justify-content: center;
            gap: 40px;
            margin-top: 40px;
            flex-wrap: wrap;
        }
        
        .contact-item {
            display: flex;
            align-items: center;
            gap: 10px;
            color: #555;
        }
        
        .contact-icon {
            width: 40px;
            height: 40px;
            background: linear-gradient(135deg, #667eea, #764ba2);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-weight: bold;
        }
        
        /* Footer */
        footer {
            background: #2c3e50;
            color: white;
            text-align: center;
            padding: 30px 0;
        }
        
        /* Responsive Design */
        @media (max-width: 768px) {
            h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
                gap: 30px;
            }
            
            nav ul {
                flex-direction: column;
                gap: 20px;
            }
            
            .projects-grid {
                grid-template-columns: 1fr;
            }
            
            .contact-info {
                flex-direction: column;
                align-items: center;
                gap: 20px;
            }
            
            .section-title {
                font-size: 2rem;
            }
        }
        
        /* Smooth scrolling */
        html {
            scroll-behavior: smooth;
        }
        
        /* Animation for elements on scroll */
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
        
        .animate-on-scroll {
            animation: fadeInUp 0.8s ease forwards;
        }
    </style>
</head>
<body>
    <header>
        <div class="container">
            <div class="profile-image">YN</div>
            <h1>Your Name</h1>
            <p class="subtitle">Student studying Computer Science. Passionate about full-stack development, machine learning, and artificial intelligence.</p>
        </div>
    </header>
    
    <nav>
        <div class="container">
            <ul>
                <li><a href="#about">About</a></li>
                <li><a href="#projects">Projects</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </div>
    </nav>
    
    <section id="about">
        <div class="container">
            <h2 class="section-title">About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Hello! I'm a passionate computer science student with a love for creating innovative solutions through code. My journey in tech began with curiosity and has evolved into a deep appreciation for both the technical and creative aspects of software development.</p>
                    
                    <p>I enjoy working on projects that challenge me to learn new technologies and solve real-world problems. Whether it's building web applications, exploring machine learning algorithms, or developing mobile apps, I'm always eager to push the boundaries of what's possible.</p>
                    
                    <div class="skills">
                        <div class="skill-item">JavaScript</div>
                        <div class="skill-item">Python</div>
                        <div class="skill-item">React</div>
                        <div class="skill-item">Node.js</div>
                        <div class="skill-item">Machine Learning</div>
                        <div class="skill-item">SQL</div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section id="projects">
        <div class="container">
            <h2 class="section-title">My Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image">📱</div>
                    <div class="project-content">
                        <h3 class="project-title">Project One</h3>
                        <p class="project-description">A full-stack web application that solves a specific problem with modern technologies and clean user interface design.</p>
                        <div class="project-tech">
                            <span class="tech-tag">React</span>
                            <span class="tech-tag">Node.js</span>
                            <span class="tech-tag">MongoDB</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn btn-primary">Live Demo</a>
                            <a href="#" class="btn btn-outline">GitHub</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🤖</div>
                    <div class="project-content">
                        <h3 class="project-title">Project Two</h3>
                        <p class="project-description">An AI-powered application that demonstrates machine learning concepts with practical real-world applications.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Python</span>
                            <span class="tech-tag">TensorFlow</span>
                            <span class="tech-tag">Flask</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn btn-primary">Live Demo</a>
                            <a href="#" class="btn btn-outline">GitHub</a>
                        </div>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image">🌐</div>
                    <div class="project-content">
                        <h3 class="project-title">Project Three</h3>
                        <p class="project-description">A responsive web application with modern design principles and optimized performance across all devices.</p>
                        <div class="project-tech">
                            <span class="tech-tag">Vue.js</span>
                            <span class="tech-tag">Express</span>
                            <span class="tech-tag">PostgreSQL</span>
                        </div>
                        <div class="project-links">
                            <a href="#" class="btn btn-primary">Live Demo</a>
                            <a href="#" class="btn btn-outline">GitHub</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <section id="contact" class="contact">
        <div class="container">
            <h2 class="section-title">Get In Touch</h2>
            <div class="contact-content">
                <p>I'm always open to discussing new opportunities, interesting projects, or just having a chat about technology and innovation.</p>
                
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">📧</div>
                        <span>your.email@example.com</span>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">🔗</div>
                        <span>linkedin.com/in/yourprofile</span>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">💻</div>
                        <span>github.com/yourusername</span>
                    </div>
                </div>
            </div>
        </div>
    </section>
    
    <footer>
        <div class="container">
            <p>&copy; 2025 Your Name. All rights reserved.</p>
        </div>
    </footer>
    
    <script>
        // Smooth scrolling for navigation links
        document.querySelectorAll('nav a[href^="#"]').forEach(anchor => {
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
        
        // Simple scroll animation
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
        
        // Observe project cards for animation
        document.querySelectorAll('.project-card').forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'opacity 0.8s ease, transform 0.8s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
