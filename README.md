[lap 1.html](https://github.com/user-attachments/files/22980135/lap.1.html)
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Mohammad Alslehat — Welcome</title>

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;600;800&family=Playfair+Display:wght@600;700&display=swap" rel="stylesheet">

  <style>
    /* =========================
       Variables & base setup
       ========================= */
    :root{
      --bg-1: #0f3b2f; /* dark green */
      --bg-2: #1fa67a; /* bright green */
      --accent: #e9ffe8; /* pale highlight */
      --card: rgba(255,255,255,0.06);
      --glass: rgba(255,255,255,0.07);
      --glass-2: rgba(255,255,255,0.04);
      --muted: rgba(255,255,255,0.75);
      --glass-border: rgba(255,255,255,0.09);
      --shadow: 0 10px 30px rgba(7,18,13,0.45);
      --radius: 14px;
      --max-width: 1100px;
      --glass-blur: 8px;
    }

    *{box-sizing:border-box}
    html,body{
      height:100%;
      margin:0;
      font-family: 'Inter', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      background: linear-gradient(135deg,var(--bg-1) 0%, #0f563d 25%, var(--bg-2) 100%);
      color: #fff;
      line-height:1.4;
    }

    /* Centering wrapper */
    .wrap{
      min-height:100vh;
      display:flex;
      align-items:center;
      justify-content:center;
      padding:4rem 1.5rem;
    }

    /* Main card */
    .card {
      width:100%;
      max-width:var(--max-width);
      background: linear-gradient(180deg, rgba(255,255,255,0.03), rgba(255,255,255,0.02));
      border-radius: 20px;
      padding: 2rem;
      box-shadow: var(--shadow);
      border: 1px solid var(--glass-border);
      position:relative;
      overflow:hidden;
      backdrop-filter: blur(var(--glass-blur));
    }

    /* decorative animated blobs */
    .blob {
      position:absolute;
      filter: blur(50px);
      opacity:0.9;
      transform: translateZ(0);
      mix-blend-mode: screen;
      pointer-events:none;
    }
    .blob.one{
      width:420px;height:420px;
      background: radial-gradient(circle at 30% 30%, rgba(255,255,255,0.08), rgba(255,255,255,0) 40%), linear-gradient(45deg, rgba(70,255,180,0.18), rgba(10,120,80,0.25));
      left:-10%;
      top:-10%;
      animation: floatA 12s ease-in-out infinite;
    }
    .blob.two{
      width:320px;height:320px;
      background: linear-gradient(135deg, rgba(20,160,100,0.20), rgba(140,255,200,0.10));
      right:-8%;
      bottom:-6%;
      animation: floatB 14s ease-in-out infinite;
    }
    @keyframes floatA{
      0%{ transform: translateY(0) rotate(0deg) }
      50%{ transform: translateY(18px) rotate(8deg) }
      100%{ transform: translateY(0) rotate(0deg) }
    }
    @keyframes floatB{
      0%{ transform: translateY(0) rotate(0deg) scale(1) }
      50%{ transform: translateY(-22px) rotate(-6deg) scale(1.03) }
      100%{ transform: translateY(0) rotate(0deg) scale(1) }
    }

    /* Layout grid */
    .grid {
      display:grid;
      grid-template-columns: 1fr 420px;
      gap:2rem;
      align-items:stretch;
    }

    @media (max-width:980px){
      .grid{ grid-template-columns: 1fr; }
    }

    /* Left: hero content */
    .hero{
      padding:1rem 1.2rem;
      display:flex;
      flex-direction:column;
      gap:1.2rem;
    }

    .kicker{
      display:inline-block;
      background: linear-gradient(90deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
      padding:6px 10px;
      border-radius: 999px;
      font-weight:600;
      letter-spacing:0.6px;
      font-size:13px;
      color:var(--accent);
      border:1px solid rgba(255,255,255,0.04);
      width:fit-content;
    }

    /* Name with subtle shimmer */
    .title {
      font-family: 'Playfair Display', serif;
      font-size: clamp(28px, 5vw, 52px);
      margin:0;
      line-height:0.95;
      letter-spacing:-0.02em;
      background: linear-gradient(90deg, #eafff2 0%, #c4ffe0 30%, rgba(255,255,255,0.6) 55%, #a7ffd9 100%);
      -webkit-background-clip: text;
      background-clip: text;
      color: transparent;
      position:relative;
      display:inline-block;
      padding-right:6px;
      padding-left:2px;
      animation: shimmer 4s linear infinite;
      background-size:200% 100%;
    }
    @keyframes shimmer{
      0%{ background-position: 0% 0% }
      50%{ background-position: 100% 0% }
      100%{ background-position: 0% 0% }
    }

    .subtitle{
      font-size:18px;
      color:var(--muted);
      margin:0.2rem 0 0;
      max-width:64ch;
    }

    /* Action buttons */
    .actions{
      margin-top:1rem;
      display:flex;
      gap:0.8rem;
      flex-wrap:wrap;
    }

    .btn{
      appearance:none;
      border:0;
      padding:10px 16px;
      border-radius: 12px;
      font-weight:600;
      cursor:pointer;
      transition: transform .18s cubic-bezier(.2,.9,.2,1), box-shadow .18s;
      box-shadow: 0 6px 18px rgba(7,18,13,0.25);
      background: linear-gradient(90deg, rgba(255,255,255,0.06), rgba(255,255,255,0.03));
      color:var(--accent);
      border:1px solid rgba(255,255,255,0.05);
      backdrop-filter: blur(6px);
    }
    .btn:active{ transform: translateY(2px) }
    .btn.primary{
      background: linear-gradient(90deg, rgba(255,255,255,0.08), rgba(255,255,255,0.03));
      box-shadow: 0 10px 30px rgba(26,120,80,0.25);
      color: #053425;
      /* subtle green glow */
      outline: 3px solid rgba(30,220,140,0.06);
    }
    .btn.ghost{
      background: transparent;
      border: 1px solid rgba(255,255,255,0.08);
      color: var(--accent);
    }
    .btn:hover{ transform: translateY(-6px) scale(1.01) }

    /* Right: profile panel */
    .panel{
      padding:1.2rem;
      border-radius: 14px;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.03);
      display:flex;
      flex-direction:column;
      gap:1rem;
      align-items:center;
      text-align:center;
      position:relative;
    }

    .avatar{
      width:140px;
      height:140px;
      border-radius: 50%;
      background: linear-gradient(135deg, rgba(255,255,255,0.06), rgba(255,255,255,0.02));
      display:flex;
      align-items:center;
      justify-content:center;
      font-weight:700;
      font-size:28px;
      color:var(--accent);
      border: 4px solid rgba(255,255,255,0.04);
      box-shadow: 0 10px 40px rgba(7,18,13,0.45);
      transition: transform .5s cubic-bezier(.2,.9,.2,1);
    }
    .avatar:hover{ transform: rotate(-6deg) scale(1.02) }

    .meta{
      font-size:14px;
      color:var(--muted);
    }

    .stats{
      width:100%;
      display:flex;
      gap:0.7rem;
      justify-content:space-between;
      margin-top:0.6rem;
    }
    .stat{
      flex:1;
      background: linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      padding:10px;
      border-radius:10px;
      border:1px solid rgba(255,255,255,0.03);
      font-weight:600;
    }
    .stat small{ display:block; font-size:12px; font-weight:400; color:var(--muted) }

    /* Sections: about, skills, projects */
    .sections{
      margin-top:1.4rem;
      display:grid;
      gap:1rem;
    }

    .section{
      background: var(--card);
      padding:1rem;
      border-radius:12px;
      border:1px solid rgba(255,255,255,0.03);
    }

    .section h3{
      margin:0 0 0.6rem 0;
      font-size:16px;
      color:var(--accent);
    }

    .skills{
      display:flex;
      gap:0.6rem;
      flex-wrap:wrap;
    }
    .chip{
      padding:6px 10px;
      border-radius:999px;
      background: linear-gradient(90deg, rgba(255,255,255,0.03), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.03);
      font-weight:600;
      font-size:13px;
    }

    .projects{
      display:grid;
      grid-template-columns: repeat(2, 1fr);
      gap:0.8rem;
    }
    @media (max-width:640px){ .projects{ grid-template-columns: 1fr } }

    .proj{
      padding:0.8rem;
      border-radius:10px;
      background: linear-gradient(180deg, rgba(255,255,255,0.015), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.03);
      transition: transform .28s cubic-bezier(.2,.9,.2,1), box-shadow .28s;
    }
    .proj:hover{
      transform: translateY(-8px) scale(1.01) rotate(-0.4deg);
      box-shadow: 0 18px 40px rgba(7,18,13,0.35);
    }
    .proj h4{ margin:0 0 0.3rem 0; }
    .proj p{ margin:0; font-size:13px; color:var(--muted) }

    /* footer */
    .footer{
      margin-top:1.6rem;
      display:flex;
      justify-content:space-between;
      align-items:center;
      gap:1rem;
      flex-wrap:wrap;
    }
    .socials{
      display:flex;
      gap:0.6rem;
    }
    .pill{
      padding:8px 10px;
      border-radius:8px;
      background: linear-gradient(90deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));
      border:1px solid rgba(255,255,255,0.03);
      font-weight:600;
      font-size:13px;
    }

    /* tiny sparkle animation for headings */
    .sparkle{
      display:inline-block;
      position:relative;
      overflow:visible;
    }
    .sparkle::after{
      content:"";
      position:absolute;
      right:-14px;
      top:-6px;
      width:10px;
      height:10px;
      background: radial-gradient(circle at 30% 30%, #fff, rgba(255,255,255,0.2) 60%, rgba(255,255,255,0) 70%);
      transform: rotate(15deg) scale(1);
      opacity:0.9;
      filter: blur(1px);
      animation: twinkle 3s linear infinite;
    }
    @keyframes twinkle{
      0%{ transform: scale(.6) translateY(0); opacity:0.6 }
      50%{ transform: scale(1.05) translateY(-6px); opacity:1 }
      100%{ transform: scale(.6) translateY(0); opacity:0.6 }
    }

    /* small responsive tweaks */
    @media (max-width:480px){
      .card{ padding:1.2rem }
      .avatar{ width:110px; height:110px; font-size:22px }
    }

  </style>
</head>
<body>
  <div class="wrap">
    <div class="card" role="main" aria-label="Welcome card">

      <!-- decorative blobs -->
      <div class="blob one" aria-hidden="true"></div>
      <div class="blob two" aria-hidden="true"></div>

      <div class="grid">
        <!-- LEFT: HERO -->
        <div class="hero">
          <span class="kicker">Welcome — Portfolio Demo</span>

          <h1 class="title sparkle">Mohammad Alslehat</h1>

          <p class="subtitle">
            Hi — I'm <strong>Mohammad Alslehat</strong>, a curious maker exploring elegant interfaces, clean
            interactions, and color-driven design. This is a small experimental welcome page (HTML + CSS).
          </p>

          <div class="actions" aria-hidden="false">
            <button class="btn primary" aria-label="Contact Mohammad">Contact Me</button>
            <button class="btn ghost" aria-label="Download resume">Download Resume</button>
            <button class="btn" aria-label="View projects">View Projects</button>
          </div>

          <!-- quick intro boxes -->
          <div style="display:flex; gap:0.8rem; margin-top:1rem; flex-wrap:wrap;">
            <div class="pill">Location: Amman, Jordan</div>
            <div class="pill">Available for freelance</div>
          </div>

          <!-- about & skills -->
          <div class="sections" aria-hidden="false">
            <div class="section" id="about">
              <h3>About</h3>
              <p style="margin:0; color:var(--muted)">
                I build small interactive prototypes and explore colorful visual systems. I enjoy turning
                complex ideas into simple, approachable interfaces.
              </p>
            </div>

            <div class="section" id="skills">
              <h3>Skills</h3>
              <div class="skills" aria-hidden="true">
                <span class="chip">UI Design</span>
                <span class="chip">HTML & CSS</span>
                <span class="chip">Prototyping</span>
                <span class="chip">Color Systems</span>
                <span class="chip">Accessibility</span>
              </div>
            </div>

            <div class="section" id="projects">
              <h3>Selected Projects</h3>
              <div class="projects">
                <div class="proj">
                  <h4>Color Playground</h4>
                  <p>A tiny system to generate and test gradients and palettes.</p>
                </div>
                <div class="proj">
                  <h4>Micro-Portfolio</h4>
                  <p>A minimal portfolio template focused on typography and rhythm.</p>
                </div>
                <div class="proj">
                  <h4>Animation Lab</h4>
                  <p>Collection of small CSS-only experiments and transitions.</p>
                </div>
                <div class="proj">
                  <h4>Responsive Card Kit</h4>
                  <p>Set of modular card patterns for dashboards and landing pages.</p>
                </div>
              </div>
            </div>

          </div><!-- /.sections -->
        </div><!-- /.hero -->

        <!-- RIGHT: PROFILE PANEL -->
        <aside class="panel" aria-label="Profile panel">
<div class="avatar" aria-hidden="true">MA</div>
          <div style="text-align:center;">
            <div style="font-weight:700; font-size:18px">Mohammad Alslehat</div>
            <div class="meta">Frontend & Visual Designer</div>
          </div>

          <div class="stats" role="list">
            <div class="stat" role="listitem">
              6+ <small>Projects</small>
            </div>
            <div class="stat" role="listitem">
              3+ <small>Years</small>
            </div>
            <div class="stat" role="listitem">
              Available <small>Now</small>
            </div>
          </div>

          <div style="width:100%;" aria-hidden="false">
            <div class="section" style="margin-top:0.8rem;">
              <h3>Contact</h3>
              <p style="margin:0 0 0.6rem 0; color:var(--muted)">Say hi — this demo uses placeholder buttons. Replace with your email or links.</p>

              <!-- faux contact form (non-functional, HTML-only) -->
              <form style="display:flex; flex-direction:column; gap:0.5rem;">
                <input type="text" aria-label="Name" placeholder="Your name" style="padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--accent); outline:none;">
                <input type="email" aria-label="Email" placeholder="Your email" style="padding:10px;border-radius:8px;border:1px solid rgba(255,255,255,0.04);background:transparent;color:var(--accent); outline:none;">
                <button class="btn primary" type="button" style="width:100%;">Say Hello</button>
              </form>
            </div>
          </div>

          <div class="footer" aria-hidden="false">
            <div style="font-size:13px; color:var(--muted)">© <strong>Mohammad Alslehat</strong></div>
            <div class="socials" role="navigation" aria-label="social links">
              <div class="pill">Twitter</div>
              <div class="pill">Dribbble</div>
              <div class="pill">GitHub</div>
            </div>
          </div>
        </aside><!-- /.panel -->
      </div><!-- /.grid -->

    </div><!-- /.card -->
  </div><!-- /.wrap -->
</body>
</html>
