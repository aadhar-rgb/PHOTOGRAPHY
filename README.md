# PHOTOGRAPHY
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>MyPhotoStudio — Portfolio (No JS)</title>
<style>
    /* BASIC RESET */
    *{box-sizing:border-box;margin:0;padding:0}
    html{scroll-behavior:smooth}
    body{font-family:system-ui,-apple-system,Segoe UI,Roboto,Arial;line-height:1.45;color:#111;background:#f6f6f6}

    /* HEADER / NAV */
    header{background:#111;color:#fff;position:sticky;top:0;z-index:10}
    .wrap{max-width:1100px;margin:0 auto;padding:12px 16px;display:flex;align-items:center;justify-content:space-between}
    .logo{font-weight:700}
    nav a{color:#fff;margin-left:14px;text-decoration:none;font-weight:600;padding:6px 8px;border-radius:6px}
    nav a:hover{background:#ffb100;color:#111}

    /* HERO */
    .hero{height:60vh;min-height:320px;background:url("https://picsum.photos/id/1018/1600/900") center/cover no-repeat;display:flex;align-items:center;justify-content:center;position:relative}
    .hero::after{content:"";position:absolute;inset:0;background:linear-gradient(180deg,rgba(0,0,0,.45),rgba(0,0,0,.2))}
    .hero-inner{position:relative;color:#fff;text-align:center;padding:22px;border-radius:10px}

    /* SECTIONS */
    section{max-width:1100px;margin:36px auto;padding:0 16px}
    h2{text-align:center;margin-bottom:12px}

    /* GALLERY GRID */
    .grid{display:grid;grid-template-columns:repeat(4,1fr);gap:14px}
    .card{background:#fff;border-radius:8px;overflow:hidden;box-shadow:0 8px 22px rgba(0,0,0,.06)}
    .card img{width:100%;height:190px;object-fit:cover;display:block}
    .meta{padding:10px;text-align:center;font-weight:600}

    /* LIGHTBOX with :target */
    .light {display:none;position:fixed;inset:0;background:rgba(0,0,0,.9);align-items:center;justify-content:center;z-index:999;padding:24px}
    .light:target{display:flex}
    .light img{max-width:95%;max-height:85vh;border-radius:8px;box-shadow:0 18px 60px rgba(0,0,0,.5)}
    .light .close{position:absolute;top:18px;right:20px;color:#fff;text-decoration:none;background:#111;padding:8px 10px;border-radius:8px}

    /* ABOUT */
    .about{background:#fff;padding:20px;border-radius:10px;box-shadow:0 8px 22px rgba(0,0,0,.04)}

    /* CONTACT / BOOK */
    .contact{background:linear-gradient(180deg,#fff,#ffb10010);padding:18px;border-radius:10px}
    .contact-grid{display:grid;grid-template-columns:1fr 380px;gap:16px}
    .contact-left{padding:8px}
    form{background:#fff;padding:12px;border-radius:8px;display:flex;flex-direction:column;gap:10px;box-shadow:0 8px 20px rgba(0,0,0,.04)}
    input,textarea,select{padding:10px;border-radius:8px;border:1px solid #d0d0d0;font-size:0.95rem}
    textarea{min-height:120px;resize:vertical}
    .btn{background:#111;color:#fff;padding:10px;border-radius:8px;border:none;font-weight:700;cursor:pointer;text-align:center}
    .btn.secondary{background:#ffb100;color:#111}

    /* FOOTER */
    footer{margin-top:28px;background:#111;color:#fff;padding:14px;text-align:center;border-top:4px solid #ffb100}

    /* RESPONSIVE */
    @media (max-width:1000px){.grid{grid-template-columns:repeat(3,1fr)} .contact-grid{grid-template-columns:1fr}}
    @media (max-width:700px){.grid{grid-template-columns:repeat(2,1fr)} nav a{display:none}}
  </style>
</head>
<body>

  <header>
    <div class="wrap">
      <div class="logo">MyPhoto<span style="color:#ffb100">Studio</span></div>
      <nav>
        <a href="#home">Home</a>
        <a href="#gallery">Gallery</a>
        <a href="#about">About</a>
        <a href="#contact">Book</a>
      </nav>
    </div>
  </header>

  <!-- HERO -->
  <section id="home" class="hero">
    <div class="hero-inner">
      <h1 style="font-size:clamp(1.4rem,4vw,2.2rem)">Capturing Moments That Matter</h1>
      <p style="opacity:.95;margin-top:8px">Weddings • Portraits • Nature • Street — storytelling photography.</p>
      <div style="margin-top:12px">
        <a class="btn" href="#gallery">View Work</a>
        <a class="btn secondary" href="#contact" style="margin-left:8px">Book a Session</a>
      </div>
    </div>
  </section>

  <!-- GALLERY -->
  <section id="gallery">
    <h2>Photography Categories</h2>

    <div class="grid" aria-hidden="false">
      <!-- Each image links to its lightbox ID (CSS :target) -->
      <div class="card" data-cat="portrait">
        <a href="#img1"><img src="https://picsum.photos/id/237/1200/900" alt="Portrait sample"></a>
        <div class="meta">Portrait Photography</div>
      </div>

      <div class="card" data-cat="portrait">
        <a href="#img2"><img src="https://picsum.photos/id/1027/1200/900" alt="Studio portrait"></a>
        <div class="meta">Studio Portrait</div>
      </div>

      <div class="card" data-cat="nature">
        <a href="#img3"><img src="https://picsum.photos/id/1003/1200/900" alt="Nature"></a>
        <div class="meta">Nature & Landscape</div>
      </div>

      <div class="card" data-cat="nature">
        <a href="#img4"><img src="https://picsum.photos/id/1011/1200/900" alt="Mountains"></a>
        <div class="meta">Mountains & Sky</div>
      </div>

      <div class="card" data-cat="wedding">
        <a href="#img5"><img src="https://picsum.photos/id/1025/1200/900" alt="Wedding"></a>
        <div class="meta">Wedding Moments</div>
      </div>

      <div class="card" data-cat="wedding">
        <a href="#img6"><img src="https://picsum.photos/id/1062/1200/900" alt="Couple"></a>
        <div class="meta">Couple Portrait</div>
      </div>

      <div class="card" data-cat="street">
        <a href="#img7"><img src="https://picsum.photos/id/1031/1200/900" alt="Street"></a>
        <div class="meta">Street Photography</div>
      </div>

      <div class="card" data-cat="street">
        <a href="#img8"><img src="https://picsum.photos/id/1043/1200/900" alt="Urban life"></a>
        <div class="meta">Urban Life</div>
      </div>
    </div>

    <!-- CSS LIGHTBOX PANELS -->
    <div id="img1" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/237/1600/1200" alt="Portrait sample"></div>
    <div id="img2" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1027/1600/1200" alt="Studio portrait"></div>
    <div id="img3" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1003/1600/1200" alt="Nature"></div>
    <div id="img4" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1011/1600/1200" alt="Mountains"></div>
    <div id="img5" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1025/1600/1200" alt="Wedding"></div>
    <div id="img6" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1062/1600/1200" alt="Couple"></div>
    <div id="img7" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1031/1600/1200" alt="Street"></div>
    <div id="img8" class="light"><a class="close" href="#gallery">✕ Close</a><img src="https://picsum.photos/id/1043/1600/1200" alt="Urban life"></div>
  </section>

  <!-- ABOUT -->
  <section id="about">
    <h2>About Me</h2>
    <div class="about">
      <p style="padding:12px">I am a photographer who prefers natural light and candid moments. I specialize in portraits, weddings and landscape photography. I focus on simple, timeless images that tell a story.</p>
    </div>
  </section>

  <!-- CONTACT / BOOK -->
  <section id="contact">
    <h2>Book a Session</h2>
    <div class="contact">
      <div class="contact-grid">
        <div class="contact-left">
          <p><strong>Info:</strong> Sessions 60–180 minutes. Travel fees may apply. Proofs within ~7 days.</p>
          <p><strong>Pricing:</strong> Please request a quote (packages available).</p>
        </div>

        <!-- MAILTO form: opens user's email client -->
        <form action="mailto:youremail@example.com" method="post" enctype="text/plain" aria-label="booking form">
          <input type="text" name="Name" placeholder="Your full name" required>
          <input type="email" name="Email" placeholder="Email address" required>
          <select name="Type" required>
            <option value="">Select photography type</option>
            <option value="Wedding">Wedding</option>
            <option value="Portrait">Portrait</option>
            <option value="Nature">Nature / Landscape</option>
            <option value="Commercial">Commercial</option>
            <option value="Other">Other</option>
          </select>
          <input type="date" name="Preferred date">
          <textarea name="Message" placeholder="Message / special requests"></textarea>

          <!-- note: mailto forms rely on client's email program -->
          <button type="submit" class="btn">Send Booking Request</button>
        </form>
      </div>
    </div>
  </section>

  <footer>
    © <span id="yr"></span> MyPhotoStudio — All rights reserved.
  </footer>

  <script>
    /* Minimal JS only to set year (optional, you can delete this script if you want ZERO JS) */
    document.getElementById('yr').textContent = new Date().getFullYear();
  </script>
</body>
</html>
