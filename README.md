# Ordem-Leitura
Ordem &amp;  Leitura is book club formed by young women to get together and read
<!DOCTYPE html>
<html lang="pt-BR">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Ordem & Leitura — Clube do Livro</title>
<meta name="description" content="Clube do livro feminino. Lemos, debatemos, discordamos. Toda leitora bem-vinda.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;0,700;1,300;1,400;1,600;1,700&family=Jost:wght@200;300;400;500&display=swap" rel="stylesheet">
<style>
/* ═══════════════════════════════════════
   TOKENS & RESET
═══════════════════════════════════════ */
:root {
  --bordo:       #6B1229;
  --bordo-deep:  #3D0A18;
  --bordo-mid:   #8B1A34;
  --rosa:        #F2C8D8;
  --rosa-light:  #FAF0F4;
  --rosa-mid:    #E8A8C0;
  --creme:       #FDF8F5;
  --text:        #2A0810;
}

*, *::before, *::after { margin: 0; padding: 0; box-sizing: border-box; }

html { scroll-behavior: smooth; }

body {
  background: var(--creme);
  font-family: 'Jost', sans-serif;
  color: var(--text);
  overflow-x: hidden;
}

/* ═══════════════════════════════════════
   UTILITIES
═══════════════════════════════════════ */
.section { padding: 5rem 2rem; max-width: 1100px; margin: 0 auto; }
.section-sm { padding: 3.5rem 2rem; max-width: 1100px; margin: 0 auto; }

.eyebrow {
  font-size: 10px;
  letter-spacing: 4px;
  text-transform: uppercase;
  font-weight: 300;
  color: var(--bordo-mid);
  display: flex;
  align-items: center;
  gap: 12px;
  margin-bottom: 1rem;
}
.eyebrow::before {
  content: '';
  display: block;
  width: 24px;
  height: 0.5px;
  background: var(--bordo-mid);
}

.section-heading {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(32px, 5vw, 52px);
  font-weight: 300;
  font-style: italic;
  color: var(--bordo-deep);
  line-height: 1.1;
  margin-bottom: 1rem;
}

.divider {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin: 2.5rem 0;
}
.divider-line { flex: 1; height: 0.5px; background: var(--rosa-mid); }
.divider-diamond { font-size: 8px; color: var(--bordo-mid); }

.btn {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  font-family: 'Jost', sans-serif;
  font-size: 10px;
  letter-spacing: 3px;
  text-transform: uppercase;
  font-weight: 400;
  padding: 13px 28px;
  border: none;
  cursor: pointer;
  text-decoration: none;
  transition: all 0.25s;
}
.btn-primary { background: var(--bordo); color: var(--rosa-light); }
.btn-primary:hover { background: var(--bordo-deep); }
.btn-outline { background: transparent; color: var(--bordo); border: 0.5px solid var(--bordo); }
.btn-outline:hover { background: var(--bordo); color: var(--rosa-light); }
.btn-rosa { background: var(--rosa-mid); color: var(--bordo-deep); }
.btn-rosa:hover { background: var(--rosa); }

/* ═══════════════════════════════════════
   NAVBAR
═══════════════════════════════════════ */
#navbar {
  position: fixed;
  top: 0; left: 0; right: 0;
  z-index: 1000;
  background: rgba(253,248,245,0.92);
  backdrop-filter: blur(12px);
  border-bottom: 0.5px solid var(--rosa-mid);
  transition: all 0.3s;
}

.nav-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 2rem;
  height: 64px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav-logo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 15px;
  font-style: italic;
  font-weight: 600;
  color: var(--bordo);
  letter-spacing: 2px;
  text-decoration: none;
}

.nav-links {
  display: flex;
  gap: 2.2rem;
  list-style: none;
}

.nav-links a {
  font-size: 10px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  font-weight: 300;
  color: var(--bordo-mid);
  text-decoration: none;
  transition: color 0.2s;
}
.nav-links a:hover { color: var(--bordo); }

.nav-cta {
  font-size: 9px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  font-weight: 400;
  color: var(--rosa-light);
  background: var(--bordo);
  padding: 8px 18px;
  text-decoration: none;
  transition: background 0.2s;
}
.nav-cta:hover { background: var(--bordo-deep); }

/* hamburger */
.hamburger {
  display: none;
  flex-direction: column;
  gap: 5px;
  cursor: pointer;
  background: none;
  border: none;
  padding: 4px;
}
.hamburger span {
  display: block;
  width: 22px;
  height: 0.5px;
  background: var(--bordo);
  transition: all 0.3s;
}

.mobile-menu {
  display: none;
  position: fixed;
  top: 64px; left: 0; right: 0;
  background: var(--creme);
  border-bottom: 0.5px solid var(--rosa-mid);
  padding: 1.5rem 2rem;
  flex-direction: column;
  gap: 1.2rem;
  z-index: 999;
}

.mobile-menu a {
  font-size: 11px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  font-weight: 300;
  color: var(--bordo-mid);
  text-decoration: none;
}

.mobile-menu.open { display: flex; }

/* ═══════════════════════════════════════
   HERO
═══════════════════════════════════════ */
#hero {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding-top: 64px;
}

.hero-left {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 5rem 4rem 5rem 5rem;
  position: relative;
}

.hero-left::after {
  content: '';
  position: absolute;
  bottom: 4rem;
  left: 5rem;
  width: 40px;
  height: 0.5px;
  background: var(--rosa-mid);
}

.hero-eyebrow {
  font-size: 10px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--bordo-mid);
  font-weight: 300;
  margin-bottom: 1.5rem;
  display: flex;
  align-items: center;
  gap: 12px;
}
.hero-eyebrow::before {
  content: '';
  display: block;
  width: 28px;
  height: 0.5px;
  background: var(--bordo-mid);
}

.hero-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(52px, 7vw, 96px);
  font-weight: 300;
  line-height: 0.9;
  color: var(--bordo-deep);
  margin-bottom: 2rem;
}
.hero-title em {
  font-style: italic;
  font-weight: 700;
  color: var(--bordo);
  display: block;
}
.hero-amp {
  display: block;
  font-style: italic;
  font-weight: 300;
  color: var(--rosa-mid);
  font-size: 0.65em;
  line-height: 1.2;
}

.hero-tagline {
  font-size: 13px;
  font-weight: 300;
  color: #7A3050;
  line-height: 1.8;
  max-width: 320px;
  margin-bottom: 2.5rem;
  letter-spacing: 0.2px;
}

.hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; }

.hero-right {
  background: var(--bordo-deep);
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.hero-right::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.05;
  background-image:
    repeating-linear-gradient(0deg, transparent, transparent 36px, var(--rosa) 36px, var(--rosa) 37px),
    repeating-linear-gradient(90deg, transparent, transparent 36px, var(--rosa) 36px, var(--rosa) 37px);
}

