<!DOCTYPE html>
<html lang="de">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>SK Automation – Wir automatisieren Ihre Prozesse. In 48 Stunden.</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Syne:wght@400;500;600;700;800&family=DM+Sans:ital,wght@0,300;0,400;0,500;1,300&display=swap" rel="stylesheet">

<style>
/* ==========================================
   CSS VARIABLEN & RESET
   ========================================== */
:root {
  --bg: #050505;
  --bg2: #0a0a0f;
  --primary: #A855F7;
  --primary-dark: #7C3AED;
  --cyan: #06B6D4;
  --cyan-dark: #0891B2;
  --white: #FFFFFF;
  --gray: #9CA3AF;
  --gray-dark: #6B7280;
  --border: rgba(168, 85, 247, 0.15);
  --glass: rgba(255, 255, 255, 0.03);
  --glass-border: rgba(255, 255, 255, 0.08);
  --glow-purple: 0 0 40px rgba(168, 85, 247, 0.3);
  --glow-cyan: 0 0 40px rgba(6, 182, 212, 0.3);
  --font-display: 'Syne', sans-serif;
  --font-body: 'DM Sans', sans-serif;
  --transition: all 0.35s cubic-bezier(0.16, 1, 0.3, 1);
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

html { scroll-behavior: smooth; font-size: 16px; }

body {
  background: var(--bg);
  color: var(--white);
  font-family: var(--font-body);
  font-weight: 400;
  line-height: 1.65;
  overflow-x: hidden;
  -webkit-font-smoothing: antialiased;
}

/* ==========================================
   UTILITY KLASSEN
   ========================================== */
.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 24px;
}

.gradient-text {
  background: linear-gradient(135deg, var(--primary) 0%, var(--cyan) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.section-label {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  font-family: var(--font-display);
  font-size: 0.7rem;
  font-weight: 600;
  letter-spacing: 0.15em;
  text-transform: uppercase;
  color: var(--primary);
  background: rgba(168, 85, 247, 0.1);
  border: 1px solid rgba(168, 85, 247, 0.25);
  padding: 6px 14px;
  border-radius: 100px;
  margin-bottom: 20px;
}

.section-title {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 800;
  line-height: 1.1;
  letter-spacing: -0.02em;
  margin-bottom: 16px;
}

.section-subtitle {
  font-size: 1.05rem;
  color: var(--gray);
  max-width: 560px;
  line-height: 1.7;
}

section { padding: 100px 0; position: relative; }

/* Scroll-reveal Klassen */
.reveal {
  opacity: 0;
  transform: translateY(40px);
  transition: opacity 0.7s cubic-bezier(0.16, 1, 0.3, 1), transform 0.7s cubic-bezier(0.16, 1, 0.3, 1);
}
.reveal.visible {
  opacity: 1;
  transform: translateY(0);
}
.reveal-delay-1 { transition-delay: 0.1s; }
.reveal-delay-2 { transition-delay: 0.2s; }
.reveal-delay-3 { transition-delay: 0.3s; }
.reveal-delay-4 { transition-delay: 0.4s; }

/* Glassmorphism Karte */
.glass-card {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 20px;
  backdrop-filter: blur(20px);
  -webkit-backdrop-filter: blur(20px);
  padding: 32px;
  transition: var(--transition);
  position: relative;
  overflow: hidden;
}
.glass-card::before {
  content: '';
  position: absolute;
  inset: 0;
  border-radius: 20px;
  padding: 1px;
  background: linear-gradient(135deg, rgba(168,85,247,0.3), transparent 60%);
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  opacity: 0;
  transition: var(--transition);
}
.glass-card:hover::before { opacity: 1; }
.glass-card:hover {
  transform: translateY(-6px) scale(1.01);
  border-color: rgba(168, 85, 247, 0.3);
  box-shadow: var(--glow-purple);
}

/* ==========================================
   NAVIGATION
   ========================================== */
nav {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  padding: 16px 0;
  transition: var(--transition);
}
nav.scrolled {
  background: rgba(5, 5, 5, 0.85);
  backdrop-filter: blur(24px);
  -webkit-backdrop-filter: blur(24px);
  border-bottom: 1px solid var(--glass-border);
  padding: 12px 0;
}

.nav-inner {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 24px;
}

.nav-logo {
  font-family: var(--font-display);
  font-size: 1.3rem;
  font-weight: 800;
  letter-spacing: -0.02em;
  text-decoration: none;
  background: linear-gradient(135deg, var(--primary) 0%, var(--cyan) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  flex-shrink: 0;
}

.nav-links {
  display: flex;
  align-items: center;
  gap: 4px;
  list-style: none;
}
.nav-links a {
  display: block;
  padding: 8px 14px;
  color: var(--gray);
  text-decoration: none;
  font-size: 0.9rem;
  font-weight: 500;
  border-radius: 8px;
  transition: var(--transition);
}
.nav-links a:hover { color: var(--white); background: rgba(255,255,255,0.05); }

.btn-primary {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 11px 22px;
  background: linear-gradient(135deg, var(--primary) 0%, var(--cyan) 100%);
  color: var(--white);
  text-decoration: none;
  font-family: var(--font-display);
  font-size: 0.88rem;
  font-weight: 700;
  border-radius: 10px;
  border: none;
  cursor: pointer;
  transition: var(--transition);
  position: relative;
  overflow: hidden;
  white-space: nowrap;
}
.btn-primary::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(135deg, var(--cyan) 0%, var(--primary) 100%);
  opacity: 0;
  transition: var(--transition);
}
.btn-primary:hover::after { opacity: 1; }
.btn-primary span { position: relative; z-index: 1; }
.btn-primary:hover { transform: translateY(-2px); box-shadow: 0 8px 30px rgba(168,85,247,0.4); }

.btn-outline {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  padding: 11px 22px;
  background: transparent;
  color: var(--white);
  text-decoration: none;
  font-family: var(--font-display);
  font-size: 0.88rem;
  font-weight: 700;
  border-radius: 10px;
  border: 1px solid rgba(255,255,255,0.2);
  cursor: pointer;
  transition: var(--transition);
  white-space: nowrap;
}
.btn-outline:hover {
  border-color: var(--primary);
  color: var(--primary);
  background: rgba(168,85,247,0.07);
  transform: translateY(-2px);
}

/* Hamburger */
.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  background: none;
  border: none;
  cursor: pointer;
  padding: 4px;
  z-index: 1001;
}
.hamburger span {
  display: block;
  width: 24px;
  height: 2px;
  background: var(--white);
  border-radius: 2px;
  transition: var(--transition);
}
.hamburger.active span:nth-child(1) { transform: translateY(7px) rotate(45deg); }
.hamburger.active span:nth-child(2) { opacity: 0; }
.hamburger.active span:nth-child(3) { transform: translateY(-7px) rotate(-45deg); }

/* Mobile Nav */
.mobile-nav {
  display: none;
  position: fixed;
  inset: 0;
  z-index: 999;
  background: rgba(5,5,5,0.98);
  backdrop-filter: blur(30px);
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 12px;
  opacity: 0;
  pointer-events: none;
  transition: opacity 0.3s ease;
}
.mobile-nav.open {
  display: flex;
  opacity: 1;
  pointer-events: all;
}
.mobile-nav a {
  font-family: var(--font-display);
  font-size: 2rem;
  font-weight: 700;
  color: var(--white);
  text-decoration: none;
  transition: var(--transition);
}
.mobile-nav a:hover { color: var(--primary); }

/* ==========================================
   HERO SECTION
   ========================================== */
#hero {
  min-height: 100vh;
  display: flex;
  align-items: center;
  padding: 140px 0 100px;
  position: relative;
  overflow: hidden;
}

