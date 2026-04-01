<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Coach Ankit Ingle — Personal Trainer & Life Coach</title>
<link href="https://fonts.googleapis.com/css2?family=Bebas+Neue&family=Outfit:wght@300;400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
:root {
  --bg: #080C18;
  --surface: #0E1426;
  --surface2: #141B30;
  --border: #1E2A48;
  --border2: rgba(99,130,255,0.15);
  --text: #F0F4FF;
  --text2: #8A9BC4;
  --text3: #4A5880;
  --accent: #4F6FFF;
  --accent2: #2B4DE0;
  --glow: rgba(79,111,255,0.25);
  --orange: #FF6B35;
  --orange-glow: rgba(255,107,53,0.2);
  --green: #00D68F;
  --green-bg: rgba(0,214,143,0.08);
  --gold: #FFB800;
  --radius: 20px;
  --radius-sm: 12px;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }

body {
  background: var(--bg);
  color: var(--text);
  font-family: 'Outfit', sans-serif;
  min-height: 100vh;
  overflow-x: hidden;
}

/* ── Animated mesh background ── */
body::before {
  content: '';
  position: fixed; inset: 0;
  background:
    radial-gradient(ellipse 80% 60% at 10% 0%, rgba(79,111,255,0.12) 0%, transparent 60%),
    radial-gradient(ellipse 60% 50% at 90% 100%, rgba(255,107,53,0.08) 0%, transparent 55%),
    radial-gradient(ellipse 40% 40% at 50% 50%, rgba(79,111,255,0.04) 0%, transparent 60%);
  pointer-events: none; z-index: 0;
}

