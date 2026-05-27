# eid-card
<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>بطاقة عيد الأضحى المبارك</title>
  <link href="https://fonts.googleapis.com/css2?family=Amiri:wght@400;700&family=Scheherazade+New:wght@400;700&display=swap" rel="stylesheet">
  <style>
    * { box-sizing: border-box; margin: 0; padding: 0; }

    body {
      min-height: 100vh;
      background: #0d0d1a;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 20px;
    }

    .card {
      width: 100%;
      max-width: 480px;
      min-height: 520px;
      background: linear-gradient(160deg, #1a0a2e 0%, #2d1155 40%, #1a3a2e 100%);
      border-radius: 20px;
      position: relative;
      overflow: hidden;
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 40px 32px;
      font-family: 'Amiri', serif;
    }

    .stars {
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      pointer-events: none;
    }

    .star {
      position: absolute;
      background: #fff;
      border-radius: 50%;
      animation: twinkle var(--d, 3s) ease-in-out infinite;
    }

    @keyframes twinkle {
      0%, 100% { opacity: 0.3; transform: scale(1); }
      50% { opacity: 1; transform: scale(1.3); }
    }

    .top-arch {
      position: absolute;
      top: -60px;
      left: 50%;
      transform: translateX(-50%);
      width: 340px;
      height: 160px;
      border: 2px solid rgba(212, 175, 55, 0.35);
      border-radius: 50% 50% 0 0 / 80% 80% 0 0;
    }

    .top-arch::before {
      content: '';
      position: absolute;
      top: 14px; left: 14px; right: 14px; bottom: 0;
      border: 1px solid rgba(212, 175, 55, 0.2);
      border-radius: 50% 50% 0 0 / 80% 80% 0 0;
    }

    .moon-wrap {
      position: relative;
      margin-bottom: 18px;
      animation: floatMoon 4s ease-in-out infinite;
    }

    @keyframes floatMoon {
      0%, 100% { transform: translateY(0px); }
      50% { transform: translateY(-8px); }
    }

    .moon {
      width: 70px;
      height: 70px;
      border-radius: 50%;
      background: radial-gradient(circle at 35% 35%, #ffe066, #c8952c);
      position: relative;
      box-shadow: 0 0 30px rgba(212, 175, 55, 0.6), 0 0 60px rgba(212, 175, 55, 0.25);
    }

    .moon::after {
      content: '';
      position: absolute;
      top: 8px; right: 6px;
      width: 52px;
      height: 52px;
      border-radius: 50%;
      background: #2d1155;
      box-shadow: -2px -2px 8px rgba(212,175,55,0.1);
    }

    .star-tip {
      position: absolute;
      top: -8px; right: -8px;
      font-size: 22px;
      color: #ffe066;
      filter: drop-shadow(0 0 6px rgba(255,224,102,0.9));
    }

    .divider-ornament {
      display: flex;
      align-items: center;
      gap: 10px;
      margin: 6px 0 14px;
      color: rgba(212,175,55,0.8);
      font-size: 18px;
      width: 100%;
      max-width: 320px;
    }

    .divider-line {
      flex: 1;
      height: 1px;
      background: linear-gradient(90deg, transparent, rgba(212,175,55,0.5));
    }

    .divider-line.rev {
      background: linear-gradient(90deg, rgba(212,175,55,0.5), transparent);
    }

    h1.title {
      font-family: 'Scheherazade New', serif;
      font-size: 42px;
      font-weight: 700;
      color: #ffe066;
      text-align: center;
      line-height: 1.2;
      text-shadow: 0 0 20px rgba(255, 224, 102, 0.5);
      margin-bottom: 6px;
      letter-spacing: 2px;
    }

    .subtitle {
      font-family: 'Scheherazade New', serif;
      font-size: 22px;
      color: rgba(255, 224, 102, 0.85);
      text-align: center;
      margin-bottom: 18px;
    }

    .msg {
      font-family: 'Amiri', serif;
      font-size: 17px;
      color: rgba(255, 255, 255, 0.82);
      text-align: center;
      line-height: 1.9;
      max-width: 380px;
      margin-bottom: 24px;
    }

    .footer-row {
      display: flex;
      gap: 28px;
      justify-content: center;
      margin-top: 4px;
    }

    .icon-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 5px;
      font-size: 11px;
      color: rgba(212,175,55,0.65);
      font-family: 'Amiri', serif;
    }

    .icon-item svg {
      width: 28px;
      height: 28px;
      opacity: 0.75;
    }

    .corner-ornament {
      position: absolute;
      width: 60px;
      height: 60px;
      opacity: 0.3;
    }
    .corner-ornament.tl { top: 10px; left: 10px; }
    .corner-ornament.tr { top: 10px; right: 10px; transform: scaleX(-1); }
    .corner-ornament.bl { bottom: 10px; left: 10px; transform: scaleY(-1); }
    .corner-ornament.br { bottom: 10px; right: 10px; transform: scale(-1,-1); }

    .lantern {
      position: absolute;
      animation: swing 3.5s ease-in-out infinite;
      transform-origin: top center;
    }

    .lantern.left  { top: 0; left: 30px;  animation-delay: 0s; }
    .lantern.right { top: 0; right: 30px; animation-delay: 1.75s; }

    @keyframes swing {
      0%, 100% { transform: rotate(-6deg); }
      50%       { transform: rotate(6deg); }
    }

    .card-border {
      position: absolute;
      inset: 8px;
      border: 1px solid rgba(212,175,55,0.2);
      border-radius: 14px;
      pointer-events: none;
    }

    .card-border::before {
      content: '';
      position: absolute;
      inset: 6px;
      border: 1px solid rgba(212,175,55,0.1);
      border-radius: 10px;
    }
  </style>
</head>
<body>
  <div class="card" id="card">

    <!-- نجوم الخلفية -->
    <div class="stars" id="stars"></div>

    <!-- إطار البطاقة -->
    <div class="card-border"></div>

    <!-- القوس العلوي -->
    <div class="top-arch"></div>

    <!-- زخارف الأركان -->
    <svg class="corner-ornament tl" viewBox="0 0 60 60" fill="none">
      <path d="M5 5 Q5 30 30 30 Q5 30 5 55" stroke="#d4af37" stroke-width="1.5" fill="none"/>
      <path d="M15 5 Q15 20 30 20 Q15 20 15 40" stroke="#d4af37" stroke-width="0.8" fill="none"/>
      <circle cx="5" cy="5" r="3" fill="#d4af37"/>
      <circle cx="30" cy="30" r="2" fill="#d4af37"/>
    </svg>
    <svg class="corner-ornament tr" viewBox="0 0 60 60" fill="none">
      <path d="M5 5 Q5 30 30 30 Q5 30 5 55" stroke="#d4af37" stroke-width="1.5" fill="none"/>
      <circle cx="5" cy="5" r="3" fill="#d4af37"/>
      <circle cx="30" cy="30" r="2" fill="#d4af37"/>
    </svg>
    <svg class="corner-ornament bl" viewBox="0 0 60 60" fill="none">
      <path d="M5 5 Q5 30 30 30 Q5 30 5 55" stroke="#d4af37" stroke-width="1.5" fill="none"/>
      <circle cx="5" cy="5" r="3" fill="#d4af37"/>
      <circle cx="30" cy="30" r="2" fill="#d4af37"/>
    </svg>
    <svg class="corner-ornament br" viewBox="0 0 60 60" fill="none">
      <path d="M5 5 Q5 30 30 30 Q5 30 5 55" stroke="#d4af37" stroke-width="1.5" fill="none"/>
      <circle cx="5" cy="5" r="3" fill="#d4af37"/>
      <circle cx="30" cy="30" r="2" fill="#d4af37"/>
    </svg>

    <!-- الفانوس الأيسر -->
    <svg class="lantern left" width="22" height="50" viewBox="0 0 22 50">
      <line x1="11" y1="0" x2="11" y2="8" stroke="#d4af37" stroke-width="1.5"/>
      <rect x="3" y="8" width="16" height="26" rx="3" fill="rgba(212,100,0,0.4)" stroke="#d4af37" stroke-width="1"/>
      <line x1="3" y1="14" x2="19" y2="14" stroke="#d4af37" stroke-width="0.5"/>
      <line x1="3" y1="28" x2="19" y2="28" stroke="#d4af37" stroke-width="0.5"/>
      <ellipse cx="11" cy="34" rx="8" ry="4" fill="rgba(212,100,0,0.3)" stroke="#d4af37" stroke-width="0.8"/>
      <line x1="11" y1="34" x2="11" y2="42" stroke="#d4af37" stroke-width="1"/>
      <ellipse cx="11" cy="21" rx="5" ry="7" fill="rgba(255,200,50,0.25)"/>
    </svg>

    <!-- الفانوس الأيمن -->
    <svg class="lantern right" width="22" height="50" viewBox="0 0 22 50">
      <line x1="11" y1="0" x2="11" y2="8" stroke="#d4af37" stroke-width="1.5"/>
      <rect x="3" y="8" width="16" height="26" rx="3" fill="rgba(20,100,60,0.5)" stroke="#d4af37" stroke-width="1"/>
      <line x1="3" y1="14" x2="19" y2="14" stroke="#d4af37" stroke-width="0.5"/>
      <line x1="3" y1="28" x2="19" y2="28" stroke="#d4af37" stroke-width="0.5"/>
      <ellipse cx="11" cy="34" rx="8" ry="4" fill="rgba(20,100,60,0.4)" stroke="#d4af37" stroke-width="0.8"/>
      <line x1="11" y1="34" x2="11" y2="42" stroke="#d4af37" stroke-width="1"/>
      <ellipse cx="11" cy="21" rx="5" ry="7" fill="rgba(100,255,180,0.18)"/>
    </svg>

    <!-- الهلال -->
    <div class="moon-wrap">
      <div class="moon"></div>
      <span class="star-tip">✦</span>
    </div>

    <!-- فاصل زخرفي علوي -->
    <div class="divider-ornament">
      <div class="divider-line rev"></div>
      <span>✦ ✦ ✦</span>
      <div class="divider-line"></div>
    </div>

    <!-- العنوان الرئيسي -->
    <h1 class="title">عيد الأضحى المبارك</h1>
    <img src="data:image/jpeg;base64,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">
    <p class="subtitle">كل عام وأنتم بخير</p>
    <p class="subtitle">اي اسم تريده</p>


    <!-- فاصل زخرفي سفلي -->
    <div class="divider-ornament">
      <div class="divider-line rev"></div>
      <span>❖</span>
      <div class="divider-line"></div>
    </div>

    <!-- نص التهنئة -->
    <p class="msg">
      تقبّل الله منّا ومنكم صالح الأعمال،<br>
      وأعاده عليكم بالسعادة والسرور،<br>
      وجعلكم من عتقاء هذا اليوم المبارك
    </p>

    <!-- أيقونات الختام -->
    <div class="footer-row">
      <div class="icon-item">
        <svg viewBox="0 0 28 28" fill="none">
          <path d="M14 3 C14 3 8 8 8 14 C8 17.3 10.7 20 14 20 C17.3 20 20 17.3 20 14 C20 8 14 3 14 3Z"
                stroke="#d4af37" stroke-width="1.2" fill="rgba(212,175,55,0.15)"/>
          <path d="M14 20 L14 25" stroke="#d4af37" stroke-width="1.2"/>
          <path d="M10 25 L18 25" stroke="#d4af37" stroke-width="1.2" stroke-linecap="round"/>
          <circle cx="14" cy="13" r="2.5" fill="rgba(212,175,55,0.4)" stroke="#d4af37" stroke-width="0.8"/>
        </svg>
        <span>نور وهداية</span>
      </div>
      <div class="icon-item">
        <svg viewBox="0 0 28 28" fill="none">
          <path d="M7 14 C7 10.1 10.1 7 14 7 C17.9 7 21 10.1 21 14" stroke="#d4af37" stroke-width="1.2" fill="none"/>
          <path d="M5 14 Q5 6 14 4 Q23 6 23 14 L23 22 Q14 26 5 22 Z"
                stroke="#d4af37" stroke-width="1" fill="rgba(212,175,55,0.08)"/>
          <circle cx="14" cy="14" r="2" fill="rgba(212,175,55,0.5)"/>
        </svg>
        <span>سلام وأمان</span>
      </div>
      <div class="icon-item">
        <svg viewBox="0 0 28 28" fill="none">
          <path d="M14 5 L16.4 11.3 L23 11.3 L17.8 15.2 L19.9 21.5 L14 17.6 L8.1 21.5 L10.2 15.2 L5 11.3 L11.6 11.3 Z"
                stroke="#d4af37" stroke-width="1.2" fill="rgba(212,175,55,0.18)"/>
        </svg>
        <span>بهجة وعطاء</span>
      </div>
    </div>

  </div>

  <script>
    // توليد النجوم عشوائياً
    const starsEl = document.getElementById('stars');
    for (let i = 0; i < 55; i++) {
      const s = document.createElement('div');
      s.className = 'star';
      const size = Math.random() * 2.5 + 0.8;
      s.style.cssText = `
        width:${size}px; height:${size}px;
        top:${Math.random() * 100}%;
        left:${Math.random() * 100}%;
        --d:${(Math.random() * 3 + 2).toFixed(1)}s;
        animation-delay:${(Math.random() * 4).toFixed(1)}s;
        opacity:${Math.random() * 0.5 + 0.2};
      `;
      starsEl.appendChild(s);
    }
  </script>
</body>
</html>