.hero-emblem {
  position: relative;
  z-index: 2;
  text-align: center;
  padding: 3rem;
}

.emblem-outer {
  width: 220px;
  height: 220px;
  border-radius: 50%;
  border: 1px solid rgba(242,200,216,0.2);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 2rem;
  position: relative;
  animation: rotate-slow 30s linear infinite;
}

.emblem-outer::before {
  content: '';
  position: absolute;
  inset: 16px;
  border-radius: 50%;
  border: 0.5px solid rgba(242,200,216,0.12);
}

.emblem-inner {
  animation: rotate-slow 30s linear infinite reverse;
}

.emblem-initials {
  font-family: 'Cormorant Garamond', serif;
  font-size: 72px;
  font-style: italic;
  font-weight: 300;
  color: var(--rosa);
  line-height: 1;
}

.emblem-tagline {
  font-size: 9px;
  letter-spacing: 5px;
  text-transform: uppercase;
  color: rgba(232,168,192,0.5);
  font-weight: 300;
}

.hero-scroll {
  position: absolute;
  bottom: 2rem;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 6px;
  z-index: 2;
}

.hero-scroll span {
  font-size: 8px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: rgba(232,168,192,0.4);
  font-weight: 300;
}

.hero-scroll-line {
  width: 0.5px;
  height: 40px;
  background: linear-gradient(to bottom, rgba(232,168,192,0.4), transparent);
  animation: scroll-pulse 2s ease-in-out infinite;
}

@keyframes rotate-slow { to { transform: rotate(360deg); } }
@keyframes scroll-pulse { 0%,100% { opacity: 0.4; } 50% { opacity: 1; } }

/* ═══════════════════════════════════════
   SOBRE
═══════════════════════════════════════ */
#sobre { background: white; padding: 6rem 0; }

.sobre-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 2rem;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
}

.sobre-visual {
  position: relative;
}

.sobre-card-bg {
  background: var(--bordo);
  border-radius: 4px;
  padding: 3rem;
  position: relative;
  overflow: hidden;
}

.sobre-card-bg::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.05;
  background-image: repeating-linear-gradient(45deg, var(--rosa) 0, var(--rosa) 1px, transparent 0, transparent 40px);
}

.sobre-quote {
  font-family: 'Cormorant Garamond', serif;
  font-size: 28px;
  font-style: italic;
  font-weight: 300;
  color: var(--rosa-light);
  line-height: 1.4;
  position: relative;
  z-index: 2;
}

.sobre-quote-mark {
  font-size: 80px;
  color: rgba(242,200,216,0.15);
  line-height: 0.6;
  font-family: 'Cormorant Garamond', serif;
  display: block;
  margin-bottom: -1rem;
}

.sobre-deco {
  position: absolute;
  bottom: -1.5rem;
  right: 2rem;
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: var(--rosa-mid);
  display: flex;
  align-items: center;
  justify-content: center;
}

.sobre-deco-text {
  font-family: 'Cormorant Garamond', serif;
  font-size: 22px;
  font-style: italic;
  color: var(--bordo-deep);
}

.sobre-text p {
  font-size: 14px;
  font-weight: 300;
  line-height: 1.9;
  color: #5A3040;
  margin-bottom: 1.2rem;
}

.sobre-pillars {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 0.8rem;
  margin-top: 2rem;
}

.pillar {
  background: var(--rosa-light);
  border: 0.5px solid var(--rosa-mid);
  border-top: 2px solid var(--bordo);
  border-radius: 8px;
  padding: 1rem;
}

.pillar-icon { font-size: 18px; display: block; margin-bottom: 4px; }

.pillar-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 15px;
  font-style: italic;
  color: var(--bordo-deep);
  display: block;
  margin-bottom: 2px;
}

.pillar-desc {
  font-size: 11px;
  font-weight: 300;
  color: #9B7080;
  line-height: 1.5;
}

/* ═══════════════════════════════════════
   LEITURA DO MÊS
═══════════════════════════════════════ */
#leitura { background: var(--bordo-deep); padding: 6rem 0; position: relative; overflow: hidden; }

#leitura::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.04;
  background-image: repeating-linear-gradient(0deg, transparent, transparent 28px, var(--rosa) 28px, var(--rosa) 29px);
}

.leitura-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
}

.leitura-eyebrow {
  font-size: 10px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--rosa-mid);
  font-weight: 300;
  margin-bottom: 1rem;
  display: flex;
  align-items: center;
  gap: 12px;
}
.leitura-eyebrow::before {
  content: '';
  display: block;
  width: 24px;
  height: 0.5px;
  background: var(--rosa-mid);
}

.leitura-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(30px, 4vw, 48px);
  font-style: italic;
  font-weight: 300;
  color: var(--rosa-light);
  margin-bottom: 3rem;
}

.leitura-card {
  display: grid;
  grid-template-columns: auto 1fr;
  gap: 3rem;
  align-items: center;
  background: rgba(255,255,255,0.04);
  border: 0.5px solid rgba(232,168,192,0.2);
  border-radius: 12px;
  padding: 2.5rem;
}

.leitura-book-cover {
  width: 140px;
  min-height: 200px;
  background: linear-gradient(135deg, var(--bordo-mid) 0%, var(--bordo) 100%);
  border-radius: 4px;
  display: flex;
  align-items: center;
  justify-content: center;
  flex-direction: column;
  gap: 0.5rem;
  padding: 1.5rem 1rem;
  text-align: center;
  box-shadow: 8px 8px 24px rgba(0,0,0,0.3);
  position: relative;
  flex-shrink: 0;
}

.leitura-book-cover::before {
  content: '';
  position: absolute;
  left: 0; top: 0; bottom: 0;
  width: 6px;
  background: rgba(0,0,0,0.2);
  border-radius: 4px 0 0 4px;
}

.book-title-cover {
  font-family: 'Cormorant Garamond', serif;
  font-size: 16px;
  font-style: italic;
  color: var(--rosa-light);
  line-height: 1.3;
}

.book-autor-cover {
  font-size: 9px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: var(--rosa-mid);
  font-weight: 300;
}

.leitura-info { color: var(--rosa-light); }

.leitura-mes {
  font-size: 9px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--rosa-mid);
  font-weight: 300;
  margin-bottom: 0.5rem;
}

.leitura-livro-titulo {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(26px, 3.5vw, 40px);
  font-style: italic;
  font-weight: 300;
  color: var(--rosa-light);
  line-height: 1.1;
  margin-bottom: 0.3rem;
}

.leitura-livro-autor {
  font-size: 12px;
  font-weight: 300;
  color: var(--rosa-mid);
  letter-spacing: 1px;
  margin-bottom: 1.5rem;
}

.leitura-sinopse {
  font-size: 13px;
  font-weight: 300;
  color: rgba(242,200,216,0.7);
  line-height: 1.8;
  max-width: 480px;
  margin-bottom: 2rem;
}

