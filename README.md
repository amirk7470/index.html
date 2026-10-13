<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Amir Khan | Operations & AI Automation Portfolio</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&family=JetBrains+Mono:wght@400;500&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #090d16;
      --card-bg: #111827;
      --card-border: rgba(255, 255, 255, 0.08);
      --accent: #3b82f6;
      --accent-glow: rgba(59, 130, 246, 0.25);
      --emerald: #10b981;
      --emerald-glow: rgba(16, 185, 129, 0.2);
      --text-main: #f3f4f6;
      --text-muted: #9ca3af;
      --badge-bg: rgba(59, 130, 246, 0.12);
      --badge-text: #93c5fd;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      scroll-behavior: smooth;
    }

    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      background-color: var(--bg);
      color: var(--text-main);
      line-height: 1.6;
      overflow-x: hidden;
      selection-background-color: var(--accent);
      selection-color: #fff;
    }

    /* Ambient Background Glow */
    .bg-gradient {
      position: fixed;
      top: 0;
      left: 50%;
      transform: translateX(-50%);
      width: 100vw;
      height: 100vh;
      background: radial-gradient(circle at 15% 15%, rgba(59, 130, 246, 0.08) 0%, transparent 40%),
                  radial-gradient(circle at 85% 65%, rgba(16, 185, 129, 0.05) 0%, transparent 45%);
      pointer-events: none;
      z-index: -1;
    }

    /* Container */
    .container {
      max-width: 1100px;
      margin: 0 auto;
      padding: 0 24px;
    }

    /* Navigation */
    nav {
      position: sticky;
      top: 0;
      backdrop-filter: blur(12px);
      background: rgba(9, 13, 22, 0.85);
      border-bottom: 1px solid var(--card-border);
      z-index: 100;
    }

    .nav-inner {
      display: flex;
      justify-content: space-between;
      align-items: center;
      height: 70px;
    }

    .brand {
      font-weight: 800;
      font-size: 1.15rem;
      letter-spacing: -0.5px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .brand span {
      color: var(--accent);
    }

    .nav-links {
      display: flex;
      gap: 24px;
      align-items: center;
    }

    .nav-links a {
      color: var(--text-muted);
      text-decoration: none;
      font-size: 0.9rem;
      font-weight: 500;
      transition: color 0.2s ease;
    }

    .nav-links a:hover {
      color: var(--text-main);
    }

    .cta-btn-sm {
      background: var(--accent);
      color: #fff;
      padding: 8px 16px;
      border-radius: 8px;
      text-decoration: none;
      font-size: 0.85rem;
      font-weight: 600;
      box-shadow: 0 0 15px var(--accent-glow);
      transition: all 0.2s ease;
    }

    .cta-btn-sm:hover {
      background: #2563eb;
      transform: translateY(-1px);
    }

    /* Hero Section */
    .hero {
      padding: 80px 0 60px;
    }

    .hero-grid {
      display: grid;
      grid-template-columns: 1.3fr 0.9fr;
      gap: 50px;
      align-items: center;
    }

    .status-badge {
      display: inline-flex;
      align-items: center;
      gap: 8px;
      padding: 6px 14px;
      border-radius: 9999px;
      background: rgba(16, 185, 129, 0.1);
      border: 1px solid rgba(16, 185, 129, 0.3);
      color: var(--emerald);
      font-size: 0.8rem;
      font-weight: 600;
      margin-bottom: 20px;
    }

    .status-dot {
      width: 8px;
      height: 8px;
      border-radius: 50%;
      background: var(--emerald);
      box-shadow: 0 0 10px var(--emerald);
      animation: pulse 2s infinite;
    }

    @keyframes pulse {
      0%, 100% { opacity: 1; transform: scale(1); }
      50% { opacity: 0.4; transform: scale(0.9); }
    }

    .hero-title {
      font-size: 3.2rem;
      font-weight: 800;
      letter-spacing: -1.5px;
      line-height: 1.15;
      margin-bottom: 16px;
    }

    .hero-title .gradient-text {
      background: linear-gradient(120deg, #60a5fa, #38bdf8);
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
    }

    .hero-subtitle {
      font-size: 1.05rem;
      color: var(--text-muted);
      margin-bottom: 28px;
      line-height: 1.65;
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 14px;
      align-items: center;
    }

    .btn-primary {
      background: var(--accent);
      color: #fff;
      padding: 12px 24px;
      border-radius: 10px;
      font-weight: 600;
      font-size: 0.95rem;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      box-shadow: 0 4px 20px var(--accent-glow);
      transition: all 0.2s ease;
    }

    .btn-primary:hover {
      background: #2563eb;
      transform: translateY(-2px);
    }

    .btn-secondary {
      background: rgba(255, 255, 255, 0.05);
      border: 1px solid var(--card-border);
      color: var(--text-main);
      padding: 12px 22px;
      border-radius: 10px;
      font-weight: 600;
      font-size: 0.95rem;
      text-decoration: none;
      display: inline-flex;
      align-items: center;
      gap: 8px;
      transition: all 0.2s ease;
    }

    .btn-secondary:hover {
      background: rgba(255, 255, 255, 0.08);
      border-color: rgba(255, 255, 255, 0.2);
    }

    /* Photo Card */
    .profile-card-wrapper {
      position: relative;
      display: flex;
      justify-content: center;
    }

    .profile-card {
      position: relative;
      width: 100%;
      max-width: 380px;
      aspect-ratio: 4/5;
      border-radius: 24px;
      padding: 10px;
      background: linear-gradient(145deg, rgba(255,255,255,0.08), rgba(255,255,255,0.02));
      border: 1px solid var(--card-border);
      box-shadow: 0 20px 40px rgba(0,0,0,0.4);
    }

    .profile-img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: top;
      border-radius: 18px;
      display: block;
    }

    .profile-floating-badge {
      position: absolute;
      bottom: -15px;
      left: 50%;
      transform: translateX(-50%);
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      padding: 10px 18px;
      border-radius: 14px;
      white-space: nowrap;
      box-shadow: 0 10px 25px rgba(0,0,0,0.5);
      display: flex;
      align-items: center;
      gap: 10px;
      font-size: 0.85rem;
      font-weight: 600;
    }

    /* Metric Counters */
    .metrics-section {
      padding: 40px 0 60px;
    }

    .metrics-grid {
      display: grid;
      grid-template-columns: repeat(4, 1fr);
      gap: 16px;
    }

    .metric-card {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      padding: 24px 20px;
      border-radius: 16px;
      text-align: center;
      transition: transform 0.2s ease;
    }

    .metric-card:hover {
      transform: translateY(-3px);
      border-color: rgba(59, 130, 246, 0.3);
    }

    .metric-num {
      font-size: 2.2rem;
      font-weight: 800;
      color: #60a5fa;
      line-height: 1;
      margin-bottom: 8px;
      font-family: 'JetBrains Mono', monospace;
    }

    .metric-label {
      color: var(--text-muted);
      font-size: 0.85rem;
      font-weight: 500;
    }

    /* Section Headers */
    .section-header {
      margin-bottom: 36px;
    }

    .section-tag {
      font-size: 0.75rem;
      font-weight: 700;
      text-transform: uppercase;
      letter-spacing: 1.5px;
      color: var(--accent);
      margin-bottom: 8px;
      display: block;
    }

    .section-title {
      font-size: 1.9rem;
      font-weight: 700;
      letter-spacing: -0.5px;
    }

    /* Experience Timeline */
    .experience-section {
      padding: 50px 0;
    }

    .timeline {
      display: flex;
      flex-direction: column;
      gap: 20px;
    }

    .timeline-item {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: 18px;
      padding: 26px;
      transition: all 0.2s ease;
    }

    .timeline-item:hover {
      border-color: rgba(59, 130, 246, 0.35);
    }

    .item-header {
      display: flex;
      justify-content: space-between;
      align-items: flex-start;
      margin-bottom: 14px;
      flex-wrap: wrap;
      gap: 10px;
    }

    .role-title {
      font-size: 1.25rem;
      font-weight: 700;
      color: var(--text-main);
    }

    .role-company {
      font-size: 0.95rem;
      color: #60a5fa;
      font-weight: 500;
      margin-top: 2px;
    }

    .role-meta {
      font-family: 'JetBrains Mono', monospace;
      font-size: 0.85rem;
      color: var(--text-muted);
      background: rgba(255, 255, 255, 0.04);
      padding: 6px 12px;
      border-radius: 8px;
      border: 1px solid var(--card-border);
    }

    .item-bullet-list {
      list-style-type: none;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .item-bullet-list li {
      position: relative;
      padding-left: 20px;
      color: #cbd5e1;
      font-size: 0.95rem;
      line-height: 1.55;
    }

    .item-bullet-list li::before {
      content: "▹";
      position: absolute;
      left: 0;
      color: var(--accent);
      font-weight: bold;
    }

    /* Skills Grid */
    .skills-section {
      padding: 50px 0;
    }

    .skills-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 20px;
    }

    .skill-category-card {
      background: var(--card-bg);
      border: 1px solid var(--card-border);
      border-radius: 18px;
      padding: 24px;
    }

    .category-title {
      font-size: 1rem;
      font-weight: 700;
      margin-bottom: 16px;
      display: flex;
      align-items: center;
      gap: 10px;
      color: #e2e8f0;
    }

    .tags-container {
      display: flex;
      flex-wrap: wrap;
      gap: 8px;
    }

    .skill-tag {
      background: rgba(255, 255, 255, 0.04);
      border: 1px solid var(--card-border);
      color: #cbd5e1;
      padding: 6px 12px;
      border-radius: 8px;
      font-size: 0.85rem;
      font-weight: 500;
      transition: all 0.2s ease;
    }

    .skill-tag:hover {
      background: var(--badge-bg);
      color: var(--badge-text);
      border-color: rgba(59, 130, 246, 0.4);
    }

    .skill-tag.highlight {
      background: rgba(59, 130, 246, 0.15);
      border-color: rgba(59, 130, 246, 0.4);
      color: #93c5fd;
      font-weight: 600;
    }

    /* Recruiter Quick Actions */
    .recruiter-cta {
      padding: 70px 0 90px;
    }

    .cta-box {
      background: linear-gradient(135deg, rgba(30, 58, 138, 0.3), rgba(17, 24, 39, 0.8));
      border: 1px solid rgba(59, 130, 246, 0.3);
      border-radius: 24px;
      padding: 48px;
      text-align: center;
      position: relative;
      overflow: hidden;
    }

    .cta-box h2 {
      font-size: 2.2rem;
      font-weight: 800;
      letter-spacing: -0.5px;
      margin-bottom: 12px;
    }

    .cta-box p {
      color: var(--text-muted);
      max-width: 600px;
      margin: 0 auto 30px;
      font-size: 1rem;
    }

    .contact-details {
      display: flex;
      justify-content: center;
      gap: 20px;
      flex-wrap: wrap;
      margin-bottom: 30px;
    }

    .contact-item {
      display: flex;
      align-items: center;
      gap: 8px;
      background: rgba(0, 0, 0, 0.3);
      padding: 10px 18px;
      border-radius: 12px;
      border: 1px solid var(--card-border);
      font-size: 0.9rem;
      color: #e2e8f0;
      text-decoration: none;
      transition: all 0.2s ease;
    }

    .contact-item:hover {
      border-color: var(--accent);
      color: #fff;
    }

    /* Toast Notification */
    .toast {
      position: fixed;
      bottom: 24px;
      right: 24px;
      background: #1e293b;
      border: 1px solid var(--accent);
      color: #fff;
      padding: 12px 20px;
      border-radius: 10px;
      font-size: 0.9rem;
      opacity: 0;
      pointer-events: none;
      transition: opacity 0.3s ease;
      z-index: 1000;
      box-shadow: 0 10px 20px rgba(0,0,0,0.3);
    }

    .toast.show {
      opacity: 1;
    }

    /* Footer */
    footer {
      border-top: 1px solid var(--card-border);
      padding: 30px 0;
      text-align: center;
      color: var(--text-muted);
      font-size: 0.85rem;
    }

    /* Responsive */
    @media (max-width: 860px) {
      .hero-grid {
        grid-template-columns: 1fr;
        text-align: center;
      }
      .hero-title {
        font-size: 2.4rem;
      }
      .hero-actions {
        justify-content: center;
      }
      .profile-card-wrapper {
        order: -1;
      }
      .profile-card {
        max-width: 280px;
      }
      .metrics-grid {
        grid-template-columns: repeat(2, 1fr);
      }
      .skills-grid {
        grid-template-columns: 1fr;
      }
      .nav-links {
        display: none;
      }
    }
  </style>
</head>
<body>

  <div class="bg-gradient"></div>

  <!-- Navigation -->
  <nav>
    <div class="container nav-inner">
      <div class="brand">
        AMIR<span>.KHAN</span>
      </div>
      <div class="nav-links">
        <a href="#about">About</a>
        <a href="#experience">Experience</a>
        <a href="#skills">Skills & AI Stack</a>
        <a href="#contact">Contact</a>
      </div>
      <a href="mailto:amirkhan9453480248@gmail.com" class="cta-btn-sm">Hire Amir</a>
    </div>
  </nav>

  <!-- Hero Section -->
  <section class="hero" id="about">
    <div class="container hero-grid">
      <div class="hero-content">
        <div class="status-badge">
          <span class="status-dot"></span> Open to Senior Operations & Automation Roles
        </div>
        <h1 class="hero-title">
          Bridging Operations with <span class="gradient-text">AI Automation</span>
        </h1>
        <p
        