/* Animated Blobs */
.blob {
  position: absolute;
  border-radius: 50%;
  filter: blur(100px);
  animation: blobFloat 8s ease-in-out infinite;
  pointer-events: none;
}
.blob-1 {
  width: 600px; height: 600px;
  background: rgba(168, 85, 247, 0.12);
  top: -100px; left: -200px;
  animation-delay: 0s;
}
.blob-2 {
  width: 500px; height: 500px;
  background: rgba(6, 182, 212, 0.1);
  top: 100px; right: -150px;
  animation-delay: -3s;
}
.blob-3 {
  width: 400px; height: 400px;
  background: rgba(168, 85, 247, 0.08);
  bottom: -100px; left: 30%;
  animation-delay: -6s;
}

@keyframes blobFloat {
  0%, 100% { transform: translate(0, 0) scale(1); }
  33% { transform: translate(30px, -50px) scale(1.05); }
  66% { transform: translate(-20px, 30px) scale(0.95); }
}

/* Grid overlay */
#hero::after {
  content: '';
  position: absolute;
  inset: 0;
  background-image:
    linear-gradient(rgba(168,85,247,0.04) 1px, transparent 1px),
    linear-gradient(90deg, rgba(168,85,247,0.04) 1px, transparent 1px);
  background-size: 60px 60px;
  pointer-events: none;
  mask-image: radial-gradient(ellipse 80% 80% at 50% 50%, black 40%, transparent 100%);
}

.hero-content { position: relative; z-index: 1; }

.hero-badge {
  display: inline-flex;
  align-items: center;
  gap: 8px;
  background: rgba(168,85,247,0.1);
  border: 1px solid rgba(168,85,247,0.3);
  border-radius: 100px;
  padding: 8px 18px;
  font-size: 0.82rem;
  font-weight: 500;
  color: var(--white);
  margin-bottom: 32px;
  animation: badgePulse 3s ease-in-out infinite;
}
@keyframes badgePulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(168,85,247,0.3); }
  50% { box-shadow: 0 0 0 8px rgba(168,85,247,0); }
}

.hero-headline {
  font-family: var(--font-display);
  font-size: clamp(3rem, 7vw, 5.5rem);
  font-weight: 800;
  line-height: 1.0;
  letter-spacing: -0.03em;
  margin-bottom: 28px;
}

.hero-sub {
  font-size: 1.1rem;
  color: var(--gray);
  max-width: 560px;
  line-height: 1.75;
  margin-bottom: 40px;
}

.hero-buttons {
  display: flex;
  flex-wrap: wrap;
  gap: 14px;
  margin-bottom: 56px;
}

.trust-badges {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  align-items: center;
}
.trust-badge {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 0.82rem;
  font-weight: 500;
  color: var(--gray);
}
.trust-badge-dot {
  width: 6px; height: 6px;
  border-radius: 50%;
  background: var(--primary);
  flex-shrink: 0;
}

/* ==========================================
   STATS BAR
   ========================================== */
#stats {
  padding: 0 0 100px;
}

.stats-card {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 20px;
  padding: 40px;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 0;
  position: relative;
  overflow: hidden;
}
.stats-card::before {
  content: '';
  position: absolute;
  top: 0; left: 0; right: 0;
  height: 1px;
  background: linear-gradient(90deg, transparent, var(--primary), var(--cyan), transparent);
}

.stat-item {
  text-align: center;
  padding: 16px 20px;
  position: relative;
}
.stat-item:not(:last-child)::after {
  content: '';
  position: absolute;
  right: 0; top: 20%; bottom: 20%;
  width: 1px;
  background: var(--glass-border);
}
.stat-number {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3vw, 2.5rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  background: linear-gradient(135deg, var(--primary) 0%, var(--cyan) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: block;
  margin-bottom: 4px;
}
.stat-label {
  font-size: 0.82rem;
  color: var(--gray);
  font-weight: 500;
}

/* ==========================================
   TOOLS SECTION
   ========================================== */
#tools { padding: 80px 0; overflow: hidden; }

.tools-header { text-align: center; margin-bottom: 48px; }

.marquee-wrapper {
  position: relative;
  overflow: hidden;
}
.marquee-wrapper::before,
.marquee-wrapper::after {
  content: '';
  position: absolute;
  top: 0; bottom: 0;
  width: 120px;
  z-index: 2;
}
.marquee-wrapper::before { left: 0; background: linear-gradient(to right, var(--bg), transparent); }
.marquee-wrapper::after { right: 0; background: linear-gradient(to left, var(--bg), transparent); }

.marquee-track {
  display: flex;
  gap: 20px;
  animation: marquee 25s linear infinite;
  width: max-content;
}
.marquee-track:hover { animation-play-state: paused; }

@keyframes marquee {
  0% { transform: translateX(0); }
  100% { transform: translateX(-50%); }
}

.tool-pill {
  display: flex;
  align-items: center;
  gap: 10px;
  padding: 14px 24px;
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 100px;
  font-family: var(--font-display);
  font-size: 0.9rem;
  font-weight: 600;
  color: var(--gray);
  white-space: nowrap;
  transition: var(--transition);
  cursor: default;
}
.tool-pill:hover {
  color: var(--white);
  border-color: rgba(168,85,247,0.4);
  background: rgba(168,85,247,0.08);
}
.tool-emoji { font-size: 1.2rem; }

/* ==========================================
   PROBLEM SECTION
   ========================================== */
#problem { background: var(--bg2); }

.problem-header { text-align: center; margin-bottom: 56px; }

.problem-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  margin-bottom: 48px;
}

.problem-card {
  background: rgba(239, 68, 68, 0.04);
  border: 1px solid rgba(239, 68, 68, 0.2);
  border-radius: 20px;
  padding: 32px;
  transition: var(--transition);
}
.problem-card:hover {
  border-color: rgba(239, 68, 68, 0.4);
  background: rgba(239, 68, 68, 0.07);
  transform: translateY(-4px);
}

.problem-icon {
  width: 44px; height: 44px;
  border-radius: 50%;
  background: rgba(239,68,68,0.15);
  display: flex; align-items: center; justify-content: center;
  font-size: 1.1rem;
  margin-bottom: 20px;
  color: #ef4444;
  font-weight: 700;
}

.problem-card h3 {
  font-family: var(--font-display);
  font-size: 1rem;
  font-weight: 700;
  color: var(--white);
  line-height: 1.4;
}

.problem-arrow {
  text-align: center;
}
.arrow-down {
  display: inline-flex;
  flex-direction: column;
  align-items: center;
  gap: 8px;
  color: var(--primary);
  font-family: var(--font-display);
  font-weight: 700;
  font-size: 0.95rem;
}
.arrow-icon {
  font-size: 2rem;
  animation: arrowBounce 2s ease-in-out infinite;
}
@keyframes arrowBounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(8px); }
}

/* ==========================================
   SERVICES SECTION
   ========================================== */
#services { }

.services-header { text-align: center; margin-bottom: 56px; }

.services-grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
  gap: 20px;
}

.service-card {
  position: relative;
  overflow: hidden;
  padding: 36px;
}

.service-card::after {
  content: '';
  position: absolute;
  bottom: 0; left: 0; right: 0;
  height: 2px;
  background: linear-gradient(90deg, var(--primary), var(--cyan));
  transform: scaleX(0);
  transition: var(--transition);
  transform-origin: left;
}
.service-card:hover::after { transform: scaleX(1); }

.service-icon {
  font-size: 2.2rem;
  margin-bottom: 20px;
  display: block;
}