.leitura-placeholder {
  text-align: center;
  padding: 3rem;
  border: 0.5px dashed rgba(232,168,192,0.3);
  border-radius: 12px;
}

.leitura-placeholder p {
  font-family: 'Cormorant Garamond', serif;
  font-size: 22px;
  font-style: italic;
  color: rgba(242,200,216,0.4);
  margin-bottom: 1rem;
}

.leitura-placeholder span {
  font-size: 11px;
  font-weight: 300;
  color: rgba(232,168,192,0.3);
  letter-spacing: 1px;
}

/* ═══════════════════════════════════════
   URNA / SORTEIO
═══════════════════════════════════════ */
#urna { background: var(--rosa-light); padding: 6rem 0; }

.urna-inner { max-width: 1100px; margin: 0 auto; padding: 0 2rem; }

.urna-tabs {
  display: flex;
  border-bottom: 0.5px solid var(--rosa-mid);
  margin-bottom: 2.5rem;
  gap: 0;
}

.urna-tab {
  font-size: 10px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  font-weight: 300;
  color: var(--bordo-mid);
  padding: 0.9rem 1.5rem;
  cursor: pointer;
  border: none;
  background: transparent;
  border-bottom: 2px solid transparent;
  transition: all 0.2s;
}

.urna-tab.active {
  color: var(--bordo);
  border-bottom-color: var(--bordo);
  font-weight: 500;
}

.urna-panel { display: none; }
.urna-panel.active { display: block; }

/* membras */
.membras-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.5rem; }

.input-group { margin-bottom: 1rem; }

.input-label {
  font-size: 9px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: var(--bordo-mid);
  font-weight: 400;
  display: block;
  margin-bottom: 5px;
}

input[type="text"] {
  width: 100%;
  padding: 11px 14px;
  border: 0.5px solid var(--rosa-mid);
  border-radius: 8px;
  font-family: 'Jost', sans-serif;
  font-size: 13px;
  font-weight: 300;
  color: var(--bordo-deep);
  background: white;
  outline: none;
  transition: border-color 0.2s;
}
input[type="text"]:focus { border-color: var(--bordo-mid); }
input[type="text"]::placeholder { color: #C4A0B0; }

.form-card {
  background: white;
  border: 0.5px solid var(--rosa-mid);
  border-radius: 12px;
  padding: 1.8rem;
}

.form-card-title {
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  font-style: italic;
  color: var(--bordo-deep);
  margin-bottom: 0.3rem;
}

.form-card-sub {
  font-size: 12px;
  font-weight: 300;
  color: #9B7080;
  margin-bottom: 1.5rem;
}

.livros-temp { display: flex; flex-direction: column; gap: 0.4rem; margin: 0.8rem 0; }

.livro-temp-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 12px;
  font-weight: 300;
  color: var(--bordo-deep);
  padding: 7px 12px;
  background: var(--rosa-light);
  border-radius: 6px;
  border: 0.5px solid var(--rosa-mid);
}

.btn-sm {
  font-size: 9px;
  letter-spacing: 1px;
  text-transform: uppercase;
  padding: 4px 10px;
  border-radius: 6px;
  cursor: pointer;
  border: 0.5px solid;
  background: transparent;
  font-family: 'Jost', sans-serif;
  transition: all 0.2s;
}

.btn-sm-danger { color: #c0392b; border-color: #e8a0a0; }
.btn-sm-danger:hover { background: #fff0f0; }
.btn-sm-bordo { color: var(--bordo); border-color: var(--rosa-mid); }
.btn-sm-bordo:hover { background: var(--rosa-light); }

.member-list-panel { display: flex; flex-direction: column; gap: 0.8rem; }

.member-card {
  background: white;
  border: 0.5px solid var(--rosa-mid);
  border-radius: 10px;
  overflow: hidden;
}

.member-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem 1.3rem;
  cursor: pointer;
  border-bottom: 0.5px solid transparent;
  transition: all 0.2s;
}

.member-header:hover { background: var(--rosa-light); }
.member-header.open { border-bottom-color: var(--rosa-mid); }

.member-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 18px;
  font-style: italic;
  color: var(--bordo-deep);
}

.member-meta {
  display: flex;
  align-items: center;
  gap: 1rem;
}

.member-count {
  font-size: 10px;
  letter-spacing: 1.5px;
  color: var(--bordo-mid);
  font-weight: 300;
}

.member-books {
  padding: 1rem 1.3rem;
  display: none;
  flex-direction: column;
  gap: 0.5rem;
}
.member-books.open { display: flex; }

.book-item {
  display: flex;
  justify-content: space-between;
  align-items: center;
  font-size: 13px;
  font-weight: 300;
  color: var(--bordo-deep);
  padding: 7px 10px;
  background: var(--rosa-light);
  border-radius: 6px;
}

.empty-state {
  text-align: center;
  padding: 3rem 2rem;
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  font-style: italic;
  color: #C4A0B0;
}

/* sorteio */
.sorteio-layout {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
}

.sorteio-stats {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  gap: 0.8rem;
  margin-bottom: 1.5rem;
}

.stat-box {
  background: white;
  border: 0.5px solid var(--rosa-mid);
  border-radius: 10px;
  padding: 1rem;
  text-align: center;
}

.stat-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 36px;
  font-style: italic;
  color: var(--bordo);
  line-height: 1;
  display: block;
}

.stat-label {
  font-size: 9px;
  letter-spacing: 2px;
  text-transform: uppercase;
  color: #9B7080;
  font-weight: 300;
}

.sorteio-box {
  background: var(--bordo-deep);
  border-radius: 16px;
  padding: 2.5rem 2rem;
  text-align: center;
  position: relative;
  overflow: hidden;
  grid-column: 1 / -1;
}

.sorteio-box::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.04;
  background-image: repeating-linear-gradient(0deg, var(--rosa) 0, var(--rosa) 1px, transparent 0, transparent 22px);
}

.sorteio-label {
  font-size: 9px;
  letter-spacing: 4px;
  text-transform: uppercase;
  color: var(--rosa-mid);
  font-weight: 300;
  margin-bottom: 1rem;
  position: relative;
  z-index: 2;
}

.sorteio-resultado {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(22px, 4vw, 36px);
  font-style: italic;
  font-weight: 300;
  color: var(--rosa-light);
  line-height: 1.3;
  min-height: 80px;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  z-index: 2;
  transition: opacity 0.3s;
}

.sorteio-autor-label {
  font-size: 12px;
  color: var(--rosa-mid);
  font-weight: 300;
  min-height: 20px;
  margin-bottom: 0.3rem;
  position: relative;
  z-index: 2;
}

.sorteio-indicada-label {
  font-size: 10px;
  color: rgba(232,168,192,0.45);
  font-weight: 300;
  letter-spacing: 1px;
  min-height: 18px;
  margin-bottom: 1.5rem;
  position: relative;
  z-index: 2;
}

