
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="shortcut icon" href="icon.jpg" type="image/x-icon">
    <title>Portfolio - MCA Student</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
            line-height: 1.6;
            color: #333;
            overflow-x: hidden;
        }

        .navbar {
            position: fixed;
            top: 0;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            padding: 1rem 5%;
            display: flex;
            justify-content: space-between;
            align-items: center;
            box-shadow: 0 2px 10px rgba(0,0,0,0.1);
            z-index: 1000;
            transition: all 0.3s ease;
        }

        .navbar.scrolled {
            padding: 0.5rem 5%;
            background: rgba(255, 255, 255, 0.98);
        }

        .logo {
            font-size: 1.5rem;
            font-weight: bold;
            color: #2563eb;
        }

        .nav-links {
            display: flex;
            gap: 2rem;
            list-style: none;
        }

        .nav-links a {
            text-decoration: none;
            color: #333;
            font-weight: 500;
            transition: color 0.3s;
        }

        .nav-links a:hover {
            color: #2563eb;
        }

        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            justify-content: center;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            text-align: center;
            padding: 2rem;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            width: 200%;
            height: 200%;
            background: radial-gradient(circle, rgba(255,255,255,0.1) 1px, transparent 1px);
            background-size: 50px 50px;
            animation: moveBackground 20s linear infinite;
        }

        @keyframes moveBackground {
            0% { transform: translate(0, 0); }
            100% { transform: translate(50px, 50px); }
        }

        .hero-content {
            position: relative;
            z-index: 1;
            animation: fadeInUp 1s ease;
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

        .hero h1 {
            font-size: 3rem;
            margin-bottom: 1rem;
        }

        .hero p {
            font-size: 1.5rem;
            margin-bottom: 2rem;
            opacity: 0.9;
        }

        .btn {
            display: inline-block;
            padding: 12px 30px;
            background: white;
            color: #667eea;
            text-decoration: none;
            border-radius: 50px;
            font-weight: 600;
            transition: all 0.3s;
            border: 2px solid white;
        }

        .btn:hover {
            background: transparent;
            color: white;
            transform: translateY(-3px);
            box-shadow: 0 10px 20px rgba(0,0,0,0.2);
        }

        .section {
            padding: 5rem 5%;
            max-width: 1200px;
            margin: 0 auto;
        }

        .section-title {
            font-size: 2.5rem;
            text-align: center;
            margin-bottom: 3rem;
            color: #2563eb;
            position: relative;
        }

        .section-title::after {
            content: '';
            display: block;
            width: 60px;
            height: 4px;
            background: #2563eb;
            margin: 1rem auto;
            border-radius: 2px;
        }

        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 3rem;
            align-items: center;
        }

        .about-text p {
            margin-bottom: 1rem;
            text-align: justify;
        }

        .profile-image {
            width: 100%;
            max-width: 350px;
            margin: 0 auto;
            position: relative;
        }

        .profile-image-wrapper {
            width: 100%;
            aspect-ratio: 1;
            border-radius: 50%;
            overflow: hidden;
            border: 8px solid #667eea;
            box-shadow: 0 10px 40px rgba(102, 126, 234, 0.3);
            position: relative;
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-20px); }
        }

        .profile-image-wrapper img {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .profile-placeholder {
            width: 100%;
            height: 100%;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 8rem;
        }

        .skills-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 2rem;
        }

        .skill-card {
            background: #f8f9fa;
            padding: 2rem;
            border-radius: 10px;
            transition: all 0.3s;
            border-left: 4px solid #2563eb;
        }

        .skill-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 10px 30px rgba(0,0,0,0.1);
        }

        .skill-card h3 {
            color: #2563eb;
            margin-bottom: 1rem;
        }

        .skill-bar {
            background: #e0e0e0;
            height: 10px;
            border-radius: 5px;
            margin-top: 0.5rem;
            overflow: hidden;
        }

        .skill-progress {
            background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
            height: 100%;
            border-radius: 5px;
            transition: width 1s ease;
        }

        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
        }

        .project-card {
            background: white;
            border-radius: 10px;
            overflow: hidden;
            box-shadow: 0 5px 15px rgba(0,0,0,0.1);
            transition: all 0.3s;
        }

        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px rgba(0,0,0,0.2);
        }

        .project-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
            overflow: hidden;
            position: relative;
        }

        .project-image img {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.3s;
        }

        .project-card:hover .project-image img {
            transform: scale(1.1);
        }

        .project-icon {
            font-size: 3rem;
        }

        .project-content {
            padding: 1.5rem;
        }

        .project-content h3 {
            color: #2563eb;
            margin-bottom: 0.5rem;
        }

        .contact-form {
            max-width: 600px;
            margin: 0 auto;
        }

        .form-group {
            margin-bottom: 1.5rem;
        }

        .form-group label {
            display: block;
            margin-bottom: 0.5rem;
            font-weight: 600;
            color: #333;
        }

        .form-group input,
        .form-group textarea {
            width: 100%;
            padding: 12px;
            border: 2px solid #e0e0e0;
            border-radius: 5px;
            font-family: inherit;
            transition: border-color 0.3s;
        }

        .form-group input:focus,
        .form-group textarea:focus {
            outline: none;
            border-color: #2563eb;
        }

        .form-group textarea {
            resize: vertical;
            min-height: 120px;
        }

        .submit-btn {
            width: 100%;
            padding: 12px;
            background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
            color: white;
            border: none;
            border-radius: 5px;
            font-size: 1rem;
            font-weight: 600;
            cursor: pointer;
            transition: all 0.3s;
        }

        .submit-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 5px 15px rgba(102, 126, 234, 0.4);
        }

        footer {
            background: #1f2937;
            color: white;
            text-align: center;
            padding: 2rem;
        }

        .social-links {
            display: flex;
            justify-content: center;
            gap: 1.5rem;
            margin-top: 1rem;
        }

        .social-links a {
            color: white;
            font-size: 1.5rem;
            transition: color 0.3s;
        }

        .social-links a:hover {
            color: #667eea;
        }

        @media (max-width: 768px) {
            .nav-links {
                gap: 1rem;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .about-content {
                grid-template-columns: 1fr;
            }

            .section {
                padding: 3rem 5%;
            }
        }
    </style>
</head>
<body>
    <nav class="navbar" id="navbar">
        <div class="logo">Portfolio</div>
        <ul class="nav-links">
            <li><a href="#home">Home</a></li>
            <li><a href="#about">About</a></li>
            <li><a href="#skills">Skills</a></li>
            <li><a href="#projects">Projects</a></li>
            <li><a href="#contact">Contact</a></li>
        </ul>
    </nav>

    <section class="hero" id="home">
        <div class="hero-content">
            <h1>SalmanKhan Desai</h1>
            <p>MCA Student | Software Developer | Cloud Developer</p>
            <a href="#contact" class="btn">Get In Touch</a>
        </div>
    </section>

    <section class="section" id="about">
        <h2 class="section-title">About Me</h2>
        <div class="about-content">
            <div class="about-text">
                <p>Hello! I'm a passionate MCA student with a strong foundation in computer applications and software development. I'm dedicated to leveraging technology to solve real-world problems and create innovative solutions.</p>
                <p>My journey in computer science has equipped me with comprehensive knowledge in programming, database management, web development, and software engineering principles. I'm constantly exploring new technologies and methodologies to stay ahead in this dynamic field.</p>
                <p>I believe in continuous learning and practical application of knowledge. Through academic projects and personal initiatives, I've developed a diverse skill set that combines technical expertise with creative problem-solving abilities.</p>
            </div>
            <div class="about-image">
                <div class="profile-image">
                    <div class="profile-image-wrapper">
                        <!-- Replace the src with your actual image URL -->
                        <img src="profile.jpg" alt="Profile Picture" id="profileImg">
                        <!-- Fallback placeholder if no image -->
                        <!-- <div class="profile-placeholder">👨‍💻</div> -->
                    </div>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="skills">
        <h2 class="section-title">Technical Skills</h2>
        <div class="skills-grid">
            <div class="skill-card">
                <h3>Programming Languages</h3>
                <p>Java</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="85" style="width: 0%"></div></div>
                <p style="margin-top: 1rem;">Python</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="80" style="width: 0%"></div></div>
                <p style="margin-top: 1rem;">C</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="70" style="width: 0%"></div></div>
            </div>
            <div class="skill-card">
                <h3>Web Development</h3>
                <p>HTML/CSS/JavaScript</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="90" style="width: 0%"></div></div>
                <p style="margin-top: 1rem;">React.js</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="75" style="width: 0%"></div></div>
                <p style="margin-top: 1rem;">Node.js</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="70" style="width: 0%"></div></div>
            </div>
            <div class="skill-card">
                <h3>Database & Tools</h3>
                <p>MySQL/PostgreSQL</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="85" style="width: 0%"></div></div>
                <p style="margin-top: 1rem;">MongoDB</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="80" style="width: 0%"></div></div>
                <p style="margin-top: 1rem;">Git/GitHub</p>
                <div class="skill-bar"><div class="skill-progress" data-progress="80" style="width: 0%"></div></div>
            </div>
        </div>
    </section>

    <section class="section" id="projects">
        <h2 class="section-title">Projects</h2>
        <div class="projects-grid">
            <!-- <div class="project-card">
                <div class="project-image"> -->
                    <!-- Replace with your project image -->
                    <!-- <img src="https://via.placeholder.com/400x200/667eea/ffffff?text=E-Commerce" alt="E-Commerce Project"> -->
                    <!-- Fallback icon if no image -->
                    <!-- <span class="project-icon">🛒</span> -->
                <!-- </div> -->
                <!-- <div class="project-content">
                    <h3>Books Management System</h3>
                    <p>A application with user authentication, book management, and payment integration. Built using React, Node.js, and MongoDB.</p>
                    <p style="margin-top: 1rem; color: #667eea; font-weight: 600;">Technologies: React, Node.js, MongoDB, Express</p>
                </div>
            </div> -->
            <div class="project-card">
                <div class="project-image">
                    <img src="sms.png" alt="Student Management System">
                    <!-- <span class="project-icon">📱</span> -->
                </div>
                <div class="project-content">
                    <h3>Student Management System</h3>
                    <p>A comprehensive system for managing student records, attendance, and grades with role-based access control for administrators and students.</p>
                    <p style="margin-top: 1rem; color: #667eea; font-weight: 600;">Technologies: Java, MySQL, JavaFX</p>
                </div>
            </div>
            <div class="project-card">
                <div class="project-image">
                    <img src="portfolio.png" alt="Machine Learning Project">
                    <!-- <span class="project-icon">🤖</span> -->
                </div>
                <div class="project-content">
                    <h3>Portfolio webpage</h3>
                    <p>Developed a professional Web site using HTML, CSS, JavaScript.</p>
                    <p style="margin-top: 1rem; color: #667eea; font-weight: 600;">Technologies: HTML, CSS, JavaScript</p>
                </div>
            </div>
        </div>
    </section>

    <section class="section" id="contact">
        <h2 class="section-title">Contact Me</h2>
        <form class="contact-form" id="contactForm">
            <div class="form-group">
                <label for="name">Name</label>
                <input type="text" id="name" required>
            </div>
            <div class="form-group">
                <label for="email">Email</label>
                <input type="email" id="email" required>
            </div>
            <div class="form-group">
                <label for="message">Message</label>
                <textarea id="message" required></textarea>
            </div>
            <button type="submit" class="submit-btn">Send Message</button>
        </form>
    </section>

    <footer>
        <p>&copy; 2025 SalmanKhan Desai. All rights reserved.</p>
        <div class="social-links">
            <a href="#" title="LinkedIn">💼</a>
            <a href="#" title="GitHub">🐙</a>
            <!-- <a href="#" title="Twitter">🐦</a> -->
            <a href="https://mail.google.com/" title="Email">✉️</a>
        </div>
    </footer>

    <script>
        // Smooth scrolling
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({ behavior: 'smooth', block: 'start' });
                }
            });
        });

        // Navbar scroll effect
        const navbar = document.getElementById('navbar');
        window.addEventListener('scroll', () => {
            if (window.scrollY > 50) {
                navbar.classList.add('scrolled');
            } else {
                navbar.classList.remove('scrolled');
            }
        });

        // Animate skill bars on scroll
        const skillBars = document.querySelectorAll('.skill-progress');
        const animateSkills = () => {
            skillBars.forEach(bar => {
                const rect = bar.getBoundingClientRect();
                if (rect.top < window.innerHeight && rect.bottom > 0) {
                    const progress = bar.getAttribute('data-progress');
                    bar.style.width = progress + '%';
                }
            });
        };

        window.addEventListener('scroll', animateSkills);
        animateSkills();

        // Form submission
        document.getElementById('contactForm').addEventListener('submit', (e) => {
            e.preventDefault();
            alert('Thank you for your message! I will get back to you soon.');
            e.target.reset();
        });
    </script>
</body>
</html>