/* Grid lines */
body::after {
  content: '';
  position: fixed; inset: 0;
  background-image:
    linear-gradient(rgba(79,111,255,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(79,111,255,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
  pointer-events: none; z-index: 0;
}

.page {
  position: relative; z-index: 1;
  max-width: 560px;
  margin: 0 auto;
  padding: 48px 18px 80px;
}

/* ══ HERO ══ */
.hero {
  display: flex; flex-direction: column; align-items: center;
  text-align: center; margin-bottom: 40px;
}

.avatar-ring {
  position: relative; width: 110px; height: 110px; margin-bottom: 24px;
}
.avatar-ring::before {
  content: '';
  position: absolute; inset: -3px;
  border-radius: 50%;
  background: conic-gradient(var(--accent), var(--orange), var(--accent));
  animation: spin 4s linear infinite;
}
.avatar-ring::after {
  content: '';
  position: absolute; inset: -3px;
  border-radius: 50%;
  background: conic-gradient(var(--accent), var(--orange), var(--accent));
  filter: blur(8px);
  animation: spin 4s linear infinite;
  opacity: 0.5;
}
.avatar-inner {
  position: absolute; inset: 3px;
  border-radius: 50%;
  background: var(--surface2);
  display: flex; align-items: center; justify-content: center;
  z-index: 1;
}
.avatar-initials {
  font-family: 'Bebas Neue', cursive;
  font-size: 38px;
  letter-spacing: 2px;
  background: linear-gradient(135deg, var(--accent), var(--orange));
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  background-clip: text;
}
@keyframes spin { to { transform: rotate(360deg); } }

.status-dot {
  position: absolute; bottom: 4px; right: 4px; z-index: 2;
  background: var(--surface);
  border-radius: 30px;
  padding: 3px 9px;
  border: 1px solid var(--border);
  display: flex; align-items: center; gap: 4px;
  font-size: 9px; font-weight: 700; color: var(--green);
  letter-spacing: 1px; text-transform: uppercase;
}
.status-dot::before {
  content: ''; width: 6px; height: 6px; border-radius: 50%;
  background: var(--green);
  box-shadow: 0 0 8px var(--green);
  animation: pulse 2s ease-in-out infinite;
}
@keyframes pulse { 0%,100% { opacity: 1; } 50% { opacity: 0.4; } }

.hero-name {
  font-family: 'Bebas Neue', cursive;
  font-size: clamp(44px, 13vw, 64px);
  letter-spacing: 3px;
  line-height: 0.95;
  margin-bottom: 12px;
}
.hero-name span {
  display: block;
  background: linear-gradient(90deg, var(--accent) 0%, #A0B4FF 50%, var(--orange) 100%);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  background-clip: text;
}

.hero-badge {
  display: inline-flex; align-items: center; gap: 8px;
  background: rgba(79,111,255,0.1);
  border: 1px solid rgba(79,111,255,0.25);
  border-radius: 40px;
  padding: 6px 18px;
  font-size: 12px; font-weight: 600; color: #A0B4FF;
  letter-spacing: 0.5px;
  margin-bottom: 18px;
  backdrop-filter: blur(8px);
}

.hero-bio {
  font-size: 14px; line-height: 1.8; color: var(--text2);
  max-width: 400px;
}
.hero-bio strong { color: var(--text); font-weight: 600; }

/* ── Stats ── */
.stats-row {
  display: grid; grid-template-columns: repeat(2, 1fr);
  gap: 12px; margin-bottom: 40px;
}
.stat-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius-sm);
  padding: 20px 16px;
  text-align: center;
  position: relative; overflow: hidden;
  transition: transform 0.2s, border-color 0.2s;
}
.stat-card::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(79,111,255,0.06), transparent);
  opacity: 0; transition: opacity 0.2s;
}
.stat-card:hover { transform: translateY(-4px); border-color: rgba(79,111,255,0.4); }
.stat-card:hover::before { opacity: 1; }
.stat-n {
  font-family: 'Bebas Neue', cursive;
  font-size: 40px; letter-spacing: 2px;
  background: linear-gradient(135deg, var(--accent), #A0B4FF);
  -webkit-background-clip: text; -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1;
}
.stat-n.orange { background: linear-gradient(135deg, var(--orange), #FFB380); -webkit-background-clip: text; background-clip: text; }
.stat-l { font-size: 11px; color: var(--text3); margin-top: 4px; font-weight: 500; letter-spacing: 1px; text-transform: uppercase; }

/* ══ SECTION HEADER ══ */
.sec-head {
  display: flex; align-items: center; gap: 12px;
  margin-bottom: 16px;
}
.sec-icon {
  width: 38px; height: 38px; border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 18px; flex-shrink: 0;
  background: rgba(79,111,255,0.1);
  border: 1px solid rgba(79,111,255,0.2);
}
.sec-head h2 {
  font-family: 'Bebas Neue', cursive;
  font-size: 22px; letter-spacing: 2px;
  color: var(--text);
}
.sec-head p { font-size: 12px; color: var(--text3); margin-top: 1px; }

/* ── Divider ── */
.divider { height: 1px; background: var(--border); margin: 36px 0; position: relative; }
.divider::after {
  content: '●';
  position: absolute; left: 50%; top: 50%;
  transform: translate(-50%, -50%);
  background: var(--bg);
  padding: 0 8px;
  color: var(--text3); font-size: 8px;
}

/* ══ ABOUT CARD ══ */
.about-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 24px;
  margin-bottom: 36px;
  position: relative; overflow: hidden;
}
.about-card::before {
  content: '';
  position: absolute; top: 0; left: 0; right: 0; height: 2px;
  background: linear-gradient(90deg, var(--accent), var(--orange));
}
.about-card p { font-size: 14px; line-height: 1.85; color: var(--text2); }
.about-card p + p { margin-top: 12px; }
.about-card strong { color: var(--text); font-weight: 600; }
.cert-badge {
  display: flex; align-items: center; gap: 10px;
  background: rgba(79,111,255,0.08);
  border: 1px solid rgba(79,111,255,0.2);
  border-radius: 10px;
  padding: 12px 16px;
  margin-top: 18px;
  font-size: 13px; font-weight: 500; color: #A0B4FF;
}

/* ══ PLAN CARDS ══ */
.plans-wrap { display: flex; flex-direction: column; gap: 12px; margin-bottom: 36px; }

.plan-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 20px 18px;
  display: flex; align-items: flex-start; gap: 14px;
  text-decoration: none; color: inherit;
  position: relative; overflow: hidden;
  transition: all 0.25s;
  cursor: pointer;
}
.plan-card::after {
  content: '';
  position: absolute; left: 0; top: 0; bottom: 0; width: 3px;
  background: var(--border);
  transition: background 0.25s;
}
.plan-card:hover { border-color: rgba(79,111,255,0.4); transform: translateX(4px); }
.plan-card.starter:hover::after { background: var(--green); }
.plan-card.standard:hover::after { background: var(--accent); }
.plan-card.premium:hover::after { background: var(--orange); }
.plan-card.standard { border-color: rgba(79,111,255,0.3); background: linear-gradient(135deg, rgba(79,111,255,0.06), var(--surface)); }
.plan-card.standard::after { background: var(--accent); }

.pop-tag {
  position: absolute; top: 0; right: 16px;
  background: linear-gradient(135deg, var(--accent), var(--accent2));
  color: white; font-size: 9px; font-weight: 700;
  letter-spacing: 1.5px; text-transform: uppercase;
  padding: 3px 12px; border-radius: 0 0 10px 10px;
}

.plan-icon {
  width: 48px; height: 48px; border-radius: 12px;
  display: flex; align-items: center; justify-content: center;
  font-size: 22px; flex-shrink: 0;
}
.starter .plan-icon { background: rgba(0,214,143,0.1); }
.standard .plan-icon { background: rgba(79,111,255,0.1); }
.premium .plan-icon { background: rgba(255,107,53,0.1); }

.plan-body { flex: 1; }
.plan-name { font-family: 'Bebas Neue', cursive; font-size: 20px; letter-spacing: 1.5px; color: var(--text); }
.plan-dur { font-size: 11px; color: var(--text3); margin-top: 2px; }
.plan-desc { font-size: 13px; color: var(--text2); margin-top: 8px; line-height: 1.6; }

.plan-cta {
  display: inline-block; margin-top: 12px;
  font-size: 11px; font-weight: 700; letter-spacing: 1px; text-transform: uppercase;
  padding: 6px 14px; border-radius: 6px;
  transition: all 0.2s;
}
.starter .plan-cta { background: rgba(0,214,143,0.15); color: var(--green); border: 1px solid rgba(0,214,143,0.25); }
.standard .plan-cta { background: rgba(79,111,255,0.2); color: #A0B4FF; border: 1px solid rgba(79,111,255,0.3); }
.premium .plan-cta { background: rgba(255,107,53,0.15); color: var(--orange); border: 1px solid rgba(255,107,53,0.25); }

.plan-price-col { text-align: right; flex-shrink: 0; }
.plan-price {
  font-family: 'Bebas Neue', cursive;
  font-size: 30px; letter-spacing: 1px; line-height: 1;
}
.starter .plan-price { color: var(--green); }
.standard .plan-price { color: var(--accent); }
.premium .plan-price { color: var(--orange); }
.plan-price-sub { font-size: 11px; color: var(--text3); margin-top: 2px; }

/* ══ TRAINING PACKAGE ══ */
.training-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  overflow: hidden;
  margin-bottom: 36px;
  position: relative;
}
.training-header {
  background: linear-gradient(135deg, #1A2560 0%, #0D183D 100%);
  padding: 28px 24px 24px;
  position: relative; overflow: hidden;
}
.training-header::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(79,111,255,0.3), transparent 60%);
}
.training-header::after {
  content: '🏋️';
  position: absolute; right: 16px; top: 50%; transform: translateY(-50%);
  font-size: 64px; opacity: 0.08;
}
.th-eyebrow {
  font-size: 10px; font-weight: 700; letter-spacing: 3px; text-transform: uppercase;
  color: rgba(160,180,255,0.7); margin-bottom: 8px; position: relative;
}
.th-title {
  font-family: 'Bebas Neue', cursive;
  font-size: 30px; letter-spacing: 2px; line-height: 1.15;
  color: white; position: relative;
}
.th-price-row { display: flex; align-items: baseline; gap: 8px; margin-top: 14px; position: relative; }
.th-price { font-family: 'Bebas Neue', cursive; font-size: 48px; color: white; letter-spacing: 1px; }
.th-period { font-size: 14px; color: rgba(255,255,255,0.55); }