.btn-sortear {
  background: var(--rosa-mid);
  color: var(--bordo-deep);
  font-family: 'Jost', sans-serif;
  font-size: 10px;
  letter-spacing: 3px;
  text-transform: uppercase;
  font-weight: 500;
  padding: 14px 36px;
  border: none;
  cursor: pointer;
  border-radius: 8px;
  transition: all 0.2s;
  position: relative;
  z-index: 2;
}
.btn-sortear:hover { background: var(--rosa); }
.btn-sortear:disabled { opacity: 0.5; cursor: not-allowed; }

.historico-section { margin-top: 2rem; }
.historico-label {
  font-size: 9px;
  letter-spacing: 3px;
  text-transform: uppercase;
  color: var(--bordo-mid);
  font-weight: 300;
  margin-bottom: 0.8rem;
}

.historico-list { display: flex; flex-direction: column; gap: 0.6rem; }

.historico-item {
  display: flex;
  align-items: center;
  gap: 1rem;
  background: white;
  border: 0.5px solid var(--rosa-mid);
  border-radius: 8px;
  padding: 0.9rem 1.1rem;
}

.historico-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  font-style: italic;
  color: var(--rosa-mid);
  min-width: 28px;
  text-align: center;
}

.historico-info { flex: 1; }

.historico-livro {
  font-family: 'Cormorant Garamond', serif;
  font-size: 16px;
  font-style: italic;
  color: var(--bordo-deep);
}

.historico-meta {
  font-size: 10px;
  color: #9B7080;
  font-weight: 300;
}

.badge {
  font-size: 8px;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 3px 8px;
  border-radius: 20px;
}
.badge-sorteado { background: var(--bordo); color: var(--rosa-light); }

/* regras */
.regras-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }

.regra-item {
  display: flex;
  gap: 1rem;
  padding: 1.2rem;
  background: white;
  border: 0.5px solid var(--rosa-mid);
  border-radius: 10px;
  border-left: 3px solid var(--bordo);
}

.regra-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 24px;
  font-style: italic;
  color: var(--rosa-mid);
  min-width: 24px;
  line-height: 1;
}

.regra-text {
  font-size: 13px;
  font-weight: 300;
  color: var(--bordo-deep);
  line-height: 1.7;
}

.regra-text strong { font-weight: 500; color: var(--bordo); }

/* ═══════════════════════════════════════
   ENCONTROS
═══════════════════════════════════════ */
#encontros { background: white; padding: 6rem 0; }

.encontros-inner { max-width: 1100px; margin: 0 auto; padding: 0 2rem; }

.encontros-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 1.2rem; margin-top: 2.5rem; }

.encontro-card {
  border: 0.5px solid var(--rosa-mid);
  border-radius: 12px;
  overflow: hidden;
}

.encontro-header {
  background: var(--bordo);
  padding: 1.5rem;
  display: flex;
  justify-content: space-between;
  align-items: flex-start;
}

.encontro-num {
  font-family: 'Cormorant Garamond', serif;
  font-size: 48px;
  font-style: italic;
  font-weight: 300;
  color: rgba(242,200,216,0.2);
  line-height: 1;
}

.encontro-badge {
  font-size: 8px;
  letter-spacing: 2px;
  text-transform: uppercase;
  padding: 4px 10px;
  border-radius: 20px;
  font-weight: 300;
}
.badge-em-breve { background: rgba(242,200,216,0.15); color: var(--rosa-mid); }
.badge-passado { background: rgba(0,0,0,0.2); color: rgba(232,168,192,0.4); }

.encontro-body { padding: 1.5rem; }

.encontro-titulo {
  font-family: 'Cormorant Garamond', serif;
  font-size: 20px;
  font-style: italic;
  color: var(--bordo-deep);
  margin-bottom: 0.5rem;
}

.encontro-detalhes {
  font-size: 11px;
  font-weight: 300;
  color: #9B7080;
  line-height: 1.8;
  letter-spacing: 0.3px;
}

.encontro-placeholder { color: #C4A0B0; font-style: italic; }

/* ═══════════════════════════════════════
   TOM DE VOZ / MANIFESTO
═══════════════════════════════════════ */
#manifesto { background: var(--bordo); padding: 6rem 0; position: relative; overflow: hidden; }

#manifesto::before {
  content: '';
  position: absolute;
  inset: 0;
  opacity: 0.05;
  background-image: repeating-linear-gradient(45deg, var(--rosa) 0, var(--rosa) 1px, transparent 0, transparent 50px);
}

.manifesto-inner {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 2rem;
  position: relative;
  z-index: 2;
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 5rem;
  align-items: center;
}

.manifesto-text-main {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(30px, 4vw, 48px);
  font-style: italic;
  font-weight: 300;
  color: var(--rosa-light);
  line-height: 1.25;
  margin-bottom: 2rem;
}

.manifesto-sub {
  font-size: 13px;
  font-weight: 300;
  color: rgba(242,200,216,0.65);
  line-height: 1.9;
  margin-bottom: 2rem;
}

.manifesto-pills {
  display: flex;
  flex-wrap: wrap;
  gap: 0.6rem;
}

.pill {
  font-size: 9px;
  letter-spacing: 2px;
  text-transform: uppercase;
  font-weight: 300;
  padding: 6px 14px;
  border-radius: 20px;
  border: 0.5px solid rgba(232,168,192,0.3);
  color: var(--rosa-mid);
}

.manifesto-values { display: flex; flex-direction: column; gap: 1.2rem; }

.value-item {
  display: flex;
  gap: 1rem;
  padding: 1.2rem 1.4rem;
  background: rgba(255,255,255,0.05);
  border: 0.5px solid rgba(232,168,192,0.15);
  border-radius: 10px;
  border-left: 3px solid var(--rosa-mid);
}

.value-icon { font-size: 20px; flex-shrink: 0; }

.value-content { flex: 1; }

.value-name {
  font-family: 'Cormorant Garamond', serif;
  font-size: 16px;
  font-style: italic;
  color: var(--rosa-light);
  display: block;
  margin-bottom: 3px;
}

.value-desc {
  font-size: 12px;
  font-weight: 300;
  color: rgba(242,200,216,0.55);
  line-height: 1.6;
}

/* ═══════════════════════════════════════
   CONTATO / REDES
═══════════════════════════════════════ */
#contato { background: var(--creme); padding: 6rem 0; }

.contato-inner {
  max-width: 700px;
  margin: 0 auto;
  padding: 0 2rem;
  text-align: center;
}

.contato-social {
  display: flex;
  justify-content: center;
  gap: 1rem;
  margin-top: 2.5rem;
  flex-wrap: wrap;
}

