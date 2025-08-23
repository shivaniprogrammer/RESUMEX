# RESUMEX...!

<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>AI-Powered Resume & Portfolio</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    :root {
      --primary: #1fa2ff;
      --secondary: #12d8fa;
      --accent: #a6ffcb;
      --bg-light: #f7faff;
      --bg-dark: #1a2233;
      --surface-light: #fff;
      --surface-dark: #232c43;
      --text-light: #1a2233;
      --text-dark: #f6f7fb;
      --heading-underline: linear-gradient(90deg, #1fa2ff 0%, #12d8fa 50%, #a6ffcb 100%);
      --card-glow: 0 4px 24px 0 rgba(31,162,255,0.12);
      --shadow: 0 2px 8px rgba(20,40,70,0.06);
      --transition: 0.35s cubic-bezier(.55,0,.1,1);
      --border-radius: 16px;
    }

    [data-theme="dark"] {
      --bg-light: var(--bg-dark);
      --text-light: var(--text-dark);
      --surface-light: var(--surface-dark);
      --card-glow: 0 4px 24px 0 rgba(31,162,255,0.18);
      --shadow: 0 2px 12px rgba(20,40,70,0.18);
    }

    html, body {
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', 'Roboto', Arial, sans-serif;
      background: var(--bg-light);
      color: var(--text-light);
      transition: background var(--transition), color var(--transition);
      min-height: 100%;
      scroll-behavior: smooth;
    }

    main {
      width: 100%;
      max-width: 1120px;
      margin: 0 auto;
      padding: 32px 16px 80px 16px;
      box-sizing: border-box;
    }

    header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin: 0 0 32px 0;
    }

    .mode-toggle {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 1rem;
      cursor: pointer;
      background: var(--surface-light);
      color: var(--text-light);
      padding: 6px 14px;
      border-radius: 20px;
      border: none;
      box-shadow: var(--shadow);
      transition: background var(--transition), color var(--transition);
      outline: none;
    }

    h1, h2, h3 {
      text-align: center;
      margin-bottom: 8px;
      color: var(--text-light);
      font-weight: 700;
      letter-spacing: 1px;
      position: relative;
    }

    h1 {
      font-size: 2.5rem;
      margin-top: 24px;
    }
    h2 {
      font-size: 2rem;
      margin-top: 48px;
    }
    h3 {
      font-size: 1.2rem;
      margin: 0 0 12px 0;
    }

    .heading-underline {
      display: inline-block;
      padding-bottom: 5px;
      border-bottom: 4px solid transparent;
      background: var(--heading-underline);
      -webkit-background-clip: text;
      color: inherit;
      background-clip: text;
      border-image: var(--heading-underline) 1;
      border-width: 0 0 4px 0;
      border-style: solid;
      margin-bottom: 16px;
    }

    /* Hero Section */
    .hero {
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 48px 0 24px 0;
      background: linear-gradient(120deg, #1fa2ff 0%, #12d8fa 60%, #a6ffcb 100%);
      border-radius: 0 0 32px 32px;
      box-shadow: 0 12px 32px -12px rgba(31,162,255,0.12);
      color: #fff;
      position: relative;
      overflow: hidden;
    }
    .hero .heading-underline {
      color: #fff;
    }

    .bio-summarize {
      margin: 28px 0 0 0;
      display: flex;
      flex-direction: column;
      align-items: center;
      width: 100%;
      max-width: 500px;
    }
    .bio-summarize textarea {
      width: 100%;
      min-height: 60px;
      border-radius: 12px;
      border: none;
      padding: 12px;
      font-size: 1rem;
      margin-bottom: 12px;
      resize: vertical;
      background: #ffffffda;
      color: #1a2233;
      box-shadow: var(--shadow);
      outline: none;
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .bio-summarize textarea {
      background: #232c43ee;
      color: #f6f7fb;
    }
    .btn {
      appearance: none;
      border: none;
      padding: 10px 26px;
      border-radius: 24px;
      background: linear-gradient(90deg, #1fa2ff 0%, #12d8fa 50%, #a6ffcb 100%);
      color: #fff;
      font-size: 1.05rem;
      font-weight: 600;
      box-shadow: var(--shadow);
      cursor: pointer;
      transition: background var(--transition), color var(--transition), box-shadow var(--transition);
      margin-bottom: 8px;
    }
    .btn:active {
      filter: brightness(0.92);
      box-shadow: 0 1px 6px rgba(31,162,255,0.18);
    }

    .hero-summary {
      margin: 18px 0 0 0;
      min-height: 44px;
      text-align: center;
      font-size: 1.13rem;
      color: #fff;
      background: rgba(20,40,70,0.08);
      padding: 10px 18px;
      border-radius: 12px;
      font-style: italic;
      box-shadow: 0 1px 8px rgba(31,162,255,0.07);
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .hero-summary {
      background: rgba(35,44,67,0.44);
      color: #f6f7fb;
    }

    /* Timeline Section */
    .timeline-section {
      padding: 32px 0 0 0;
    }
    .timeline {
      position: relative;
      margin: 40px auto 0 auto;
      padding-left: 18px;
      max-width: 700px;
    }
    .timeline:before {
      content: "";
      position: absolute;
      left: 17px;
      top: 0;
      bottom: 0;
      width: 4px;
      background: linear-gradient(to bottom, #1fa2ff 0%, #12d8fa 100%);
      border-radius: 2px;
      z-index: 0;
    }
    .timeline-item {
      position: relative;
      margin-bottom: 44px;
      opacity: 0;
      transform: translateY(60px);
      transition: opacity 0.7s var(--transition), transform 0.7s var(--transition);
      z-index: 1;
    }
    .timeline-item.visible {
      opacity: 1;
      transform: translateY(0);
    }
    .timeline-dot {
      position: absolute;
      left: -2px;
      top: 0;
      width: 22px;
      height: 22px;
      background: linear-gradient(120deg, #12d8fa, #a6ffcb);
      border-radius: 50%;
      border: 4px solid #fff;
      box-shadow: 0 2px 14px rgba(31,162,255,0.13);
      z-index: 2;
    }
    .timeline-content {
      margin-left: 38px;
      background: var(--surface-light);
      box-shadow: var(--card-glow);
      padding: 18px 22px;
      border-radius: var(--border-radius);
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .timeline-content {
      background: var(--surface-dark);
      color: var(--text-dark);
    }
    .timeline-title {
      font-weight: 600;
      font-size: 1.13rem;
      margin: 0 0 6px 0;
    }
    .timeline-date {
      font-size: 0.98rem;
      color: #1fa2ff;
      font-weight: 500;
      margin-bottom: 7px;
    }

    /* Skills Section */
    .skills-section {
      margin: 50px 0 0 0;
      padding: 0 0 16px 0;
    }
    .skills-list {
      max-width: 640px;
      margin: 35px auto 0 auto;
      display: flex;
      flex-direction: column;
      gap: 22px;
    }
    .skill-bar-container {
      width: 100%;
      background: var(--surface-light);
      border-radius: 20px;
      box-shadow: var(--shadow);
      padding: 10px 20px;
      display: flex;
      flex-direction: column;
      gap: 7px;
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .skill-bar-container {
      background: var(--surface-dark);
      color: var(--text-dark);
    }
    .skill-bar-labels {
      display: flex;
      justify-content: space-between;
      align-items: center;
      font-size: 1.04rem;
      margin-bottom: 5px;
      font-weight: 500;
    }
    .skill-bar-bg {
      height: 14px;
      background: #ddeffd;
      border-radius: 14px;
      overflow: hidden;
      position: relative;
    }
    [data-theme="dark"] .skill-bar-bg {
      background: #233548;
    }
    .skill-bar {
      height: 100%;
      border-radius: 14px;
      width: 0;
      background: linear-gradient(90deg, #1fa2ff 0%, #12d8fa 50%, #a6ffcb 100%);
      box-shadow: 0 2px 8px rgba(31,162,255,0.16);
      transition: width 1.4s cubic-bezier(.55,0,.1,1);
    }

    /* Achievements Section */
    .achievements-section {
      margin-top: 56px;
    }
    .achievements-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(230px, 1fr));
      gap: 32px;
      margin: 36px 0 0 0;
    }
    .achievement-card {
      background: var(--surface-light);
      border-radius: var(--border-radius);
      box-shadow: var(--card-glow);
      padding: 28px 22px 22px 22px;
      display: flex;
      flex-direction: column;
      align-items: flex-start;
      gap: 14px;
      position: relative;
      transition: background var(--transition), color var(--transition);
      min-height: 200px;
    }
    [data-theme="dark"] .achievement-card {
      background: var(--surface-dark);
      color: var(--text-dark);
    }
    .achievement-title {
      font-weight: 600;
      font-size: 1.13rem;
      color: #1fa2ff;
      margin-bottom: 2px;
    }
    .achievement-desc {
      font-size: 0.99rem;
      color: inherit;
    }
    .learn-more-btn {
      margin-top: auto;
      font-size: 0.98rem;
      padding: 8px 18px;
    }

    /* AI Resume Score Section */
    .resume-score-section {
      margin-top: 52px;
      background: linear-gradient(90deg, #f7faff 70%, #a6ffcb33 100%);
      border-radius: var(--border-radius);
      box-shadow: 0 2px 14px rgba(31,162,255,0.09);
      padding: 28px 16px;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
    }
    [data-theme="dark"] .resume-score-section {
      background: linear-gradient(90deg, #232c43 70%, #12d8fa11 100%);
    }
    .resume-upload-label {
      display: block;
      margin-bottom: 12px;
      font-weight: 500;
      font-size: 1.05rem;
    }
    .resume-upload-input {
      display: block;
      margin-bottom: 16px;
      font-size: 1rem;
    }
    .resume-analysis {
      margin-top: 18px;
      background: var(--surface-light);
      color: var(--text-light);
      border-radius: 12px;
      padding: 16px 19px;
      min-height: 54px;
      font-size: 1.03rem;
      box-shadow: var(--shadow);
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .resume-analysis {
      background: var(--surface-dark);
      color: var(--text-dark);
    }

    /* Career Match Section */
    .career-match-section {
      margin-top: 54px;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
      padding: 22px 16px;
      background: var(--surface-light);
      border-radius: var(--border-radius);
      box-shadow: var(--card-glow);
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .career-match-section {
      background: var(--surface-dark);
      color: var(--text-dark);
    }
    .career-match-form {
      display: flex;
      flex-direction: row;
      align-items: center;
      gap: 12px;
      justify-content: center;
      margin-top: 12px;
      flex-wrap: wrap;
    }
    .career-match-select {
      padding: 7px 16px;
      border-radius: 14px;
      border: 1.5px solid #1fa2ff;
      font-size: 1rem;
      background: var(--bg-light);
      color: var(--text-light);
      outline: none;
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .career-match-select {
      background: var(--bg-dark);
      color: var(--text-dark);
      border-color: #12d8fa;
    }
    .career-match-result {
      margin-top: 16px;
      background: var(--surface-light);
      color: var(--text-light);
      border-radius: 12px;
      padding: 14px 18px;
      min-height: 54px;
      font-size: 1.03rem;
      box-shadow: var(--shadow);
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .career-match-result {
      background: var(--surface-dark);
      color: var(--text-dark);
    }

    /* Download Resume Section */
    .download-section {
      margin-top: 54px;
      display: flex;
      justify-content: center;
      align-items: center;
      gap: 16px;
      flex-wrap: wrap;
    }
    .download-btn {
      padding: 12px 30px;
      font-size: 1.07rem;
      font-weight: 600;
    }

    /* AI Career Advice Section */
    .career-advice-section {
      margin-top: 54px;
      background: linear-gradient(90deg, #f7faff 70%, #a6ffcb33 100%);
      border-radius: var(--border-radius);
      box-shadow: 0 2px 14px rgba(31,162,255,0.09);
      padding: 28px 16px;
      max-width: 700px;
      margin-left: auto;
      margin-right: auto;
    }
    [data-theme="dark"] .career-advice-section {
      background: linear-gradient(90deg, #232c43 70%, #12d8fa11 100%);
    }
    .career-advice-form {
      display: flex;
      flex-direction: row;
      align-items: center;
      gap: 12px;
      justify-content: center;
      margin-top: 12px;
      flex-wrap: wrap;
    }
    .career-advice-input {
      flex: 1;
      min-width: 180px;
      max-width: 380px;
      padding: 8px 16px;
      border-radius: 14px;
      border: 1.5px solid #1fa2ff;
      font-size: 1rem;
      background: var(--bg-light);
      color: var(--text-light);
      outline: none;
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .career-advice-input {
      background: var(--bg-dark);
      color: var(--text-dark);
      border-color: #12d8fa;
    }
    .career-advice-result {
      margin-top: 16px;
      background: var(--surface-light);
      color: var(--text-light);
      border-radius: 12px;
      padding: 14px 18px;
      min-height: 54px;
      font-size: 1.03rem;
      box-shadow: var(--shadow);
      transition: background var(--transition), color var(--transition);
    }
    [data-theme="dark"] .career-advice-result {
      background: var(--surface-dark);
      color: var(--text-dark);
    }

    /* Responsive Design */
    @media (max-width: 900px) {
      main {
        max-width: 99vw;
      }
      .timeline {
        max-width: 95vw;
      }
    }
    @media (max-width: 650px) {
      .hero {
        padding: 28px 0 18px 0;
        border-radius: 0 0 20px 20px;
      }
      .timeline-section, .skills-section, .achievements-section {
        padding: 0 0 12px 0;
      }
      .resume-score-section, .career-match-section, .career-advice-section {
        padding: 18px 6px;
      }
      .achievements-grid {
        gap: 18px;
      }
      h1 {
        font-size: 2rem;
      }
      h2 {
        font-size: 1.2rem;
      }
    }
    @media (max-width: 480px) {
      h1 {
        font-size: 1.5rem;
      }
      main {
        padding: 12px 2px 60px 2px;
      }
      .download-btn {
        padding: 10px 16px;
        font-size: 0.98rem;
      }
    }
  </style>
</head>
<body>
  <header>
    <div></div>
    <button class="mode-toggle" id="darkModeBtn"><span id="modeLabel">Dark Mode</span></button>
  </header>
  <main>
    <!-- Hero Section -->
    <section class="hero">
      <h1 class="heading-underline">AI-Powered Resume & Portfolio</h1>
      <div class="bio-summarize">
        <textarea id="bioInput" placeholder="Type your own bio here, or paste your LinkedIn summary..."></textarea>
        <button class="btn" id="summarizeBtn">Summarize Me</button>
        <div class="hero-summary" id="heroSummary">
          A professional with a passion for technology, creativity, and continuous learning. Explore my AI-enhanced portfolio and resume!
        </div>
      </div>
    </section>

    <!-- Career Timeline -->
    <section class="timeline-section">
      <h2 class="heading-underline">Career Timeline</h2>
      <div class="timeline" id="careerTimeline">
        <!-- Timeline items populated by JS for animation -->
      </div>
    </section>

    <!-- Skills Section -->
    <section class="skills-section">
      <h2 class="heading-underline">Skills</h2>
      <div class="skills-list" id="skillsList">
        <!-- Skill bars populated by JS -->
      </div>
    </section>

    <!-- Achievements Section -->
    <section class="achievements-section">
      <h2 class="heading-underline">Personal Achievements</h2>
      <div class="achievements-grid" id="achievementsGrid">
        <!-- Achievements populated by JS -->
      </div>
    </section>

    <!-- AI Resume Score Section -->
    <section class="resume-score-section">
      <h2 class="heading-underline">AI Resume Score</h2>
      <label class="resume-upload-label" for="resumeUpload">Upload your resume (PDF or DOCX):</label>
      <input type="file" id="resumeUpload" accept=".pdf,.doc,.docx" class="resume-upload-input">
      <button class="btn" id="analyzeResumeBtn">Analyze Resume</button>
      <div class="resume-analysis" id="resumeAnalysis">
        Upload your resume to receive an AI-powered analysis of your strengths, weaknesses, and missing keywords.
      </div>
    </section>

    <!-- Career Match Section -->
    <section class="career-match-section">
      <h2 class="heading-underline">Career Match</h2>
      <form class="career-match-form" id="careerMatchForm">
        <select id="careerRole" class="career-match-select" required>
          <option value="">Select a role...</option>
          <option value="data_scientist">Data Scientist</option>
          <option value="ai_engineer">AI Engineer</option>
          <option value="frontend_dev">Frontend Developer</option>
          <option value="backend_dev">Backend Developer</option>
          <option value="product_manager">Product Manager</option>
          <option value="ux_designer">UX Designer</option>
        </select>
        <button class="btn" type="submit">Submit</button>
      </form>
      <div class="career-match-result" id="careerMatchResult">
        Get tailored career insights and see which paths suit your experience.
      </div>
    </section>

    <!-- Download Resume Section -->
    <section class="download-section">
      <button class="btn download-btn" id="downloadResumeBtn">Download Resume Template</button>
    </section>

    <!-- AI Career Advice Section -->
    <section class="career-advice-section">
      <h2 class="heading-underline">AI Career Advice</h2>
      <form class="career-advice-form" id="careerAdviceForm">
        <input class="career-advice-input" id="careerGoalInput" type="text" placeholder="Type your career goal (e.g. 'Become a CTO')" required>
        <button class="btn" type="submit">Get Advice</button>
      </form>
      <div class="career-advice-result" id="careerAdviceResult">
        Receive personalized AI-powered career tips based on your goals.
      </div>
    </section>
  </main>
  <script>
    // ------------- DARK/LIGHT MODE -------------
    const darkModeBtn = document.getElementById('darkModeBtn');
    const modeLabel = document.getElementById('modeLabel');
    function setTheme(theme) {
      document.documentElement.setAttribute('data-theme', theme);
      if (theme === 'dark') {
        modeLabel.textContent = 'Light Mode';
      } else {
        modeLabel.textContent = 'Dark Mode';
      }
      localStorage.setItem('theme', theme);
    }
    darkModeBtn.onclick = () => {
      const current = document.documentElement.getAttribute('data-theme') || 'light';
      setTheme(current === 'dark' ? 'light' : 'dark');
    };
    // On page load, apply saved theme
    (function() {
      const saved = localStorage.getItem('theme');
      if (saved === 'dark') setTheme('dark');
      else setTheme('light');
    })();

    // ------------- HERO SUMMARIZE -------------
    const summarizeBtn = document.getElementById('summarizeBtn');
    const bioInput = document.getElementById('bioInput');
    const heroSummary = document.getElementById('heroSummary');
    summarizeBtn.onclick = async () => {
      const bio = bioInput.value.trim();
      heroSummary.textContent = "Summarizing...";
      // Try backend, fallback to placeholder
      try {
        if (window.fetch && window.location.hostname !== 'localhost') {
          // Assume backend at /summarize_me (optional)
          const resp = await fetch('/summarize_me', {
            method: 'POST',
            headers: {'Content-Type': 'application/json'},
            body: JSON.stringify({bio})
          });
          if (resp.ok) {
            const {summary} = await resp.json();
            heroSummary.textContent = summary || "No summary available.";
            return;
          }
        }
      } catch {}
      // Placeholder fallback
      heroSummary.textContent = bio
        ? "Result: " + bio.slice(0, 110) + (bio.length > 110 ? "..." : "") + " [AI summary placeholder]"
        : "A professional with a passion for technology, creativity, and continuous learning. Explore my AI-enhanced portfolio and resume!";
    };

    // ------------- CAREER TIMELINE -------------
    const timelineData = [
      {
        title: "Graduated B.Sc. in Computer Science",
        date: "2015",
        desc: "Completed a Bachelor’s degree with honors, focusing on AI and software engineering."
      },
      {
        title: "Software Engineer at TechNova",
        date: "2016-2019",
        desc: "Developed scalable web solutions and participated in machine learning pilot projects."
      },
      {
        title: "AI Bootcamp & Certification",
        date: "2019",
        desc: "Completed an intensive AI/ML bootcamp and earned industry certifications."
      },
      {
        title: "Senior AI Engineer at NextGenAI",
        date: "2019-2022",
        desc: "Led a team delivering NLP and computer vision projects for global clients."
      },
      {
        title: "Promoted: Lead Solutions Architect",
        date: "2022-Present",
        desc: "Designs intelligent products, mentors teams, and drives innovation in AI-powered platforms."
      }
    ];
    const careerTimeline = document.getElementById('careerTimeline');
    timelineData.forEach((item, idx) => {
      const div = document.createElement('div');
      div.className = 'timeline-item';
      div.innerHTML = `
        <div class="timeline-dot"></div>
        <div class="timeline-content">
          <div class="timeline-title">${item.title}</div>
          <div class="timeline-date">${item.date}</div>
          <div class="timeline-desc">${item.desc}</div>
        </div>
      `;
      careerTimeline.appendChild(div);
    });
    // Animate timeline items on scroll
    function animateTimeline() {
      const items = document.querySelectorAll('.timeline-item');
      const trigger = window.innerHeight * 0.8;
      items.forEach(item => {
        const rect = item.getBoundingClientRect();
        if (rect.top < trigger) item.classList.add('visible');
      });
    }
    window.addEventListener('scroll', animateTimeline);
    window.addEventListener('resize', animateTimeline);
    setTimeout(animateTimeline, 100);

    // ------------- SKILLS BARS -------------
    const skillsArr = [
      { name: "Python", percent: 95 },
      { name: "Machine Learning", percent: 92 },
      { name: "JavaScript", percent: 87 },
      { name: "React.js", percent: 84 },
      { name: "Natural Language Processing", percent: 90 },
      { name: "Cloud (AWS/GCP)", percent: 78 }
    ];
    const skillsList = document.getElementById('skillsList');
    skillsArr.forEach(skill => {
      const container = document.createElement('div');
      container.className = 'skill-bar-container';
      container.innerHTML = `
        <div class="skill-bar-labels">
          <span>${skill.name}</span>
          <span>${skill.percent}%</span>
        </div>
        <div class="skill-bar-bg">
          <div class="skill-bar"></div>
        </div>
      `;
      skillsList.appendChild(container);
    });
    // Animate skill bars
    function animateSkills() {
      const bars = document.querySelectorAll('.skill-bar');
      bars.forEach((bar, idx) => {
        bar.style.width = '0%';
        setTimeout(() => {
          bar.style.width = skillsArr[idx].percent + '%';
        }, 200 + idx * 190);
      });
    }
    setTimeout(animateSkills, 500);

    // ------------- ACHIEVEMENTS -------------
    const achievements = [
      {
        title: "AI Innovation Award",
        desc: "Recognized for developing a cutting-edge NLP tool adopted by 5+ enterprises.",
        details: "Awarded at NextGenAI (2021) for leading the creation and successful deployment of a Natural Language Processing platform, impacting customer communication strategies."
      },
      {
        title: "Hackathon Champion",
        desc: "Led a team to win 1st place at the National AI Hackathon 2020.",
        details: "Our solution applied deep learning to real-time healthcare analytics, earning industry recognition and a grant for further development."
      },
      {
        title: "Certified AWS Solution Architect",
        desc: "Earned AWS certification for architecting and deploying scalable, secure cloud solutions.",
        details: "Certificate awarded in 2022 after passing the AWS Solutions Architect Professional exam and completing several cloud migration projects."
      },
      {
        title: "Published Research",
        desc: "Co-authored a research paper on adversarial learning in computer vision.",
        details: "Presented at AI World Conference 2023; the paper advanced methods for robust AI image classification."
      }
    ];
    const achievementsGrid = document.getElementById('achievementsGrid');
    achievements.forEach((ach, idx) => {
      const card = document.createElement('div');
      card.className = 'achievement-card';
      card.innerHTML = `
        <div class="achievement-title">${ach.title}</div>
        <div class="achievement-desc">${ach.desc}</div>
        <button class="btn learn-more-btn" data-idx="${idx}">Learn More</button>
      `;
      achievementsGrid.appendChild(card);
    });
    achievementsGrid.addEventListener('click', e => {
      if (e.target && e.target.classList.contains('learn-more-btn')) {
        const idx = e.target.getAttribute('data-idx');
        alert(achievements[idx].details + "\n\n[Placeholder for details modal]");
      }
    });

    // ------------- AI RESUME SCORE -------------
    const resumeUpload = document.getElementById('resumeUpload');
    const analyzeResumeBtn = document.getElementById('analyzeResumeBtn');
    const resumeAnalysis = document.getElementById('resumeAnalysis');
    analyzeResumeBtn.onclick = async () => {
      if (!resumeUpload.files[0]) {
        resumeAnalysis.textContent = "Please select a PDF or DOCX resume to analyze.";
        return;
      }
      resumeAnalysis.textContent = "Analyzing resume...";
      const file = resumeUpload.files[0];
      // Backend call (POST /analyze_resume), fallback to placeholder
      try {
        if (window.fetch && window.location.hostname !== 'localhost') {
          const formData = new FormData();
          formData.append('resume', file);
          const resp = await fetch('/analyze_resume', {
            method: 'POST',
            body: formData
          });
          if (resp.ok) {
            const d = await resp.json();
            resumeAnalysis.innerHTML = `
              <b>Strengths:</b> ${d.strengths || '-'}<br>
              <b>Weaknesses:</b> ${d.weaknesses || '-'}<br>
              <b>Missing Keywords:</b> ${d.missing_keywords || '-'}
            `;
            return;
          }
        }
      } catch {}
      // Placeholder fallback
      resumeAnalysis.innerHTML = `
        <b>Strengths:</b> <span style="color:#12d8fa">Technical breadth, leadership, project impact</span><br>
        <b>Weaknesses:</b> <span style="color:#ff6464">Lacks specific metrics, insufficient soft skills</span><br>
        <b>Missing Keywords:</b> <span style="color:#ffb347">"Agile", "CI/CD", "Kubernetes"</span>
        <br><i>[AI analysis placeholder]</i>
      `;
    };

    // ------------- CAREER MATCH -------------
    const careerMatchForm = document.getElementById('careerMatchForm');
    const careerMatchResult = document.getElementById('careerMatchResult');
    careerMatchForm.onsubmit = async (e) => {
      e.preventDefault();
      const role = document.getElementById('careerRole').value;
      if (!role) {
        careerMatchResult.textContent = "Please choose a career role.";
        return;
      }
      careerMatchResult.textContent = "Analyzing best career match...";
      // Backend call (POST /career_match), fallback to placeholder
      try {
        if (window.fetch && window.location.hostname !== 'localhost') {
          const resp = await fetch('/career_match', {
            method: 'POST',
            headers: {'Content-Type': 'application/json'},
            body: JSON.stringify({role})
          });
          if (resp.ok) {
            const d = await resp.json();
            careerMatchResult.textContent = d.match_result || "No recommendations.";
            return;
          }
        }
      } catch {}
      // Placeholder results
      const roleMap = {
        data_scientist: "You excel at data wrangling, hypothesis-driven analysis, and ML workflows. Consider roles in analytics-driven organizations.",
        ai_engineer: "Strong fit for R&D, model deployment, and end-to-end AI pipelines. Look for positions building scalable AI products.",
        frontend_dev: "You have a keen eye for UI/UX and interactive design. Ideal for modern web and app teams.",
        backend_dev: "You thrive at scalability, APIs, and architecture. Consider positions focused on microservices and cloud.",
        product_manager: "Your skills bridge tech and business. Product management roles in AI-focused orgs are a great match.",
        ux_designer: "Your creativity and empathy suit you for UX, user research, and product design teams."
      };
      careerMatchResult.textContent = roleMap[role] + " [AI match placeholder]";
    };

    // ------------- DOWNLOAD RESUME -------------
    document.getElementById('downloadResumeBtn').onclick = () => {
      // Create and download a basic resume PDF (placeholder)
      const pdfBlob = new Blob([
        "%PDF-1.3\n%Fake PDF: see real download at backend.\n"
      ], {type: 'application/pdf'});
      const url = URL.createObjectURL(pdfBlob);
      const link = document.createElement('a');
      link.href = url;
      link.download = 'Resume_Template.pdf';
      document.body.appendChild(link);
      link.click();
      setTimeout(() => {
        document.body.removeChild(link);
        URL.revokeObjectURL(url);
      }, 150);
    };

    // ------------- AI CAREER ADVICE -------------
    const careerAdviceForm = document.getElementById('careerAdviceForm');
    const careerGoalInput = document.getElementById('careerGoalInput');
    const careerAdviceResult = document.getElementById('careerAdviceResult');
    careerAdviceForm.onsubmit = async (e) => {
      e.preventDefault();
      const goal = careerGoalInput.value.trim();
      if (!goal) {
        careerAdviceResult.textContent = "Please specify your career goal.";
        return;
      }
      careerAdviceResult.textContent = "Generating AI advice...";
      // Backend call (POST /ai_career_advice), fallback to placeholder
      try {
        if (window.fetch && window.location.hostname !== 'localhost') {
          const resp = await fetch('/ai_career_advice', {
            method: 'POST',
            headers: {'Content-Type': 'application/json'},
            body: JSON.stringify({goal})
          });
          if (resp.ok) {
            const d = await resp.json();
            careerAdviceResult.textContent = d.tips || "No advice found.";
            return;
          }
        }
      } catch {}
      // Placeholder tips
      careerAdviceResult.innerHTML = `
        <b>Tips:</b><br>
        • Break your goal "${goal}" into actionable steps.<br>
        • Network with professionals in your target role.<br>
        • Keep learning—consider certifications and hands-on projects.<br>
        • Regularly update your resume and portfolio.<br>
        <i>[AI advice placeholder]</i>
      `;
    };

    // Accessibility: focus outlines
    document.querySelectorAll('button, input, select, textarea').forEach(el => {
      el.addEventListener('keydown', e => {
        if (e.key === 'Tab') el.style.outline = '2px solid #1fa2ff';
      });
      el.addEventListener('blur', e => {
        el.style.outline = '';
      });
    });
  </script>
</body>
</html>