.training-body { padding: 24px; }
.feat-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; margin-bottom: 22px; }
.feat-item {
  display: flex; align-items: flex-start; gap: 10px;
  font-size: 13px; color: var(--text2); line-height: 1.45;
}
.feat-check {
  width: 20px; height: 20px; border-radius: 50%;
  background: rgba(79,111,255,0.15);
  color: var(--accent);
  display: flex; align-items: center; justify-content: center;
  font-size: 11px; flex-shrink: 0; margin-top: 1px;
  font-weight: 700;
}
.feat-item strong { color: var(--text); font-weight: 600; }

.enq-btn {
  display: block; text-align: center; text-decoration: none;
  background: linear-gradient(135deg, var(--accent), var(--accent2));
  color: white;
  font-family: 'Bebas Neue', cursive;
  font-size: 18px; letter-spacing: 3px;
  padding: 16px; border-radius: 12px;
  transition: all 0.2s;
  position: relative; overflow: hidden;
}
.enq-btn::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(255,255,255,0.1), transparent);
  opacity: 0; transition: opacity 0.2s;
}
.enq-btn:hover { transform: translateY(-2px); box-shadow: 0 12px 32px rgba(79,111,255,0.35); }
.enq-btn:hover::before { opacity: 1; }

/* ══ ONLINE PLANS ══ */
.online-wrap { display: flex; flex-direction: column; gap: 12px; margin-bottom: 36px; }