.social-pill {
  display: flex;
  align-items: center;
  gap: 8px;
  font-size: 11px;
  letter-spacing: 2px;
  text-transform: uppercase;
  font-weight: 300;
  color: var(--bordo-mid);
  background: white;
  border: 0.5px solid var(--rosa-mid);
  padding: 10px 20px;
  border-radius: 40px;
  text-decoration: none;
  transition: all 0.2s;
}
.social-pill:hover { background: var(--bordo); color: var(--rosa-light); border-color: var(--bordo); }

.contato-tagline {
  font-family: 'Cormorant Garamond', serif;
  font-size: clamp(20px, 3vw, 30px);
  font-style: italic;
  font-weight: 300;
  color: var(--bordo-deep);
  line-height: 1.4;
  margin: 2rem 0;
}

/* ═══════════════════════════════════════
   FOOTER
═══════════════════════════════════════ */
footer {
  background: var(--bordo-deep);
  padding: 2.5rem 2rem;
}

.footer-inner {
  max-width: 1100px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 1rem;
}

.footer-wm {
  font-family: 'Cormorant Garamond', serif;
  font-size: 14px;
  font-style: italic;
  color: var(--rosa-mid);
  letter-spacing: 2px;
}

.footer-links {
  display: flex;
  gap: 2rem;
  list-style: none;
}

.footer-links a {
  font-size: 9px;
  letter-spacing: 2.5px;
  text-transform: uppercase;
  color: rgba(232,168,192,0.4);
  text-decoration: none;
  font-weight: 300;
  transition: color 0.2s;
}
.footer-links a:hover { color: var(--rosa-mid); }

.footer-copy {
  font-size: 9px;
  letter-spacing: 1.5px;
  color: rgba(232,168,192,0.25);
  font-weight: 300;
  text-transform: uppercase;
}

/* ═══════════════════════════════════════
   ANIMAÇÕES
═══════════════════════════════════════ */
@keyframes fadeUp {
  from { opacity: 0; transform: translateY(30px); }
  to { opacity: 1; transform: translateY(0); }
}

@keyframes spin-text {
  0%   { opacity: 0.3; transform: scale(0.97); }
  50%  { opacity: 1;   transform: scale(1.02); }
  100% { opacity: 0.3; transform: scale(0.97); }
}

@keyframes winner-pop {
  0%   { transform: scale(0.8); opacity: 0; }
  70%  { transform: scale(1.06); }
  100% { transform: scale(1);   opacity: 1; }
}

.spinning { animation: spin-text 0.15s ease-in-out infinite; }
.winner-pop { animation: winner-pop 0.5s ease both; }

.reveal {
  opacity: 0;
  transform: translateY(30px);
  transition: opacity 0.7s ease, transform 0.7s ease;
}
.reveal.visible { opacity: 1; transform: translateY(0); }

/* ═══════════════════════════════════════
   RESPONSIVO
═══════════════════════════════════════ */
@media (max-width: 900px) {
  #hero { grid-template-columns: 1fr; min-height: auto; }
  .hero-left { padding: 4rem 2rem 3rem; }
  .hero-right { display: none; }
  .sobre-inner { grid-template-columns: 1fr; gap: 2.5rem; }
  .sobre-visual { order: -1; }
  .membras-grid { grid-template-columns: 1fr; }
  .sorteio-layout { grid-template-columns: 1fr; }
  .encontros-grid { grid-template-columns: 1fr; }
  .manifesto-inner { grid-template-columns: 1fr; gap: 2.5rem; }
  .regras-grid { grid-template-columns: 1fr; }
  .leitura-card { grid-template-columns: 1fr; text-align: center; }
  .leitura-book-cover { margin: 0 auto; }
  .nav-links, .nav-cta { display: none; }
  .hamburger { display: flex; }
  .sorteio-box { grid-column: 1; }
}
</style>
</head>
<body>

<!-- ═══ NAVBAR ═══ -->
<nav id="navbar">
  <div class="nav-inner">
    <a href="#hero" class="nav-logo">Ordem & Leitura</a>
    <ul class="nav-links">
      <li><a href="#sobre">Sobre</a></li>
      <li><a href="#leitura">Leitura</a></li>
      <li><a href="#urna">Urna</a></li>
      <li><a href="#encontros">Encontros</a></li>
      <li><a href="#contato">Contato</a></li>
    </ul>
    <a href="#urna" class="nav-cta">Indicar livro</a>
    <button class="hamburger" id="hamburger" onclick="toggleMenu()">
      <span></span><span></span><span></span>
    </button>
  </div>
</nav>

<div class="mobile-menu" id="mobile-menu">
  <a href="#sobre" onclick="closeMenu()">Sobre</a>
  <a href="#leitura" onclick="closeMenu()">Leitura do mês</a>
  <a href="#urna" onclick="closeMenu()">Urna de sorteio</a>
  <a href="#encontros" onclick="closeMenu()">Encontros</a>
  <a href="#contato" onclick="closeMenu()">Contato</a>
</div>

<!-- ═══ HERO ═══ -->
<section id="hero">
  <div class="hero-left">
    <div class="hero-eyebrow">Clube do Livro · João Pessoa</div>
    <h1 class="hero-title">
      Ordem
      <span class="hero-amp">&</span>
      <em>Leitura</em>
    </h1>
    <p class="hero-tagline">
      Toda leitora bem-vinda. Toda opinião respeitada.<br>
      Todo livro, uma nova janela para o mundo.
    </p>
    <div class="hero-actions">
      <a href="#sobre" class="btn btn-primary">Conheça o clube →</a>
      <a href="#urna" class="btn btn-outline">Indicar livro</a>
    </div>
  </div>
  <div class="hero-right">
    <div class="hero-emblem">
      <div class="emblem-outer">
        <div class="emblem-inner">
          <div class="emblem-initials">O&L</div>
        </div>
      </div>
      <div class="emblem-tagline">Lemos · Debatemos · Discordamos</div>
    </div>
    <div class="hero-scroll">
      <span>scroll</span>
      <div class="hero-scroll-line"></div>
    </div>
  </div>
</section>

