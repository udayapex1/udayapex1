<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Uday Pareta | Full Stack Developer</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        :root {
            --primary: #2563eb;
            --secondary: #1e293b;
            --accent: #0ea5e9;
            --light: #f8fafc;
            --dark: #0f172a;
            --success: #10b981;
            --code-bg: #1a1b26;
            --transition: all 0.3s ease;
        }

        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }

        body {
            background-color: var(--light);
            color: var(--dark);
            line-height: 1.6;
            overflow-x: hidden;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }

        /* Header & Navigation */
        header {
            background-color: var(--secondary);
            color: white;
            position: fixed;
            width: 100%;
            z-index: 1000;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
        }

        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }

        .logo {
            font-size: 1.8rem;
            font-weight: 700;
            color: var(--accent);
        }

        .nav-links {
            display: flex;
            list-style: none;
        }

        .nav-links li {
            margin-left: 30px;
        }

        .nav-links a {
            color: white;
            text-decoration: none;
            font-weight: 500;
            transition: var(--transition);
            position: relative;
        }

        .nav-links a:after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background-color: var(--accent);
            transition: var(--transition);
        }

        .nav-links a:hover:after {
            width: 100%;
        }

        .hamburger {
            display: none;
            cursor: pointer;
        }

        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            padding-top: 80px;
            background: linear-gradient(to bottom right, #f0f9ff, #e0f2fe);
            position: relative;
            overflow: hidden;
        }

        .hero-content {
            max-width: 600px;
            z-index: 1;
        }

        .hero h1 {
            font-size: 3.5rem;
            margin-bottom: 20px;
            color: var(--secondary);
        }

        .hero p {
            font-size: 1.2rem;
            margin-bottom: 30px;
            color: var(--secondary);
        }

        .tagline {
            color: var(--primary);
            font-weight: 600;
            font-size: 1.3rem;
            margin-bottom: 10px;
        }

        .btn {
            display: inline-block;
            padding: 12px 28px;
            background-color: var(--primary);
            color: white;
            border-radius: 30px;
            text-decoration: none;
            font-weight: 600;
            transition: var(--transition);
            border: none;
            cursor: pointer;
            box-shadow: 0 4px 14px rgba(37, 99, 235, 0.4);
        }

        .btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 6px 18px rgba(37, 99, 235, 0.5);
        }

        .btn-outline {
            background-color: transparent;
            border: 2px solid var(--primary);
            color: var(--primary);
            margin-left: 15px;
        }

        .btn-outline:hover {
            background-color: var(--primary);
            color: white;
        }

        /* Floating elements */
        .floating-element {
            position: absolute;
            border-radius: 50%;
            opacity: 0.1;
            z-index: 0;
        }

        .float-1 {
            width: 300px;
            height: 300px;
            background-color: var(--primary);
            top: 10%;
            right: 10%;
        }

        .float-2 {
            width: 200px;
            height: 200px;
            background-color: var(--accent);
            bottom: 20%;
            left: 5%;
        }

        /* Sections */
        section {
            padding: 80px 0;
        }

        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }

        .section-title h2 {
            font-size: 2.5rem;
            color: var(--secondary);
            display: inline-block;
        }

        .section-title h2:after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background-color: var(--primary);
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }

        /* Skills Section */
        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
            gap: 30px;
        }

        .skill-category {
            background-color: white;
            padding: 25px;
            border-radius: 10px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .skill-category:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        .skill-category h3 {
            color: var(--primary);
            margin-bottom: 20px;
            font-size: 1.4rem;
        }

        .skill-list {
            list-style: none;
        }

        .skill-list li {
            margin-bottom: 12px;
            display: flex;
            align-items: center;
        }

        .skill-list li:before {
            content: '▹';
            color: var(--accent);
            margin-right: 10px;
        }

        /* Projects Section */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(350px, 1fr));
            gap: 30px;
        }

        .project-card {
            background-color: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            transition: var(--transition);
        }

        .project-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 8px 20px rgba(0, 0, 0, 0.1);
        }

        .project-img {
            height: 200px;
            background-color: var(--code-bg);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }

        .project-content {
            padding: 25px;
        }

        .project-content h3 {
            color: var(--secondary);
            margin-bottom: 15px;
        }

        .project-content p {
            margin-bottom: 20px;
            color: #64748b;
        }

        .project-tags {
            display: flex;
            flex-wrap: wrap;
            margin-bottom: 20px;
        }

        .project-tag {
            background-color: #e0f2fe;
            color: var(--primary);
            padding: 5px 12px;
            border-radius: 20px;
            font-size: 0.8rem;
            margin-right: 8px;
            margin-bottom: 8px;
        }

        .project-links a {
            color: var(--primary);
            text-decoration: none;
            font-weight: 600;
            margin-right: 20px;
            display: inline-flex;
            align-items: center;
        }

        .project-links a i {
            margin-right: 5px;
        }

        /* Contact Section */
        .contact-container {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 50px;
        }

        .contact-info {
            display: flex;
            flex-direction: column;
        }

        .contact-item {
            display: flex;
            align-items: center;
            margin-bottom: 25px;
        }

        .contact-icon {
            width: 50px;
            height: 50px;
            background-color: var(--primary);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 1.2rem;
            margin-right: 15px;
        }

        .contact-text h4 {
            color: var(--secondary);
            margin-bottom: 5px;
        }

        .contact-text p {
            color: #64748b;
        }

        .social-links {
            display: flex;
            margin-top: 20px;
        }

        .social-links a {
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background-color: var(--primary);
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            margin-right: 15px;
            transition: var(--transition);
        }

        .social-links a:hover {
            transform: translateY(-3px);
            background-color: var(--accent);
        }

        /* Footer */
        footer {
            background-color: var(--secondary);
            color: white;
            padding: 40px 0;
            text-align: center;
        }

        .footer-content {
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        .footer-logo {
            font-size: 2rem;
            font-weight: 700;
            color: var(--accent);
            margin-bottom: 20px;
        }

        .footer-quote {
            font-style: italic;
            margin-bottom: 20px;
            max-width: 600px;
        }

        .copyright {
            margin-top: 20px;
            color: #94a3b8;
            font-size: 0.9rem;
        }

        /* Responsive Design */
        @media (max-width: 992px) {
            .contact-container {
                grid-template-columns: 1fr;
            }
            
            .hero h1 {
                font-size: 2.8rem;
            }
        }

        @media (max-width: 768px) {
            .nav-links {
                display: none;
            }

            .hamburger {
                display: block;
            }

            .hero h1 {
                font-size: 2.5rem;
            }

            .hero-buttons {
                display: flex;
                flex-direction: column;
            }

            .btn-outline {
                margin-left: 0;
                margin-top: 15px;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header>
        <div class="container">
            <nav>
                <div class="logo">UP</div>
                <ul class="nav-links">
                    <li><a href="#home">Home</a></li>
                    <li><a href="#skills">Skills</a></li>
                    <li><a href="#projects">Projects</a></li>
                    <li><a href="#contact">Contact</a></li>
                </ul>
                <div class="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <p class="tagline">Full Stack Developer | Systems Engineer</p>
                <h1>Uday Pareta</h1>
                <p>Building scalable systems, crushing APIs, and living the open-source life. Passionate about creating efficient, user-friendly applications with cutting-edge technology.</p>
                <div class="hero-buttons">
                    <a href="#projects" class="btn">View My Work</a>
                    <a href="#contact" class="btn btn-outline">Get In Touch</a>
                </div>
            </div>
        </div>
        <div class="floating-element float-1"></div>
        <div class="floating-element float-2"></div>
    </section>

    <!-- Skills Section -->
    <section id="skills">
        <div class="container">
            <div class="section-title">
                <h2>Technical Stack</h2>
            </div>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>Languages</h3>
                    <ul class="skill-list">
                        <li>JavaScript (Node.js)</li>
                        <li>Python</li>
                        <li>Java</li>
                        <li>C / C++</li>
                        <li>Bash</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>Backend</h3>
                    <ul class="skill-list">
                        <li>Express.js</li>
                        <li>Fastify</li>
                        <li>MongoDB</li>
                        <li>PostgreSQL</li>
                        <li>Redis</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>Frontend</h3>
                    <ul class="skill-list">
                        <li>Next.js</li>
                        <li>Tailwind CSS</li>
                        <li>GSAP</li>
                        <li>Framer Motion</li>
                    </ul>
                </div>
                <div class="skill-category">
                    <h3>Tools & OS</h3>
                    <ul class="skill-list">
                        <li>Postman</li>
                        <li>Docker</li>
                        <li>PM2</li>
                        <li>Ubuntu</li>
                        <li>Git</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" style="background-color: #f8fafc;">
        <div class="container">
            <div class="section-title">
                <h2>Current Projects</h2>
            </div>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-robot"></i>
                    </div>
                    <div class="project-content">
                        <h3>Utron</h3>
                        <p>AI-powered terminal assistant with natural language processing. Available as an npm package.</p>
                        <div class="project-tags">
                            <span class="project-tag">AI</span>
                            <span class="project-tag">NLP</span>
                            <span class="project-tag">Node.js</span>
                        </div>
                        <div class="project-links">
                            <a href="https://www.npmjs.com/package/utron" target="_blank"><i class="fas fa-external-link-alt"></i> View on npm</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-code"></i>
                    </div>
                    <div class="project-content">
                        <h3>Analyzer</h3>
                        <p>VS Code extension for comprehensive code analysis with detailed reporting and suggestions.</p>
                        <div class="project-tags">
                            <span class="project-tag">VS Code</span>
                            <span class="project-tag">Extension</span>
                            <span class="project-tag">JavaScript</span>
                        </div>
                        <div class="project-links">
                            <a href="https://marketplace.visualstudio.com/items?itemName=UdayPareta.analyzer" target="_blank"><i class="fas fa-external-link-alt"></i> View Extension</a>
                        </div>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-img">
                        <i class="fas fa-pizza-slice"></i>
                    </div>
                    <div class="project-content">
                        <h3>Food Buddy</h3>
                        <p>Modern food ordering and discovery platform with intuitive UI and seamless user experience.</p>
                        <div class="project-tags">
                            <span class="project-tag">Next.js</span>
                            <span class="project-tag">MongoDB</span>
                            <span class="project-tag">Tailwind</span>
                        </div>
                        <div class="project-links">
                            <a href="https://food-buddy-three.vercel.app" target="_blank"><i class="fas fa-external-link-alt"></i> Live Demo</a>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact">
        <div class="container">
            <div class="section-title">
                <h2>Get In Touch</h2>
            </div>
            <div class="contact-container">
                <div class="contact-info">
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-envelope"></i>
                        </div>
                        <div class="contact-text">
                            <h4>Email</h4>
                            <p>udaypareta645@gmail.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-map-marker-alt"></i>
                        </div>
                        <div class="contact-text">
                            <h4>Location</h4>
                            <p>Open to remote opportunities worldwide</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <div class="contact-icon">
                            <i class="fas fa-heart"></i>
                        </div>
                        <div class="contact-text">
                            <h4>Interests</h4>
                            <p>Open-source, Linux, Systems Programming</p>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="mailto:udaypareta645@gmail.com" target="_blank"><i class="fas fa-envelope"></i></a>
                        <a href="https://www.linkedin.com/in/uday-pareta-b114aa284" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="https://github.com/udayapex1" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="https://www.instagram.com/you_dazzz?igsh=bWk4czFndDF4bDJr" target="_blank"><i class="fab fa-instagram"></i></a>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-content">
                <div class="footer-logo">UP</div>
                <p class="footer-quote">"Big fan of Linus Torvalds and the open-source movement. Currently exploring operating systems internals and low-level programming. Always curious about how things work under the hood."</p>
                <p class="copyright">© 2023 Uday Pareta. All rights reserved.</p>
            </div>
        </div>
    </footer>

    <script>
        // Simple smooth scrolling for navigation links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                document.querySelector(this.getAttribute('href')).scrollIntoView({
                    behavior: 'smooth'
                });
            });
        });

        // Hamburger menu toggle for mobile
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', () => {
            navLinks.style.display = navLinks.style.display === 'flex' ? 'none' : 'flex';
        });
    </script>
</body>
</html>
