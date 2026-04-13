<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Before You Start</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700&family=Manrope:wght@400;500;700;800&display=swap" rel="stylesheet">
  <style>
    :root {
      --bg: #12081d;
      --bg-soft: #1c0d2d;
      --panel: rgba(248, 239, 221, 0.96);
      --panel-soft: rgba(255, 248, 234, 0.84);
      --text: #2e1a40;
      --muted: #66507b;
      --purple: #71419b;
      --purple-deep: #29123f;
      --gold: #d7b15c;
      --gold-deep: #9b7427;
      --line: rgba(113, 65, 155, 0.13);
      --shadow: 0 24px 60px rgba(8, 2, 15, 0.35);
      --radius: 28px;
    }

    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      margin: 0;
      font-family: "Manrope", sans-serif;
      background:
        radial-gradient(circle at top left, rgba(215, 177, 92, 0.12), transparent 22%),
        radial-gradient(circle at 85% 15%, rgba(113, 65, 155, 0.24), transparent 24%),
        linear-gradient(160deg, #0f0618 0%, #1c0c2c 38%, #30124b 72%, #12081d 100%);
      color: #f9f0dc;
      line-height: 1.6;
      min-height: 100vh;
    }

    .page {
      width: min(1180px, calc(100% - 32px));
      margin: 0 auto;
      padding: 28px 0 56px;
    }

    .hero {
      position: relative;
      overflow: hidden;
      padding: 56px 42px;
      border-radius: 0 0 34px 34px;
      background: linear-gradient(140deg, #160920 0%, #341552 34%, #71419b 70%, #d7b15c 100%);
      box-shadow: var(--shadow);
      isolation: isolate;
    }

    .hero::before,
    .hero::after {
      content: "";
      position: absolute;
      border-radius: 50%;
      background: rgba(255,255,255,0.08);
      filter: blur(2px);
      z-index: -1;
    }

    .hero::before {
      width: 260px;
      height: 260px;
      top: -100px;
      right: -60px;
    }

    .hero::after {
      width: 180px;
      height: 180px;
      bottom: -60px;
      left: 10px;
    }

    .eyebrow {
      display: inline-flex;
      padding: 8px 18px;
      border-radius: 999px;
      background: rgba(255,255,255,0.14);
      border: 1px solid rgba(255,255,255,0.22);
      font-size: 11px;
      font-weight: 800;
      letter-spacing: 0.18em;
      text-transform: uppercase;
    }

    h1, h2, h3 {
      margin: 0;
      font-family: "Cinzel", serif;
      font-weight: 700;
      letter-spacing: 0.02em;
    }

    h1 {
      margin-top: 18px;
      font-size: clamp(2.6rem, 7vw, 5rem);
      line-height: 0.96;
      max-width: 11ch;
    }

    .hero p {
      max-width: 60ch;
      margin: 18px 0 24px;
      font-size: 1.04rem;
      color: rgba(255, 248, 235, 0.92);
    }

    .hero-actions {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
      margin-top: 22px;
    }

    .button,
    .ghost {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      text-decoration: none;
      padding: 12px 18px;
      border-radius: 999px;
      font-weight: 800;
      transition: transform 180ms ease, background 180ms ease;
    }

    .button {
      background: linear-gradient(135deg, #28113d, #71419b);
      color: #fff4de;
      box-shadow: 0 14px 30px rgba(30, 8, 46, 0.28);
    }

    .ghost {
      background: rgba(255,255,255,0.14);
      color: #fff4de;
      border: 1px solid rgba(255,255,255,0.2);
    }

    .button:hover,
    .ghost:hover { transform: translateY(-2px); }

    .hero-grid {
      display: grid;
      grid-template-columns: repeat(4, minmax(0, 1fr));
      gap: 14px;
      margin-top: 26px;
    }

    .hero-stat {
      padding: 16px;
      border-radius: 18px;
      background: rgba(255,255,255,0.12);
      border: 1px solid rgba(255,255,255,0.16);
      backdrop-filter: blur(8px);
    }

    .hero-stat strong {
      display: block;
      font-size: 1.2rem;
      margin-bottom: 4px;
      color: #fff5dd;
    }

    .lead-panel,
    .section,
    .cta {
      background: var(--panel);
      color: var(--text);
      box-shadow: var(--shadow);
      border-radius: var(--radius);
      border: 1px solid rgba(255,255,255,0.28);
    }

    .lead-panel {
      margin-top: 22px;
      padding: 24px 26px;
      border-left: 5px solid var(--gold);
      font-size: 1rem;
    }

    .lead-panel strong { color: var(--gold-deep); }

    .section {
      margin-top: 18px;
      padding: 28px;
    }

    .section-label {
      display: inline-flex;
      align-items: center;
      padding: 7px 14px;
      border-radius: 999px;
      background: rgba(215, 177, 92, 0.16);
      color: var(--purple);
      font-size: 11px;
      font-weight: 800;
      letter-spacing: 0.12em;
      text-transform: uppercase;
      margin-bottom: 14px;
    }

    .section h2 {
      font-size: clamp(1.8rem, 4vw, 2.7rem);
      line-height: 1.02;
      margin-bottom: 12px;
    }

    .section p {
      margin: 0 0 14px;
      color: var(--muted);
    }

    .grid-2,
    .grid-3,
    .grid-4 {
      display: grid;
      gap: 16px;
      margin-top: 18px;
    }

    .grid-2 { grid-template-columns: repeat(2, minmax(0, 1fr)); }
    .grid-3 { grid-template-columns: repeat(3, minmax(0, 1fr)); }
    .grid-4 { grid-template-columns: repeat(4, minmax(0, 1fr)); }

    .card,
    .check-card,
    .path-card,
    .support-card,
    .image-card {
      background: var(--panel-soft);
      border: 1px solid var(--line);
      border-radius: 22px;
      padding: 18px;
    }

    .card h3,
    .check-card h3,
    .path-card h3,
    .support-card h3,
    .image-card h3 {
      font-size: 1.08rem;
      color: var(--purple-deep);
      margin-bottom: 8px;
    }

    .check-card,
    .path-card {
      border-top: 4px solid var(--purple);
    }

    ul {
      margin: 0;
      padding-left: 20px;
      color: var(--muted);
    }

    li { margin-bottom: 8px; }

    .list-clean {
      display: grid;
      gap: 10px;
      margin-top: 14px;
    }

    .list-clean div {
      display: flex;
      align-items: start;
      gap: 10px;
      font-weight: 700;
      color: var(--text);
    }

    .tick {
      width: 24px;
      height: 24px;
      border-radius: 50%;
      display: inline-flex;
      align-items: center;
      justify-content: center;
      flex: none;
      background: linear-gradient(135deg, var(--gold), #f1d590);
      color: var(--purple-deep);
      font-size: 0.9rem;
      font-weight: 900;
      box-shadow: inset 0 1px 0 rgba(255,255,255,0.3);
    }

    .quote {
      padding: 18px;
      margin-top: 18px;
      border-radius: 22px;
      background: linear-gradient(135deg, rgba(215, 177, 92, 0.18), rgba(113, 65, 155, 0.08));
      border: 1px solid rgba(215, 177, 92, 0.22);
      color: var(--purple-deep);
      font-weight: 700;
    }

    .path-gallery {
      display: grid;
      grid-template-columns: repeat(3, minmax(0, 1fr));
      gap: 18px;
      margin-top: 18px;
    }

    .image-card {
      padding: 14px;
      overflow: hidden;
    }

    .image-card img {
      width: 100%;
      display: block;
      border-radius: 18px;
      box-shadow: 0 14px 30px rgba(15, 5, 24, 0.2);
      margin-bottom: 12px;
    }

    .image-card p {
      margin: 0;
      color: var(--muted);
      font-size: 0.95rem;
    }

    .cta {
      margin-top: 20px;
      padding: 28px;
      text-align: center;
      background: linear-gradient(135deg, rgba(41, 18, 63, 0.98), rgba(113, 65, 155, 0.92));
      color: #fff4de;
    }

    .cta h2 {
      font-size: clamp(1.9rem, 4vw, 3rem);
      margin-bottom: 12px;
    }

    .cta p {
      max-width: 56ch;
      margin: 0 auto 18px;
      color: rgba(255, 243, 221, 0.88);
    }

    @media (max-width: 980px) {
      .hero-grid,
      .grid-4,
      .path-gallery {
        grid-template-columns: repeat(2, minmax(0, 1fr));
      }

      .grid-2,
      .grid-3 {
        grid-template-columns: 1fr;
      }
    }

    @media (max-width: 640px) {
      .page {
        width: min(100% - 16px, 1180px);
      }

      .hero,
      .section,
      .lead-panel,
      .cta {
        padding: 22px;
      }

      .hero-grid,
      .grid-4,
      .path-gallery {
        grid-template-columns: 1fr;
      }

      .hero-actions {
        flex-direction: column;
        align-items: stretch;
      }
    }
  </style>
</head>
<body>
  <div class="page">
    <section class="hero">
      <span class="eyebrow">Academy Welcome</span>
      <h1>Before You Start</h1>
      <p>
        Take one minute to understand how the academy works. Everything is organized to be simple, step-by-step, and easier to follow than trying to figure it out on your own.
      </p>
      <div class="hero-actions">
        <a class="button" href="#start">Start Here First</a>
        <a class="ghost" href="#paths">See the Paths</a>
      </div>
      <div class="hero-grid">
        <div class="hero-stat">
          <strong>Start Simple</strong>
          <span>Begin with the first two core sections instead of jumping around</span>
        </div>
        <div class="hero-stat">
          <strong>Use the Vault</strong>
          <span>Templates, prompts, scripts, and downloads are already organized for you</span>
        </div>
        <div class="hero-stat">
          <strong>Get Support</strong>
          <span>Coaching and community are built into the system</span>
        </div>
        <div class="hero-stat">
          <strong>Choose One Path</strong>
          <span>Build one income stream first, then expand later</span>
        </div>
      </div>
    </section>

    <div class="lead-panel">
      This academy is designed to reduce overwhelm. <strong>You do not need to do everything at once.</strong> You just need to know where to begin, where to find support, and which path you are focusing on first.
    </div>

    <section class="section" id="start">
      <div class="section-label">Getting Started</div>
      <h2>Where You Should Start</h2>
      <p>Always start with the foundation. These first two sections give you the right order, the right momentum, and the clearest next moves.</p>
      <div class="grid-2">
        <div class="check-card">
          <h3>Start Here</h3>
          <p>This is your orientation section. It gives you the big picture and helps you understand how the academy is structured.</p>
          <div class="list-clean">
            <div><span class="tick">□</span><span>Use this to understand the layout of the program</span></div>
            <div><span class="tick">□</span><span>See how the academy is organized step-by-step</span></div>
          </div>
        </div>
        <div class="check-card">
          <h3>Creator Plug Launch Challenge</h3>
          <p>This section shows you exactly what to do first so you stop planning and start taking action.</p>
          <div class="list-clean">
            <div><span class="tick">□</span><span>Follow the challenge in order</span></div>
            <div><span class="tick">□</span><span>Use it to get your first momentum quickly</span></div>
          </div>
        </div>
      </div>
      <div class="quote">If you are unsure what to do first, the answer is simple: start here, then complete the Creator Plug Launch Challenge.</div>
    </section>

    <section class="section">
      <div class="section-label">Resources</div>
      <h2>Where to Find Resources</h2>
      <p>Templates and downloads are inside the <strong>Template Vault</strong>. This is where you go when you want ready-to-use materials instead of starting from scratch.</p>
      <div class="grid-4">
        <div class="card">
          <h3>Content Templates</h3>
          <p>Use these when you need structure for posts, offers, and content ideas.</p>
        </div>
        <div class="card">
          <h3>AI Prompts</h3>
          <p>Use these to speed up brainstorming, content writing, and creative workflows.</p>
        </div>
        <div class="card">
          <h3>Sales Page Templates</h3>
          <p>Use these when you are ready to present and sell an offer more clearly.</p>
        </div>
        <div class="card">
          <h3>Scripts</h3>
          <p>Use these for lives, content delivery, selling, and smoother communication.</p>
        </div>
      </div>
      <div class="quote">The Vault exists to save time, reduce friction, and make execution easier.</div>
    </section>

    <section class="section">
      <div class="section-label">Support</div>
      <h2>Coaching and Support</h2>
      <p>You do not have to build this alone. There are two main places to get help depending on what you need.</p>
      <div class="grid-2">
        <div class="support-card">
          <h3>Rise and Grind Coaching Hub</h3>
          <p>Use this for daily motivation, coaching calls, structure, and tasks that keep you moving.</p>
          <ul>
            <li>Daily motivation</li>
            <li>Coaching calls</li>
            <li>Tasks and accountability</li>
          </ul>
        </div>
        <div class="support-card">
          <h3>Community</h3>
          <p>Use this when you want connection, answers, and proof that other people are building too.</p>
          <ul>
            <li>Ask questions</li>
            <li>Share wins</li>
            <li>Connect with other creators</li>
          </ul>
        </div>
      </div>
    </section>

    <section class="section" id="paths">
      <div class="section-label">Choose Your Path</div>
      <h2>The Rule That Makes This Easy</h2>
      <p>Do not try to do everything. Choose <strong>one</strong> path first. Build one income stream first. Then expand later.</p>
      <div class="grid-3">
        <div class="path-card">
          <h3>Creator Path</h3>
          <p>Best if you want to grow an audience, build trust, and monetize content.</p>
        </div>
        <div class="path-card">
          <h3>Digital Product Path</h3>
          <p>Best if you want to create digital assets and sell them repeatedly.</p>
        </div>
        <div class="path-card">
          <h3>Ecommerce / Service Path</h3>
          <p>Best if you want to sell products or services online.</p>
        </div>
      </div>
      <div class="quote">One focused path is easier to finish than three half-started ones.</div>

      <div class="path-gallery">
        <div class="image-card">
          <img src="file:///F:/The%20Creator%20Plug/453058e2663748ed88bf5d8becc0d1cd7244bd64b0344a6297b19a8d3ccf9a1a.jpg" alt="Creator Path">
          <h3>Creator Path Visual</h3>
          <p>Use this path if your main goal is to build attention, grow your following, and turn content into income.</p>
        </div>
        <div class="image-card">
          <img src="file:///F:/The%20Creator%20Plug/92be4b7c84cc406eab79412c543ed247653a8007f00649888a7ea486702d5259-md.jpg" alt="Digital Product Path">
          <h3>Digital Product Path Visual</h3>
          <p>Use this path if you want to create assets once and keep selling them repeatedly over time.</p>
        </div>
        <div class="image-card">
          <img src="file:///F:/The%20Creator%20Plug/27e919353aad468299c5a5e2ae4f137f50dffa6667fe4ad0bbfb4905fe1f2d77-md.jpg" alt="E-Commerce Service Path">
          <h3>Ecommerce / Service Path Visual</h3>
          <p>Use this path if you want to build a product-based or service-based online business.</p>
        </div>
      </div>
    </section>

    <section class="section" id="checklist">
      <div class="section-label">Checklist</div>
      <h2>Quick Start Checklist</h2>
      <p>If you want the simplest possible starting point, complete these steps in order.</p>
      <div class="grid-2">
        <div class="check-card">
          <h3>Your First Actions</h3>
          <div class="list-clean">
            <div><span class="tick">□</span><span>Start Here</span></div>
            <div><span class="tick">□</span><span>Creator Plug Launch Challenge</span></div>
          </div>
        </div>
        <div class="check-card">
          <h3>Your Focus</h3>
          <div class="list-clean">
            <div><span class="tick">□</span><span>Choose your path</span></div>
            <div><span class="tick">□</span><span>Complete those modules</span></div>
          </div>
        </div>
      </div>
      <div class="quote">That's it! You do not need a complicated plan to begin. You need a clear first move.</div>
    </section>

    <section class="cta">
      <div class="section-label" style="background:rgba(255,255,255,0.14); color:#fff5dd;">Next Step</div>
      <h2>Now Let's Get Started</h2>
      <p>Start with the first two sections, choose one path, and complete the modules for that path. Build one income stream first. Expand later once the foundation is working.</p>
    </section>
  </div>
</body>
</html>