<!-- ═══ SOBRE ═══ -->
<section id="sobre">
  <div class="sobre-inner">
    <div class="sobre-visual reveal">
      <div class="sobre-card-bg">
        <span class="sobre-quote-mark">"</span>
        <div class="sobre-quote">
          Onde a política é uma página e cada página é uma revolução.
        </div>
        <div class="sobre-deco">
          <div class="sobre-deco-text">O&L</div>
        </div>
      </div>
    </div>
    <div class="sobre-text reveal">
      <div class="eyebrow">Sobre o clube</div>
      <h2 class="section-heading">Um encontro de leitoras com vontade de ir além</h2>
      <p>O Ordem & Leitura nasceu da vontade de criar um espaço onde bons livros e boas conversas se encontram — sem julgamento, sem protocolo, sem veto.</p>
      <p>Todo mês, um livro. Todo encontro, uma discussão que começa na página e termina no mundo. Abertas a todas as perspectivas, a todos os gêneros literários, a todas as leitoras.</p>
      <div class="sobre-pillars">
        <div class="pillar">
          <span class="pillar-icon">📖</span>
          <span class="pillar-name">Leitura mensal</span>
          <span class="pillar-desc">Um livro por mês, escolhido por sorteio entre as indicações do grupo.</span>
        </div>
        <div class="pillar">
          <span class="pillar-icon">💬</span>
          <span class="pillar-name">Debate livre</span>
          <span class="pillar-desc">Sem posição certa ou errada. Só ideias, vinho e boa companhia.</span>
        </div>
        <div class="pillar">
          <span class="pillar-icon">🌍</span>
          <span class="pillar-name">Perspectivas diversas</span>
          <span class="pillar-desc">Leitoras de todo lugar, com vivências que enriquecem cada discussão.</span>
        </div>
        <div class="pillar">
          <span class="pillar-icon">🍷</span>
          <span class="pillar-name">Encontros presenciais</span>
          <span class="pillar-desc">Uma vez por mês, em pessoa. O melhor jeito de terminar um bom livro.</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ LEITURA DO MÊS ═══ -->
<section id="leitura">
  <div class="leitura-inner">
    <div class="leitura-eyebrow">Leitura atual</div>
    <h2 class="leitura-title">O livro do mês</h2>
    <div class="leitura-placeholder reveal">
      <p>A leitura deste mês será anunciada em breve.</p>
      <span>Acompanhe nossas redes ou ative as notificações</span>
    </div>
  </div>
</section>

<!-- ═══ URNA / SORTEIO ═══ -->
<section id="urna">
  <div class="urna-inner">
    <div class="eyebrow">Sistema de escolha</div>
    <h2 class="section-heading">A Urna Literária</h2>
    <p style="font-size:13px;font-weight:300;color:#7A3050;line-height:1.8;max-width:560px;margin-bottom:2.5rem;">
      Cada membra indica os livros que deseja ler. A sorte decide qual viaja com o grupo esse mês. Simples, justo e com um toque de drama.
    </p>

    <div class="urna-tabs">
      <button class="urna-tab active" onclick="switchUrna('membras', this)">Membras & Listas</button>
      <button class="urna-tab" onclick="switchUrna('sorteio', this)">Sorteio</button>
      <button class="urna-tab" onclick="switchUrna('regras', this)">Como Funciona</button>
    </div>

    <!-- PANEL: MEMBRAS -->
    <div class="urna-panel active" id="urna-membras">
      <div class="membras-grid">
        <div class="form-card">
          <div class="form-card-title">Adicionar Membra</div>
          <div class="form-card-sub">Cadastre a participante e os livros da lista dela.</div>
          <div class="input-group">
            <label class="input-label">Nome da membra</label>
            <input type="text" id="input-nome" placeholder="Ex: Ana Luiza" />
          </div>
          <div class="input-group">
            <label class="input-label">Título do livro</label>
            <input type="text" id="input-livro" placeholder="Título" />
          </div>
          <div class="input-group">
            <label class="input-label">Autora / Autor</label>
            <input type="text" id="input-autor" placeholder="Autora ou autor" />
          </div>
          <div style="display:flex;gap:0.6rem;flex-wrap:wrap;margin-bottom:1rem;">
            <button class="btn btn-outline" style="font-size:10px;padding:10px 20px;" onclick="addLivro()">+ Adicionar livro</button>
            <button class="btn btn-primary" style="font-size:10px;padding:10px 20px;" onclick="salvarMembra()">Salvar membra</button>
          </div>
          <div class="livros-temp" id="livros-temp"></div>
        </div>

        <div>
          <div style="font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--bordo-mid);font-weight:300;margin-bottom:1rem;">Membras cadastradas</div>
          <div class="member-list-panel" id="member-list">
            <div class="empty-state">Nenhuma membra ainda.<br>Adicione a primeira ao lado.</div>
          </div>
        </div>
      </div>
    </div>

    <!-- PANEL: SORTEIO -->
    <div class="urna-panel" id="urna-sorteio">
      <div class="sorteio-stats">
        <div class="stat-box">
          <span class="stat-num" id="stat-m">0</span>
          <span class="stat-label">Membras</span>
        </div>
        <div class="stat-box">
          <span class="stat-num" id="stat-l">0</span>
          <span class="stat-label">Livros na urna</span>
        </div>
        <div class="stat-box">
          <span class="stat-num" id="stat-s">0</span>
          <span class="stat-label">Sorteios feitos</span>
        </div>
      </div>

      <div class="sorteio-box">
        <div class="sorteio-label">Livro sorteado</div>
        <div class="sorteio-resultado" id="res-titulo">
          <span style="color:rgba(242,200,216,0.25);font-size:14px;letter-spacing:2px;">aguardando sorteio</span>
        </div>
        <div class="sorteio-autor-label" id="res-autor"></div>
        <div class="sorteio-indicada-label" id="res-indicada"></div>
        <button class="btn-sortear" id="btn-sortear" onclick="sortear()">✦ Realizar sorteio</button>
      </div>

      <div class="historico-section" id="historico-section" style="display:none;">
        <div class="historico-label">Histórico de sorteios</div>
        <div class="historico-list" id="historico-list"></div>
      </div>
    </div>

    <!-- PANEL: REGRAS -->
    <div class="urna-panel" id="urna-regras">
      <div class="regras-grid">
        <div class="regra-item">
          <div class="regra-num">1</div>
          <div class="regra-text"><strong>Cada membra faz sua lista</strong> com os livros que deseja ler — sem limite mínimo ou máximo.</div>
        </div>
        <div class="regra-item">
          <div class="regra-num">2</div>
          <div class="regra-text"><strong>Todos os livros entram na urna.</strong> O sorteio é aleatório entre todos os títulos indicados.</div>
        </div>
        <div class="regra-item">
          <div class="regra-num">3</div>
          <div class="regra-text"><strong>O sorteio é feito no encontro,</strong> com todas presentes. Suspense garantido. Sem veto, sem abstenção.</div>
        </div>
        <div class="regra-item">
          <div class="regra-num">4</div>
          <div class="regra-text"><strong>Livros já sorteados</strong> saem da urna automaticamente para que todas as indicações tenham chance.</div>
        </div>
        <div class="regra-item">
          <div class="regra-num">5</div>
          <div class="regra-text"><strong>Nenhum gênero literário é proibido.</strong> Romance, ficção científica, ensaio, poesia — tudo entra na urna.</div>
        </div>
        <div class="regra-item">
          <div class="regra-num">6</div>
          <div class="regra-text"><strong>A lista pode ser renovada</strong> a cada ciclo — basta atualizar as indicações antes do próximo sorteio.</div>
        </div>
      </div>
      <div class="divider"><div class="divider-line"></div><div class="divider-diamond">◆</div><div class="divider-line"></div></div>
      <div style="text-align:center;background:var(--bordo-deep);border-radius:12px;padding:2.5rem;">
        <div style="font-family:'Cormorant Garamond',serif;font-size:22px;font-style:italic;color:var(--rosa-light);line-height:1.5;">"A sorte decide o livro.<br>A gente decide o que fazer com ele."</div>
        <div style="font-size:9px;letter-spacing:3px;text-transform:uppercase;color:var(--rosa-mid);font-weight:300;margin-top:1rem;">Ordem & Leitura</div>
      </div>
    </div>

  </div>