.online-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 18px;
  display: flex; align-items: center; gap: 16px;
  text-decoration: none; color: inherit;
  transition: all 0.25s;
  cursor: pointer;
}
.online-card:hover { border-color: rgba(79,111,255,0.35); transform: translateX(4px); box-shadow: 0 8px 30px rgba(0,0,0,0.2); }

.oi {
  width: 52px; height: 52px; border-radius: 14px;
  display: flex; align-items: center; justify-content: center;
  font-size: 24px; flex-shrink: 0;
}
.oc1 .oi { background: rgba(79,111,255,0.1); border: 1px solid rgba(79,111,255,0.2); }
.oc2 .oi { background: rgba(255,107,53,0.1); border: 1px solid rgba(255,107,53,0.2); }
.oc3 .oi { background: rgba(0,214,143,0.1); border: 1px solid rgba(0,214,143,0.2); }

.ob { flex: 1; }
.on { font-family: 'Bebas Neue', cursive; font-size: 18px; letter-spacing: 1.5px; color: var(--text); }
.os { font-size: 11px; color: var(--text3); margin-top: 2px; }
.ot { display: flex; flex-wrap: wrap; gap: 5px; margin-top: 8px; }
.otag {
  font-size: 10px; font-weight: 600; letter-spacing: 0.5px;
  background: var(--surface2); color: var(--text3);
  border: 1px solid var(--border); border-radius: 4px;
  padding: 2px 8px;
}
.op { font-family: 'Bebas Neue', cursive; font-size: 26px; letter-spacing: 1px; color: var(--accent); text-align: right; flex-shrink: 0; }
.op small { display: block; font-family: 'Outfit', sans-serif; font-size: 11px; color: var(--text3); font-weight: 400; }

