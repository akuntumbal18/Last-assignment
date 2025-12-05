<!doctype html>
<html lang="id">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>Davin Marciano E — Web Profile Preview</title>
  <meta name="description" content="Personal profile preview for Davin Marciano E." />
  <style>
    :root{
      /* All font colors set to #161d39 per request */
      --font-color: #161d39;
      --bg:#f6f7fb;
      --card: rgba(255,255,255,0.04);
      --accent1:#6C5CE7;
      --accent2:#00BFA6;
      --glass: rgba(255,255,255,0.03);
      --content-z: 1;
    }

    *{box-sizing:border-box}
    html,body{height:100%}
    html { scroll-behavior: smooth; } /* smooth scroll for anchor links */

    body{
      margin:0;
      font-family:Inter, ui-sans-serif, system-ui, -apple-system, "Segoe UI", Roboto, "Helvetica Neue", Arial;
      color:var(--font-color); /* global font color */
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      line-height:1.45;
      background-color: var(--bg); /* fallback */
      position:relative;
      z-index:var(--content-z);
      min-height:100vh;
    }
    body::before{
      content: "";
      position: fixed;
      inset: 0;
      z-index: -1;
      pointer-events: none;
      /* soft gradient background */
      background-image:
        radial-gradient(600px 300px at 85% 10%, rgba(255,173,110,0.14), transparent 30%),
        radial-gradient(700px 420px at 20% 85%, rgba(86,156,255,0.12), transparent 30%),
        linear-gradient(120deg, rgba(255,243,236,1) 0%, rgba(245,250,255,1) 30%, rgba(242,235,255,1) 60%, rgba(255,250,242,1) 100%);
      background-repeat: no-repeat;
      background-size: cover;
      background-position: center;
      filter: blur(8px) brightness(0.95);
      transform: scale(1.02);
    }

    .container{max-width:1000px;margin:0 auto;padding:24px;position:relative;z-index:var(--content-z)}
    .site-header{
      background: linear-gradient(90deg, rgba(255,255,255,0.30), rgba(255,255,255,0.18));
      border-bottom:1px solid rgba(255,255,255,0.06);
      position:sticky;top:0;z-index:30;
      transition: background-color .22s ease, backdrop-filter .22s ease, -webkit-backdrop-filter .22s ease, box-shadow .22s ease, transform .22s ease;
      will-change: transform, box-shadow;
      backdrop-filter: none;
    }
    .site-header.scrolled{
      backdrop-filter: blur(6px) saturate(1.02);
      -webkit-backdrop-filter: blur(6px) saturate(1.02);
      background: rgba(255,255,255,0.08);
      box-shadow: 0 8px 30px rgba(2,6,23,0.06);
      border-bottom-color: rgba(0,0,0,0.06);
      transform: translateZ(0);
    }

    .header-inner{display:flex;align-items:center;justify-content:space-between}
    .brand{display:flex;gap:14px;align-items:center}
    .avatar {width:64px;height:64px;border-radius:50%;overflow:hidden;flex:0 0 64px;display:block;border:1px solid rgba(0,0,0,0.06);background:#fff}
    /* PROFILE IMAGE now uses the external link provided */
    .avatar img{
      width:100%;
      height:100%;
      object-fit:cover;
      object-position:center;
      display:block;
      filter: brightness(0.55) contrast(0.95);
      transition: filter .25s ease;
    }
    .avatar:hover img{ filter: brightness(0.75) contrast(0.95); }

    h1{font-size:18px;margin:0;color:var(--font-color)}
    .muted{color:var(--font-color);margin:6px 0 0;font-size:14px}
    .nav a{color:var(--font-color);text-decoration:none;margin:0 8px;font-size:14px}
    .nav{display:flex;align-items:center;gap:8px}
    #themeToggle{background:transparent;border:0;color:var(--font-color);cursor:pointer;font-size:18px;padding:6px;border-radius:6px}

    a, a:visited, button, .btn, .btn.ghost, .link-as-button, .blog-item a, .socials a {
      color: var(--font-color) !important;
    }

    .card{background:linear-gradient(180deg, rgba(255,255,255,0.60), rgba(255,255,255,0.50));padding:22px;border-radius:12px;margin:20px 0;border:1px solid rgba(0,0,0,0.04);box-shadow: 0 4px 14px rgba(12,18,28,0.04)}
    .hero{display:grid;grid-template-columns:1fr 320px;gap:20px;align-items:center}
    .hero-left h2{margin:0;font-size:28px;color:var(--font-color)}
    .lead{color:var(--font-color);margin:12px 0 18px}
    .btn{background:linear-gradient(90deg,var(--accent1),var(--accent2));color:var(--font-color);padding:10px 14px;border-radius:8px;text-decoration:none;border:0;cursor:pointer}
    .btn.ghost{background:transparent;border:1px solid rgba(0,0,0,0.06);color:var(--font-color)}
    .contact-card{background:rgba(255,255,255,0.66);padding:14px;border-radius:10px}
    .chips{list-style:none;padding:0;display:flex;flex-wrap:wrap;gap:8px;margin:12px 0}
    .chips li{background:rgba(255,255,255,0.72);padding:8px 12px;border-radius:999px;font-size:13px;color:var(--font-color)}
    .link-as-button{background:transparent;border:0;color:var(--font-color);cursor:pointer;padding:0;font:inherit}
    .form-actions{display:flex;gap:10px;margin-top:12px;align-items:center}
    input,textarea{width:100%;padding:10px;border-radius:8px;border:1px solid rgba(0,0,0,0.06);background:transparent;color:var(--font-color);margin-top:6px}
    label{display:block;margin-top:12px;font-size:14px;color:var(--font-color)}
    .site-footer{padding:18px 0;color:var(--font-color);font-size:14px;text-align:center}
    @media (max-width:880px){
      .hero{grid-template-columns:1fr;gap:10px}
      .avatar{width:56px;height:56px}
      .nav{gap:6px}
    }

    .quick-sections{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
    .quick-link{padding:12px 16px;background:linear-gradient(90deg,var(--accent1),var(--accent2));color:var(--font-color);border-radius:10px;text-decoration:none;font-weight:600;cursor:pointer;border:0}
    .section-title{margin:0 0 10px;font-size:18px;color:var(--font-color)}
    section{scroll-margin-top:90px}

    .art-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:12px;margin-top:12px}
    figure.art-card{background:rgba(255,255,255,0.66);height:260px;border-radius:8px;display:flex;flex-direction:column;align-items:center;justify-content:flex-start;color:var(--font-color);overflow:hidden;border:1px solid rgba(0,0,0,0.04)}
    figure.art-card img{width:100%;height:180px;object-fit:cover;display:block}
    figure.art-card figcaption{padding:8px 10px;font-size:13px;color:var(--font-color);text-align:center}

    .blog-list{list-style:none;padding:0;margin:0;display:flex;flex-direction:column;gap:12px}
    .blog-item{padding:12px;border-radius:8px;background:rgba(255,255,255,0.66);border:1px solid rgba(0,0,0,0.04)}
    .blog-item a{color:var(--font-color);text-decoration:none;font-weight:600}

    .preview-badge{position:fixed;right:14px;bottom:14px;background:rgba(0,0,0,0.5);color:var(--font-color);padding:8px 10px;border-radius:10px;font-size:13px;backdrop-filter:blur(4px);z-index:60}
  </style>
</head>
<body>
  <header class="site-header" id="siteHeader">
    <div class="container header-inner">
      <div class="brand">
        <div class="avatar" aria-hidden="true">
          <!-- Profile image now set to the requested external link -->
          <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446508334160023613/IMG-20251028-WA0054.jpg?ex=69343d5d&is=6932ebdd&hm=54070c234d5020734c789c18ff44645d684a1501c462ccab1b6bc475844b31c9" alt="Davin Marciano E" id="profileImage" />
        </div>
        <div>
          <h1 id="name">Davin Marciano E</h1>
          <p class="muted" id="headline">Developer • Designer • Maker</p>
        </div>
      </div>

      <nav class="nav" aria-label="Main navigation">
        <a href="#about-me">About me</a>
        <a href="#the-art">The Art</a>
        <a href="#blog">Blog</a>
        <a href="#contact">Contact</a>
        <button id="themeToggle" aria-label="Toggle theme">🌙</button>
      </nav>
    </div>
  </header>

  <main class="container">
    <section class="card" aria-label="Quick sections">
      <h3 class="section-title">Jump to a section</h3>
      <div class="quick-sections">
        <a class="quick-link" href="#about-me">Section 1 — About me</a>
        <a class="quick-link" href="#the-art">Section 2 — The Art</a>
        <a class="quick-link" href="#blog">Section 3 — Blog</a>
      </div>
    </section>

    <section id="about-me" class="card hero" aria-label="About me">
      <div class="hero-left">
        <h2>Hello — I’m <span class="accent">Davin Marciano E</span></h2>
        <p class="lead">Perkenalkan nama saya Davin Marciano Enrico. Saya berasal dari mahasiswa MaChung dengan prodi DKV angkatan 25. Motivasi saya memilih DKV adalah saya suka dengan Graphic Design. Saya juga berpengalaman dalam menggunakan aplikasi Adobe seperti After Effects, Photoshop, dan Illustrator. Saya sudah terjun di dunia Adobe selama kurang lebih 4 tahun. Jurusan DKV ini sangat menarik karena melatih diri saya untuk lebih kreatif lagi.</p>
        <p>
          <a class="btn ghost" href="#the-art">See The Art</a>
        </p>
      </div>
      <div class="hero-right">
        <div class="contact-card">
          <h3 style="color:var(--font-color)">Get in touch</h3>
          <p>Email: <button class="link-as-button" id="copyEmail">marcianodavin@gmail.com</button></p>
          <p style="color:var(--font-color)">Location: Malang, Jawa Timur</p>
          <div class="socials">
            <a href="https://www.instagram.com/vinz.18_?igsh=MjlrenU0NWxvbHl4" target="_blank" rel="noopener">My IG</a>
          </div>
        </div>
      </div>
    </section>

    <section id="the-art" class="card" aria-label="The Art">
      <h3 style="color:var(--font-color)">The Art</h3>
      <p class="muted">Galeri karya — klik gambar untuk melihat lebih besar.</p>
      <div class="art-grid" aria-hidden="false">
        <!-- Art images use the links you provided earlier -->
        <figure class="art-card">
          <a href="https://cdn.discordapp.com/attachments/973073382558019594/1446504901852270745/IMG-20251130-WA0013.jpg?ex=69343a2b&is=6932e8ab&hm=744eeccfb97f444ea3e909b356006bf90f53997f12b9d1e1922a77ee17ac61a6&" target="_blank" rel="noopener">
            <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446504901852270745/IMG-20251130-WA0013.jpg?ex=69343a2b&is=6932e8ab&hm=744eeccfb97f444ea3e909b356006bf90f53997f12b9d1e1922a77ee17ac61a6&" alt="Gambar 1" />
          </a>
          <figcaption>Gambar tangan bagian kanan dengan pose terbuka</figcaption>
        </figure>

        <figure class="art-card">
          <a href="https://cdn.discordapp.com/attachments/973073382558019594/1446504902443405463/IMG-20251204-WA0015.jpg?ex=69343a2b&is=6932e8ab&hm=db9e97a245a328c9dcb47d14dcfe79e693013cad3c90897368ea8dc58f476455&" target="_blank" rel="noopener">
            <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446504902443405463/IMG-20251204-WA0015.jpg?ex=69343a2b&is=6932e8ab&hm=db9e97a245a328c9dcb47d14dcfe79e693013cad3c90897368ea8dc58f476455&" alt="Gambar 2" />
          </a>
          <figcaption>Gambar punggung tangan bagian kiri</figcaption>
        </figure>

        <figure class="art-card">
          <a href="https://cdn.discordapp.com/attachments/973073382558019594/1446504902816694362/IMG-20251204-WA0026.jpg?ex=69343a2b&is=6932e8ab&hm=2b3f0344f373f0c644254b7713114aa787918332e29edbb7f973342e651d7e0d&" target="_blank" rel="noopener">
            <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446504902816694362/IMG-20251204-WA0026.jpg?ex=69343a2b&is=6932e8ab&hm=2b3f0344f373f0c644254b7713114aa787918332e29edbb7f973342e651d7e0d&" alt="Gambar 3" />
          </a>
          <figcaption>Gambar pemandangan alam dengan teknik Hacthing</figcaption>
        </figure>

        <figure class="art-card">
          <a href="https://cdn.discordapp.com/attachments/973073382558019594/1446504903177535622/IMG-20251205-WA0002.jpg?ex=69343a2b&is=6932e8ab&hm=40645401abea77c71ca323e3545f899ce5c292850dedaae59febf1d54501611c&" target="_blank" rel="noopener">
            <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446504903177535622/IMG-20251205-WA0002.jpg?ex=69343a2b&is=6932e8ab&hm=40645401abea77c71ca323e3545f899ce5c292850dedaae59febf1d54501611c&" alt="Gambar 4" />
          </a>
          <figcaption>Lengan cowok dengan otot</figcaption>
        </figure>

        <figure class="art-card">
          <a href="https://cdn.discordapp.com/attachments/973073382558019594/1446504903550832741/WhatsApp_Image_2025-12-05_at_11.29.29_0589c5e4.jpg?ex=69343a2b&is=6932e8ab&hm=f96196e69ca28db491cf1853f36445b3e4536664826f9a4822ce548fb767e5ae&" target="_blank" rel="noopener">
            <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446504903550832741/WhatsApp_Image_2025-12-05_at_11.29.29_0589c5e4.jpg?ex=69343a2b&is=6932e8ab&hm=f96196e69ca28db491cf1853f36445b3e4536664826f9a4822ce548fb767e5ae&" alt="Gambar 5" />
          </a>
          <figcaption>Nirmana tekstur dengan menggunakan batu dan kacang hijau</figcaption>
        </figure>

        <figure class="art-card">
          <a href="https://cdn.discordapp.com/attachments/973073382558019594/1446504903899087012/WhatsApp_Image_2025-12-05_at_11.29.30_2f20774b.jpg?ex=69343a2b&is=6932e8ab&hm=920021d7f7531ce913c367d926a73262062001175f4f4caadc09fba57dc78a07&" target="_blank" rel="noopener">
            <img src="https://cdn.discordapp.com/attachments/973073382558019594/1446504903899087012/WhatsApp_Image_2025-12-05_at_11.29.30_2f20774b.jpg?ex=69343a2b&is=6932e8ab&hm=920021d7f7531ce913c367d926a73262062001175f4f4caadc09fba57dc78a07&" alt="Gambar 6" />
          </a>
          <figcaption>Gambar tangan dengan posisi terbuka bagian kanan dan kiri</figcaption>
        </figure>
      </div>
    </section>

    <section id="blog" class="card" aria-label="Blog">
      <h3 style="color:var(--font-color)">Blog</h3>
      <p class="muted">Recent posts and thoughts — link each title to the full post.</p>
      <ul class="blog-list">
        <li class="blog-item">
          <a href="https://www.umn.ac.id/keunggulan-lulusan-jurusan-dkv-banyak-dicari-bahkan-bisa-punya-usaha-sendiri/" target="_blank" rel="noopener">Mengapa saya tertarik dengan DKV?</a>
          <div class="muted" style="margin-top:6px;font-size:13px">Link referensi: UMN — keunggulan lulusan DKV.</div>
        </li>
        <li class="blog-item">
          <a href="https://www.umn.ac.id/fun-fact-jurusan-dkv-menggali-kreativitas-tanpa-batas-dalam-desain-visual/" target="_blank" rel="noopener">Mengapa DKV itu menarik dan menyenangkan?</a>
          <div class="muted" style="margin-top:6px;font-size:13px">Link referensi: UMN — fun facts DKV.</div>
        </li>
      </ul>
    </section>

    <section id="skills" class="card">
      <h3 style="color:var(--font-color)">Skills</h3>
      <p class="muted">Keahlian utama saya.</p>
      <ul class="chips">
        <li>Graphics Design</li>
        <li>Video Editor</li>
        <li>Photo Editor</li>
        <li>Photography</li>
        <li>Videography</li>
      </ul>
    </section>

    <section id="contact" class="card">
      <h3 style="color:var(--font-color)">Contact</h3>
      <p class="muted">Want to work together or just say hi? Send a message.</p>
      <form id="contactForm" action="mailto:marcianodavin@gmail.com" method="GET" onsubmit="return sendMail(event)">
        <label>
          Your name
          <input type="text" name="name" id="c-name" required placeholder="Your name" />
        </label>
        <label>
          Your email
          <input type="email" name="email" id="c-email" required placeholder="you@example.com" />
        </label>
        <label>
          Message
          <textarea name="message" id="c-message" rows="5" required placeholder="Hi — I’d like to..."></textarea>
        </label>
        <div class="form-actions">
          <button type="submit" class="btn">Send email</button>
          <a class="btn ghost" href="mailto:marcianodavin@gmail.com">Open email client</a>
        </div>
      </form>
    </section>
  </main>

  <footer class="site-footer">
    <div class="container">
      <p style="color:var(--font-color)">@2025 - Davin Marciano E - Web Profile</p>
    </div>
  </footer>

  <div class="preview-badge">Preview — save as preview.html</div>

  <script>
    (function(){
      const toggle = document.getElementById('themeToggle');
      const root = document.documentElement;
      const dark = {
        '--bg':'#0f1724',
        '--card':'#0b1220',
        '--font-color':'#ffffff'
      };
      const light = {
        '--bg':'#f6f7fb',
        '--card':'rgba(255,255,255,0.04)',
        '--font-color':'#161d39'
      };
      function applyTheme(vars){ for(const k in vars) root.style.setProperty(k, vars[k]); }
      const saved = localStorage.getItem('site-theme') || 'light';
      applyTheme(saved === 'light' ? light : dark);
      if(toggle){
        toggle.addEventListener('click', ()=>{
          const cur = localStorage.getItem('site-theme') === 'light' ? 'light' : 'dark';
          const next = cur === 'light' ? 'dark' : 'light';
          applyTheme(next === 'light' ? light : dark);
          localStorage.setItem('site-theme', next);
          toggle.textContent = next === 'light' ? '🌞' : '🌙';
        });
        toggle.textContent = saved === 'light' ? '🌞' : '🌙';
      }

      const copyBtn = document.getElementById('copyEmail');
      if(copyBtn){
        copyBtn.addEventListener('click', async () => {
          const email = copyBtn.textContent.trim();
          try{
            await navigator.clipboard.writeText(email);
            copyBtn.textContent = 'Copied ✓';
            setTimeout(()=> copyBtn.textContent = email, 1500);
          }catch(e){
            window.location.href = 'mailto:' + email;
          }
        });
      }

      window.sendMail = function(e){
        e.preventDefault();
        const name = document.getElementById('c-name').value.trim();
        const email = document.getElementById('c-email').value.trim();
        const msg = document.getElementById('c-message').value.trim();
        const to = 'marcianodavin@gmail.com';
        const subject = encodeURIComponent(Message from ${name});
        const body = encodeURIComponent(Name: ${name}\nEmail: ${email}\n\n${msg});
        const mailto = mailto:${to}?subject=${subject}&body=${body};
        window.location.href = mailto;
        return false;
      };

      const header = document.getElementById('siteHeader');
      const SCROLL_THRESHOLD = 40;
      function onScroll(){
        if(window.scrollY > SCROLL_THRESHOLD) header.classList.add('scrolled');
        else header.classList.remove('scrolled');
      }
      onScroll();
      let ticking = false;
      window.addEventListener('scroll', function(){
        if(!ticking){
          window.requestAnimationFrame(function(){ onScroll(); ticking = false; });
          ticking = true;
        }
      }, { passive: true });

      const img = document.getElementById('profileImage');
      if(img){
        img.addEventListener('error', function(){
          const parent = img.parentElement;
          parent.innerHTML = `
            <svg viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg" role="img">
              <defs>
                <linearGradient id="g" x1="0" x2="1">
                  <stop offset="0" stop-color="#6C5CE7"/>
                  <stop offset="1" stop-color="#00BFA6"/>
                </linearGradient>
              </defs>
              <circle cx="50" cy="40" r="22" fill="url(#g)"/>
              <rect x="20" y="68" width="60" height="20" rx="10" fill="#F6F7FB"/>
            </svg>
          `;
        });
      }
    })();
  </script>
</body>
</html>