</section>

<!-- ═══ ENCONTROS ═══ -->
<section id="encontros">
  <div class="encontros-inner">
    <div class="eyebrow reveal">Agenda</div>
    <h2 class="section-heading reveal">Próximos encontros</h2>
    <p style="font-size:13px;font-weight:300;color:#7A3050;line-height:1.8;max-width:520px;" class="reveal">
      Uma vez por mês, em pessoa. O melhor jeito de terminar um bom livro é com alguém que também o leu.
    </p>
    <div class="encontros-grid">
      <div class="encontro-card reveal">
        <div class="encontro-header">
          <div class="encontro-num">01</div>
          <span class="encontro-badge badge-em-breve">Em breve</span>
        </div>
        <div class="encontro-body">
          <div class="encontro-titulo">Primeiro Encontro</div>
          <div class="encontro-detalhes encontro-placeholder">Data, horário e local a confirmar.<br>Acompanhe nossas redes sociais.</div>
        </div>
      </div>
      <div class="encontro-card reveal">
        <div class="encontro-header">
          <div class="encontro-num">02</div>
          <span class="encontro-badge badge-em-breve">Em breve</span>
        </div>
        <div class="encontro-body">
          <div class="encontro-titulo">Segundo Encontro</div>
          <div class="encontro-detalhes encontro-placeholder">A ser definido após o primeiro encontro.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ MANIFESTO ═══ -->
<section id="manifesto">
  <div class="manifesto-inner">
    <div class="reveal">
      <h2 class="manifesto-text-main">Lemos. Debatemos. Discordamos. Voltamos no próximo mês.</h2>
      <p class="manifesto-sub">O Ordem & Leitura não é um clube para quem concorda com tudo. É para quem tem opinião, gosta de ouvi-la ser desafiada e sai melhor por isso. Toda leitora bem-vinda — independente do que leu, do que sabe ou de onde vem.</p>
      <div class="manifesto-pills">
        <span class="pill">Sem veto</span>
        <span class="pill">Sem abstenção</span>
        <span class="pill">Sem spoiler sem aviso</span>
        <span class="pill">Com muito vinho</span>
      </div>
    </div>
    <div class="manifesto-values reveal">
      <div class="value-item">
        <div class="value-icon">📖</div>
        <div class="value-content">
          <span class="value-name">Inteligente</span>
          <span class="value-desc">Falamos com profundidade. Gostamos de referências, contexto e de ir além do óbvio.</span>
        </div>
      </div>
      <div class="value-item">
        <div class="value-icon">🌍</div>
        <div class="value-content">
          <span class="value-name">Plural</span>
          <span class="value-desc">Nenhuma perspectiva é mais válida que outra. A riqueza está na diversidade de vozes.</span>
        </div>
      </div>
      <div class="value-item">
        <div class="value-icon">💬</div>
        <div class="value-content">
          <span class="value-name">Honesta</span>
          <span class="value-desc">Se o livro foi ruim, a gente fala. Se alguém discorda, a gente ouve. Sem protocolo.</span>
        </div>
      </div>
      <div class="value-item">
        <div class="value-icon">🌹</div>
        <div class="value-content">
          <span class="value-name">Acolhedora</span>
          <span class="value-desc">Sérias nos debates, calorosas nos encontros. Toda leitora tem lugar à mesa.</span>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ═══ CONTATO ═══ -->
<section id="contato">
  <div class="contato-inner">
    <div class="eyebrow" style="justify-content:center;margin-bottom:1rem;">Faça parte</div>
    <h2 class="section-heading" style="text-align:center;">Quer entrar no clube?</h2>
    <div class="contato-tagline">
      "Toda leitora bem-vinda.<br>Traga um livro pra indicar e uma opinião pra defender."
    </div>
    <p style="font-size:13px;font-weight:300;color:#7A3050;line-height:1.8;margin-bottom:1rem;">
      Entre em contato pelas nossas redes sociais ou apareça no próximo encontro. A urna está sempre aberta para novas indicações.
    </p>
    <div class="contato-social">
      <a href="https://instagram.com/ordemeleitura" target="_blank" class="social-pill">
        <span>📸</span> @ordemeleitura
      </a>
      <a href="mailto:ordemeleitura@gmail.com" class="social-pill">
        <span>✉️</span> ordemeleitura@gmail.com
      </a>
    </div>
  </div>
</section>

<!-- ═══ FOOTER ═══ -->
<footer>
  <div class="footer-inner">
    <div class="footer-wm">Ordem & Leitura</div>
    <ul class="footer-links">
      <li><a href="#sobre">Sobre</a></li>
      <li><a href="#leitura">Leitura</a></li>
      <li><a href="#urna">Urna</a></li>
      <li><a href="#encontros">Encontros</a></li>
    </ul>
    <div class="footer-copy">João Pessoa · 2025</div>
  </div>
</footer>

<script>
/* ══════════════════════════
   NAVBAR
══════════════════════════ */
function toggleMenu() {
  document.getElementById('mobile-menu').classList.toggle('open');
}
function closeMenu() {
  document.getElementById('mobile-menu').classList.remove('open');
}

/* ══════════════════════════
   REVEAL ON SCROLL
══════════════════════════ */
const observer = new IntersectionObserver(entries => {
  entries.forEach(e => {
    if (e.isIntersecting) { e.target.classList.add('visible'); observer.unobserve(e.target); }
  });
}, { threshold: 0.12 });

document.querySelectorAll('.reveal').forEach(el => observer.observe(el));

/* ══════════════════════════
   URNA TABS
══════════════════════════ */
function switchUrna(name, btn) {
  document.querySelectorAll('.urna-tab').forEach(t => t.classList.remove('active'));
  document.querySelectorAll('.urna-panel').forEach(p => p.classList.remove('active'));
  btn.classList.add('active');
  document.getElementById('urna-' + name).classList.add('active');
  if (name === 'sorteio') atualizarStats();
}

/* ══════════════════════════
   ESTADO
══════════════════════════ */
let membras = [];
let livrosTemp = [];
let historico = [];

/* ══════════════════════════
   MEMBRAS
══════════════════════════ */
function addLivro() {
  const titulo = document.getElementById('input-livro').value.trim();
  const autor  = document.getElementById('input-autor').value.trim();
  if (!titulo) return;
  livrosTemp.push({ titulo, autor: autor || 'Autor não informado' });
  document.getElementById('input-livro').value = '';
  document.getElementById('input-autor').value = '';
  renderLivrosTemp();
}