/* ══ PAYMENT SECTION ══ */
.payment-section { margin-bottom: 36px; }
.payment-card {
  background: var(--surface);
  border: 1px solid rgba(99,130,255,0.2);
  border-radius: var(--radius);
  padding: 24px;
  text-align: center;
  position: relative; overflow: hidden;
}
.payment-card::before {
  content: '';
  position: absolute; inset: 0;
  background: linear-gradient(135deg, rgba(79,111,255,0.05), transparent);
}
.payment-title {
  font-family: 'Bebas Neue', cursive;
  font-size: 22px; letter-spacing: 2px; color: var(--text);
  margin-bottom: 6px; position: relative;
}
.payment-sub { font-size: 12px; color: var(--text3); margin-bottom: 20px; position: relative; }
.qr-wrap {
  display: inline-block;
  padding: 14px;
  background: white;
  border-radius: 14px;
  position: relative;
  box-shadow: 0 8px 32px rgba(0,0,0,0.3);
}
.qr-wrap img { width: 180px; height: 180px; display: block; border-radius: 6px; }
.payment-name {
  font-family: 'Bebas Neue', cursive;
  font-size: 18px; letter-spacing: 2px; color: var(--accent);
  margin-top: 16px; position: relative;
}
.phonepe-badge {
  display: inline-flex; align-items: center; gap: 6px;
  background: #5F259F;
  border-radius: 20px; padding: 4px 14px;
  font-size: 12px; font-weight: 700; color: white;
  margin-top: 8px; position: relative;
}

/* ══ SOCIAL LINKS ══ */
.social-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-bottom: 36px; }

