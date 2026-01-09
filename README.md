<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <meta name="description" content="Adam's simple personal web page — ideas, projects, and goals." />
  <title>Adam — Personal Page</title>
  <style>
    :root{
      --bg:#f4f6f8;
      --header:#2c3e50;
      --nav:#34495e;
      --card:#ffffff;
      --accent:#1abc9c;
      --text:#222;
      --muted:#6b7280;
      --radius:10px;
      --max-width:960px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      font-family:Inter, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      margin:0;
      color:var(--text);
      background:var(--bg);
      line-height:1.5;
      -webkit-font-smoothing:antialiased;
    }

    a{color:var(--accent); text-decoration:none}
    a:focus{outline:3px solid rgba(26,188,156,0.18); outline-offset:3px}

    /* Skip link */
    .skip-link {
      position: absolute;
      left: -999px;
      top: auto;
      width: 1px;
      height: 1px;
      overflow: hidden;
    }
    .skip-link:focus {
      left: 1rem;
      top: 1rem;
      width: auto;
      height: auto;
      padding: .5rem .75rem;
      background:#000;
      color:#fff;
      z-index:999;
      border-radius:6px;
    }

    header{
      background:var(--header);
      color:#fff;
      padding:1.25rem 1rem;
    }
    .header-inner{
      max-width:var(--max-width);
      margin:0 auto;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:1rem;
    }
    h1{font-size:1.25rem; margin:0}
    p.lead{margin:0; color:var(--muted)}

    nav{
      background:var(--nav);
      color:#fff;
    }
    .nav-inner{
      max-width:var(--max-width);
      margin:0 auto;
      padding:.5rem 1rem;
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:1rem;
    }
    .nav-links{
      display:flex;
      gap:.75rem;
      align-items:center;
    }
    .nav-links a{
      color:white;
      padding:.35rem .5rem;
      border-radius:6px;
      font-weight:600;
    }
    .nav-toggle{
      display:none;
      background:transparent;
      border:1px solid rgba(255,255,255,0.12);
      color:#fff;
      padding:.4rem .6rem;
      border-radius:6px;
    }

    main{
      max-width:var(--max-width);
      margin:1.25rem auto;
      padding:0 1rem 3rem;
    }
    .grid{
      display:grid;
      gap:1rem;
      grid-template-columns:repeat(auto-fit, minmax(240px, 1fr));
    }
    .card{
      background:var(--card);
      padding:1rem;
      border-radius:var(--radius);
      box-shadow: 0 6px 18px rgba(28,41,54,0.06);
    }
    .card h2{margin-top:0}
    ul{margin:0.5rem 0 0 1.25rem}

    footer{
      margin-top:2rem;
      padding:1rem;
      background:var(--header);
      color:#fff;
      text-align:center;
    }

    @media (max-width:720px){
      .nav-links{display:none}
      .nav-toggle{display:inline-block}
    }
  </style>
</head>
<body>
  <a class="skip-link" href="#main">Skip to content</a>

  <header role="banner">
    <div class="header-inner">
      <div>
        <h1>Adam</h1>
        <p class="lead">This is the beginning of my coding awakening</p>
      </div>
      <div aria-hidden="true" style="font-size:.9rem; color:rgba(255,255,255,0.85)">Welcome 👋</div>
    </div>
  </header>

  <nav role="navigation" aria-label="Primary navigation">
    <div class="nav-inner">
      <div style="font-weight:700;color:#fff">Menu</div>
      <div class="nav-links" id="navLinks">
        <a href="#" aria-current="page">Home</a>
        <a href="#about">About</a>
        <a href="#contact">Contact</a>
      </div>
      <button class="nav-toggle" id="navToggle" aria-expanded="false" aria-controls="navLinks">☰ Menu</button>
    </div>
  </nav>

  <main id="main" role="main">
    <section id="about" class="card" aria-labelledby="about-heading">
      <h2 id="about-heading">About My Page</h2>
      <p>Hi — this is a simple HTML page where I'm starting to learn web development. It's a great place to list ideas, projects, and goals.</p>
    </section>

    <section aria-labelledby="goals-heading" style="margin-top:1rem">
      <div class="grid">
        <div class="card" id="goals">
          <h2 id="goals-heading">Things I want to do</h2>
          <ul>
            <li>Make my website popular</li>
            <li>Make games</li>
            <li>Make a lot of cash</li>
          </ul>
        </div>

        <div class="card" aria-labelledby="todo-heading">
          <h2 id="todo-heading">Next steps</h2>
          <ul>
            <li>Share progress on social media</li>
            <li>Learn JavaScript and build interactive demos</li>
            <li>Start a small game project (prototype)</li>
          </ul>
        </div>
      </div>
    </section>
  </main>

  <footer role="contentinfo">
    <div style="max-width:var(--max-width); margin:0 auto; padding:0 1rem;">
      <p style="margin:.25rem 0">© 2026 Adam — Built with curiosity</p>
      <p style="margin:.25rem 0; color:var(--muted) font-size:.9rem">Made for learning. Want this live? Ask me to deploy it.</p>
    </div>
  </footer>

  <script>
    // Simple nav toggle for small screens
    (function(){
      var btn = document.getElementById('navToggle');
      var links = document.getElementById('navLinks');
      if(!btn || !links) return;
      btn.addEventListener('click', function(){
        var expanded = this.getAttribute('aria-expanded') === 'true';
        this.setAttribute('aria-expanded', String(!expanded));
        if(!expanded){
          links.style.display = 'flex';
          links.style.flexDirection = 'column';
          links.style.gap = '.5rem';
          links.style.alignItems = 'flex-start';
          links.style.marginTop = '.5rem';
        } else {
          links.style.display = '';
        }
      });
    })();
  </script>
</body>
</html>
