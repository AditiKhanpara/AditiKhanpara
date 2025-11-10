<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Aditi's Profile</title>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;600&family=Poppins:wght@300;400;500;600&display=swap');
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background: linear-gradient(135deg, #fef4f8 0%, #ffe8f0 50%, #fdf0f5 100%);
            color: #5a4a5e;
            overflow-x: hidden;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 20px;
        }
        
        /* Floating particles animation */
        .particles {
            position: fixed;
            width: 100%;
            height: 100%;
            top: 0;
            left: 0;
            pointer-events: none;
            z-index: 1;
        }
        
        .particle {
            position: absolute;
            width: 4px;
            height: 4px;
            background: linear-gradient(45deg, #f4c2d4, #e8b4c8);
            border-radius: 50%;
            animation: float 15s infinite;
            opacity: 0.3;
        }
        
        @keyframes float {
            0%, 100% { transform: translateY(0) translateX(0); }
            25% { transform: translateY(-50px) translateX(20px); }
            50% { transform: translateY(-100px) translateX(-20px); }
            75% { transform: translateY(-50px) translateX(30px); }
        }
        
        /* Header Section */
        .header {
            text-align: center;
            padding: 60px 20px;
            position: relative;
            z-index: 2;
        }
        
        .header h1 {
            font-family: 'Playfair Display', serif;
            font-size: 4rem;
            background: linear-gradient(135deg, #d4a5c9 0%, #e8b4c8 50%, #f4c2d4 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 10px;
            animation: fadeInDown 1s ease;
        }
        
        .header .subtitle {
            font-size: 1.2rem;
            color: #8a7a8e;
            font-weight: 300;
            animation: fadeIn 1.5s ease;
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
        
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
        
        /* Divider with floral accent */
        .divider {
            width: 100px;
            height: 2px;
            background: linear-gradient(90deg, transparent, #e8b4c8, transparent);
            margin: 40px auto;
            position: relative;
        }
        
        .divider::before {
            content: '✦';
            position: absolute;
            left: 50%;
            top: 50%;
            transform: translate(-50%, -50%);
            background: #fef4f8;
            padding: 0 15px;
            color: #e8b4c8;
            font-size: 1.2rem;
        }
        
        /* Card styling */
        .card {
            background: rgba(255, 255, 255, 0.7);
            backdrop-filter: blur(10px);
            border-radius: 20px;
            padding: 40px;
            margin: 30px 0;
            box-shadow: 0 8px 32px rgba(212, 165, 201, 0.1);
            border: 1px solid rgba(232, 180, 200, 0.2);
            transition: all 0.3s ease;
            animation: slideUp 0.8s ease;
        }
        
        .card:hover {
            transform: translateY(-5px);
            box-shadow: 0 12px 40px rgba(212, 165, 201, 0.2);
        }
        
        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        .card h2 {
            font-family: 'Playfair Display', serif;
            color: #d4a5c9;
            font-size: 2rem;
            margin-bottom: 20px;
            position: relative;
            display: inline-block;
        }
        
        .card h2::after {
            content: '';
            position: absolute;
            bottom: -5px;
            left: 0;
            width: 0;
            height: 2px;
            background: linear-gradient(90deg, #d4a5c9, #f4c2d4);
            transition: width 0.3s ease;
        }
        
        .card:hover h2::after {
            width: 100%;
        }
        
        /* About section with image */
        .about-content {
            display: grid;
            grid-template-columns: 1fr 1fr;
            gap: 40px;
            align-items: center;
        }
        
        .about-text p {
            line-height: 1.8;
            margin-bottom: 15px;
            color: #6a5a6e;
        }
        
        .about-image {
            position: relative;
            animation: float 6s ease-in-out infinite;
        }
        
        .about-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 10px 30px rgba(212, 165, 201, 0.3);
        }
        
        .highlight-box {
            background: linear-gradient(135deg, #f9dde7 0%, #fef4f8 100%);
            border-left: 4px solid #e8b4c8;
            padding: 20px;
            margin: 20px 0;
            border-radius: 10px;
            font-style: italic;
            color: #7a6a7e;
        }
        
        /* Tech stack grid */
        .tech-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
            gap: 20px;
            margin-top: 30px;
        }
        
        .tech-item {
            background: linear-gradient(135deg, #ffffff 0%, #fef4f8 100%);
            padding: 20px;
            border-radius: 15px;
            text-align: center;
            transition: all 0.3s ease;
            border: 2px solid transparent;
            cursor: pointer;
        }
        
        .tech-item:hover {
            border-color: #e8b4c8;
            transform: scale(1.05);
            box-shadow: 0 5px 20px rgba(232, 180, 200, 0.3);
        }
        
        .tech-item span {
            display: block;
            font-weight: 500;
            color: #8a7a8e;
            font-size: 0.9rem;
        }
        
        /* Projects showcase */
        .projects-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }
        
        .project-card {
            background: #ffffff;
            border-radius: 20px;
            overflow: hidden;
            transition: all 0.3s ease;
            border: 2px solid #f9dde7;
            position: relative;
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 40px rgba(212, 165, 201, 0.3);
        }
        
        .project-image {
            width: 100%;
            height: 200px;
            background: linear-gradient(135deg, #f9dde7, #e8b4c8);
            position: relative;
            overflow: hidden;
        }
        
        .project-image::before {
            content: '';
            position: absolute;
            top: -50%;
            left: -50%;
            width: 200%;
            height: 200%;
            background: linear-gradient(45deg, transparent, rgba(255, 255, 255, 0.3), transparent);
            animation: shimmer 3s infinite;
        }
        
        @keyframes shimmer {
            0% { transform: translateX(-100%) translateY(-100%); }
            100% { transform: translateX(100%) translateY(100%); }
        }
        
        .project-content {
            padding: 25px;
        }
        
        .project-title {
            font-family: 'Playfair Display', serif;
            font-size: 1.3rem;
            color: #d4a5c9;
            margin-bottom: 10px;
        }
        
        .project-desc {
            color: #7a6a7e;
            line-height: 1.6;
            margin-bottom: 15px;
            font-size: 0.9rem;
        }
        
        .project-tech {
            font-size: 0.85rem;
            color: #a89aac;
            margin-bottom: 15px;
        }
        
        .project-link {
            display: inline-block;
            padding: 10px 25px;
            background: linear-gradient(135deg, #e8b4c8, #f4c2d4);
            color: white;
            text-decoration: none;
            border-radius: 25px;
            transition: all 0.3s ease;
            font-size: 0.9rem;
        }
        
        .project-link:hover {
            background: linear-gradient(135deg, #d4a5c9, #e8b4c8);
            transform: scale(1.05);
        }
        
        /* Skills section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 30px;
            margin-top: 30px;
        }
        
        .skill-category {
            background: linear-gradient(135deg, #ffffff 0%, #fef4f8 100%);
            padding: 30px;
            border-radius: 15px;
            border: 2px solid #f9dde7;
        }
        
        .skill-category h3 {
            color: #d4a5c9;
            margin-bottom: 20px;
            font-family: 'Playfair Display', serif;
        }
        
        .skill-item {
            background: #fef4f8;
            padding: 10px 15px;
            margin: 8px 0;
            border-radius: 8px;
            border-left: 3px solid #e8b4c8;
            transition: all 0.3s ease;
        }
        
        .skill-item:hover {
            background: #f9dde7;
            transform: translateX(5px);
        }
        
        /* Quote section */
        .quote-section {
            text-align: center;
            padding: 50px 20px;
            margin: 50px 0;
            position: relative;
        }
        
        .quote-text {
            font-family: 'Playfair Display', serif;
            font-size: 1.5rem;
            font-style: italic;
            color: #8a7a8e;
            max-width: 700px;
            margin: 0 auto;
            line-height: 1.8;
        }
        
        .quote-text::before,
        .quote-text::after {
            content: '"';
            font-size: 3rem;
            color: #e8b4c8;
            opacity: 0.3;
        }
        
        /* Footer */
        .footer {
            text-align: center;
            padding: 40px 20px;
            color: #8a7a8e;
            font-size: 0.9rem;
        }
        
        .social-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 20px;
        }
        
        .social-link {
            width: 50px;
            height: 50px;
            background: linear-gradient(135deg, #e8b4c8, #f4c2d4);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            text-decoration: none;
            transition: all 0.3s ease;
        }
        
        .social-link:hover {
            transform: translateY(-5px) rotate(10deg);
            box-shadow: 0 10px 25px rgba(232, 180, 200, 0.4);
        }
        
        /* Responsive */
        @media (max-width: 768px) {
            .header h1 {
                font-size: 2.5rem;
            }
            
            .about-content {
                grid-template-columns: 1fr;
            }
            
            .projects-grid,
            .skills-container {
                grid-template-columns: 1fr;
            }
        }
    </style>
</head>
<body>
    <div class="particles" id="particles"></div>
    
    <div class="container">
        <!-- Header -->
        <div class="header">
            <h1>Aditeaa</h1>
            <p class="subtitle">Full Stack Web Developer | Crafting Digital Elegance</p>
        </div>
        
        <div class="divider"></div>
        
        <!-- About Section -->
        <div class="card">
            <h2>About Me</h2>
            <div class="about-content">
                <div class="about-text">
                    <p>Hey there! I'm <strong>Aditi</strong>, a Full Stack Web Developer from India, building elegant, performance-driven web experiences that balance design, logic, and usability.</p>
                    
                    <p>I've developed <strong>12+ live websites</strong> across industries — from manufacturing and energy companies to personal brands and creative studios. I focus on crafting visually refined interfaces and robust backends that bring ideas to life.</p>
                    
                    <p>Alongside development, I also run <strong>The Ribbon Rose – Bouquet Studio</strong>, a small creative business that blends my passion for design, craft, and storytelling.</p>
                    
                    <div class="highlight-box">
                        "Code is my craft. Design is my instinct. Together, they build my world."
                    </div>
                    
                    <p><strong>What I'm currently up to:</strong></p>
                    <ul style="list-style: none; padding-left: 0;">
                        <li style="margin: 10px 0;">✦ Building scalable full-stack systems with React, Node.js & MySQL</li>
                        <li style="margin: 10px 0;">✦ Designing minimal, aesthetic, and responsive interfaces</li>
                        <li style="margin: 10px 0;">✦ Exploring product design, SEO, and web performance optimization</li>
                        <li style="margin: 10px 0;">✦ Leading end-to-end website development for brands and startups</li>
                    </ul>
                </div>
                <div class="about-image">
                    <img src="https://user-images.githubusercontent.com/74038190/229223263-cf2e4b07-2615-4f87-9c38-e37600f8381a.gif" alt="Coding">
                </div>
            </div>
        </div>
        
        <div class="divider"></div>
        
        <!-- Tech Stack -->
        <div class="card">
            <h2>Tech Stack</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>Frontend</h3>
                    <div class="skill-item">React</div>
                    <div class="skill-item">Vite</div>
                    <div class="skill-item">TailwindCSS</div>
                    <div class="skill-item">Bootstrap</div>
                    <div class="skill-item">Framer Motion</div>
                </div>
                
                <div class="skill-category">
                    <h3>Backend & Database</h3>
                    <div class="skill-item">Node.js</div>
                    <div class="skill-item">Express.js</div>
                    <div class="skill-item">MySQL</div>
                    <div class="skill-item">REST APIs</div>
                </div>
                
                <div class="skill-category">
                    <h3>Tools & Platforms</h3>
                    <div class="skill-item">Git & GitHub</div>
                    <div class="skill-item">Postman</div>
                    <div class="skill-item">Figma</div>
                    <div class="skill-item">VS Code</div>
                    <div class="skill-item">Vercel</div>
                </div>
                
                <div class="skill-category">
                    <h3>Soft Skills</h3>
                    <div class="skill-item">Problem Solving</div>
                    <div class="skill-item">UI/UX Thinking</div>
                    <div class="skill-item">Client Communication</div>
                    <div class="skill-item">Project Management</div>
                    <div class="skill-item">Creative Direction</div>
                </div>
            </div>
        </div>
        
        <div class="divider"></div>
        
        <!-- Featured Projects -->
        <div class="card">
            <h2>Featured Projects</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <div class="project-image"></div>
                    <div class="project-content">
                        <h3 class="project-title">Nikki's Bakes</h3>
                        <p class="project-desc">A warm, modern bakery website showcasing handcrafted desserts with a soft visual palette and smooth transitions.</p>
                        <p class="project-tech"><strong>Tech:</strong> React, TailwindCSS</p>
                        <a href="https://nikkis-bakes.vercel.app/" target="_blank" class="project-link">View Live</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image"></div>
                    <div class="project-content">
                        <h3 class="project-title">Mili's Portfolio</h3>
                        <p class="project-desc">A clean and elegant personal portfolio built to highlight a creative professional's story and projects.</p>
                        <p class="project-tech"><strong>Tech:</strong> React, Vite, TailwindCSS</p>
                        <a href="https://milisheth.in/" target="_blank" class="project-link">View Live</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image"></div>
                    <div class="project-content">
                        <h3 class="project-title">Window & Door Quotation Generator</h3>
                        <p class="project-desc">A business tool for generating instant window & door quotations with GST pricing, responsive UI, and PDF export.</p>
                        <p class="project-tech"><strong>Tech:</strong> React, TailwindCSS, Node.js</p>
                        <a href="https://window-door-quotation.vercel.app/" target="_blank" class="project-link">View Live</a>
                    </div>
                </div>
                
                <div class="project-card">
                    <div class="project-image"></div>
                    <div class="project-content">
                        <h3 class="project-title">Company Projects</h3>
                        <p class="project-desc">Developed and maintained multiple production-level company websites for corporate and industrial clients.</p>
                        <p class="project-tech"><strong>Tech:</strong> React, Node.js, MySQL</p>
                        <span style="padding: 10px 25px; background: #f9dde7; color: #8a7a8e; border-radius: 25px; font-size: 0.9rem; display: inline-block;">Private</span>
                    </div>
                </div>
            </div>
        </div>
        
        <div class="divider"></div>
        
        <!-- Quote Section -->
        <div class="quote-section">
            <p class="quote-text">Good design is as little design as possible</p>
            <p style="margin-top: 15px; color: #a89aac; font-size: 0.9rem;">— Dieter Rams</p>
        </div>
        
        <!-- Footer -->
        <div class="footer">
            <p>Made with love by Aditeaa</p>
            <p style="margin-top: 10px; font-size: 0.85rem; color: #a89aac;">Crafting beautiful experiences, one commit at a time</p>
        </div>
    </div>
    
    <script>
        // Create floating particles
        const particlesContainer = document.getElementById('particles');
        for (let i = 0; i < 30; i++) {
            const particle = document.createElement('div');
            particle.className = 'particle';
            particle.style.left = Math.random() * 100 + '%';
            particle.style.top = Math.random() * 100 + '%';
            particle.style.animationDelay = Math.random() * 15 + 's';
            particle.style.animationDuration = (Math.random() * 10 + 10) + 's';
            particlesContainer.appendChild(particle);
        }
        
        // Animate cards on scroll
        const cards = document.querySelectorAll('.card');
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
        
        cards.forEach(card => {
            card.style.opacity = '0';
            card.style.transform = 'translateY(30px)';
            card.style.transition = 'all 0.8s ease';
            observer.observe(card);
        });
    </script>
</body>
</html>
