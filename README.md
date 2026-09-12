<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>Brain &amp; Mind Academy • AP Calculus AB - Unit 1 Limits Review</title>

  <!-- MathJax Configuration & Loader -->
  <script>
    window.MathJax = {
      tex: {
        inlineMath: [['\\(', '\\)'], ['$', '$']],
        displayMath: [['\\[', '\\]'], ['$$', '$$']],
        processEscapes: true
      },
      svg: { fontCache: 'global' }
    };
  </script>
  <script type="text/javascript" id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js">
  </script>

  <style>
    :root {
      --navy-dark: #0c4a6e;
      --brand-blue: #0284c7;
      --accent-cyan: #0ea5e9;
      --bg-tint: #f0f9ff;
      --card-surf: #ffffff;
      --border-accent: #7dd3fc;
      --border-soft: #bae6fd;
      --green-ok: #059669;
      --green-surf: #d1fae5;
      --red-fail: #dc2626;
      --red-surf: #fee2e2;
      --brand-gold: #f59e0b;
      --gold-dark: #d97706;
      --gold-surf: #fef3c7;
      --text-main: #0f172a;
      --text-muted: #475569;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
    }

    body {
      background-color: var(--bg-tint);
      color: var(--text-main);
      display: flex;
      flex-direction: column;
      min-height: 100vh;
    }

    header {
      background: var(--navy-dark);
      color: #fff;
      padding: 12px 24px;
      display: flex;
      justify-content: space-between;
      align-items: center;
      box-shadow: 0 4px 12px rgba(12, 74, 110, 0.15);
      position: sticky;
      top: 0;
      z-index: 100;
    }

    .brand-wrap {
      display: flex;
      align-items: center;
      gap: 14px;
    }

    .logo-badge {
      width: 44px;
      height: 44px;
      background: #ffffff;
      border-radius: 10px;
      display: flex;
      align-items: center;
      justify-content: center;
      box-shadow: 0 2px 6px rgba(0,0,0,0.2);
    }

    .brand-title h1 {
      font-size: 1.15rem;
      font-weight: 700;
      letter-spacing: 0.5px;
    }

    .brand-title p {
      font-size: 0.78rem;
      color: var(--accent-cyan);
      font-weight: 500;
    }

    .header-controls {
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .chip {
      background: rgba(255, 255, 255, 0.15);
      border: 1px solid var(--border-accent);
      padding: 6px 14px;
      border-radius: 20px;
      font-size: 0.88rem;
      color: #ffffff;
      display: flex;
      align-items: center;
      gap: 6px;
    }

    .chip strong {
      color: #ffffff;
      font-weight: 800;
      letter-spacing: 0.3px;
    }

    .btn-icon {
      background: transparent;
      border: 1px solid var(--border-accent);
      color: #fff;
      border-radius: 50%;
      width: 36px;
      height: 36px;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1rem;
    }

    nav {
      background: #ffffff;
      border-bottom: 1px solid var(--border-soft);
      display: flex;
      justify-content: center;
      gap: 8px;
      padding: 8px 16px;
    }

    nav button {
      background: none;
      border: none;
      outline: none;
      padding: 10px 20px;
      font-size: 0.95rem;
      font-weight: 600;
      color: var(--text-muted);
      cursor: pointer;
      border-radius: 8px;
      transition: all 0.2s;
    }

    nav button.active {
      background: var(--bg-tint);
      color: var(--brand-blue);
      border-bottom: 3px solid var(--brand-blue);
    }

    main {
      flex: 1;
      padding: 24px;
      max-width: 1400px;
      margin: 0 auto;
      width: 100%;
    }

    .view {
      display: none;
    }

    .view.active {
      display: block;
    }

    #loginGateView {
      position: fixed;
      top: 0;
      left: 0;
      right: 0;
      bottom: 0;
      background: rgba(12, 74, 110, 0.92);
      backdrop-filter: blur(6px);
      z-index: 1000;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .login-box {
      background: #fff;
      padding: 36px;
      border-radius: 16px;
      width: 100%;
      max-width: 440px;
      text-align: center;
      box-shadow: 0 14px 35px rgba(0,0,0,0.3);
    }

    .login-box h2 {
      font-size: 1.45rem;
      color: var(--navy-dark);
      margin-bottom: 6px;
    }

    .login-box p {
      font-size: 0.88rem;
      color: var(--text-muted);
      margin-bottom: 24px;
    }

    .login-box input {
      width: 100%;
      padding: 12px 16px;
      border: 1px solid var(--border-soft);
      border-radius: 8px;
      font-size: 1rem;
      margin-bottom: 16px;
      outline: none;
    }

    .btn-primary {
      background: var(--brand-blue);
      color: #fff;
      border: none;
      padding: 12px 24px;
      font-size: 1rem;
      font-weight: 600;
      border-radius: 8px;
      cursor: pointer;
      width: 100%;
      transition: background 0.2s;
    }

    .btn-primary:hover {
      background: var(--navy-dark);
    }

    .theory-card {
      background: #fff;
      border-radius: 12px;
      border: 1px solid var(--border-soft);
      padding: 24px;
      margin-bottom: 24px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.02);
    }

    .theory-card h3 {
      color: var(--navy-dark);
      margin-bottom: 14px;
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 1.25rem;
    }

    .theory-intro-text {
      color: var(--text-main);
      line-height: 1.65;
      margin-bottom: 18px;
      font-size: 0.95rem;
    }

    .compendium-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 20px;
      margin: 16px 0;
    }

    .comp-card {
      background: #ffffff;
      border: 1px solid var(--border-soft);
      border-radius: 10px;
      padding: 18px;
      display: flex;
      flex-direction: column;
      box-shadow: 0 2px 6px rgba(12, 74, 110, 0.04);
    }

    .comp-card h4 {
      color: var(--navy-dark);
      border-bottom: 2px solid var(--border-soft);
      padding-bottom: 8px;
      margin-bottom: 12px;
      font-size: 1.05rem;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .recap-body {
      font-size: 0.92rem;
      line-height: 1.65;
      color: var(--text-main);
    }

    .formula-box {
      background: #f8fafc;
      border-left: 4px solid var(--brand-blue);
      border-radius: 0 6px 6px 0;
      padding: 10px 14px;
      margin-top: 10px;
    }

    .sheet-grid {
      display: grid;
      grid-template-columns: 1fr 340px;
      gap: 24px;
    }

    @media (max-width: 990px) {
      .sheet-grid {
        grid-template-columns: 1fr;
      }
    }

    .question-card {
      background: #fff;
      border-radius: 12px;
      border: 1px solid var(--border-soft);
      padding: 26px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.03);
    }

    .concept-tag {
      display: inline-block;
      padding: 4px 10px;
      border-radius: 14px;
      font-size: 0.75rem;
      font-weight: 700;
      letter-spacing: 0.4px;
      text-transform: uppercase;
      margin-bottom: 8px;
      background: #e0f2fe;
      color: #0369a1;
      border: 1px solid #7dd3fc;
    }

    .mcq-container {
      display: grid;
      grid-template-columns: 1fr;
      gap: 10px;
      margin: 18px 0;
    }

    .mcq-option-btn {
      background: #f8fafc;
      border: 2px solid var(--border-soft);
      border-radius: 8px;
      padding: 12px 16px;
      text-align: left;
      font-size: 0.96rem;
      color: var(--text-main);
      cursor: pointer;
      transition: all 0.15s ease;
      display: flex;
      align-items: center;
      gap: 12px;
    }

    .mcq-option-btn:hover:not(:disabled) {
      background: var(--bg-tint);
      border-color: var(--brand-blue);
    }

    .mcq-option-btn.selected-correct {
      background: var(--green-surf) !important;
      border-color: var(--green-ok) !important;
      color: var(--green-ok) !important;
      font-weight: 700;
    }

    .mcq-option-btn.selected-wrong {
      background: var(--red-surf) !important;
      border-color: var(--red-fail) !important;
      color: var(--red-fail) !important;
    }

    .opt-letter {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      width: 28px;
      height: 28px;
      border-radius: 50%;
      background: #ffffff;
      border: 1px solid var(--border-accent);
      font-weight: 700;
      color: var(--navy-dark);
      flex-shrink: 0;
    }

    .attempts-badge {
      font-size: 0.8rem;
      font-weight: 700;
      padding: 4px 10px;
      border-radius: 12px;
      background: #f1f5f9;
      color: #64748b;
      margin-left: 6px;
    }

    .btn-reveal {
      background: var(--brand-gold);
      color: #fff;
      border: none;
      padding: 6px 14px;
      border-radius: 6px;
      font-weight: 600;
      font-size: 0.85rem;
      cursor: pointer;
      margin-left: 8px;
    }

    .btn-reveal:hover {
      background: var(--gold-dark);
    }

    .feedback-box {
      margin-top: 16px;
      padding: 16px;
      border-radius: 8px;
      font-size: 0.95rem;
      line-height: 1.65;
      display: block;
      animation: fadeIn 0.25s ease-in;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(4px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .feedback-box.correct {
      background: #ecfdf5;
      border-left: 5px solid var(--green-ok);
      color: #065f46;
    }

    .feedback-box.incorrect {
      background: #fef2f2;
      border-left: 5px solid var(--red-fail);
      color: #991b1b;
    }

    .svg-container {
      display: flex;
      justify-content: center;
      margin: 16px 0;
      padding: 14px;
      background: var(--bg-tint);
      border-radius: 8px;
      border: 1px solid var(--border-soft);
      overflow-x: auto;
    }

    .nav-toolbar {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 26px;
      padding-top: 18px;
      border-top: 1px solid var(--border-soft);
    }

    .nav-btn-group {
      display: flex;
      gap: 10px;
    }

    .btn-nav-action {
      background: #f8fafc;
      border: 1px solid var(--border-accent);
      color: var(--navy-dark);
      padding: 8px 18px;
      border-radius: 6px;
      font-weight: 600;
      font-size: 0.9rem;
      cursor: pointer;
      display: flex;
      align-items: center;
      gap: 6px;
      transition: all 0.15s;
    }

    .btn-nav-action:hover:not(:disabled) {
      background: var(--bg-tint);
      border-color: var(--brand-blue);
    }

    .btn-nav-action:disabled {
      opacity: 0.45;
      cursor: not-allowed;
    }

    .btn-skip {
      border-color: var(--brand-gold);
      color: var(--gold-dark);
      background: var(--gold-surf);
    }

    .btn-skip:hover {
      background: #fde68a;
    }

    .palette-box {
      background: #fff;
      border: 1px solid var(--border-soft);
      border-radius: 12px;
      padding: 16px;
      margin-bottom: 20px;
    }

    .palette-legend {
      display: flex;
      justify-content: space-between;
      font-size: 0.75rem;
      margin: 8px 0 12px 0;
      padding: 6px 8px;
      background: var(--bg-tint);
      border-radius: 6px;
    }

    .legend-item {
      display: flex;
      align-items: center;
      gap: 4px;
      font-weight: 600;
    }

    .legend-dot {
      width: 10px;
      height: 10px;
      border-radius: 50%;
    }

    .palette-grid {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 6px;
      margin-bottom: 12px;
    }

    .palette-btn {
      aspect-ratio: 1;
      border: 1px solid var(--border-soft);
      background: var(--bg-tint);
      border-radius: 6px;
      font-weight: 600;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: all 0.15s;
      font-size: 0.85rem;
      color: var(--navy-dark);
    }

    .palette-btn.active {
      border: 2px solid var(--navy-dark) !important;
      background: var(--border-accent);
      color: #fff;
      font-weight: 800;
    }

    .palette-btn.completed {
      background: var(--green-ok) !important;
      color: #fff !important;
      border-color: var(--green-ok) !important;
    }

    .palette-btn.skipped {
      background: var(--brand-gold) !important;
      color: #fff !important;
      border-color: var(--gold-dark) !important;
    }

    .hero-score-card {
      background: #fff;
      border-radius: 12px;
      border: 1px solid var(--border-soft);
      padding: 28px;
      text-align: center;
      margin-bottom: 24px;
      box-shadow: 0 4px 14px rgba(0,0,0,0.03);
    }

    .student-badge {
      display: inline-block;
      background: var(--bg-tint);
      border: 1px solid var(--border-accent);
      padding: 6px 18px;
      border-radius: 20px;
      font-size: 1rem;
      margin-bottom: 14px;
      color: var(--navy-dark);
    }

    .student-badge strong {
      color: var(--brand-blue);
    }

    .score-badge {
      font-size: 3rem;
      font-weight: 800;
      color: var(--brand-blue);
      margin: 8px 0;
    }

    .progress-bar-wrap {
      width: 100%;
      height: 12px;
      background: #e2e8f0;
      border-radius: 6px;
      overflow: hidden;
      margin: 16px 0;
    }

    .progress-bar-fill {
      height: 100%;
      background: var(--green-ok);
      width: 0%;
      transition: width 0.3s ease;
    }

    .toast {
      position: fixed;
      bottom: 20px;
      right: 20px;
      background: var(--navy-dark);
      color: #fff;
      padding: 12px 20px;
      border-radius: 8px;
      box-shadow: 0 4px 16px rgba(0,0,0,0.2);
      display: none;
      z-index: 1000;
    }

    @media print {
      header, nav, .palette-box, .btn-primary, #loginGateView, .nav-toolbar {
        display: none !important;
      }
      body { background: #fff; }
      main { width: 100%; max-width: 100%; padding: 0; }
      .sheet-grid { display: block; }
      .view { display: block !important; }
    }
  </style>
</head>
<body>

  <!-- Brand Header -->
  <header>
    <div class="brand-wrap">
      <div class="logo-badge">
        <svg width="34" height="34" viewBox="0 0 100 100" fill="none">
          <path d="M 20 30 Q 50 10 80 30" stroke="#f59e0b" stroke-width="8" stroke-linecap="round"/>
          <path d="M 26 40 Q 50 22 74 40" stroke="#f59e0b" stroke-width="8" stroke-linecap="round"/>
          <path d="M 32 50 Q 50 36 68 50" stroke="#f59e0b" stroke-width="7" stroke-linecap="round"/>
          <path d="M 18 80 Q 50 68 50 82 Q 50 68 82 80 L 82 52 Q 50 42 50 56 Q 50 42 18 52 Z" fill="#ffffff" stroke="#334155" stroke-width="7" stroke-linejoin="round"/>
        </svg>
      </div>
      <div class="brand-title">
        <h1>Brain &amp; Mind Academy</h1>
        <p>B&amp;M – The Experts • AP Calculus AB (Unit 1: Limits &amp; Continuity Review)</p>
      </div>
    </div>
    <div class="header-controls">
      <div class="chip" id="timerChip">⏱️ 00:00</div>
      <div class="chip" id="userPill"><strong>Student: Guest</strong></div>
      <button class="btn-icon" id="audioToggleBtn" title="Toggle Audio">🔊</button>
    </div>
  </header>

  <!-- Navigation Bar -->
  <nav>
    <button class="tab-btn active" id="tabPracticeBtn" onclick="switchView('practiceView')">✍️ Interactive Review Test</button>
    <button class="tab-btn" id="tabTheoryBtn" onclick="switchView('theoryView')">📖 Concept &amp; Asymptotics Guide</button>
    <button class="tab-btn" id="tabResultsBtn" onclick="switchView('resultsView')">📋 Complete Solutions &amp; Report</button>
  </nav>

  <!-- Student Authentication Modal -->
  <div id="loginGateView">
    <div class="login-box">
      <h2>AP Calculus Portal</h2>
      <p>Unit 1 (Chapter 2) • Limits &amp; Continuity Comprehensive Review</p>
      <input type="text" id="studentNameInput" placeholder="Enter Student Name" />
      <button class="btn-primary" onclick="initDirectLogin()">Start Practice Session</button>
    </div>
  </div>

  <main>
    <!-- View 1: Interactive Review Test Workstation -->
    <div id="practiceView" class="view active">
      <div class="sheet-grid">
        <div class="question-card" id="activeQuestionCard"></div>

        <aside>
          <div class="palette-box">
            <div style="display: flex; justify-content: space-between; align-items: center;">
              <h4>Abhyas Palette</h4>
              <span style="font-size:0.8rem; color:var(--text-muted);" id="paletteCount">0 / 17 Completed</span>
            </div>

            <div class="palette-legend">
              <div class="legend-item"><span class="legend-dot" style="background:var(--green-ok);"></span> Solved</div>
              <div class="legend-item"><span class="legend-dot" style="background:#f59e0b;"></span> Skipped</div>
              <div class="legend-item"><span class="legend-dot" style="background:#7dd3fc;"></span> Active</div>
              <div class="legend-item"><span class="legend-dot" style="background:#f0f9ff; border:1px solid #bae6fd;"></span> Unseen</div>
            </div>
            
            <div class="palette-grid" id="paletteGrid"></div>
            
            <button class="btn-primary" style="margin-top: 10px; background: var(--navy-dark);" onclick="switchView('resultsView')">
              📊 View Performance Scorecard
            </button>
          </div>

          <div class="palette-box" style="background: #f8fafc;">
            <h4 style="font-size: 0.92rem; margin-bottom: 8px; color: var(--navy-dark);">Workstation Scaffolding</h4>
            <p style="font-size: 0.82rem; line-height: 1.6; color: var(--text-muted);">
              • Select your option for instant evaluation.<br/>
              • You are granted <strong>2 attempts</strong> per problem before the <strong>Reveal Solution</strong> button unlocks.<br/>
              • Every problem is backed by worked derivations and AP-aligned graphical visualizations.
            </p>
          </div>
        </aside>
      </div>
    </div>

    <!-- View 2: Concept & Asymptotics Guide -->
    <div id="theoryView" class="view">
      <div class="theory-card">
        <h3>📐 AP Calculus AB Limits &amp; Continuity Compendium</h3>
        <p class="theory-intro-text">
          Review core foundational definitions for limits, horizontal asymptotes, the Intermediate Value Theorem, and the Squeeze Theorem.
        </p>

        <div class="compendium-grid">
          <!-- Card 1 -->
          <div class="comp-card">
            <h4>1. Continuity &amp; Discontinuities</h4>
            <div class="recap-body">
              <p>A function \(f\) is continuous at \(x = c\) if and only if:</p>
              <div class="formula-box">
                \[1. \, f(c) \text{ exists}, \quad 2. \, \lim_{x \to c} f(x) \text{ exists}, \quad 3. \, \lim_{x \to c} f(x) = f(c)\]
                <p style="margin-top:4px; font-size:0.85rem;"><strong>Removable:</strong> \(\lim_{x \to c} f(x)\) exists but does not equal \(f(c)\).</p>
                <p style="margin-top:2px; font-size:0.85rem;"><strong>Jump:</strong> \(\lim_{x \to c^-} f(x) \ne \lim_{x \to c^+} f(x)\).</p>
              </div>
            </div>
          </div>

          <!-- Card 2 -->
          <div class="comp-card">
            <h4>2. Horizontal Asymptotes via Radicals</h4>
            <div class="recap-body">
              <p>For \(f(x) = \frac{\sqrt{5x^2 - x}}{x + 3}\), note the definition \(\sqrt{x^2} = |x|\):</p>
              <div class="formula-box">
                <p>• As \(x \to \infty\): \(\frac{\sqrt{x^2(5 - 1/x)}}{x(1 + 3/x)} = \frac{x\sqrt{5}}{x} \to \sqrt{5}\).</p>
                <p>• As \(x \to -\infty\): \(|x| = -x \implies \frac{-x\sqrt{5}}{x} \to -\sqrt{5}\).</p>
              </div>
            </div>
          </div>

          <!-- Card 3 -->
          <div class="comp-card">
            <h4>3. Intermediate Value Theorem (IVT)</h4>
            <div class="recap-body">
              <p>If \(f\) is continuous on \([a, b]\) and \(k\) is any value strictly between \(f(a)\) and \(f(b)\), there exists at least one \(c \in (a, b)\) such that \(f(c) = k\).</p>
              <div class="formula-box">
                <p><strong>Root Existence:</strong> If \(f(a) \cdot f(b) < 0\), a zero exists in \((a, b)\).</p>
              </div>
            </div>
          </div>

          <!-- Card 4 -->
          <div class="comp-card">
            <h4>4. The Squeeze (Sandwich) Theorem</h4>
            <div class="recap-body">
              <p>If \(k(x) \le f(x) \le m(x)\) near \(c\), and:</p>
              <div class="formula-box">
                \[\lim_{x \to c} k(x) = \lim_{x \to c} m(x) = L\]
                \[\implies \lim_{x \to c} f(x) = L\]
                <p style="font-size:0.85rem; margin-top:4px;">If the limits of the bounding functions are unequal, the Squeeze Theorem cannot be applied.</p>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- View 3: Complete Solutions & Final Results -->
    <div id="resultsView" class="view">
      <div class="hero-score-card">
        <h2>AP Calculus Review Diagnostic Scorecard</h2>
        <div class="student-badge" id="reportStudentBadge"><strong>Student: Guest</strong></div>
        <div class="score-badge" id="scoreValue">0 / 17</div>
        <div class="progress-bar-wrap">
          <div class="progress-bar-fill" id="progressBarFill"></div>
        </div>
        <p id="scoreSubtitle" style="font-size:1.02rem; font-weight:600; color:var(--navy-dark); margin-top:8px;">
          Review all your question outcomes and worked derivations below.
        </p>
        <button class="btn-primary" style="margin-top: 14px; max-width: 240px;" onclick="window.print()">🖨️ Print Review Scorecard</button>
      </div>

      <div id="completeSolutionsContainer"></div>
    </div>
  </main>

  <div class="toast" id="toastMessage"></div>

  <script>
    /* ==========================================================================
       COMPLETE 17-QUESTION DATASET (EVERY SINGLE PART CONVERTED TO MCQ)
       Source: AP Calculus AB 2023-24 Unit 1 Review
       ========================================================================== */
    const CHAPTER_QUESTIONS = [
      // ---------- SECTION 1: FREE RESPONSE REVIEW AS MCQs (Q1 - Q7) ----------
      {
        id: 1,
        section: "Free Response Review Q1",
        title: "Function Graphing from Limit Specifications",
        prompt: "A function \\(f(x)\\) satisfies all of the following conditions:<br>" +
                "• \\(f(3) = 1, \\, f(0) = -1\\)[cite: 4]<br>" +
                "• \\(\\lim_{x \\to -2} f(x) = -\\infty\\)[cite: 4]<br>" +
                "• \\(\\lim_{x \\to 0^+} f(x) = 2\\) and \\(\\lim_{x \\to 0} f(x)\\) does not exist[cite: 4]<br>" +
                "• \\(\\lim_{x \\to 3} f(x) = 3\\)[cite: 4]<br>" +
                "• \\(\\lim_{x \\to \\infty} f(x) = -1\\) and \\(\\lim_{x \\to -\\infty} f(x) = 2\\)[cite: 4]<br><br>" +
                "Which statement correctly classifies the discontinuities and asymptotes of \\(f(x)\\)?",
        svg: `<svg width="100%" height="240" viewBox="0 0 460 220" style="max-width:440px;">
          <rect width="460" height="220" fill="#ffffff" stroke="#cbd5e1" stroke-width="1.5" rx="6"/>
          <!-- Grid Lines -->
          <defs>
            <pattern id="grid" width="20" height="20" patternUnits="userSpaceOnUse">
              <path d="M 20 0 L 0 0 0 20" fill="none" stroke="#f1f5f9" stroke-width="1"/>
            </pattern>
          </defs>
          <rect width="460" height="220" fill="url(#grid)" />
          
          <!-- Axes (Origin at 200, 120) -->
          <line x1="20" y1="120" x2="440" y2="120" stroke="#475569" stroke-width="1.8"/>
          <line x1="200" y1="15" x2="200" y2="205" stroke="#475569" stroke-width="1.8"/>
          <text x="430" y="135" font-size="11" fill="#475569">x</text>
          <text x="206" y="25" font-size="11" fill="#475569">y</text>
          
          <!-- Horizontal Asymptote y = 2 for x -> -infinity (scaled: 1 unit = 20px, y=2 -> 80) -->
          <line x1="20" y1="80" x2="160" y2="80" stroke="#0284c7" stroke-width="1.5" stroke-dasharray="4"/>
          <text x="30" y="74" font-size="9" fill="#0284c7">y = 2</text>
          
          <!-- Horizontal Asymptote y = -1 for x -> infinity (y=-1 -> 140) -->
          <line x1="260" y1="140" x2="440" y2="140" stroke="#0284c7" stroke-width="1.5" stroke-dasharray="4"/>
          <text x="390" y="152" font-size="9" fill="#0284c7">y = -1</text>
          
          <!-- Vertical Asymptote x = -2 (scaled: x = 200 - 40 = 160) -->
          <line x1="160" y1="15" x2="160" y2="205" stroke="#dc2626" stroke-width="1.5" stroke-dasharray="4"/>
          <text x="125" y="200" font-size="9" fill="#dc2626">x = −2</text>
          
          <!-- Curve Left of -2: from y=2 plunging to -infinity -->
          <path d="M 25,82 Q 130,85 155,210" fill="none" stroke="#0c4a6e" stroke-width="2.2"/>
          
          <!-- Curve between -2 and 0: from -infinity up to (0, -1) -->
          <path d="M 165,210 Q 185,150 200,140" fill="none" stroke="#0c4a6e" stroke-width="2.2"/>
          <circle cx="200" cy="140" r="4" fill="#0c4a6e"/> <!-- f(0) = -1 -->
          <text x="206" y="144" font-size="9">(0, −1)</text>
          
          <!-- Curve from x=0+ at y=2 through (3, 3) to y=-1 -->
          <circle cx="200" cy="80" r="4" fill="#ffffff" stroke="#0c4a6e" stroke-width="2"/> <!-- lim x->0+ = 2 -->
          <path d="M 204,80 Q 230,60 260,60" fill="none" stroke="#0c4a6e" stroke-width="2.2"/>
          <circle cx="260" cy="60" r="4" fill="#ffffff" stroke="#0c4a6e" stroke-width="2"/> <!-- hole at (3,3) -->
          <circle cx="260" cy="100" r="4" fill="#0c4a6e"/> <!-- f(3) = 1 -->
          <text x="266" y="104" font-size="9">(3, 1)</text>
          
          <!-- Continuing right to y = -1 -->
          <path d="M 264,60 Q 300,60 340,120 T 435,139" fill="none" stroke="#0c4a6e" stroke-width="2.2"/>
        </svg>`,
        options: [
          { label: "A", text: "Vertical asymptote at x = -2; jump discontinuity at x = 0; removable discontinuity at x = 3; horizontal asymptotes at y = 2 (as x -> -∞) and y = -1 (as x -> ∞)." },
          { label: "B", text: "Vertical asymptote at x = 2; removable discontinuity at x = 0; jump discontinuity at x = 3; single horizontal asymptote at y = 0." },
          { label: "C", text: "Vertical asymptote at x = -2; continuous at x = 0; removable discontinuity at x = 3; horizontal asymptote at y = -1 only." },
          { label: "D", text: "Vertical asymptote at x = 0; jump discontinuity at x = -2; continuous at x = 3; horizontal asymptotes at y = 1 and y = -1." }
        ],
        correctIndex: 0,
        explanation: "• At \\(x = -2\\), \\(\\lim_{x \\to -2} f(x) = -\\infty\\), giving a vertical asymptote at \\(x = -2\\)[cite: 4].<br>" +
                     "• At \\(x = 0\\), \\(f(0) = -1\\) while \\(\\lim_{x \\to 0^+} f(x) = 2\\), producing a jump discontinuity[cite: 4].<br>" +
                     "• At \\(x = 3\\), \\(\\lim_{x \\to 3} f(x) = 3\\) but \\(f(3) = 1 \\ne 3\\), producing a removable discontinuity[cite: 4].<br>" +
                     "• The limits at \\(\\pm\\infty\\) yield horizontal asymptotes \\(y = 2\\) as \\(x \\to -\\infty\\) and \\(y = -1\\) as \\(x \\to \\infty\\)[cite: 4]."
      },
      {
        id: 2,
        section: "Free Response Review Q2a",
        title: "Intermediate Value Theorem: Polynomial Root",
        prompt: "Consider the equation \\(3x = x^3 - 3x^2 + 2\\) on the closed interval \\([0, 2]\\)[cite: 4]. Let \\(g(x) = x^3 - 3x^2 - 3x + 2\\). What are the values of \\(g(0)\\) and \\(g(2)\\), and what does the Intermediate Value Theorem conclude?",
        options: [
          { label: "A", text: "g(0) = 2 and g(2) = -8; since g(x) is continuous on [0, 2] and changes sign, IVT guarantees at least one solution in (0, 2)." },
          { label: "B", text: "g(0) = -2 and g(2) = 8; IVT does not apply because g(0) is negative." },
          { label: "C", text: "g(0) = 2 and g(2) = 2; IVT guarantees roots only if the endpoint values are equal." },
          { label: "D", text: "g(0) = 0 and g(2) = -6; IVT cannot guarantee a root because g(0) is already zero." }
        ],
        correctIndex: 0,
        explanation: "Rewriting the equation gives \\(g(x) = x^3 - 3x^2 - 3x + 2 = 0\\).<br>" +
                     "\\(g(0) = 0 - 0 - 0 + 2 = 2 > 0\\).<br>" +
                     "\\(g(2) = 2^3 - 3(2)^2 - 3(2) + 2 = 8 - 12 - 6 + 2 = -8 < 0\\).<br>" +
                     "Because \\(g(x)\\) is a polynomial, it is continuous everywhere on \\([0, 2]\\). Since 0 lies between \\(g(0) = 2\\) and \\(g(2) = -8\\), by IVT there exists at least one \\(c \\in (0, 2)\\) such that \\(g(c) = 0\\)."
      },
      {
        id: 3,
        section: "Free Response Review Q2b",
        title: "Intermediate Value Theorem: Trigonometric Equation",
        prompt: "Consider the equation \\(x \\sin(x) = \\frac{1}{2}\\) on the interval \\([\\frac{\\pi}{2}, \\pi]\\)[cite: 4]. Let \\(h(x) = x \\sin(x) - \\frac{1}{2}\\). Which statement rigorously proves that a solution exists on \\([\\frac{\\pi}{2}, \\pi]\\)?",
        options: [
          { label: "A", text: "h(π/2) = (π - 1)/2 > 0 and h(π) = -1/2 < 0; since h(x) is continuous on [π/2, π], IVT guarantees at least one solution." },
          { label: "B", text: "h(π/2) = 1/2 and h(π) = 1/2; since the values are equal, Rolle's Theorem guarantees a zero." },
          { label: "C", text: "h(x) is not continuous at π/2, so the Intermediate Value Theorem cannot be applied." },
          { label: "D", text: "h(π/2) < 0 and h(π) < 0; no root exists on this interval." }
        ],
        correctIndex: 0,
        explanation: "Let \\(h(x) = x \\sin(x) - \\frac{1}{2}\\).<br>" +
                     "\\(h(\\frac{\\pi}{2}) = \\frac{\\pi}{2} \\sin(\\frac{\\pi}{2}) - \\frac{1}{2} = \\frac{\\pi}{2}(1) - \\frac{1}{2} = \\frac{\\pi - 1}{2} \\approx \\frac{2.14}{2} = 1.07 > 0\\).<br>" +
                     "\\(h(\\pi) = \\pi \\sin(\\pi) - \\frac{1}{2} = \\pi(0) - \\frac{1}{2} = -\\frac{1}{2} < 0\\).<br>" +
                     "Since \\(h(x)\\) is continuous on \\([\\frac{\\pi}{2}, \\pi]\\) and changes sign, the Intermediate Value Theorem guarantees at least one solution in \\((\\frac{\\pi}{2}, \\pi)\\)."
      },
      {
        id: 4,
        section: "Free Response Review Q2c",
        title: "Intermediate Value Theorem: Logarithmic Equation Analysis",
        prompt: "Consider the equation \\(2\\log(x) = x\\) on the interval \\([1, 10]\\)[cite: 4]. Let \\(j(x) = 2\\log_{10}(x) - x\\). Evaluating at the endpoints gives:<br>" +
                "\\[j(1) = 2(0) - 1 = -1 < 0 \\quad \\text{and} \\quad j(10) = 2(1) - 10 = -8 < 0\\]<br>" +
                "Can the Intermediate Value Theorem using solely the endpoints \\(x = 1\\) and \\(x = 10\\) guarantee a solution on \\([1, 10]\\)?",
        options: [
          { label: "A", text: "No, because j(1) and j(10) have the same sign (both negative), so IVT does not guarantee a sign change across [1, 10] from the endpoints alone." },
          { label: "B", text: "Yes, because all continuous functions on closed intervals must cross the x-axis." },
          { label: "C", text: "Yes, because j(x) is positive for all x in (1, 10)." },
          { label: "D", text: "No, because logarithmic functions are not continuous on [1, 10]." }
        ],
        correctIndex: 0,
        explanation: "The Intermediate Value Theorem requires the target value (0) to lie between \\(j(a)\\) and \\(j(b)\\). Since \\(j(1) = -1 < 0\\) and \\(j(10) = -8 < 0\\), both endpoints are negative, so IVT on \\([1, 10]\\) alone does not show a sign change (in fact, \\(j(x) < 0\\) for all \\(x \\ge 1\\), so no real solution exists on \\([1, 10]\\))."
      },
      {
        id: 5,
        section: "Free Response Review Q3",
        title: "Continuity of a Piecewise Function",
        prompt: "Let \\(f(x) = \\begin{cases} \\frac{x^2 - 16}{x - 4} & x \\ne 4 \\\\ 6 & x = 4 \\end{cases}\\)[cite: 4].<br><br>" +
                "Which of the following statements about \\(f\\) are true?[cite: 4]<br>" +
                "I. \\(f\\) has a limit at \\(x = 4\\)[cite: 4].<br>" +
                "II. \\(f(4)\\) exists[cite: 4].<br>" +
                "III. \\(f\\) is continuous at \\(x = 4\\)[cite: 4].",
        options: [
          { label: "A", text: "I only" },
          { label: "B", text: "II only" },
          { label: "C", text: "I and II only" },
          { label: "D", text: "I, II and III" }
        ],
        correctIndex: 2,
        explanation: "• Statement I is true: \\(\\lim_{x \\to 4} \\frac{x^2 - 16}{x - 4} = \\lim_{x \\to 4} (x + 4) = 4 + 4 = 8\\)[cite: 4].<br>" +
                     "• Statement II is true: \\(f(4) = 6\\) by definition[cite: 4].<br>" +
                     "• Statement III is false: \\(\\lim_{x \\to 4} f(x) = 8 \\ne 6 = f(4)\\), so \\(f\\) has a removable discontinuity at \\(x = 4\\)[cite: 4].<br>" +
                     "Thus, only I and II are true (Option C)[cite: 4]."
      },
      {
        id: 6,
        section: "Free Response Review Q4",
        title: "Horizontal Asymptotes of Radical Rational Function",
        prompt: "Find the horizontal asymptote(s) of the function \\(f(x) = \\frac{\\sqrt{5x^2 - x}}{x + 3}\\)[cite: 4].",
        svg: `<svg width="100%" height="200" viewBox="0 0 460 180" style="max-width:440px;">
          <rect width="460" height="180" fill="#ffffff" stroke="#cbd5e1" stroke-width="1.5" rx="6"/>
          <line x1="20" y1="90" x2="440" y2="90" stroke="#64748b" stroke-width="1.5"/>
          <line x1="230" y1="15" x2="230" y2="165" stroke="#64748b" stroke-width="1.5"/>
          <text x="430" y="105" font-size="11" fill="#475569">x</text>
          <text x="236" y="25" font-size="11" fill="#475569">y</text>
          
          <!-- Asymptotes y = sqrt(5) ≈ 2.24 (scaled: 1 unit = 20px, y = 45) -->
          <line x1="20" y1="45" x2="440" y2="45" stroke="#0284c7" stroke-width="1.5" stroke-dasharray="4"/>
          <text x="350" y="38" font-size="10" font-weight="bold" fill="#0284c7">y = √5</text>
          
          <!-- Asymptotes y = -sqrt(5) ≈ -2.24 (y = 135) -->
          <line x1="20" y1="135" x2="440" y2="135" stroke="#0284c7" stroke-width="1.5" stroke-dasharray="4"/>
          <text x="30" y="148" font-size="10" font-weight="bold" fill="#0284c7">y = −√5</text>
          
          <!-- Vertical asymptote x = -3 (scaled: x = 230 - 60 = 170) -->
          <line x1="170" y1="15" x2="170" y2="165" stroke="#dc2626" stroke-width="1.2" stroke-dasharray="3"/>
          <text x="140" y="160" font-size="9" fill="#dc2626">x = −3</text>
          
          <!-- Right branch approaching y = sqrt(5) -->
          <path d="M 235,160 Q 250,55 435,47" fill="none" stroke="#0c4a6e" stroke-width="2.2"/>
          <!-- Left branch approaching y = -sqrt(5) -->
          <path d="M 25,133 Q 120,132 160,20" fill="none" stroke="#0c4a6e" stroke-width="2.2"/>
        </svg>`,
        options: [
          { label: "A", text: "y = √5 and y = -√5" },
          { label: "B", text: "y = √5 only" },
          { label: "C", text: "y = 5 and y = -5" },
          { label: "D", text: "y = 0 only" }
        ],
        correctIndex: 0,
        explanation: "Factor \\(x^2\\) from the radical: \\(\\sqrt{5x^2 - x} = \\sqrt{x^2(5 - 1/x)} = |x|\\sqrt{5 - 1/x}\\).<br>" +
                     "• As \\(x \\to \\infty\\), \\(|x| = x\\):<br>" +
                     "\\[\\lim_{x \\to \\infty} \\frac{x\\sqrt{5 - 1/x}}{x(1 + 3/x)} = \\lim_{x \\to \\infty} \\frac{\\sqrt{5 - 1/x}}{1 + 3/x} = \\frac{\\sqrt{5}}{1} = \\sqrt{5}\\]<br>" +
                     "• As \\(x \\to -\\infty\\), \\(|x| = -x\\):<br>" +
                     "\\[\\lim_{x \\to -\\infty} \\frac{-x\\sqrt{5 - 1/x}}{x(1 + 3/x)} = \\lim_{x \\to -\\infty} \\frac{-\\sqrt{5 - 1/x}}{1 + 3/x} = -\\sqrt{5}\\]<br>" +
                     "Therefore, the horizontal asymptotes are \\(y = \\sqrt{5}\\) and \\(y = -\\sqrt{5}\\)."
      },
      {
        id: 7,
        section: "Free Response Review Q5",
        title: "Criteria of the Squeeze Theorem",
        prompt: "Let \\(k(x) = -x^2 - 2x + 3\\) and \\(m(x) = \\frac{1}{2}x + x + \\frac{13}{2} = \\frac{3}{2}x + \\frac{13}{2}\\)[cite: 4]. If \\(f(x)\\) satisfies \\(k(x) \\le f(x) \\le m(x)\\)[cite: 4], why can the Squeeze Theorem NOT be used to find \\(\\lim_{x \\to -1} f(x)\\)[cite: 4]?",
        svg: `<svg width="100%" height="200" viewBox="0 0 460 180" style="max-width:440px;">
          <rect width="460" height="180" fill="#ffffff" stroke="#cbd5e1" stroke-width="1.5" rx="6"/>
          <line x1="20" y1="140" x2="440" y2="140" stroke="#64748b" stroke-width="1.5"/>
          <line x1="260" y1="15" x2="260" y2="165" stroke="#64748b" stroke-width="1.5"/>
          <text x="430" y="152" font-size="11" fill="#475569">x</text>
          <text x="266" y="25" font-size="11" fill="#475569">y</text>
          
          <!-- x = -1 is at 200 (scale: 1 unit = 30px) -->
          <line x1="200" y1="15" x2="200" y2="165" stroke="#94a3b8" stroke-dasharray="3"/>
          <text x="190" y="155" font-size="10">−1</text>
          
          <!-- k(x) = -x^2 - 2x + 3 has vertex (-1, 4). Scaled y: 140 - 4*20 = 60 -->
          <path d="M 110,140 Q 200,-20 290,140" fill="none" stroke="#0284c7" stroke-width="2.2"/>
          <circle cx="200" cy="60" r="4" fill="#0284c7"/>
          <text x="208" y="65" font-size="10" font-weight="bold" fill="#0284c7">k(−1) = 4</text>
          
          <!-- m(x) = 1.5x + 6.5 has value at x=-1: m(-1) = 5. Scaled y: 140 - 5*20 = 40 -->
          <line x1="80" y1="85" x2="320" y2="-5" stroke="#ea580c" stroke-width="2.2"/>
          <circle cx="200" cy="40" r="4" fill="#ea580c"/>
          <text x="208" y="38" font-size="10" font-weight="bold" fill="#ea580c">m(−1) = 5</text>
          
          <!-- Gap of 1 unit -->
          <line x1="195" y1="40" x2="195" y2="60" stroke="#dc2626" stroke-width="2"/>
          <text x="150" y="52" font-size="9" font-weight="bold" fill="#dc2626">Gap = 1</text>
        </svg>`,
        options: [
          { label: "A", text: "Because lim(x -> -1) k(x) = 4 while lim(x -> -1) m(x) = 5; since the limits are not equal, the bounding functions do not trap f(x) at a single value." },
          { label: "B", text: "Because k(x) is not continuous at x = -1." },
          { label: "C", text: "Because m(x) is less than k(x) near x = -1." },
          { label: "D", text: "Because the Squeeze Theorem cannot be applied to polynomial bounds." }
        ],
        correctIndex: 0,
        explanation: "Evaluating the limits of the bounding functions at \\(x = -1\\):<br>" +
                     "\\[\\lim_{x \\to -1} k(x) = -(-1)^2 - 2(-1) + 3 = -1 + 2 + 3 = 4\\]<br>" +
                     "\\[\\lim_{x \\to -1} m(x) = \\frac{3}{2}(-1) + \\frac{13}{2} = \\frac{10}{2} = 5\\]<br>" +
                     "For the Squeeze Theorem to apply, the two outer limits must be equal (\\(\\lim k(x) = \\lim m(x) = L\\)). Since \\(4 \\ne 5\\), the Squeeze Theorem cannot be used to determine \\(\\lim_{x \\to -1} f(x)\\)."
      },

      // ---------- SECTION 2: MULTIPLE CHOICE REVIEW (Q8 - Q17) ----------
      {
        id: 8,
        section: "Multiple Choice Review Q1",
        title: "Limit from a Piecewise Graph",
        prompt: "The graph of \\(y = f(x)\\) is shown above[cite: 4]. What is \\(\\lim_{x \\to 1} f(x)\\)?[cite: 4]",
        svg: `<svg width="100%" height="220" viewBox="0 0 340 220" style="max-width:320px;">
          <rect width="340" height="220" fill="#ffffff" stroke="#cbd5e1" stroke-width="1.5" rx="6"/>
          <!-- Axes -->
          <line x1="20" y1="160" x2="320" y2="160" stroke="#475569" stroke-width="1.8"/>
          <line x1="110" y1="20" x2="110" y2="200" stroke="#475569" stroke-width="1.8"/>
          <text x="310" y="152" font-size="12" fill="#475569">x</text>
          <text x="100" y="32" font-size="12" fill="#475569">y</text>
          
          <!-- Ticks -->
          <line x1="60" y1="157" x2="60" y2="163" stroke="#475569"/><text x="52" y="176" font-size="10">−1</text>
          <text x="96" y="176" font-size="10">O</text>
          <line x1="160" y1="157" x2="160" y2="163" stroke="#475569"/><text x="157" y="176" font-size="10">1</text>
          <line x1="210" y1="157" x2="210" y2="163" stroke="#475569"/><text x="207" y="176" font-size="10">2</text>
          <line x1="260" y1="157" x2="260" y2="163" stroke="#475569"/><text x="257" y="176" font-size="10">3</text>
          
          <line x1="107" y1="120" x2="113" y2="120" stroke="#475569"/><text x="94" y="123" font-size="10">1</text>
          <line x1="107" y1="80" x2="113" y2="80" stroke="#475569"/><text x="94" y="83" font-size="10">2</text>
          <line x1="107" y1="40" x2="113" y2="40" stroke="#475569"/><text x="94" y="43" font-size="10">3</text>
          <line x1="107" y1="190" x2="113" y2="190" stroke="#475569"/><text x="90" y="193" font-size="10">−1</text>
          
          <!-- Linear branch from left passing through (0, 1) to (1, 3) -->
          <line x1="35" y1="210" x2="160" y2="40" stroke="#0284c7" stroke-width="2.5"/>
          <circle cx="160" cy="40" r="4.5" fill="#ffffff" stroke="#0284c7" stroke-width="2"/> <!-- hole at (1,3) -->
          
          <!-- Horizontal branch for x > 1 at y = 1 -->
          <line x1="164" y1="120" x2="290" y2="120" stroke="#0284c7" stroke-width="2.5"/>
          <circle cx="160" cy="120" r="4.5" fill="#ffffff" stroke="#0284c7" stroke-width="2"/> <!-- hole at (1,1) -->
          
          <!-- Closed dot at (1, 0) -->
          <circle cx="160" cy="160" r="4.5" fill="#0c4a6e"/>
        </svg>`,
        options: [
          { label: "A", text: "0" },
          { label: "B", text: "1" },
          { label: "C", text: "3" },
          { label: "D", text: "The limit does not exist." }
        ],
        correctIndex: 3,
        explanation: "Inspect the one-sided limits as \\(x \\to 1\\):<br>" +
                     "• Left-hand limit: \\(\\lim_{x \\to 1^-} f(x) = 3\\).<br>" +
                     "• Right-hand limit: \\(\\lim_{x \\to 1^+} f(x) = 1\\).<br>" +
                     "Because the left-hand and right-hand limits are unequal (\\(3 \\ne 1\\)), \\(\\lim_{x \\to 1} f(x)\\) does not exist (Option D)[cite: 4]."
      },
      {
        id: 9,
        section: "Multiple Choice Review Q2",
        title: "Indeterminate Form 0/0 Limit",
        prompt: "\\(\\lim_{x \\to 0} \\frac{4x^2}{e^{4x} - 4x - 1}\\) is:[cite: 4]",
        options: [
          { label: "A", text: "0" },
          { label: "B", text: "1/2" },
          { label: "C", text: "8" },
          { label: "D", text: "nonexistent" }
        ],
        correctIndex: 1,
        explanation: "Evaluating directly gives \\(\\frac{0}{1 - 0 - 1} = \\frac{0}{0}\\). Applying L'Hôpital's Rule:<br>" +
                     "\\[\\lim_{x \\to 0} \\frac{8x}{4e^{4x} - 4}\\]<br>" +
                     "This is still \\(\\frac{0}{0}\\). Applying L'Hôpital's Rule a second time:<br>" +
                     "\\[\\lim_{x \\to 0} \\frac{8}{16e^{4x}} = \\frac{8}{16e^0} = \\frac{8}{16} = \\frac{1}{2} \\quad \\text{(Option B)} \\text{[cite: 4]}\\]"
      },
      {
        id: 10,
        section: "Multiple Choice Review Q3",
        title: "Finding Removable Discontinuities",
        prompt: "Let \\(f\\) be the function given by \\(f(x) = \\frac{2x^2 + 14x - 16}{x^2 - 9x + 8}\\)[cite: 4]. For what values of \\(x\\) does \\(f\\) have a removable discontinuity?[cite: 4]",
        options: [
          { label: "A", text: "1 only" },
          { label: "B", text: "8 only" },
          { label: "C", text: "-8 and 1" },
          { label: "D", text: "1 and 8" }
        ],
        correctIndex: 0,
        explanation: "Factor both the numerator and denominator:<br>" +
                     "\\[f(x) = \\frac{2(x^2 + 7x - 8)}{(x - 1)(x - 8)} = \\frac{2(x + 8)(x - 1)}{(x - 1)(x - 8)}\\]<br>" +
                     "• The factor \\((x - 1)\\) cancels out, meaning \\(\\lim_{x \\to 1} f(x) = \\frac{2(1 + 8)}{1 - 8} = -\\frac{18}{7}\\) exists. Thus, \\(x = 1\\) is a removable discontinuity[cite: 4].<br>" +
                     "• The factor \\((x - 8)\\) remains in the denominator, creating a vertical asymptote at \\(x = 8\\) (non-removable).<br>" +
                     "Therefore, \\(f\\) has a removable discontinuity at \\(x = 1\\) only (Option A)[cite: 4]."
      },
      {
        id: 11,
        section: "Multiple Choice Review Q4",
        title: "Vertical Asymptotes Count",
        prompt: "How many vertical asymptotes does the graph of \\(y = \\frac{x - 2}{x^4 - 16}\\) have?[cite: 4]",
        options: [
          { label: "A", text: "One" },
          { label: "B", text: "Two" },
          { label: "C", text: "Three" },
          { label: "D", text: "Four" }
        ],
        correctIndex: 0,
        explanation: "Factor the denominator completely:<br>" +
                     "\\[x^4 - 16 = (x^2 - 4)(x^2 + 4) = (x - 2)(x + 2)(x^2 + 4)\\]<br>" +
                     "Substituting into \\(y\\):<br>" +
                     "\\[y = \\frac{x - 2}{(x - 2)(x + 2)(x^2 + 4)} = \\frac{1}{(x + 2)(x^2 + 4)} \\quad (x \\ne 2)\\]<br>" +
                     "• At \\(x = 2\\), there is a hole (removable discontinuity), not a vertical asymptote.<br>" +
                     "• At \\(x = -2\\), the denominator is 0 while numerator is 1, creating a vertical asymptote.<br>" +
                     "• \\(x^2 + 4 = 0\\) has no real solutions.<br>" +
                     "Thus, there is exactly one vertical asymptote at \\(x = -2\\) (Option A)[cite: 4]."
      },
      {
        id: 12,
        section: "Multiple Choice Review Q5",
        title: "Exponential Limit as x -> -∞",
        prompt: "\\(\\lim_{x \\to -\\infty} \\frac{3 + 2^x}{4 - 5^x}\\) is:[cite: 4]",
        options: [
          { label: "A", text: "-2/5" },
          { label: "B", text: "0" },
          { label: "C", text: "3/4" },
          { label: "D", text: "nonexistent" }
        ],
        correctIndex: 2,
        explanation: "For base \\(a > 1\\), \\(\\lim_{x \\to -\\infty} a^x = 0\\).<br>" +
                     "Therefore, as \\(x \\to -\\infty\\), \\(2^x \\to 0\\) and \\(5^x \\to 0\\):<br>" +
                     "\\[\\lim_{x \\to -\\infty} \\frac{3 + 2^x}{4 - 5^x} = \\frac{3 + 0}{4 - 0} = \\frac{3}{4} \\quad \\text{(Option C)} \\text{[cite: 4]}\\]"
      },
      {
        id: 13,
        section: "Multiple Choice Review Q6",
        title: "Continuity Parameter Determination",
        prompt: "Let \\(f(x) = \\begin{cases} 6 + cx & \\text{for } x < 1 \\\\ 9 + 2\\ln x & \\text{for } x \\ge 1 \\end{cases}\\)[cite: 4]. If \\(f\\) is continuous at \\(x = 1\\), what is the value of \\(c\\)?[cite: 4]",
        options: [
          { label: "A", text: "2" },
          { label: "B", text: "3" },
          { label: "C", text: "5" },
          { label: "D", text: "9" }
        ],
        correctIndex: 1,
        explanation: "For \\(f\\) to be continuous at \\(x = 1\\), the left-hand limit, right-hand limit, and value \\(f(1)\\) must be equal:<br>" +
                     "• \\(\\lim_{x \\to 1^-} f(x) = 6 + c(1) = 6 + c\\)<br>" +
                     "• \\(f(1) = \\lim_{x \\to 1^+} f(x) = 9 + 2\\ln(1) = 9 + 2(0) = 9\\)<br>" +
                     "Equating: \\(6 + c = 9 \\implies c = 3\\) (Option B)[cite: 4]."
      },
      {
        id: 14,
        section: "Multiple Choice Review Q7",
        title: "Rational Limit with Radical at Infinity",
        prompt: "\\(\\lim_{x \\to \\infty} \\frac{\\sqrt{9x^4 + 1}}{4x^2 + 3}\\) is:[cite: 4]",
        options: [
          { label: "A", text: "1/3" },
          { label: "B", text: "3/4" },
          { label: "C", text: "3/2" },
          { label: "D", text: "9/4" },
          { label: "E", text: "infinite" }
        ],
        correctIndex: 1,
        explanation: "Divide both numerator and denominator by \\(x^2\\) (noting that \\(x^2 = \\sqrt{x^4}\\) for \\(x > 0\\)):<br>" +
                     "\\[\\lim_{x \\to \\infty} \\frac{\\frac{\\sqrt{9x^4 + 1}}{\\sqrt{x^4}}}{\\frac{4x^2 + 3}{x^2}} = \\lim_{x \\to \\infty} \\frac{\\sqrt{9 + \\frac{1}{x^4}}}{4 + \\frac{3}{x^2}} = \\frac{\\sqrt{9 + 0}}{4 + 0} = \\frac{3}{4} \\quad \\text{(Option B)} \\text{[cite: 4]}\\]"
      },
      {
        id: 15,
        section: "Multiple Choice Review Q8",
        title: "Dominant Rates of Growth at Infinity",
        prompt: "For which of the following pairs of functions \\(f\\) and \\(g\\) is \\(\\lim_{x \\to \\infty} \\frac{f(x)}{g(x)}\\) infinite?[cite: 4]",
        options: [
          { label: "A", text: "f(x) = x² + 2x and g(x) = x² + ln x" },
          { label: "B", text: "f(x) = 3x³ and g(x) = x⁴" },
          { label: "C", text: "f(x) = 3^x and g(x) = x³" },
          { label: "D", text: "f(x) = 3e^x + x³ and g(x) = 2e^x + x²" },
          { label: "E", text: "f(x) = ln(3x) and g(x) = ln(2x)" }
        ],
        correctIndex: 2,
        explanation: "Analyze each ratio as \\(x \\to \\infty\\):<br>" +
                     "• (A): \\(\\lim \\frac{x^2+2x}{x^2+\\ln x} = 1\\)[cite: 4]<br>" +
                     "• (B): \\(\\lim \\frac{3x^3}{x^4} = \\lim \\frac{3}{x} = 0\\)[cite: 4]<br>" +
                     "• (C): Exponential growth \\(3^x\\) dominates polynomial growth \\(x^3\\). By L'Hôpital's Rule applied 3 times, \\(\\lim_{x \\to \\infty} \\frac{3^x}{x^3} = \\infty\\) (Option C)[cite: 4].<br>" +
                     "• (D): \\(\\lim \\frac{3e^x + x^3}{2e^x + x^2} = \\frac{3}{2}\\)[cite: 4]<br>" +
                     "• (E): \\(\\lim \\frac{\\ln 3 + \\ln x}{\\ln 2 + \\ln x} = 1\\)[cite: 4]"
      },
      {
        id: 16,
        section: "Multiple Choice Review Q9",
        title: "Removable Factor Continuity",
        prompt: "Let \\(f(x) = \\begin{cases} \\frac{(2x+1)(x-2)}{x-2} & \\text{for } x \\ne 2 \\\\ k & \\text{for } x = 2 \\end{cases}\\)[cite: 4]. For what value of \\(k\\) is \\(f\\) continuous at \\(x = 2\\)?[cite: 4]",
        options: [
          { label: "A", text: "0" },
          { label: "B", text: "1" },
          { label: "C", text: "2" },
          { label: "D", text: "3" },
          { label: "E", text: "5" }
        ],
        correctIndex: 4,
        explanation: "For \\(x \\ne 2\\), \\(f(x) = 2x + 1\\).<br>" +
                     "The limit as \\(x \\to 2\\) is \\(\\lim_{x \\to 2} (2x + 1) = 2(2) + 1 = 5\\).<br>" +
                     "For continuity, we must have \\(f(2) = k = \\lim_{x \\to 2} f(x) = 5\\) (Option E)[cite: 4]."
      },
      {
        id: 17,
        section: "Multiple Choice Review Q10",
        title: "Cubic Rational Function Limit at Infinity",
        prompt: "\\(\\lim_{x \\to \\infty} \\frac{x^3 - 2x^2 + 3x - 4}{4x^3 - 3x^2 + 2x - 1} =\\)[cite: 4]",
        options: [
          { label: "A", text: "4" },
          { label: "B", text: "1" },
          { label: "C", text: "1/4" },
          { label: "D", text: "0" },
          { label: "E", text: "-1" }
        ],
        correctIndex: 2,
        explanation: "Divide both the numerator and denominator by the highest power \\(x^3\\):<br>" +
                     "\\[\\lim_{x \\to \\infty} \\frac{1 - \\frac{2}{x} + \\frac{3}{x^2} - \\frac{4}{x^3}}{4 - \\frac{3}{x} + \\frac{2}{x^2} - \\frac{1}{x^3}} = \\frac{1 - 0 + 0 - 0}{4 - 0 + 0 - 0} = \\frac{1}{4} \\quad \\text{(Option C)} \\text{[cite: 4]}\\]"
      }
    ];

    /* ==========================================================================
       PRACTICE ENGINE: 2 ATTEMPTS PER QUESTION WITH ACCUMULATED SCORECARD
       ========================================================================== */
    let currentStudentName = "Guest";
    let currentQuestionIndex = 0;
    
    // Per-question tracking
    let questionStates = CHAPTER_QUESTIONS.map(() => ({
      attempts: 0,
      selectedIndex: null,
      isResolved: false,
      isCorrect: false,
      status: "unseen" // 'unseen', 'active', 'completed', 'skipped'
    }));

    let audioMuted = false;
    let totalSeconds = 0;
    let timerInterval = null;

    const AudioEngine = {
      ctx: null,
      init() {
        if (!this.ctx) {
          this.ctx = new (window.AudioContext || window.webkitAudioContext)();
        }
      },
      playTone(freq, type, duration, delay = 0) {
        if (audioMuted || !this.ctx) return;
        setTimeout(() => {
          try {
            const osc = this.ctx.createOscillator();
            const gain = this.ctx.createGain();
            osc.type = type;
            osc.frequency.setValueAtTime(freq, this.ctx.currentTime);
            gain.gain.setValueAtTime(0.12, this.ctx.currentTime);
            gain.gain.exponentialRampToValueAtTime(0.0001, this.ctx.currentTime + duration);
            osc.connect(gain);
            gain.connect(this.ctx.destination);
            osc.start();
            osc.stop(this.ctx.currentTime + duration);
          } catch (e) {
            console.warn(e);
          }
        }, delay * 1000);
      },
      correct() {
        this.init();
        this.playTone(659.25, 'sine', 0.15, 0);
        this.playTone(880.00, 'sine', 0.25, 0.12);
      },
      incorrect() {
        this.init();
        this.playTone(196.00, 'triangle', 0.2, 0);
        this.playTone(146.83, 'triangle', 0.3, 0.12);
      },
      milestone() {
        this.init();
        [523.25, 659.25, 783.99, 1046.50].forEach((freq, idx) => {
          this.playTone(freq, 'sine', 0.22, idx * 0.09);
        });
      }
    };

    function startTimer() {
      if (timerInterval) clearInterval(timerInterval);
      timerInterval = setInterval(() => {
        totalSeconds++;
        const mins = String(Math.floor(totalSeconds / 60)).padStart(2, '0');
        const secs = String(totalSeconds % 60).padStart(2, '0');
        document.getElementById('timerChip').innerText = `⏱️ ${mins}:${secs}`;
      }, 1000);
    }

    function showToast(msg) {
      const t = document.getElementById('toastMessage');
      t.innerText = msg;
      t.style.display = 'block';
      setTimeout(() => { t.style.display = 'none'; }, 2800);
    }

    function initDirectLogin() {
      const name = document.getElementById('studentNameInput').value.trim() || 'Student';
      currentStudentName = name;
      sessionStorage.setItem('bm_apcalc_student', name);
      document.getElementById('userPill').innerHTML = `<strong>Student: ${name}</strong>`;
      document.getElementById('reportStudentBadge').innerHTML = `<strong>Student: ${name}</strong>`;
      document.getElementById('loginGateView').style.display = 'none';
      AudioEngine.init();
      startTimer();
      renderPalette();
      loadQuestion(0);
      renderSolutions();
    }

    function switchView(viewId) {
      document.querySelectorAll('.view').forEach(v => v.classList.remove('active'));
      document.querySelectorAll('nav button').forEach(b => b.classList.remove('active'));
      document.getElementById(viewId).classList.add('active');

      if (viewId === 'practiceView') document.getElementById('tabPracticeBtn').classList.add('active');
      if (viewId === 'theoryView') document.getElementById('tabTheoryBtn').classList.add('active');
      if (viewId === 'resultsView') {
        document.getElementById('tabResultsBtn').classList.add('active');
        renderSolutions();
      }

      if (window.MathJax && window.MathJax.typesetPromise) {
        MathJax.typesetPromise();
      }
    }

    function renderPalette() {
      const grid = document.getElementById('paletteGrid');
      grid.innerHTML = '';

      let solvedCount = 0;
      CHAPTER_QUESTIONS.forEach((q, idx) => {
        const state = questionStates[idx];
        if (state.isResolved) solvedCount++;

        const btn = document.createElement('button');
        let stateClass = '';
        if (idx === currentQuestionIndex) {
          stateClass = 'active';
        } else if (state.isResolved) {
          stateClass = 'completed';
        } else if (state.status === 'skipped') {
          stateClass = 'skipped';
        }

        btn.className = `palette-btn ${stateClass}`;
        btn.innerText = q.id;
        btn.title = `Problem ${q.id}: ${q.title}`;
        btn.onclick = () => loadQuestion(idx);
        grid.appendChild(btn);
      });

      document.getElementById('paletteCount').innerText = `${solvedCount} / ${CHAPTER_QUESTIONS.length} Completed`;
    }

    function loadQuestion(idx) {
      currentQuestionIndex = idx;
      renderPalette();
      const q = CHAPTER_QUESTIONS[idx];
      const state = questionStates[idx];
      const card = document.getElementById('activeQuestionCard');

      let optionsHtml = '';
      q.options.forEach((opt, optIdx) => {
        let optClass = '';
        if (state.isResolved) {
          if (optIdx === q.correctIndex) {
            optClass = 'selected-correct';
          } else if (state.selectedIndex === optIdx) {
            optClass = 'selected-wrong';
          }
        }

        optionsHtml += `
          <button class="mcq-option-btn ${optClass}" 
            onclick="handleOptionSelect(${idx}, ${optIdx})"
            ${state.isResolved ? 'disabled' : ''}>
            <span class="opt-letter">${opt.label}</span>
            <span>${opt.text}</span>
          </button>
        `;
      });

      let feedbackHtml = '';
      if (state.isResolved) {
        feedbackHtml = `
          <div class="feedback-box ${state.isCorrect ? 'correct' : 'incorrect'}">
            <strong>${state.isCorrect ? '✓ Correct!' : '✗ Solution Revealed'}</strong> (Correct Answer: Option ${q.options[q.correctIndex].label})<br/>
            <div style="margin-top: 8px;">${q.explanation}</div>
          </div>
        `;
      }

      const prevDisabled = idx === 0 ? 'disabled' : '';
      const nextDisabled = idx === CHAPTER_QUESTIONS.length - 1 ? 'disabled' : '';

      card.innerHTML = `
        <span class="concept-tag">${q.section}</span>
        <h2 style="color:var(--navy-dark); margin: 6px 0 10px 0;">Problem ${q.id}: ${q.title}</h2>
        <div style="margin-top: 8px; line-height: 1.65; font-size:1.02rem;">${q.prompt}</div>
        ${q.svg ? `<div class="svg-container">${q.svg}</div>` : ''}
        <div class="mcq-container">${optionsHtml}</div>
        
        <div style="display:flex; align-items:center; margin-top:12px;">
          <span class="attempts-badge">Attempts: ${state.attempts}/2</span>
          ${!state.isResolved && state.attempts >= 2 ? `
            <button class="btn-reveal" onclick="revealSolution(${idx})">Reveal Solution</button>
          ` : ''}
        </div>

        ${feedbackHtml}

        <div class="nav-toolbar">
          <button class="btn-nav-action" onclick="navigateQuestion(-1)" ${prevDisabled}>
            ⏮ Previous
          </button>
          <div class="nav-btn-group">
            <button class="btn-nav-action btn-skip" onclick="skipQuestion()">
              ⏭ Skip Question
            </button>
            <button class="btn-nav-action" onclick="navigateQuestion(1)" ${nextDisabled}>
              Next ❯
            </button>
          </div>
        </div>
      `;

      if (window.MathJax && window.MathJax.typesetPromise) {
        MathJax.typesetPromise();
      }
    }

    function handleOptionSelect(qIdx, optIdx) {
      const q = CHAPTER_QUESTIONS[qIdx];
      const state = questionStates[qIdx];
      if (state.isResolved) return;

      state.selectedIndex = optIdx;
      state.attempts++;

      if (optIdx === q.correctIndex) {
        state.isResolved = true;
        state.isCorrect = true;
        state.status = 'completed';
        AudioEngine.correct();
        showToast("Correct! Answer registered.");
      } else {
        AudioEngine.incorrect();
        if (state.attempts >= 2) {
          showToast("2 attempts reached. You may retry or click 'Reveal Solution'.");
        } else {
          showToast("Incorrect option. You have 1 attempt remaining!");
        }
      }

      renderPalette();
      loadQuestion(qIdx);
      renderSolutions();
    }

    function revealSolution(qIdx) {
      const state = questionStates[qIdx];
      state.isResolved = true;
      state.status = 'completed';
      AudioEngine.incorrect();
      showToast("Solution revealed.");
      renderPalette();
      loadQuestion(qIdx);
      renderSolutions();
    }

    function navigateQuestion(delta) {
      const target = currentQuestionIndex + delta;
      if (target >= 0 && target < CHAPTER_QUESTIONS.length) {
        loadQuestion(target);
      }
    }

    function skipQuestion() {
      const state = questionStates[currentQuestionIndex];
      if (!state.isResolved) {
        state.status = 'skipped';
      }
      showToast(`Problem ${currentQuestionIndex + 1} marked as skipped.`);
      renderPalette();
      navigateQuestion(1);
    }

    function renderSolutions() {
      const container = document.getElementById('completeSolutionsContainer');
      let score = 0;

      CHAPTER_QUESTIONS.forEach((q, idx) => {
        if (questionStates[idx].isCorrect) score++;
      });

      const totalQuestions = CHAPTER_QUESTIONS.length;
      const percentage = Math.round((score / totalQuestions) * 100);

      document.getElementById('scoreValue').innerText = `${score} / ${totalQuestions}`;
      document.getElementById('progressBarFill').style.width = `${percentage}%`;
      document.getElementById('reportStudentBadge').innerHTML = `<strong>Student: ${currentStudentName}</strong> (${percentage}% Score)`;

      let html = '';
      CHAPTER_QUESTIONS.forEach((q, idx) => {
        const state = questionStates[idx];
        let statusBadge = `<span style="color:var(--text-muted); font-weight:bold;">Unattempted</span>`;

        if (state.isResolved) {
          statusBadge = state.isCorrect
            ? `<span style="color:var(--green-ok); font-weight:bold;">✓ Correct (1/1)</span>`
            : `<span style="color:var(--red-fail); font-weight:bold;">✗ Incorrect / Revealed (0/1)</span>`;
        }

        const studentChoiceLabel = (state.selectedIndex !== null && q.options[state.selectedIndex])
          ? `[${q.options[state.selectedIndex].label}] ${q.options[state.selectedIndex].text}`
          : 'None';

        html += `
          <div class="theory-card">
            <div style="display:flex; justify-content:space-between; align-items:center;">
              <span class="concept-tag">${q.section}</span>
              ${statusBadge}
            </div>
            <h3 style="margin-top:6px;">Problem ${q.id}: ${q.title}</h3>
            <div style="margin: 8px 0; font-size:0.95rem;">${q.prompt}</div>
            ${q.svg ? `<div class="svg-container" style="max-width:320px; margin:12px 0;">${q.svg}</div>` : ''}
            
            <div style="background:#f8fafc; border-left:4px solid var(--brand-blue); padding:14px; margin-top:12px; border-radius:0 6px 6px 0;">
              <strong>Correct Option:</strong> [${q.options[q.correctIndex].label}] ${q.options[q.correctIndex].text}<br/>
              <strong>Your Selection:</strong> ${studentChoiceLabel}<br/>
              <div style="margin-top:8px;"><strong>Full Worked Derivation:</strong><br/>${q.explanation}</div>
            </div>
          </div>
        `;
      });

      container.innerHTML = html;
      if (window.MathJax && window.MathJax.typesetPromise) {
        MathJax.typesetPromise();
      }
    }

    document.getElementById('audioToggleBtn').onclick = () => {
      audioMuted = !audioMuted;
      document.getElementById('audioToggleBtn').innerText = audioMuted ? '🔇' : '🔊';
    };
  </script>
</body>
</html>