function renderLivrosTemp() {
  const el = document.getElementById('livros-temp');
  el.innerHTML = livrosTemp.map((l, i) => `
    <div class="livro-temp-item">
      <span>📖 <em>${l.titulo}</em>${l.autor !== 'Autor não informado' ? ' · ' + l.autor : ''}</span>
      <button class="btn-sm btn-sm-danger" onclick="removeLivroTemp(${i})">remover</button>
    </div>
  `).join('');
}

function removeLivroTemp(i) {
  livrosTemp.splice(i, 1);
  renderLivrosTemp();
}

function salvarMembra() {
  const nome = document.getElementById('input-nome').value.trim();
  const livro = document.getElementById('input-livro').value.trim();
  const autor = document.getElementById('input-autor').value.trim();
  if (livro) livrosTemp.push({ titulo: livro, autor: autor || 'Autor não informado' });
  if (!nome) { alert('Digite o nome da membra!'); return; }
  if (!livrosTemp.length) { alert('Adicione pelo menos um livro!'); return; }

  const existente = membras.find(m => m.nome.toLowerCase() === nome.toLowerCase());
  if (existente) {
    existente.livros.push(...livrosTemp);
  } else {
    membras.push({ nome, livros: [...livrosTemp] });
  }

  livrosTemp = [];
  ['input-nome','input-livro','input-autor'].forEach(id => document.getElementById(id).value = '');
  document.getElementById('livros-temp').innerHTML = '';
  renderMembras();
}

function renderMembras() {
  const el = document.getElementById('member-list');
  if (!membras.length) {
    el.innerHTML = '<div class="empty-state">Nenhuma membra ainda.<br>Adicione a primeira ao lado.</div>';
    return;
  }
  el.innerHTML = membras.map((m, mi) => `
    <div class="member-card">
      <div class="member-header" onclick="toggleMember(${mi}, this)">
        <div class="member-name">${m.nome}</div>
        <div class="member-meta">
          <span class="member-count">${m.livros.length} livro${m.livros.length !== 1 ? 's' : ''}</span>
          <button class="btn-sm btn-sm-danger" onclick="event.stopPropagation();removeMembra(${mi})">remover</button>
        </div>
      </div>
      <div class="member-books" id="mb-${mi}">
        ${m.livros.map((l, li) => `
          <div class="book-item">
            <span>📖 <em>${l.titulo}</em> · ${l.autor}</span>
            <button class="btn-sm btn-sm-danger" onclick="removeLivro(${mi},${li})">✕</button>
          </div>
        `).join('')}
        <div style="display:flex;gap:0.5rem;margin-top:0.4rem;flex-wrap:wrap;">
          <input type="text" placeholder="Novo livro" id="nl-t-${mi}" style="flex:2;font-size:12px;padding:8px 10px;" />
          <input type="text" placeholder="Autor" id="nl-a-${mi}" style="flex:1;font-size:12px;padding:8px 10px;" />
          <button class="btn-sm btn-sm-bordo" onclick="addLivroMembra(${mi})">+ Livro</button>
        </div>
      </div>
    </div>
  `).join('');
}

function toggleMember(i, header) {
  const el = document.getElementById('mb-' + i);
  el.classList.toggle('open');
  header.classList.toggle('open');
}

function removeMembra(i) {
  membras.splice(i, 1);
  renderMembras();
}

function removeLivro(mi, li) {
  membras[mi].livros.splice(li, 1);
  renderMembras();
}

function addLivroMembra(mi) {
  const titulo = document.getElementById('nl-t-' + mi).value.trim();
  const autor  = document.getElementById('nl-a-' + mi).value.trim();
  if (!titulo) return;
  membras[mi].livros.push({ titulo, autor: autor || 'Autor não informado' });
  renderMembras();
}

/* ══════════════════════════
   SORTEIO
══════════════════════════ */
function getPool() {
  const sorteados = historico.map(h => h._key);
  let pool = [];
  membras.forEach(m => {
    m.livros.forEach(l => {
      const key = l.titulo + '||' + l.autor + '||' + m.nome;
      if (!sorteados.includes(key)) {
        pool.push({ titulo: l.titulo, autor: l.autor, indicada: m.nome, _key: key });
      }
    });
  });
  return pool;
}

function atualizarStats() {
  document.getElementById('stat-m').textContent = membras.length;
  document.getElementById('stat-l').textContent = getPool().length;
  document.getElementById('stat-s').textContent = historico.length;
}

function sortear() {
  const pool = getPool();
  if (!pool.length) { alert('Nenhum livro na urna! Adicione membras e livros primeiro.'); return; }

  const btn = document.getElementById('btn-sortear');
  btn.disabled = true;
  btn.textContent = 'Sorteando...';

  const resT = document.getElementById('res-titulo');
  const resA = document.getElementById('res-autor');
  const resI = document.getElementById('res-indicada');

  resT.classList.remove('winner-pop');
  resT.classList.add('spinning');
  resA.textContent = '';
  resI.textContent = '';

  let count = 0;
  const interval = setInterval(() => {
    const rand = pool[Math.floor(Math.random() * pool.length)];
    resT.innerHTML = `<em>${rand.titulo}</em>`;
    count++;
    if (count > 22) {
      clearInterval(interval);
      const winner = pool[Math.floor(Math.random() * pool.length)];
      resT.classList.remove('spinning');
      resT.innerHTML = `<em>${winner.titulo}</em>`;
      resT.classList.add('winner-pop');
      resA.textContent = winner.autor;
      resI.textContent = `✦ indicado por ${winner.indicada}`;

      historico.unshift({
        titulo: winner.titulo, autor: winner.autor,
        indicada: winner.indicada, _key: winner._key,
        mes: new Date().toLocaleDateString('pt-BR', { month: 'long', year: 'numeric' })
      });

      renderHistorico();
      atualizarStats();
      btn.disabled = false;
      btn.textContent = '✦ Realizar novo sorteio';
    }
  }, 80);
}

function renderHistorico() {
  if (!historico.length) return;
  document.getElementById('historico-section').style.display = 'block';
  document.getElementById('historico-list').innerHTML = historico.map((h, i) => `
    <div class="historico-item">
      <div class="historico-num">${historico.length - i}°</div>
      <div class="historico-info">
        <div class="historico-livro">${h.titulo}</div>
        <div class="historico-meta">${h.autor} · indicado por ${h.indicada} · ${h.mes}</div>
      </div>
      <span class="badge badge-sorteado">sorteado</span>
    </div>
  `).join('');
}

/* Enter nos inputs */
document.addEventListener('keydown', e => {
  if (e.key !== 'Enter') return;
  const id = document.activeElement?.id;
  if (id === 'input-livro' || id === 'input-autor') addLivro();
  if (id === 'input-nome') document.getElementById('input-livro').focus();
});
</script>
</body>
</html>