.soc-card {
  background: var(--surface);
  border: 1px solid var(--border);
  border-radius: var(--radius);
  padding: 16px;
  display: flex; align-items: center; gap: 12px;
  text-decoration: none; color: var(--text);
  transition: all 0.2s;
}
.soc-card:hover { transform: translateY(-4px); box-shadow: 0 12px 30px rgba(0,0,0,0.25); }
.sc-ig:hover { border-color: #E1306C; }
.sc-yt:hover { border-color: #FF0000; }
.sc-wa:hover { border-color: #25D366; }
.sc-em:hover { border-color: var(--accent); }

.si {
  width: 42px; height: 42px; border-radius: 10px;
  display: flex; align-items: center; justify-content: center;
  font-size: 20px; flex-shrink: 0;
}
.sc-ig .si { background: linear-gradient(135deg, #F09433, #E6683C, #DC2743, #CC2366); }
.sc-yt .si { background: #FF0000; }
.sc-wa .si { background: #25D366; }
.sc-em .si { background: rgba(79,111,255,0.2); border: 1px solid rgba(79,111,255,0.3); }

.sn { font-family: 'Outfit', sans-serif; font-weight: 700; font-size: 14px; color: var(--text); }
.sh { font-size: 10px; color: var(--text3); margin-top: 2px; }

/* ══ FOOTER ══ */
.footer {
  text-align: center; font-size: 11px; color: var(--text3);
  padding-top: 16px; border-top: 1px solid var(--border);
  line-height: 1.8;
}
.footer a { color: var(--accent); text-decoration: none; }

/* ── Fade in animations ── */
.fade-up {
  opacity: 0; transform: translateY(28px);
  transition: opacity 0.65s cubic-bezier(0.16,1,0.3,1), transform 0.65s cubic-bezier(0.16,1,0.3,1);
}
.fade-up.visible { opacity: 1; transform: none; }

/* Ripple */
.ripple { position: relative; overflow: hidden; }
.rip-el {
  position: absolute; border-radius: 50%;
  background: rgba(255,255,255,0.06);
  transform: scale(0);
  animation: rip 0.5s ease-out forwards;
  pointer-events: none;
}
@keyframes rip { to { transform: scale(5); opacity: 0; } }

@media (max-width: 420px) {
  .feat-grid { grid-template-columns: 1fr; }
  .social-grid { grid-template-columns: 1fr; }
  .stats-row { grid-template-columns: 1fr 1fr; }
}
</style>
</head>
<body>
<div class="page">

  <!-- ══ HERO ══ -->
  <div class="hero fade-up visible">
    <div class="avatar-ring">
      <div class="avatar-inner">
        <div class="avatar-initials">AI</div>
      </div>
      <div class="status-dot">Active</div>
    </div>
    <h1 class="hero-name">
      Coach<br><span>Ankit Ingle</span>
    </h1>
    <div class="hero-badge">🎓 Certified Personal Trainer &amp; Life Coach</div>
    <p class="hero-bio">
      Helping real people build <strong>real results</strong> through science-backed training,<br>
      customized nutrition &amp; consistent daily support — across India 🇮🇳
    </p>
  </div>

  <!-- ══ STATS ══ -->
  <div class="stats-row fade-up">
    <div class="stat-card">
      <div class="stat-n">100+</div>
      <div class="stat-l">Clients Transformed</div>
    </div>
    <div class="stat-card">
      <div class="stat-n orange">8+</div>
      <div class="stat-l">Years Experience</div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ══ ABOUT ME ══ -->
  <div class="sec-head fade-up">
    <div class="sec-icon">👋</div>
    <div>
      <h2>About The Coach</h2>
      <p>The mind behind your transformation</p>
    </div>
  </div>

  <div class="about-card fade-up">
    <p>
      Hi, I'm <strong>Coach Ankit</strong> — a certified Personal Trainer and graduate of <strong>Mission India Fitness Institute</strong>. My passion is helping real people build real results through science-backed training, customized nutrition, and consistent daily support.
    </p>
    <p>
      Whether you're just starting out or looking to <strong>break your plateau</strong> — I design programs built around <em>your body, your lifestyle, and your goals.</em> No generic templates. No shortcuts. No guesswork.
    </p>
    <p>
      I've worked with clients from busy professionals in <strong>Nashik and Pune</strong> to students and homemakers — helping them lose weight, build muscle, and build lasting healthy habits that actually fit Indian food culture and schedules.
    </p>
    <div class="cert-badge">
      🎓 &nbsp; Mission India Fitness Institute — Certified Personal Trainer
    </div>
  </div>

  <div class="divider"></div>

  <!-- ══ CONSULTATION PLANS ══ -->
  <div class="sec-head fade-up">
    <div class="sec-icon">📞</div>
    <div>
      <h2>Consultation Plans</h2>
      <p>100% online · Available pan-India</p>
    </div>
  </div>

  <div class="plans-wrap">

    <a href="https://docs.google.com/forms/d/e/1FAIpQLSe_STARTER_FORM/viewform" target="_blank"
       class="plan-card starter ripple fade-up" style="transition-delay:0.05s">
      <div class="plan-icon">💬</div>
      <div class="plan-body">
        <div class="plan-name">Starter</div>
        <div class="plan-dur">⏱ 30-Minute Quick Call</div>
        <div class="plan-desc">Perfect for clarity on goals, diet direction, or workout basics. Ideal for first-timers.</div>
        <div class="plan-cta">Book Now →</div>
      </div>
      <div class="plan-price-col">
        <div class="plan-price">₹199</div>
        <div class="plan-price-sub">one-time</div>
      </div>
    </a>

    <a href="https://docs.google.com/forms/d/e/1FAIpQLSe_STANDARD_FORM/viewform" target="_blank"
       class="plan-card standard ripple fade-up" style="transition-delay:0.1s">
      <div class="pop-tag">⭐ Most Popular</div>
      <div class="plan-icon">🔥</div>
      <div class="plan-body">
        <div class="plan-name">Standard</div>
        <div class="plan-dur">⏱ 60-Minute Deep Dive</div>
        <div class="plan-desc">Full body assessment, detailed goals discussion, complete diet overview &amp; training plan direction.</div>
        <div class="plan-cta">Book Now →</div>
      </div>
      <div class="plan-price-col">
        <div class="plan-price">₹499</div>
        <div class="plan-price-sub">one-time</div>
      </div>
    </a>

    <a href="https://docs.google.com/forms/d/e/1FAIpQLSe_PREMIUM_FORM/viewform" target="_blank"
       class="plan-card premium ripple fade-up" style="transition-delay:0.15s">
      <div class="plan-icon">👑</div>
      <div class="plan-body">
        <div class="plan-name">Premium</div>
        <div class="plan-dur">⏱ 90-Minute Power Session</div>
        <div class="plan-desc">In-depth session + 7-day sample diet &amp; workout plans + free follow-up call within 7 days. Best value.</div>
        <div class="plan-cta">Book Now →</div>
      </div>
      <div class="plan-price-col">
        <div class="plan-price">₹999</div>
        <div class="plan-price-sub">+ follow-up</div>
      </div>
    </a>

  </div>

  <div class="divider"></div>

  <!-- ══ PERSONAL TRAINING ══ -->
  <div class="sec-head fade-up">
    <div class="sec-icon">🏋️</div>
    <div>
      <h2>Personal Training</h2>
      <p>Full transformation — 3 months</p>
    </div>
  </div>

  <div class="training-card fade-up">
    <div class="training-header">
      <div class="th-eyebrow">3-Month Coaching Program</div>
      <div class="th-title">Total Body Transformation<br>Package</div>
      <div class="th-price-row">
        <div class="th-price">₹25,000</div>
        <div class="th-period">/ 3 months</div>
      </div>
    </div>
    <div class="training-body">
      <div class="feat-grid">
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>CoachKit App</strong> for tracking workouts &amp; diet</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>Weekly Video Meets</strong> with Coach Ankit</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>Daily Check-ins</strong> via WhatsApp</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>24/7 Support</strong> — always guided</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>Custom Diet Plan</strong> for Indian food habits</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>Custom Workout Plan</strong> for your equipment</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>Monthly Plan Revisions</strong> based on progress</div></div>
        <div class="feat-item"><div class="feat-check">✓</div><div><strong>Progress Tracking</strong> with body reports</div></div>
      </div>
      <a href="mailto:coachankitingle@gmail.com?subject=Enquiry: 3-Month Transformation Package&body=Hi Coach Ankit, I am interested in your 3-Month Total Body Transformation Package. Please share more details.%0A%0AName:%0AAge:%0AGoal:%0ACity:" class="enq-btn ripple">
        Enquire About This Program →
      </a>
    </div>
  </div>

  <!-- ══ ONLINE TRAINING PLANS ══ -->
  <div class="sec-head fade-up">
    <div class="sec-icon">📲</div>
    <div>
      <h2>Online Training Plans</h2>
      <p>Train from anywhere in India — fully digital</p>
    </div>
  </div>

  <div class="online-wrap">

    <a href="mailto:coachankitingle@gmail.com?subject=Enquiry: Foundation Plan&body=Hi Coach Ankit, I am interested in the Foundation Plan (₹2,999/month). Please share more details.%0A%0AName:%0AAge:%0AGoal:%0ACity:" class="online-card oc1 ripple fade-up" style="transition-delay:0.05s">
      <div class="oi">🌱</div>
      <div class="ob">
        <div class="on">Foundation Plan</div>
        <div class="os">1 Month · Beginner Friendly</div>
        <div class="ot">
          <span class="otag">Custom Workout</span>
          <span class="otag">Diet Chart</span>
          <span class="otag">WhatsApp Support</span>
        </div>
      </div>
      <div class="op">₹2,999<small>/ month</small></div>
    </a>

    <a href="mailto:coachankitingle@gmail.com?subject=Enquiry: Performance Plan&body=Hi Coach Ankit, I am interested in the Performance Plan (₹4,999/month). Please share more details.%0A%0AName:%0AAge:%0AGoal:%0ACity:" class="online-card oc2 ripple fade-up" style="transition-delay:0.1s">
      <div class="oi">⚡</div>
      <div class="ob">
        <div class="on">Performance Plan</div>
        <div class="os">2 Months · Intermediate</div>
        <div class="ot">
          <span class="otag">Weekly Calls</span>
          <span class="otag">Macro Tracking</span>
          <span class="otag">Progress Reviews</span>
        </div>
      </div>
      <div class="op">₹4,999<small>/ month</small></div>
    </a>

    <a href="mailto:coachankitingle@gmail.com?subject=Enquiry: Elite Plan&body=Hi Coach Ankit, I am interested in the Elite Plan (₹7,999/month). Please share more details.%0A%0AName:%0AAge:%0AGoal:%0ACity:" class="online-card oc3 ripple fade-up" style="transition-delay:0.15s">
      <div class="oi">🏆</div>
      <div class="ob">
        <div class="on">Elite Plan</div>
        <div class="os">3 Months · Advanced</div>
        <div class="ot">
          <span class="otag">Daily Check-ins</span>
          <span class="otag">CoachKit App</span>
          <span class="otag">Body Analysis</span>
          <span class="otag">24/7 Support</span>
        </div>
      </div>
      <div class="op">₹7,999<small>/ month</small></div>
    </a>

  </div>

  <div class="divider"></div>

  <!-- ══ PAYMENT ══ -->
  <div class="payment-section fade-up">
    <div class="sec-head" style="margin-bottom:16px">
      <div class="sec-icon">💳</div>
      <div>
        <h2>Pay Via PhonePe</h2>
        <p>Scan & pay instantly — secure UPI payment</p>
      </div>
    </div>
    <div class="payment-card">
      <div class="payment-title">Scan QR to Pay</div>
      <div class="payment-sub">Works with any UPI app — PhonePe, GPay, Paytm &amp; more</div>
      <div class="qr-wrap">
        <img src="/mnt/user-data/uploads/qr.jpeg" alt="PhonePe QR Code — Ankit Ashish Ingle">
      </div>
      <div class="payment-name">ANKIT ASHISH INGLE</div>
      <div><span class="phonepe-badge">pe PhonePe Accepted Here</span></div>
    </div>
  </div>

  <div class="divider"></div>

  <!-- ══ CONNECT ══ -->
  <div class="sec-head fade-up">
    <div class="sec-icon">🔗</div>
    <div>
      <h2>Connect With Me</h2>
      <p>Follow for daily tips, workouts &amp; motivation</p>
    </div>
  </div>

  <div class="social-grid">
    <a href="https://www.instagram.com/ankitingleofficial?igsh=MTZlbndpMG10bHY3OQ==" target="_blank" class="soc-card sc-ig ripple fade-up" style="transition-delay:0.05s">
      <div class="si">📸</div>
      <div>
        <div class="sn">Instagram</div>
        <div class="sh">@ankitingleofficial</div>
      </div>
    </a>
    <a href="https://youtube.com/@trainwithai21?si=G5G0zZOQAoYT4D5P" target="_blank" class="soc-card sc-yt ripple fade-up" style="transition-delay:0.1s">
      <div class="si">▶️</div>
      <div>
        <div class="sn">YouTube</div>
        <div class="sh">@trainwithai21</div>
      </div>
    </a>
    <a href="https://wa.me/91XXXXXXXXXX" target="_blank" class="soc-card sc-wa ripple fade-up" style="transition-delay:0.15s">
      <div class="si">💬</div>
      <div>
        <div class="sn">WhatsApp</div>
        <div class="sh">Join the community</div>
      </div>
    </a>
    <a href="mailto:coachankitingle@gmail.com" class="soc-card sc-em ripple fade-up" style="transition-delay:0.2s">
      <div class="si" style="font-size:18px">✉️</div>
      <div>
        <div class="sn">Email</div>
        <div class="sh">coachankitingle@gmail.com</div>
      </div>
    </a>
  </div>

  <!-- ══ FOOTER ══ -->
  <div class="footer fade-up">
    🇮🇳 &nbsp;Based in Nashik · Serving clients across India<br>
    © 2025 <a href="#">Coach Ankit Ingle</a> · All rights reserved
  </div>

</div>

<script>
// Scroll reveal
const els = document.querySelectorAll('.fade-up:not(.visible)');
const obs = new IntersectionObserver(entries => {
  entries.forEach((e, i) => {
    if (e.isIntersecting) {
      setTimeout(() => e.target.classList.add('visible'), i * 70);
      obs.unobserve(e.target);
    }
  });
}, { threshold: 0.08 });
els.forEach(el => obs.observe(el));

// Ripple
document.querySelectorAll('.ripple').forEach(el => {
  el.addEventListener('click', function(e) {
    const r = document.createElement('span');
    r.classList.add('rip-el');
    const rect = this.getBoundingClientRect();
    const size = Math.max(rect.width, rect.height);
    r.style.cssText = `width:${size}px;height:${size}px;left:${e.clientX-rect.left-size/2}px;top:${e.clientY-rect.top-size/2}px`;
    this.appendChild(r);
    r.addEventListener('animationend', () => r.remove());
  });
});
</script>
</body>
</html>