.service-badge {
  display: inline-block;
  padding: 4px 12px;
  background: rgba(168,85,247,0.15);
  border: 1px solid rgba(168,85,247,0.3);
  border-radius: 100px;
  font-size: 0.75rem;
  font-weight: 700;
  color: var(--primary);
  font-family: var(--font-display);
  margin-bottom: 16px;
}

.service-badge.gold {
  background: rgba(251,191,36,0.12);
  border-color: rgba(251,191,36,0.3);
  color: #FBBF24;
}

.premium-label {
  position: absolute;
  top: 24px; right: 24px;
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  color: white;
  font-size: 0.65rem;
  font-weight: 800;
  letter-spacing: 0.08em;
  font-family: var(--font-display);
  padding: 4px 10px;
  border-radius: 6px;
}

.service-card h3 {
  font-family: var(--font-display);
  font-size: 1.2rem;
  font-weight: 700;
  margin-bottom: 10px;
}

.service-card p {
  font-size: 0.92rem;
  color: var(--gray);
  line-height: 1.65;
}

/* ==========================================
   HOW IT WORKS
   ========================================== */
#how { background: var(--bg2); }
.how-header { text-align: center; margin-bottom: 64px; }

.steps-wrapper {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 0;
  position: relative;
}
.steps-wrapper::before {
  content: '';
  position: absolute;
  top: 32px; left: 16.66%; right: 16.66%;
  height: 1px;
  background: linear-gradient(90deg, var(--primary), var(--cyan));
}

.step {
  text-align: center;
  padding: 0 24px;
  position: relative;
}

.step-num {
  width: 64px; height: 64px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-display);
  font-size: 1.3rem;
  font-weight: 800;
  color: white;
  margin: 0 auto 28px;
  position: relative;
  z-index: 1;
  box-shadow: 0 0 30px rgba(168,85,247,0.4);
}

.step-emoji { font-size: 1.5rem; margin-bottom: 14px; display: block; }

.step h3 {
  font-family: var(--font-display);
  font-size: 1.05rem;
  font-weight: 700;
  margin-bottom: 10px;
}
.step p { font-size: 0.9rem; color: var(--gray); }

/* ==========================================
   PRICING SECTION
   ========================================== */
#pricing { }
.pricing-header { text-align: center; margin-bottom: 56px; }

.pricing-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
  align-items: start;
}

.pricing-card {
  padding: 36px;
  position: relative;
}

.pricing-card.featured {
  background: linear-gradient(135deg, rgba(168,85,247,0.12), rgba(6,182,212,0.08));
  border-color: rgba(168,85,247,0.4);
  transform: scale(1.03);
  box-shadow: var(--glow-purple);
}

.pricing-card.ai-card {
  border-color: rgba(251,191,36,0.3);
  background: rgba(251,191,36,0.03);
}

.popular-badge {
  position: absolute;
  top: -14px; left: 50%;
  transform: translateX(-50%);
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  color: white;
  font-family: var(--font-display);
  font-size: 0.7rem;
  font-weight: 800;
  letter-spacing: 0.1em;
  padding: 5px 16px;
  border-radius: 100px;
}

.pricing-name {
  font-family: var(--font-display);
  font-size: 0.8rem;
  font-weight: 700;
  letter-spacing: 0.12em;
  text-transform: uppercase;
  color: var(--gray);
  margin-bottom: 12px;
}

