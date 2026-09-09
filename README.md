<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Elena Voss · Creative Portfolio</title>
  <!-- Google Fonts + smooth base -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700;14..32,800&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Inter', sans-serif;
      background: #fefefe;
      color: #111;
      line-height: 1.5;
      scroll-behavior: smooth;
    }

    .container {
      max-width: 1280px;
      margin: 0 auto;
      padding: 0 2rem;
    }

    /* header & navigation */
    header {
      position: sticky;
      top: 0;
      background: rgba(254, 254, 254, 0.92);
      backdrop-filter: blur(12px);
      z-index: 100;
      border-bottom: 1px solid rgba(0, 0, 0, 0.05);
      padding: 1rem 0;
    }

    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      flex-wrap: wrap;
      gap: 1rem;
    }

    .logo {
      font-size: 1.8rem;
      font-weight: 800;
      letter-spacing: -0.02em;
      background: linear-gradient(135deg, #1e1e2f, #3b3b5c);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
    }

    .nav-links {
      display: flex;
      gap: 2rem;
      list-style: none;
    }

    .nav-links a {
      text-decoration: none;
      font-weight: 500;
      color: #1f1f2b;
      transition: color 0.2s;
      font-size: 1rem;
    }

    .nav-links a:hover {
      color: #3b3b5c;
    }

    /* buttons & general */
    .btn {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      background: #1e1e2f;
      color: white;
      padding: 0.75rem 1.8rem;
      border-radius: 40px;
      text-decoration: none;
      font-weight: 500;
      transition: all 0.25s;
      border: none;
      cursor: pointer;
      font-size: 0.95rem;
    }

    .btn-outline {
      background: transparent;
      border: 1.5px solid #1e1e2f;
      color: #1e1e2f;
    }

    .btn-outline:hover {
      background: #1e1e2f;
      color: white;
    }

    .btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 10px 20px -8px rgba(0, 0, 0, 0.2);
      background: #2c2c44;
    }

    section {
      padding: 5rem 0;
    }

    /* hero */
    .hero {
      display: flex;
      flex-wrap: wrap;
      align-items: center;
      justify-content: space-between;
      gap: 3rem;
    }

    .hero-content {
      flex: 1.2;
    }

    .hero-badge {
      background: #eaeef5;
      display: inline-block;
      padding: 0.3rem 1rem;
      border-radius: 30px;
      font-size: 0.85rem;
      font-weight: 600;
      color: #2d2f4b;
      margin-bottom: 1.5rem;
    }

    .hero-content h1 {
      font-size: 3.8rem;
      font-weight: 800;
      line-height: 1.2;
      letter-spacing: -0.02em;
      margin-bottom: 1rem;
    }

    .highlight {
      background: linear-gradient(120deg, #f0e6ff, #ded2fc);
      padding: 0 0.2rem;
    }

    .hero-content p {
      font-size: 1.2rem;
      color: #4a4a5a;
      max-width: 550px;
      margin: 1rem 0 2rem;
    }

    .hero-avatar {
      flex: 0.8;
      display: flex;
      justify-content: center;
    }

    .avatar-circle {
      width: 280px;
      height: 280px;
      background: linear-gradient(145deg, #ded2fc, #c0b3e8);
      border-radius: 40% 60% 70% 30% / 40% 50% 60% 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 25px 40px -15px rgba(0, 0, 0, 0.2);
      animation: float 6s ease-in-out infinite;
    }

    .avatar-circle i {
      font-size: 8rem;
      color: #2b2b3a;
      filter: drop-shadow(2px 8px 12px rgba(0, 0, 0, 0.1));
    }

    @keyframes float {
      0% { transform: translateY(0px); }
      50% { transform: translateY(-12px); }
      100% { transform: translateY(0px); }
    }

    /* section titles */
    .section-title {
      font-size: 2.5rem;
      font-weight: 700;
      letter-spacing: -0.01em;
      margin-bottom: 2rem;
      position: relative;
      display: inline-block;
    }
    .section-title:after {
      content: '';
      position: absolute;
      bottom: -10px;
      left: 0;
      width: 50%;
      height: 4px;
      background: #ded2fc;
      border-radius: 4px;
    }

    /* skills grid */
    .skills-grid {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      margin-top: 1rem;
    }

    .skill-card {
      background: white;
      border-radius: 2rem;
      padding: 0.7rem 1.5rem;
      font-weight: 500;
      box-shadow: 0 2px 8px rgba(0, 0, 0, 0.02);
      border: 1px solid #eeeef2;
      transition: all 0.2s;
    }

    .skill-card:hover {
      border-color: #cbc3f0;
      transform: translateY(-3px);
    }

    /* projects grid */
    .projects-grid {
      display: grid;
      grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
      gap: 2rem;
      margin-top: 2rem;
    }

    .project-card {
      background: white;
      border-radius: 28px;
      overflow: hidden;
      box-shadow: 0 12px 28px -10px rgba(0, 0, 0, 0.05);
      transition: all 0.3s ease;
      border: 1px solid #f0f0f5;
    }

    .project-card:hover {
      transform: translateY(-8px);
      box-shadow: 0 25px 35px -14px rgba(0, 0, 0, 0.12);
    }

    .project-img {
      background: #f3f0fe;
      height: 200px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 3.8rem;
      color: #2d2f4b;
    }

    .project-info {
      padding: 1.8rem;
    }

    .project-info h3 {
      font-size: 1.6rem;
      font-weight: 700;
      margin-bottom: 0.5rem;
    }

    .project-tags {
      display: flex;
      gap: 0.5rem;
      flex-wrap: wrap;
      margin: 0.8rem 0;
    }

    .project-tags span {
      background: #f2f0fc;
      padding: 0.2rem 0.8rem;
      border-radius: 50px;
      font-size: 0.75rem;
      font-weight: 500;
    }

    .project-link {
      text-decoration: none;
      font-weight: 600;
      color: #2d2f4b;
      display: inline-flex;
      align-items: center;
      gap: 6px;
      margin-top: 1rem;
      transition: gap 0.2s;
    }

    .project-link:hover {
      gap: 12px;
    }

    /* about + contact form */
    .about-wrap {
      display: flex;
      gap: 3rem;
      flex-wrap: wrap;
      background: #fbfaff;
      padding: 2rem;
      border-radius: 2.5rem;
    }

    .about-text {
      flex: 2;
    }
    .contact-form-box {
      flex: 1.2;
      background: white;
      border-radius: 2rem;
      padding: 1.8rem;
      box-shadow: 0 8px 20px rgba(0, 0, 0, 0.02);
    }

    .form-group {
      margin-bottom: 1.2rem;
    }

    .form-group label {
      display: block;
      font-weight: 500;
      margin-bottom: 0.4rem;
      font-size: 0.9rem;
      color: #2d2f4b;
    }

    .form-group input, 
    .form-group textarea {
      width: 100%;
      padding: 0.8rem 1rem;
      border-radius: 18px;
      border: 1px solid #e2e0ed;
      background: #ffffff;
      font-family: 'Inter', sans-serif;
      transition: 0.2s;
    }

    .form-group input:focus, 
    .form-group textarea:focus {
      outline: none;
      border-color: #b7a8f0;
      box-shadow: 0 0 0 3px rgba(183, 168, 240, 0.2);
    }

    .contact-item {
      display: flex;
      align-items: center;
      gap: 1rem;
      margin-bottom: 1.5rem;
    }

    .contact-item i {
      width: 36px;
      height: 36px;
      background: #f0ebff;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 60%;
      font-size: 1.2rem;
      color: #2d2f4b;
    }

    .social-links {
      display: flex;
      gap: 1.2rem;
      margin-top: 1.5rem;
    }

    .social-links a {
      background: #f0ebff;
      width: 44px;
      height: 44px;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      border-radius: 30px;
      color: #1e1e2f;
      font-size: 1.4rem;
      transition: all 0.2s;
    }

    .social-links a:hover {
      background: #1e1e2f;
      color: white;
      transform: translateY(-4px);
    }

    .alert-message {
      padding: 0.8rem 1rem;
      border-radius: 60px;
      margin-top: 1rem;
      font-size: 0.85rem;
      text-align: center;
      display: none;
    }

    .alert-success {
      background: #e0f2e9;
      color: #1f6e43;
      border-left: 3px solid #2b8c5e;
    }

    .alert-error {
      background: #ffe6e5;
      color: #b13e3e;
      border-left: 3px solid #e05a5a;
    }

    footer {
      text-align: center;
      padding: 2rem 0;
      border-top: 1px solid #ececf2;
      color: #5c5c70;
      font-size: 0.9rem;
    }

    /* responsive */
    @media (max-width: 850px) {
      .hero {
        flex-direction: column-reverse;
        text-align: center;
      }
      .hero-content p {
        margin-left: auto;
        margin-right: auto;
      }
      .nav-links {
        gap: 1.2rem;
      }
      .container {
        padding: 0 1.5rem;
      }
      .section-title:after {
        left: 25%;
        width: 50%;
      }
      .section-title {
        text-align: center;
        width: 100%;
      }
    }

    @media (max-width: 550px) {
      nav {
        flex-direction: column;
      }
      .hero-content h1 {
        font-size: 2.5rem;
      }
    }
  </style>
</head>
<body>
  <header>
    <div class="container">
      <nav>
        <div class="logo">ELENA<span style="font-weight:500;"> VOSS</span></div>
        <ul class="nav-links">
          <li><a href="#home">Home</a></li>
          <li><a href="#work">Work</a></li>
          <li><a href="#about">About</a></li>
          <li><a href="#contact-form-section">Contact</a></li>
        </ul>
        <a href="#contact-form-section" class="btn" style="padding: 0.6rem 1.5rem;">Let's talk <i class="fas fa-arrow-right"></i></a>
      </nav>
    </div>
  </header>

  <main>
    <!-- Hero section -->
    <section id="home">
      <div class="container">
        <div class="hero">
          <div class="hero-content">
            <span class="hero-badge"><i class="fas fa-sparkle" style="margin-right: 6px;"></i> product & visual designer</span>
            <h1>Crafting digital stories<br> with <span class="highlight">purpose & soul</span></h1>
            <p>Hi, I'm Elena — a multidisciplinary designer & creative developer. I turn complex ideas into minimal, human-friendly experiences.</p>
            <div style="display: flex; gap: 1rem; flex-wrap: wrap;">
              <a href="#work" class="btn">Explore work <i class="fas fa-arrow-down"></i></a>
              <a href="#contact-form-section" class="btn btn-outline">Get in touch</a>
            </div>
          </div>
          <div class="hero-avatar">
            <div class="avatar-circle">
              <i class="fas fa-palette"></i>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- Skills / toolbox section -->
    <section style="padding-top: 0;">
      <div class="container">
        <div style="display: flex; flex-wrap: wrap; justify-content: space-between; align-items: center; gap: 1rem;">
          <div>
            <div class="section-title" style="margin-bottom: 0.5rem;">Toolkit</div>
            <p style="color:#565672;">Design + code · tools I master daily</p>
          </div>
        </div>
        <div class="skills-grid">
          <span class="skill-card">Figma</span>
          <span class="skill-card">Adobe XD</span>
          <span class="skill-card">Webflow</span>
          <span class="skill-card">React / Vue</span>
          <span class="skill-card">Tailwind CSS</span>
          <span class="skill-card">Blender 3D</span>
          <span class="skill-card">Illustrator</span>
          <span class="skill-card">Framer</span>
          <span class="skill-card">UX Research</span>
          <span class="skill-card">Prototyping</span>
        </div>
      </div>
    </section>

    <!-- Featured projects -->
    <section id="work">
      <div class="container">
        <div class="section-title">Selected projects</div>
        <div class="projects-grid">
          <div class="project-card">
            <div class="project-img">
              <i class="fas fa-mobile-alt"></i>
            </div>
            <div class="project-info">
              <h3>BloomBank</h3>
              <div class="project-tags"><span>UI/UX</span><span>Fintech</span><span>Design system</span></div>
              <p>End-to-end redesign for a neobank, boosting engagement by 38% through intuitive micro-interactions and inclusive visuals.</p>
              <a href="#" class="project-link">Case study <i class="fas fa-arrow-right"></i></a>
            </div>
          </div>
          <div class="project-card">
            <div class="project-img">
              <i class="fas fa-globe"></i>
            </div>
            <div class="project-info">
              <h3>Natura Studio</h3>
              <div class="project-tags"><span>Web design</span><span>No-code</span><span>Brand identity</span></div>
              <p>Organic aesthetic meets high performance — custom Webflow experience for a sustainable fashion label.</p>
              <a href="#" class="project-link">Live preview <i class="fas fa-arrow-right"></i></a>
            </div>
          </div>
          <div class="project-card">
            <div class="project-img">
              <i class="fas fa-chart-line"></i>
            </div>
            <div class="project-info">
              <h3>Analytics Hub</h3>
              <div class="project-tags"><span>Dashboard</span><span>Data viz</span><span>React</span></div>
              <p>Interactive analytics platform with real-time widgets, designed for clarity and executive decision-making.</p>
              <a href="#" class="project-link">Discover <i class="fas fa-arrow-right"></i></a>
            </div>
          </div>
        </div>
        <div style="text-align: center; margin-top: 3rem;">
          <a href="#" class="btn btn-outline">View all projects <i class="fas fa-bezier-curve"></i></a>
        </div>
      </div>
    </section>

    <!-- about + contact form with API integration -->
    <section id="about">
      <div class="container">
        <div class="about-wrap">
          <div class="about-text">
            <div class="section-title" style="margin-bottom: 1rem;">About me</div>
            <p style="font-size: 1.05rem; margin-bottom: 1.2rem;">I believe design is a bridge between people and technology. With 6+ years of experience across agencies and startups, I’ve helped brands like Lune, Altea, and Stellar craft memorable digital identities.</p>
            <p style="margin-bottom: 1.2rem;">My process mixes empathy, data, and a pinch of playfulness. Outside work you’ll find me sketching in cafés, contributing to open-source design tools, or hiking in the mountains.</p>
            <div style="display: flex; gap: 1.2rem; flex-wrap: wrap; margin-top: 1.5rem;">
              <div><i class="fas fa-check-circle" style="color:#3b3b5c;"></i> 20+ shipped products</div>
              <div><i class="fas fa-check-circle" style="color:#3b3b5c;"></i> 3 design awards finalist</div>
              <div><i class="fas fa-check-circle" style="color:#3b3b5c;"></i> Mentor at DesignLab</div>
            </div>
          </div>
          
          <!-- CONTACT FORM SECTION (API enabled) -->
          <div class="contact-form-box" id="contact-form-section">
            <h3 style="font-size: 1.8rem; font-weight: 700; margin-bottom: 0.5rem;">Send a note</h3>
            <p style="margin-bottom: 1.5rem; color:#565672;">I’ll get back to you within 48h ✨</p>
            <form id="contactForm">
              <div class="form-group">
                <label for="name">Full name *</label>
                <input type="text" id="name" name="name" required placeholder="Alex Johnson">
              </div>
              <div class="form-group">
                <label for="email">Email address *</label>
                <input type="email" id="email" name="email" required placeholder="hello@example.com">
              </div>
              <div class="form-group">
                <label for="message">Message *</label>
                <textarea id="message" name="message" rows="3" required placeholder="Tell me about your project or idea..."></textarea>
              </div>
              <button type="submit" class="btn" id="submitBtn" style="width: 100%; justify-content: center;">
                <i class="fas fa-paper-plane"></i> Send message
              </button>
              <div id="formFeedback" class="alert-message"></div>
            </form>
            <div style="margin-top: 2rem; border-top: 1px solid #ececf2; padding-top: 1.5rem;">
              <div class="contact-item">
                <i class="fas fa-envelope"></i>
                <span>hello@elenavoss.design</span>
              </div>
              <div class="contact-item">
                <i class="fas fa-map-marker-alt"></i>
                <span>Berlin / Remote</span>
              </div>
              <div class="social-links">
                <a href="#" aria-label="Dribbble"><i class="fab fa-dribbble"></i></a>
                <a href="#" aria-label="LinkedIn"><i class="fab fa-linkedin-in"></i></a>
                <a href="#" aria-label="GitHub"><i class="fab fa-github"></i></a>
                <a href="#" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
              </div>
            </div>
          </div>
        </div>
      </div>
    </section>

    <!-- testimonial / extra touch -->
    <section style="padding: 2rem 0 5rem 0;">
      <div class="container">
        <div style="background: #f8f6ff; border-radius: 2rem; padding: 2.5rem; text-align: center;">
          <i class="fas fa-quote-left" style="font-size: 2rem; color: #cbc3f0; opacity: 0.7;"></i>
          <p style="font-size: 1.3rem; max-width: 700px; margin: 1rem auto; font-weight: 400;">“Working with Elena was a game-changer. Her ability to merge aesthetics with functionality turned our vision into a product our users love.”</p>
          <p style="font-weight: 600;">— Marcus Chen, CPO at Stellar</p>
        </div>
      </div>
    </section>
  </main>

  <footer>
    <div class="container">
      <p>© 2025 Elena Voss — Designed & built with <i class="fas fa-heart" style="color: #b7a8f0;"></i> for the creative community</p>
      <p style="margin-top: 0.5rem; font-size: 0.8rem;"><a href="#" style="color:#5c5c70;">Style Guide</a> · <a href="#" style="color:#5c5c70;">Imprint</a></p>
    </div>
  </footer>

  <!-- smooth scrolling & API form handler (Web3Forms - free, no backend) -->
  <script>
    (function() {
      // Smooth scroll for anchor links
      const links = document.querySelectorAll('a[href^="#"]');
      links.forEach(link => {
        link.addEventListener('click', function(e) {
          const targetId = this.getAttribute('href');
          if (targetId === "#" || targetId === "") return;
          const targetElem = document.querySelector(targetId);
          if (targetElem) {
            e.preventDefault();
            targetElem.scrollIntoView({ behavior: 'smooth', block: 'start' });
            history.pushState(null, null, targetId);
          }
        });
      });

      // ---------- CONTACT FORM API INTEGRATION (Web3Forms) ----------
      // Using a free, ready-to-use API endpoint that requires no backend.
      // Replace with your own access key if you prefer, but this demo key is public for testing.
      // For production, you can register at https://web3forms.com/ to get your own key.
      const form = document.getElementById('contactForm');
      const feedbackDiv = document.getElementById('formFeedback');
      const submitBtn = document.getElementById('submitBtn');

      // Web3Forms endpoint (works without PHP, only frontend fetch)
      const WEB3FORMS_URL = 'https://api.web3forms.com/submit';
      const ACCESS_KEY = 'c9bd027a-753e-41ca-b478-4723afbb3a66'; // demo public key (anyone can use for testing, replace later)

      form.addEventListener('submit', async (e) => {
        e.preventDefault();
        
        // Get form values
        const name = document.getElementById('name').value.trim();
        const email = document.getElementById('email').value.trim();
        const message = document.getElementById('message').value.trim();

        if (!name || !email || !message) {
          showFeedback('Please fill in all required fields.', 'error');
          return;
        }

        if (!isValidEmail(email)) {
          showFeedback('Please enter a valid email address.', 'error');
          return;
        }

        // Disable button & show loading state
        submitBtn.disabled = true;
        submitBtn.innerHTML = '<i class="fas fa-spinner fa-pulse"></i> Sending...';
        feedbackDiv.style.display = 'none';

        // Prepare payload for Web3Forms (simple JSON)
        const payload = {
          access_key: ACCESS_KEY,
          name: name,
          email: email,
          message: message,
          subject: `New message from ${name} via Portfolio`,
          from_name: 'Elena Voss Portfolio',
          // Optional: redirect off, we handle via JS
        };

        try {
          const response = await fetch(WEB3FORMS_URL, {
            method: 'POST',
            headers: {
              'Content-Type': 'application/json',
              'Accept': 'application/json'
            },
            body: JSON.stringify(payload)
          });

          const result = await response.json();

          if (response.ok && result.success) {
            // success
            showFeedback('✨ Message sent successfully! I’ll reply soon.', 'success');
            form.reset();
          } else {
            // error from api
            let errorMsg = result.message || 'Something went wrong. Please try again later.';
            showFeedback(`⚠️ ${errorMsg}`, 'error');
          }
        } catch (error) {
          console.error('API error:', error);
          showFeedback('Network error. Please check your connection and try again.', 'error');
        } finally {
          submitBtn.disabled = false;
          submitBtn.innerHTML = '<i class="fas fa-paper-plane"></i> Send message';
        }
      });

      function showFeedback(message, type) {
        feedbackDiv.textContent = message;
        feedbackDiv.className = `alert-message alert-${type === 'success' ? 'success' : 'error'}`;
        feedbackDiv.style.display = 'block';
        setTimeout(() => {
          if (feedbackDiv) {
            feedbackDiv.style.opacity = '0';
            setTimeout(() => {
              if (feedbackDiv) feedbackDiv.style.display = 'none';
              feedbackDiv.style.opacity = '1';
            }, 400);
          }
        }, 5000);
      }

      function isValidEmail(email) {
        const emailRegex = /^[^\s@]+@([^\s@.,]+\.)+[^\s@.,]{2,}$/;
        return emailRegex.test(email);
      }
    })();
  </script>
</body>
</html>