.pricing-price {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 2.8rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  margin-bottom: 4px;
  background: linear-gradient(135deg, var(--white) 0%, var(--gray) 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.pricing-card.featured .pricing-price {
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  -webkit-background-clip: text;
  background-clip: text;
}

.pricing-card.ai-card .pricing-price {
  background: linear-gradient(135deg, #FBBF24, #F59E0B);
  -webkit-background-clip: text;
  background-clip: text;
}

.pricing-period {
  font-size: 0.82rem;
  color: var(--gray);
  margin-bottom: 28px;
}

.pricing-divider {
  height: 1px;
  background: var(--glass-border);
  margin-bottom: 24px;
}

.pricing-features { list-style: none; margin-bottom: 32px; }
.pricing-features li {
  display: flex;
  align-items: flex-start;
  gap: 10px;
  font-size: 0.88rem;
  color: var(--gray);
  padding: 6px 0;
}
.pricing-features li.yes { color: var(--white); }
.check { color: var(--primary); font-weight: 700; flex-shrink: 0; margin-top: 1px; }
.cross { color: var(--gray-dark); flex-shrink: 0; margin-top: 1px; }

.pricing-btn {
  width: 100%;
  text-align: center;
  justify-content: center;
  border-radius: 12px;
  padding: 13px 20px;
  font-size: 0.9rem;
}

.pricing-btn-featured {
  width: 100%;
  text-align: center;
  justify-content: center;
  padding: 13px 20px;
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  color: white;
  border: none;
  cursor: pointer;
  border-radius: 12px;
  font-family: var(--font-display);
  font-size: 0.9rem;
  font-weight: 700;
  transition: var(--transition);
  text-decoration: none;
  display: block;
}
.pricing-btn-featured:hover {
  transform: translateY(-2px);
  box-shadow: var(--glow-purple);
}

/* ==========================================
   CASE STUDY
   ========================================== */
#case { background: var(--bg2); }
.case-header { text-align: center; margin-bottom: 48px; }

.case-card {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0;
  overflow: hidden;
  padding: 0;
}

.case-left {
  padding: 48px;
  border-right: 1px solid var(--glass-border);
}

.case-tag {
  display: inline-block;
  padding: 4px 12px;
  background: rgba(6,182,212,0.1);
  border: 1px solid rgba(6,182,212,0.3);
  border-radius: 6px;
  font-size: 0.72rem;
  font-weight: 700;
  color: var(--cyan);
  font-family: var(--font-display);
  letter-spacing: 0.08em;
  text-transform: uppercase;
  margin-bottom: 20px;
}

.case-left h3 {
  font-family: var(--font-display);
  font-size: 1.3rem;
  font-weight: 700;
  margin-bottom: 20px;
  line-height: 1.3;
}

.case-left p { font-size: 0.92rem; color: var(--gray); line-height: 1.7; margin-bottom: 16px; }

.case-right {
  padding: 48px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  gap: 32px;
  background: rgba(168,85,247,0.03);
}

.case-metric { text-align: center; }

.case-metric-number {
  font-family: var(--font-display);
  font-size: clamp(2rem, 4vw, 3rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  display: block;
  margin-bottom: 4px;
}
.case-metric-number.purple { color: var(--primary); }
.case-metric-number.cyan { color: var(--cyan); }
.case-metric-number.white { color: var(--white); }

.case-metric-label { font-size: 0.82rem; color: var(--gray); }

/* ==========================================
   TESTIMONIALS
   ========================================== */
#testimonials { }
.test-header { text-align: center; margin-bottom: 56px; }

.test-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 20px;
}

.test-card { padding: 32px; }

.stars { color: #FBBF24; font-size: 0.95rem; margin-bottom: 18px; letter-spacing: 2px; }

.test-quote {
  font-size: 0.95rem;
  color: var(--gray);
  line-height: 1.7;
  margin-bottom: 24px;
  font-style: italic;
}

.test-author {
  display: flex;
  align-items: center;
  gap: 12px;
}

.test-avatar {
  width: 42px; height: 42px;
  border-radius: 50%;
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  display: flex; align-items: center; justify-content: center;
  font-family: var(--font-display);
  font-size: 0.85rem;
  font-weight: 700;
  color: white;
  flex-shrink: 0;
}

.test-name {
  font-family: var(--font-display);
  font-size: 0.88rem;
  font-weight: 700;
  color: var(--white);
}
.test-role { font-size: 0.78rem; color: var(--gray); }

/* ==========================================
   ABOUT SECTION
   ========================================== */
#about { background: var(--bg2); }
.about-header { margin-bottom: 56px; }

.about-grid {
  display: grid;
  grid-template-columns: 1fr 2fr;
  gap: 64px;
  align-items: center;
}

.about-avatar-wrap {
  position: relative;
  text-align: center;
}

.about-avatar {
  width: 200px; height: 200px;
  border-radius: 50%;
  background: linear-gradient(135deg, rgba(168,85,247,0.3), rgba(6,182,212,0.3));
  display: flex; align-items: center; justify-content: center;
  font-size: 5rem;
  margin: 0 auto 16px;
  position: relative;
  border: 2px solid rgba(168,85,247,0.4);
  box-shadow: 0 0 60px rgba(168,85,247,0.3);
  animation: avatarGlow 4s ease-in-out infinite;
}
@keyframes avatarGlow {
  0%, 100% { box-shadow: 0 0 60px rgba(168,85,247,0.3); }
  50% { box-shadow: 0 0 80px rgba(168,85,247,0.5), 0 0 120px rgba(6,182,212,0.2); }
}

.about-name {
  font-family: var(--font-display);
  font-size: 1rem;
  font-weight: 700;
  color: var(--white);
}
.about-loc { font-size: 0.82rem; color: var(--gray); }

.about-text h2 {
  font-family: var(--font-display);
  font-size: clamp(1.8rem, 3vw, 2.5rem);
  font-weight: 800;
  letter-spacing: -0.02em;
  margin-bottom: 20px;
  line-height: 1.15;
}
.about-text p {
  font-size: 0.95rem;
  color: var(--gray);
  line-height: 1.75;
  margin-bottom: 16px;
  max-width: 520px;
}

.about-badges {
  display: flex;
  flex-wrap: wrap;
  gap: 10px;
  margin-top: 28px;
}
.about-badge {
  display: inline-flex;
  align-items: center;
  gap: 7px;
  padding: 8px 16px;
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 8px;
  font-size: 0.82rem;
  font-weight: 600;
  color: var(--gray);
}

/* ==========================================
   FAQ SECTION
   ========================================== */
#faq { }
.faq-header { text-align: center; margin-bottom: 56px; }

.faq-list {
  max-width: 760px;
  margin: 0 auto;
  display: flex;
  flex-direction: column;
  gap: 12px;
}

.faq-item {
  background: var(--glass);
  border: 1px solid var(--glass-border);
  border-radius: 14px;
  overflow: hidden;
  transition: var(--transition);
}
.faq-item.open {
  border-color: rgba(168,85,247,0.3);
}

.faq-question {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 16px;
  padding: 22px 24px;
  background: none;
  border: none;
  cursor: pointer;
  text-align: left;
  color: var(--white);
  font-family: var(--font-display);
  font-size: 0.95rem;
  font-weight: 600;
  transition: var(--transition);
}
.faq-question:hover { color: var(--primary); }

.faq-icon {
  width: 28px; height: 28px;
  border-radius: 50%;
  border: 1px solid rgba(168,85,247,0.3);
  display: flex; align-items: center; justify-content: center;
  flex-shrink: 0;
  transition: var(--transition);
  font-size: 0.75rem;
  color: var(--primary);
}
.faq-item.open .faq-icon { background: var(--primary); color: white; transform: rotate(45deg); }

.faq-answer {
  max-height: 0;
  overflow: hidden;
  transition: max-height 0.4s cubic-bezier(0.16, 1, 0.3, 1);
}
.faq-item.open .faq-answer { max-height: 200px; }

.faq-answer-inner {
  padding: 0 24px 22px;
  font-size: 0.9rem;
  color: var(--gray);
  line-height: 1.7;
}

/* ==========================================
   CONTACT / CTA SECTION
   ========================================== */
#contact {
  background: var(--bg2);
  text-align: center;
  overflow: hidden;
}

.cta-inner {
  position: relative;
  max-width: 700px;
  margin: 0 auto;
}

.cta-glow {
  position: absolute;
  width: 400px; height: 400px;
  border-radius: 50%;
  background: radial-gradient(circle, rgba(168,85,247,0.2) 0%, transparent 70%);
  top: 50%; left: 50%;
  transform: translate(-50%, -50%);
  pointer-events: none;
  animation: ctaGlow 4s ease-in-out infinite;
}
@keyframes ctaGlow {
  0%, 100% { transform: translate(-50%, -50%) scale(1); opacity: 0.5; }
  50% { transform: translate(-50%, -50%) scale(1.2); opacity: 1; }
}

.cta-title {
  font-family: var(--font-display);
  font-size: clamp(2.5rem, 5vw, 4rem);
  font-weight: 800;
  letter-spacing: -0.03em;
  margin-bottom: 20px;
  line-height: 1.05;
  position: relative;
}
.cta-sub {
  font-size: 1.05rem;
  color: var(--gray);
  margin-bottom: 40px;
  position: relative;
}
.cta-btn {
  font-size: 1.05rem;
  padding: 16px 40px;
  border-radius: 14px;
  position: relative;
  box-shadow: 0 0 0 0 rgba(168,85,247,0.4);
  animation: ctaBtnPulse 3s ease-in-out infinite;
}
@keyframes ctaBtnPulse {
  0%, 100% { box-shadow: 0 0 0 0 rgba(168,85,247,0); }
  50% { box-shadow: 0 0 40px 10px rgba(168,85,247,0.3); }
}

.cta-email {
  margin-top: 24px;
  font-size: 0.88rem;
  color: var(--gray);
  position: relative;
}
.cta-email a {
  color: var(--primary);
  text-decoration: none;
  font-weight: 500;
}
.cta-email a:hover { color: var(--cyan); }

/* ==========================================
   FOOTER
   ========================================== */
footer {
  padding: 48px 0 32px;
  border-top: 1px solid var(--glass-border);
}

.footer-inner {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 28px;
  text-align: center;
}

.footer-logo {
  font-family: var(--font-display);
  font-size: 1.2rem;
  font-weight: 800;
  text-decoration: none;
  background: linear-gradient(135deg, var(--primary), var(--cyan));
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.footer-tagline {
  font-size: 0.82rem;
  color: var(--gray);
  margin-top: 4px;
}

.footer-links {
  display: flex;
  flex-wrap: wrap;
  gap: 24px;
  list-style: none;
  justify-content: center;
}
.footer-links a {
  color: var(--gray);
  text-decoration: none;
  font-size: 0.88rem;
  transition: var(--transition);
}
.footer-links a:hover { color: var(--white); }

.footer-socials {
  display: flex;
  gap: 12px;
}

.social-btn {
  display: flex; align-items: center; justify-content: center;
  width: 40px; height: 40px;
  border-radius: 10px;
  background: var(--glass);
  border: 1px solid var(--glass-border);
  color: var(--gray);
  text-decoration: none;
  font-size: 0.85rem;
  font-weight: 700;
  transition: var(--transition);
}
.social-btn:hover {
  color: var(--white);
  border-color: rgba(168,85,247,0.4);
  background: rgba(168,85,247,0.1);
}

.footer-copy {
  font-size: 0.8rem;
  color: var(--gray-dark);
}

/* ==========================================
   FLOATING BUTTONS
   ========================================== */
.floating-wa {
  position: fixed;
  bottom: 28px; right: 28px;
  z-index: 998;
  width: 58px; height: 58px;
  border-radius: 50%;
  background: #25D366;
  display: flex; align-items: center; justify-content: center;
  text-decoration: none;
  font-size: 1.6rem;
  box-shadow: 0 4px 20px rgba(37,211,102,0.4);
  transition: var(--transition);
  animation: waPulse 3s ease-in-out infinite;
}
@keyframes waPulse {
  0%, 100% { box-shadow: 0 4px 20px rgba(37,211,102,0.4); }
  50% { box-shadow: 0 4px 40px rgba(37,211,102,0.7); }
}
.floating-wa:hover { transform: scale(1.1); }

.back-top {
  position: fixed;
  bottom: 96px; right: 28px;
  z-index: 998;
  width: 44px; height: 44px;
  border-radius: 12px;
  background: var(--glass);
  border: 1px solid var(--glass-border);
  display: flex; align-items: center; justify-content: center;
  cursor: pointer;
  color: var(--gray);
  font-size: 1rem;
  transition: var(--transition);
  opacity: 0;
  pointer-events: none;
}
.back-top.visible {
  opacity: 1;
  pointer-events: all;
}
.back-top:hover {
  color: var(--white);
  border-color: rgba(168,85,247,0.4);
  background: rgba(168,85,247,0.1);
}

/* ==========================================
   RESPONSIVE
   ========================================== */
@media (max-width: 1024px) {
  .pricing-card.featured { transform: scale(1); }
  .about-grid { grid-template-columns: 1fr; gap: 40px; }
  .about-avatar { width: 160px; height: 160px; }
  .about-avatar-wrap { display: flex; align-items: center; gap: 24px; text-align: left; }
}

@media (max-width: 768px) {
  .nav-links { display: none; }
  .nav-cta { display: none; }
  .hamburger { display: flex; }

  section { padding: 72px 0; }

  .hero-headline { font-size: clamp(2.5rem, 8vw, 3.5rem); }

  .stats-card { grid-template-columns: repeat(2, 1fr); }
  .stat-item:nth-child(2)::after { display: none; }
  .stat-item:nth-child(4)::after { display: none; }

  .problem-grid { grid-template-columns: 1fr; }
  .services-grid { grid-template-columns: 1fr; }
  .steps-wrapper { grid-template-columns: 1fr; gap: 32px; }
  .steps-wrapper::before { display: none; }
  .pricing-grid { grid-template-columns: 1fr; }
  .case-card { grid-template-columns: 1fr; }
  .case-left { border-right: none; border-bottom: 1px solid var(--glass-border); }
  .test-grid { grid-template-columns: 1fr; }
  .about-avatar-wrap { flex-direction: column; text-align: center; }

  .hero-buttons { flex-direction: column; }
  .btn-primary, .btn-outline { justify-content: center; }
}

@media (max-width: 480px) {
  .stats-card { grid-template-columns: repeat(2, 1fr); padding: 24px 16px; }
  .trust-badges { gap: 12px; }
}
</style>
</head>
<body>

<!-- ==========================================
     NAVIGATION
     ========================================== -->
<nav id="navbar">
  <div class="container">
    <div class="nav-inner">
      <a href="#hero" class="nav-logo">SK Automation</a>

      <ul class="nav-links">
        <li><a href="#services">Leistungen</a></li>
        <li><a href="#pricing">Preise</a></li>
        <li><a href="#testimonials">Projekte</a></li>
        <li><a href="#about">Über mich</a></li>
        <li><a href="#contact">Kontakt</a></li>
      </ul>

      <a href="#contact" class="btn-primary nav-cta">
        <span>Kostenlose Demo</span>
      </a>

      <button class="hamburger" id="hamburger" aria-label="Menü öffnen">
        <span></span><span></span><span></span>
      </button>
    </div>
  </div>
</nav>

<!-- Mobile Navigation -->
<div class="mobile-nav" id="mobileNav">
  <a href="#services" onclick="closeMobile()">Leistungen</a>
  <a href="#pricing" onclick="closeMobile()">Preise</a>
  <a href="#testimonials" onclick="closeMobile()">Projekte</a>
  <a href="#about" onclick="closeMobile()">Über mich</a>
  <a href="#contact" onclick="closeMobile()">Kontakt</a>
  <a href="#contact" onclick="closeMobile()" class="btn-primary" style="margin-top:16px; font-size:1rem; padding:14px 32px;">Demo buchen</a>
</div>

<!-- ==========================================
     HERO SECTION
     ========================================== -->
<section id="hero">
  <!-- Animated Blobs -->
  <div class="blob blob-1"></div>
  <div class="blob blob-2"></div>
  <div class="blob blob-3"></div>

  <div class="container">
    <div class="hero-content">
      <!-- Badge -->
      <div class="hero-badge reveal">
        🔥 Nur noch 2 Plätze im März verfügbar
      </div>

      <!-- Headline -->
      <h1 class="hero-headline reveal reveal-delay-1">
        Wir automatisieren<br>
        <span class="gradient-text">Ihre Prozesse.</span><br>
        In 48 Stunden.
      </h1>

      <!-- Subtext -->
      <p class="hero-sub reveal reveal-delay-2">
        Mit n8n und KI bauen wir Workflows die manuelle Arbeit eliminieren –<br>
        100% DSGVO-konform, Made in Germany.
      </p>

      <!-- Buttons -->
      <div class="hero-buttons reveal reveal-delay-3">
        <a href="#contact" class="btn-primary">
          <span>Kostenlose Demo buchen →</span>
        </a>
        <a href="#services" class="btn-outline">Workflows ansehen</a>
      </div>

      <!-- Trust Badges -->
      <div class="trust-badges reveal reveal-delay-4">
        <div class="trust-badge"><div class="trust-badge-dot"></div> ⚡ 48h Lieferzeit</div>
        <div class="trust-badge"><div class="trust-badge-dot"></div> 🔒 DSGVO-konform</div>
        <div class="trust-badge"><div class="trust-badge-dot"></div> 🇩🇪 Made in Germany</div>
        <div class="trust-badge"><div class="trust-badge-dot"></div> ⭐ 5-Sterne Support</div>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     STATS BAR
     ========================================== -->
<section id="stats">
  <div class="container">
    <div class="stats-card reveal">
      <div class="stat-item">
        <span class="stat-number" data-target="50" data-suffix="+">0</span>
        <span class="stat-label">Workflows geliefert</span>
      </div>
      <div class="stat-item">
        <span class="stat-number" data-target="200" data-suffix="+">0</span>
        <span class="stat-label">Stunden pro Monat gespart</span>
      </div>
      <div class="stat-item">
        <span class="stat-number" data-target="100" data-suffix="%">0</span>
        <span class="stat-label">DSGVO-konform</span>
      </div>
      <div class="stat-item">
        <span class="stat-number" data-target="48" data-suffix="h">0</span>
        <span class="stat-label">Durchschnittliche Lieferzeit</span>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     TOOLS SECTION
     ========================================== -->
<section id="tools">
  <div class="container">
    <div class="tools-header reveal">
      <div class="section-label">Stack</div>
      <h2 class="section-title">Tools die ich <span class="gradient-text">beherrsche</span></h2>
    </div>
  </div>

  <div class="marquee-wrapper">
    <div class="marquee-track">
      <!-- Doppelt für seamless loop -->
      <div class="tool-pill"><span class="tool-emoji">⚙️</span> n8n</div>
      <div class="tool-pill"><span class="tool-emoji">🤖</span> OpenAI / GPT-4</div>
      <div class="tool-pill"><span class="tool-emoji">📊</span> Google Sheets</div>
      <div class="tool-pill"><span class="tool-emoji">💬</span> Slack</div>
      <div class="tool-pill"><span class="tool-emoji">📧</span> Gmail</div>
      <div class="tool-pill"><span class="tool-emoji">🟠</span> HubSpot</div>
      <div class="tool-pill"><span class="tool-emoji">⚡</span> Zapier</div>
      <div class="tool-pill"><span class="tool-emoji">🔮</span> Make.com</div>
      <div class="tool-pill"><span class="tool-emoji">🗄️</span> Airtable</div>
      <div class="tool-pill"><span class="tool-emoji">📅</span> Google Calendar</div>
      <div class="tool-pill"><span class="tool-emoji">🌐</span> Webhook</div>
      <div class="tool-pill"><span class="tool-emoji">🔔</span> Telegram Bot</div>
      <!-- Dupliziert -->
      <div class="tool-pill"><span class="tool-emoji">⚙️</span> n8n</div>
      <div class="tool-pill"><span class="tool-emoji">🤖</span> OpenAI / GPT-4</div>
      <div class="tool-pill"><span class="tool-emoji">📊</span> Google Sheets</div>
      <div class="tool-pill"><span class="tool-emoji">💬</span> Slack</div>
      <div class="tool-pill"><span class="tool-emoji">📧</span> Gmail</div>
      <div class="tool-pill"><span class="tool-emoji">🟠</span> HubSpot</div>
      <div class="tool-pill"><span class="tool-emoji">⚡</span> Zapier</div>
      <div class="tool-pill"><span class="tool-emoji">🔮</span> Make.com</div>
      <div class="tool-pill"><span class="tool-emoji">🗄️</span> Airtable</div>
      <div class="tool-pill"><span class="tool-emoji">📅</span> Google Calendar</div>
      <div class="tool-pill"><span class="tool-emoji">🌐</span> Webhook</div>
      <div class="tool-pill"><span class="tool-emoji">🔔</span> Telegram Bot</div>
    </div>
  </div>
</section>

<!-- ==========================================
     PROBLEM SECTION
     ========================================== -->
<section id="problem">
  <div class="container">
    <div class="problem-header reveal">
      <div class="section-label">Das Problem</div>
      <h2 class="section-title">Kennen Sie <span class="gradient-text">das?</span></h2>
      <p class="section-subtitle" style="margin: 0 auto;">Diese Probleme kosten täglich Stunden Ihrer wertvollen Arbeitszeit.</p>
    </div>

    <div class="problem-grid">
      <div class="problem-card reveal">
        <div class="problem-icon">✕</div>
        <h3>Leads gehen verloren weil Antworten zu langsam kommen</h3>
      </div>
      <div class="problem-card reveal reveal-delay-1">
        <div class="problem-icon">✕</div>
        <h3>Stunden täglich mit manueller Dateneingabe verschwenden</h3>
      </div>
      <div class="problem-card reveal reveal-delay-2">
        <div class="problem-icon">✕</div>
        <h3>Kein Überblick wer wann was angefragt hat</h3>
      </div>
    </div>

    <div class="problem-arrow reveal">
      <div class="arrow-down">
        <span>Wir lösen genau das</span>
        <span class="arrow-icon">↓</span>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     SERVICES SECTION
     ========================================== -->
<section id="services">
  <div class="container">
    <div class="services-header reveal">
      <div class="section-label">Leistungen</div>
      <h2 class="section-title">Meine <span class="gradient-text">Leistungen</span></h2>
      <p class="section-subtitle">Individuelle Automatisierungslösungen für jede Unternehmensgröße.</p>
    </div>

    <div class="services-grid">
      <!-- Card 1 -->
      <div class="glass-card service-card reveal">
        <span class="service-icon">🔥</span>
        <div class="service-badge">Ab 399 €</div>
        <h3>Lead Automation</h3>
        <p>Jede Anfrage landet automatisch in Ihrem CRM + Slack in Echtzeit. Kein Lead geht mehr verloren.</p>
      </div>

      <!-- Card 2 -->
      <div class="glass-card service-card reveal reveal-delay-1" style="border-color: rgba(168,85,247,0.3);">
        <div class="premium-label">PREMIUM</div>
        <span class="service-icon">🤖</span>
        <div class="service-badge">Ab 3.000 €</div>
        <h3>AI Sales Agent</h3>
        <p>KI analysiert Leads, bewertet sie mit einem Score und schreibt personalisierte E-Mails automatisch.</p>
      </div>

      <!-- Card 3 -->
      <div class="glass-card service-card reveal reveal-delay-2">
        <span class="service-icon">🛒</span>
        <div class="service-badge">Ab 1.500 €</div>
        <h3>E-Commerce Automation</h3>
        <p>Lagerbestand, Bestellungen, Abandoned Cart – alles läuft automatisiert ohne manuelle Eingriffe.</p>
      </div>

      <!-- Card 4 -->
      <div class="glass-card service-card reveal reveal-delay-3">
        <span class="service-icon">🔧</span>
        <div class="service-badge">Ab 299 €/Monat</div>
        <h3>Retainer & Wartung</h3>
        <p>Monatliche Wartung, Optimierung und Erweiterung Ihrer bestehenden Workflows. Immer auf dem neuesten Stand.</p>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     HOW IT WORKS
     ========================================== -->
<section id="how">
  <div class="container">
    <div class="how-header reveal">
      <div class="section-label">Der Prozess</div>
      <h2 class="section-title">So einfach <span class="gradient-text">funktioniert es</span></h2>
      <p class="section-subtitle" style="margin: 0 auto;">Von der Idee zum laufenden Workflow in drei Schritten.</p>
    </div>

    <div class="steps-wrapper">
      <div class="step reveal">
        <div class="step-num">1</div>
        <span class="step-emoji">📞</span>
        <h3>Kostenloses Gespräch</h3>
        <p>Wir analysieren Ihren Prozess und finden genau die richtigen Automatisierungen.</p>
      </div>
      <div class="step reveal reveal-delay-1">
        <div class="step-num">2</div>
        <span class="step-emoji">⚙️</span>
        <h3>Workflow wird gebaut</h3>
        <p>Fertig in 48 Stunden. Getestet, dokumentiert und übergabe-bereit.</p>
      </div>
      <div class="step reveal reveal-delay-2">
        <div class="step-num">3</div>
        <span class="step-emoji">🚀</span>
        <h3>Sie sparen sofort Zeit</h3>
        <p>Ab sofort läuft alles automatisch – Sie können sich auf das Wesentliche konzentrieren.</p>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     PRICING SECTION
     ========================================== -->
<section id="pricing">
  <div class="container">
    <div class="pricing-header reveal">
      <div class="section-label">Preise</div>
      <h2 class="section-title">Transparente <span class="gradient-text">Preise</span></h2>
      <p class="section-subtitle" style="margin: 0 auto;">Keine versteckten Kosten. Kein Abo-Zwang. Einmalig oder monatlich.</p>
    </div>

    <div class="pricing-grid">
      <!-- Starter -->
      <div class="glass-card pricing-card reveal">
        <div class="pricing-name">Starter</div>
        <div class="pricing-price">399 €</div>
        <div class="pricing-period">Einmalig · Fertig in 48h</div>
        <div class="pricing-divider"></div>
        <ul class="pricing-features">
          <li class="yes"><span class="check">✓</span> Webhook Setup</li>
          <li class="yes"><span class="check">✓</span> Google Sheets CRM</li>
          <li class="yes"><span class="check">✓</span> E-Mail Benachrichtigung</li>
          <li class="yes"><span class="check">✓</span> Dokumentation</li>
          <li><span class="cross">–</span> Slack Integration</li>
          <li><span class="cross">–</span> Video-Tutorial</li>
        </ul>
        <a href="#contact" class="btn-outline pricing-btn">Jetzt buchen</a>
      </div>

      <!-- Professional (Featured) -->
      <div class="glass-card pricing-card featured reveal reveal-delay-1">
        <div class="popular-badge">✦ BELIEBT</div>
        <div class="pricing-name">Professional</div>
        <div class="pricing-price">799 €</div>
        <div class="pricing-period">Einmalig · Fertig in 48h</div>
        <div class="pricing-divider"></div>
        <ul class="pricing-features">
          <li class="yes"><span class="check">✓</span> Alles aus Starter</li>
          <li class="yes"><span class="check">✓</span> Slack Benachrichtigung</li>
          <li class="yes"><span class="check">✓</span> Auto-Antwort E-Mail</li>
          <li class="yes"><span class="check">✓</span> Video-Tutorial</li>
          <li class="yes"><span class="check">✓</span> 2 Wochen Support</li>
          <li><span class="cross">–</span> KI-Integration</li>
        </ul>
        <a href="#contact" class="pricing-btn-featured">Jetzt buchen</a>
      </div>

      <!-- AI Agent -->
      <div class="glass-card pricing-card ai-card reveal reveal-delay-2">
        <div class="pricing-name">AI Agent</div>
        <div class="pricing-price">ab 3.000 €</div>
        <div class="pricing-period">Einmalig · Individuell</div>
        <div class="pricing-divider"></div>
        <ul class="pricing-features">
          <li class="yes"><span class="check">✓</span> Alles aus Professional</li>
          <li class="yes"><span class="check">✓</span> GPT-4 KI-Integration</li>
          <li class="yes"><span class="check">✓</span> Lead-Scoring (0–100)</li>
          <li class="yes"><span class="check">✓</span> Personalisierte KI-E-Mails</li>
          <li class="yes"><span class="check">✓</span> 1 Monat Support</li>
        </ul>
        <a href="#contact" class="btn-outline pricing-btn" style="border-color: rgba(251,191,36,0.4); color: #FBBF24;">Anfrage stellen</a>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     CASE STUDY
     ========================================== -->
<section id="case">
  <div class="container">
    <div class="case-header reveal">
      <div class="section-label">Ergebnis</div>
      <h2 class="section-title">Echtes <span class="gradient-text">Ergebnis</span></h2>
    </div>

    <div class="glass-card case-card reveal">
      <div class="case-left">
        <div class="case-tag">FALLSTUDIE · IMMOBILIEN</div>
        <h3>Von manueller Dateneingabe zu vollautomatischer Lead-Pipeline</h3>
        <p><strong style="color: var(--white);">Problem:</strong> Ein Münchner Immobilienmakler verlor täglich Leads weil Anfragen manuell ins CRM eingetragen wurden – das dauerte 10+ Minuten pro Lead.</p>
        <p><strong style="color: var(--white);">Lösung:</strong> n8n Workflow: Anfrage → sofortiger CRM-Eintrag → Slack-Alert → automatische Bestätigungs-Mail an den Interessenten. Alles in unter 30 Sekunden.</p>
        <p><strong style="color: var(--white);">Ergebnis:</strong> 0 Sekunden manuelle Arbeit pro Lead. 10 Stunden pro Woche gespart.</p>
      </div>
      <div class="case-right">
        <div class="case-metric">
          <span class="case-metric-number gray" style="color: var(--gray-dark); text-decoration: line-through; font-size: 1.5rem;">10 Min.</span>
          <span class="case-metric-label">Vorher: manuelle Bearbeitung</span>
        </div>
        <div class="case-metric">
          <span class="case-metric-number cyan">30 Sek.</span>
          <span class="case-metric-label">Nachher: vollautomatisch</span>
        </div>
        <div class="case-metric">
          <span class="case-metric-number purple">10 Std.</span>
          <span class="case-metric-label">gespart pro Woche</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     TESTIMONIALS
     ========================================== -->
<section id="testimonials">
  <div class="container">
    <div class="test-header reveal">
      <div class="section-label">Kundenstimmen</div>
      <h2 class="section-title">Was Kunden <span class="gradient-text">sagen</span></h2>
    </div>

    <div class="test-grid">
      <div class="glass-card test-card reveal">
        <div class="stars">★★★★★</div>
        <p class="test-quote">"Der Workflow läuft seit Wochen perfekt. Kein einziger Lead geht mehr verloren und wir sparen täglich mindestens 3 Stunden – unglaublich!"</p>
        <div class="test-author">
          <div class="test-avatar">MM</div>
          <div>
            <div class="test-name">Max Müller</div>
            <div class="test-role">Immobilienmakler, München</div>
          </div>
        </div>
      </div>

      <div class="glass-card test-card reveal reveal-delay-1">
        <div class="stars">★★★★★</div>
        <p class="test-quote">"Seit der Automation ist kein Lead mehr verloren gegangen. ROI bereits nach 2 Wochen erreicht. Absolut empfehlenswert!"</p>
        <div class="test-author">
          <div class="test-avatar" style="background: linear-gradient(135deg, var(--cyan), var(--primary));">LS</div>
          <div>
            <div class="test-name">Lisa Schmidt</div>
            <div class="test-role">Inhaberin Online-Shop</div>
          </div>
        </div>
      </div>

      <div class="glass-card test-card reveal reveal-delay-2">
        <div class="stars">★★★★★</div>
        <p class="test-quote">"Der AI Sales Agent ist einfach unglaublich. Er schreibt bessere Erstantworten als wir es manuell je könnten – und das in Sekunden."</p>
        <div class="test-author">
          <div class="test-avatar" style="background: linear-gradient(135deg, #FBBF24, #F59E0B); color: #000;">TW</div>
          <div>
            <div class="test-name">Thomas Weber</div>
            <div class="test-role">Geschäftsführer, Marketing-Agentur</div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     ABOUT SECTION
     ========================================== -->
<section id="about">
  <div class="container">
    <div class="about-grid">
      <div class="about-avatar-wrap reveal">
        <div>
          <div class="about-avatar">👨‍💻</div>
          <div class="about-name">Suraj Kumar</div>
          <div class="about-loc">📍 Bayern, Deutschland</div>
        </div>
      </div>

      <div class="about-text reveal reveal-delay-1">
        <div class="section-label">Über mich</div>
        <h2>Wer steckt <span class="gradient-text">dahinter?</span></h2>
        <p>Ich bin Suraj Kumar, Automatisierungsexperte aus Bayern. Seit Jahren helfe ich Unternehmen dabei, repetitive Prozesse zu automatisieren – schnell, zuverlässig und vollständig DSGVO-konform.</p>
        <p>Mein Ansatz: Ich baue keine komplizierten Systeme. Ich baue Systeme die einfach funktionieren. Fertig in 48 Stunden, dokumentiert und sofort einsatzbereit.</p>

        <div class="about-badges">
          <div class="about-badge">⚙️ n8n Certified</div>
          <div class="about-badge">🇩🇪 Made in Germany</div>
          <div class="about-badge">🔒 DSGVO-Experte</div>
          <div class="about-badge">⭐ 5-Sterne Bewertungen</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     FAQ SECTION
     ========================================== -->
<section id="faq">
  <div class="container">
    <div class="faq-header reveal">
      <div class="section-label">FAQ</div>
      <h2 class="section-title">Häufige <span class="gradient-text">Fragen</span></h2>
    </div>

    <div class="faq-list">
      <div class="faq-item reveal">
        <button class="faq-question" onclick="toggleFaq(this)">
          Brauche ich technisches Wissen?
          <span class="faq-icon">+</span>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">Nein! Alles wird fertig konfiguriert und übergeben – inklusive Video-Tutorial das genau erklärt was der Workflow tut. Sie müssen nichts selbst einrichten.</div>
        </div>
      </div>

      <div class="faq-item reveal reveal-delay-1">
        <button class="faq-question" onclick="toggleFaq(this)">
          Ist das DSGVO-konform?
          <span class="faq-icon">+</span>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">Ja, zu 100%. Alle Daten bleiben auf deutschen Servern. Es werden keine Daten an Drittanbieter außerhalb der EU übermittelt. Alle Verbindungen sind verschlüsselt.</div>
        </div>
      </div>

      <div class="faq-item reveal reveal-delay-2">
        <button class="faq-question" onclick="toggleFaq(this)">
          Was passiert wenn etwas nicht funktioniert?
          <span class="faq-icon">+</span>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">Kostenlose Fehlerbehebung innerhalb von 24 Stunden. Ich bin per E-Mail und WhatsApp erreichbar und kümmere mich sofort darum.</div>
        </div>
      </div>

      <div class="faq-item reveal reveal-delay-3">
        <button class="faq-question" onclick="toggleFaq(this)">
          Kann ich meinen Workflow später erweitern?
          <span class="faq-icon">+</span>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">Ja, jederzeit. Mit dem Retainer-Paket kümmere ich mich monatlich um Wartung, Optimierungen und neue Features. Kein Neustart nötig.</div>
        </div>
      </div>

      <div class="faq-item reveal reveal-delay-4">
        <button class="faq-question" onclick="toggleFaq(this)">
          Wie schnell sehe ich erste Ergebnisse?
          <span class="faq-icon">+</span>
        </button>
        <div class="faq-answer">
          <div class="faq-answer-inner">Ab dem ersten Test-Run – also sofort nach Übergabe. Meistens schon beim ersten Live-Test. Die Zeitersparnis ist vom ersten Moment an spürbar.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ==========================================
     CONTACT / CTA SECTION
     ========================================== -->
<section id="contact">
  <div class="container">
    <div class="cta-inner reveal">
      <div class="cta-glow"></div>
      <div class="section-label" style="margin: 0 auto 24px;">Jetzt starten</div>
      <h2 class="cta-title">
        Bereit <span class="gradient-text">loszulegen?</span>
      </h2>
      <p class="cta-sub">
        Buchen Sie jetzt ein kostenloses 15-Minuten Gespräch.<br>
        Kein Risiko. Kein Commitment. Nur Ergebnisse.
      </p>
      <a href="mailto:suraj@sk-automation.de" class="btn-primary cta-btn">
        <span>Jetzt Demo buchen →</span>
      </a>
      <p class="cta-email">
        Oder schreiben Sie direkt: <a href="mailto:suraj@sk-automation.de">suraj@sk-automation.de</a>
      </p>
    </div>
  </div>
</section>

<!-- ==========================================
     FOOTER
     ========================================== -->
<footer>
  <div class="container">
    <div class="footer-inner">
      <div>
        <a href="#hero" class="footer-logo">SK Automation</a>
        <p class="footer-tagline">Wir automatisieren Ihre Prozesse. In 48 Stunden.</p>
      </div>

      <ul class="footer-links">
        <li><a href="#services">Leistungen</a></li>
        <li><a href="#pricing">Preise</a></li>
        <li><a href="#about">Über mich</a></li>
        <li><a href="#contact">Kontakt</a></li>
        <li><a href="#">Impressum</a></li>
        <li><a href="#">Datenschutz</a></li>
      </ul>

      <div class="footer-socials">
        <a href="#" class="social-btn" title="LinkedIn">in</a>
        <a href="#" class="social-btn" title="Fiverr">F</a>
      </div>

      <p class="footer-copy">© 2026 SK Automation – Suraj Kumar · Bayern, Deutschland</p>
    </div>
  </div>
</footer>

<!-- ==========================================
     FLOATING BUTTONS
     ========================================== -->
<!-- WhatsApp Button -->
<a href="https://wa.me/491234567890" class="floating-wa" target="_blank" rel="noopener" title="WhatsApp">
  💬
</a>

<!-- Back to top Button -->
<button class="back-top" id="backTop" onclick="window.scrollTo({top:0,behavior:'smooth'})" title="Nach oben">
  ↑
</button>

<!-- ==========================================
     JAVASCRIPT
     ========================================== -->
<script>
// ==========================================
// NAVIGATION – Scroll-Effekt
// ==========================================
const navbar = document.getElementById('navbar');
const backTop = document.getElementById('backTop');

window.addEventListener('scroll', () => {
  if (window.scrollY > 60) {
    navbar.classList.add('scrolled');
    backTop.classList.add('visible');
  } else {
    navbar.classList.remove('scrolled');
    backTop.classList.remove('visible');
  }
});

// ==========================================
// HAMBURGER MENU
// ==========================================
const hamburger = document.getElementById('hamburger');
const mobileNav = document.getElementById('mobileNav');

hamburger.addEventListener('click', () => {
  hamburger.classList.toggle('active');
  mobileNav.classList.toggle('open');
  document.body.style.overflow = mobileNav.classList.contains('open') ? 'hidden' : '';
});

function closeMobile() {
  hamburger.classList.remove('active');
  mobileNav.classList.remove('open');
  document.body.style.overflow = '';
}

// ==========================================
// SCROLL REVEAL (Intersection Observer)
// ==========================================
const reveals = document.querySelectorAll('.reveal');
const revealObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      entry.target.classList.add('visible');
    }
  });
}, { threshold: 0.12, rootMargin: '0px 0px -60px 0px' });

reveals.forEach(el => revealObserver.observe(el));

// ==========================================
// ANIMATED COUNTER (Stats)
// ==========================================
function animateCounter(el) {
  const target = parseInt(el.dataset.target);
  const suffix = el.dataset.suffix || '';
  const duration = 1800;
  const start = performance.now();

  function update(now) {
    const elapsed = now - start;
    const progress = Math.min(elapsed / duration, 1);
    // Easing: ease-out-cubic
    const eased = 1 - Math.pow(1 - progress, 3);
    const current = Math.round(eased * target);
    el.textContent = current + suffix;
    if (progress < 1) requestAnimationFrame(update);
  }
  requestAnimationFrame(update);
}

const statNumbers = document.querySelectorAll('.stat-number[data-target]');
const counterObserver = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting && !entry.target.dataset.animated) {
      entry.target.dataset.animated = 'true';
      animateCounter(entry.target);
    }
  });
}, { threshold: 0.5 });

statNumbers.forEach(el => counterObserver.observe(el));

// ==========================================
// FAQ ACCORDION
// ==========================================
function toggleFaq(btn) {
  const item = btn.closest('.faq-item');
  const isOpen = item.classList.contains('open');

  // Alle schließen
  document.querySelectorAll('.faq-item.open').forEach(openItem => {
    openItem.classList.remove('open');
  });

  // Wenn geschlossen war, öffnen
  if (!isOpen) {
    item.classList.add('open');
  }
}

// ==========================================
// SMOOTH SCROLL für alle Anker-Links
// ==========================================
document.querySelectorAll('a[href^="#"]').forEach(link => {
  link.addEventListener('click', function(e) {
    const target = document.querySelector(this.getAttribute('href'));
    if (target) {
      e.preventDefault();
      const offset = 80;
      const top = target.getBoundingClientRect().top + window.scrollY - offset;
      window.scrollTo({ top, behavior: 'smooth' });
    }
  });
});

// ==========================================
// ACTIVE NAV LINK bei Scroll
// ==========================================
const sections = document.querySelectorAll('section[id]');
const navLinks = document.querySelectorAll('.nav-links a');

window.addEventListener('scroll', () => {
  let current = '';
  sections.forEach(section => {
    const sectionTop = section.offsetTop - 120;
    if (window.scrollY >= sectionTop) {
      current = section.getAttribute('id');
    }
  });
  navLinks.forEach(link => {
    link.style.color = '';
    if (link.getAttribute('href') === '#' + current) {
      link.style.color = 'var(--white)';
    }
  });
});
</script>

</body>
</html>
