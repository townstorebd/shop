<!DOCTYPE html>
<html lang="bn">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>টাউনস্টোর — জীবনের ভান্ডার</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,400;0,700;1,400&family=Hind+Siliguri:wght@300;400;500;600&family=EB+Garamond:ital,wght@0,400;1,400&display=swap" rel="stylesheet">
<style>
:root {
  --cream: #F7F2E8;
  --cream-dark: #EDE5D4;
  --brown-deep: #2E1D0E;
  --brown: #5C3D1E;
  --brown-mid: #8B6240;
  --brown-light: #C4A882;
  --green-deep: #243D1A;
  --green: #3D6B2C;
  --gold: #B8882A;
  --gold-light: #D4A84B;
  --text: #2E1D0E;
  --text-muted: #7A5C3E;
  --wa: #25D366;
  --fb: #1877F2;
}
* { margin:0; padding:0; box-sizing:border-box; }
html { scroll-behavior: smooth; }
body {
  background: var(--cream);
  color: var(--text);
  font-family: 'Hind Siliguri', sans-serif;
  min-height: 100vh;
}

/* ── HERO ── */
.hero {
  background: var(--brown-deep);
  min-height: 100vh;
  display: flex; flex-direction: column;
  align-items: center; justify-content: center;
  position: relative; overflow: hidden;
  padding: 3rem 2rem;
}
.hero::before {
  content:'';position:absolute;inset:0;
  background:
    radial-gradient(ellipse 80% 60% at 20% 80%,rgba(61,107,44,.22) 0%,transparent 60%),
    radial-gradient(ellipse 60% 80% at 80% 20%,rgba(184,136,42,.13) 0%,transparent 60%);
}
.hero-pattern {
  position:absolute;inset:0;opacity:.035;
  background-image:
    repeating-linear-gradient(45deg,#fff 0px,#fff 1px,transparent 1px,transparent 28px),
    repeating-linear-gradient(-45deg,#fff 0px,#fff 1px,transparent 1px,transparent 28px);
}
.hero-content { position:relative; text-align:center; max-width:780px; }
.store-tag {
  display:inline-block;font-family:'EB Garamond',serif;font-style:italic;
  color:var(--gold-light);font-size:1rem;letter-spacing:.18em;
  text-transform:uppercase;margin-bottom:2rem;opacity:.85;
}
.hero-title {
  font-family:'Playfair Display',serif;font-size:clamp(3rem,8vw,6rem);
  color:var(--cream);line-height:1.05;margin-bottom:.5rem;font-weight:400;
}
.hero-title span { display:block;color:var(--gold-light);font-style:italic; }
.hero-slogan {
  font-size:clamp(.95rem,2.5vw,1.2rem);color:var(--brown-light);
  font-weight:300;letter-spacing:.08em;margin-bottom:2.5rem;margin-top:.3rem;
}
.hero-divider { width:50px;height:1px;background:var(--gold);margin:0 auto 2rem;opacity:.55; }
.hero-desc {
  font-size:1rem;color:#C8B89A;line-height:1.9;
  max-width:540px;margin:0 auto 2.5rem;font-weight:300;
}
.hero-cta {
  display:inline-block;background:transparent;
  border:1px solid var(--gold);color:var(--gold-light);
  padding:.8rem 2.5rem;font-size:1rem;letter-spacing:.1em;
  cursor:pointer;text-decoration:none;transition:all .3s;
}
.hero-cta:hover { background:var(--gold);color:var(--brown-deep); }
.hero-stats {
  position:relative;display:flex;gap:3rem;margin-top:4rem;
  padding-top:2rem;border-top:1px solid rgba(255,255,255,.07);
}
.stat { text-align:center; }
.stat-num { font-family:'Playfair Display',serif;font-size:2rem;color:var(--gold-light);line-height:1; }
.stat-label { font-size:.75rem;color:var(--brown-light);letter-spacing:.1em;margin-top:.3rem;font-weight:300; }
@media(max-width:600px){.hero-stats{gap:1.5rem;flex-wrap:wrap;justify-content:center;}}

/* ── CATALOGUE ── */
.catalogue { padding:4.5rem 2rem 3rem;max-width:1400px;margin:0 auto; }
.section-header { text-align:center;margin-bottom:3rem; }
.section-label {
  font-family:'EB Garamond',serif;font-style:italic;
  color:var(--gold);font-size:.9rem;letter-spacing:.2em;
  text-transform:uppercase;display:block;margin-bottom:.6rem;
}
.section-title { font-family:'Playfair Display',serif;font-size:clamp(1.8rem,4vw,2.8rem);color:var(--brown-deep);font-weight:400; }

/* Search */
.search-wrap { max-width:500px;margin:0 auto 2rem;position:relative; }
.search-input {
  width:100%;padding:.9rem 1.4rem .9rem 3rem;background:white;
  border:1px solid var(--brown-light);color:var(--text);
  font-family:'Hind Siliguri',sans-serif;font-size:1rem;outline:none;transition:border-color .2s;
}
.search-input:focus { border-color:var(--green); }
.search-input::placeholder { color:var(--brown-light); }
.search-icon { position:absolute;left:.9rem;top:50%;transform:translateY(-50%);color:var(--brown-light); }

/* Filters */
.filters { display:flex;flex-wrap:wrap;gap:.45rem;justify-content:center;margin-bottom:2.5rem; }
.filter-btn {
  padding:.4rem 1rem;background:transparent;border:1px solid var(--brown-light);
  color:var(--text-muted);font-family:'Hind Siliguri',sans-serif;
  font-size:.82rem;cursor:pointer;transition:all .2s;
}
.filter-btn:hover { border-color:var(--green);color:var(--green); }
.filter-btn.active { background:var(--brown-deep);border-color:var(--brown-deep);color:var(--cream); }

.results-info {
  text-align:center;color:var(--text-muted);font-size:.83rem;
  margin-bottom:1.8rem;font-style:italic;font-family:'EB Garamond',serif;
}

/* Product grid */
.product-grid {
  display:grid;grid-template-columns:repeat(auto-fill,minmax(220px,1fr));
  gap:1px;background:var(--cream-dark);border:1px solid var(--cream-dark);
}
.product-card {
  background:white;padding:1.4rem 1.3rem;
  display:flex;flex-direction:column;transition:background .2s;position:relative;
}
.product-card:hover { background:#FDFAF4; }
.product-cat-badge {
  font-size:.68rem;color:var(--green);text-transform:uppercase;
  letter-spacing:.12em;font-weight:500;margin-bottom:.6rem;
}
.product-name {
  font-size:.93rem;color:var(--brown-deep);font-weight:500;
  line-height:1.4;flex:1;margin-bottom:.9rem;
}
.product-footer { display:flex;align-items:center;justify-content:space-between;margin-bottom:.8rem; }
.product-price { font-family:'Playfair Display',serif;font-size:1.05rem;color:var(--green-deep);font-weight:700; }
.product-price span { font-size:.68rem;font-family:'Hind Siliguri',sans-serif;color:var(--text-muted);font-weight:400;margin-left:2px; }
.stock-badge { font-size:.7rem;padding:.18rem .55rem;border-radius:20px; }
.in-stock { background:#EAF2E3;color:#2D6B1A; }
.out-stock { background:#F5EDED;color:#9B3B3B; }

/* Add to cart btn */
.btn-add {
  width:100%;padding:.55rem;background:var(--brown-deep);color:var(--cream);
  border:none;font-family:'Hind Siliguri',sans-serif;font-size:.88rem;
  cursor:pointer;transition:background .2s;letter-spacing:.03em;
  display:flex;align-items:center;justify-content:center;gap:.4rem;
}
.btn-add:hover { background:var(--green-deep); }
.btn-add.added { background:var(--green);color:#fff; }
.btn-add:disabled { background:#C4A882;cursor:not-allowed; }

.no-results { text-align:center;padding:4rem 2rem;color:var(--text-muted);font-family:'EB Garamond',serif;font-style:italic;font-size:1.2rem;grid-column:1/-1;background:white; }

@media(max-width:600px){.product-grid{grid-template-columns:1fr 1fr;}}
@media(max-width:400px){.product-grid{grid-template-columns:1fr;}}

/* ── CART BUTTON (floating) ── */
.cart-fab {
  position:fixed;bottom:2rem;right:1.5rem;z-index:900;
  background:var(--brown-deep);color:var(--cream);
  width:58px;height:58px;border-radius:50%;border:none;
  display:flex;align-items:center;justify-content:center;
  cursor:pointer;box-shadow:0 4px 18px rgba(0,0,0,.35);
  transition:transform .2s,background .2s;
  font-family:'Hind Siliguri',sans-serif;
}
.cart-fab:hover { background:var(--green-deep);transform:scale(1.08); }
.cart-count {
  position:absolute;top:-4px;right:-4px;
  background:var(--wa);color:#fff;
  width:22px;height:22px;border-radius:50%;
  font-size:.72rem;font-weight:600;
  display:flex;align-items:center;justify-content:center;
  opacity:0;transform:scale(0);transition:all .25s;
}
.cart-count.show { opacity:1;transform:scale(1); }

/* ── CART SIDEBAR ── */
.cart-overlay {
  position:fixed;inset:0;background:rgba(0,0,0,.5);z-index:950;
  opacity:0;pointer-events:none;transition:opacity .3s;
}
.cart-overlay.open { opacity:1;pointer-events:all; }

.cart-sidebar {
  position:fixed;top:0;right:-420px;width:min(420px,100vw);
  height:100vh;background:white;z-index:960;
  display:flex;flex-direction:column;
  box-shadow:-8px 0 40px rgba(0,0,0,.2);
  transition:right .35s cubic-bezier(.4,0,.2,1);
}
.cart-sidebar.open { right:0; }

.cart-header {
  background:var(--brown-deep);color:var(--cream);
  padding:1.2rem 1.5rem;
  display:flex;align-items:center;justify-content:space-between;
  flex-shrink:0;
}
.cart-header h3 { font-family:'Playfair Display',serif;font-size:1.3rem;font-weight:400; }
.cart-close {
  background:transparent;border:none;color:var(--cream);
  font-size:1.5rem;cursor:pointer;line-height:1;padding:.2rem .4rem;
  transition:opacity .2s;
}
.cart-close:hover { opacity:.7; }

.cart-items { flex:1;overflow-y:auto;padding:1rem 1.5rem; }
.cart-empty {
  display:flex;flex-direction:column;align-items:center;justify-content:center;
  height:100%;color:var(--text-muted);font-family:'EB Garamond',serif;
  font-style:italic;font-size:1.1rem;text-align:center;gap:.8rem;
}
.cart-empty-icon { font-size:2.5rem;opacity:.4; }

.cart-item {
  display:flex;gap:1rem;padding:.9rem 0;
  border-bottom:1px solid var(--cream-dark);
}
.cart-item-info { flex:1;min-width:0; }
.cart-item-name { font-size:.88rem;font-weight:500;color:var(--brown-deep);line-height:1.35;margin-bottom:.3rem; }
.cart-item-price { font-family:'Playfair Display',serif;font-size:.95rem;color:var(--green-deep); }
.cart-item-controls { display:flex;align-items:center;gap:.5rem; }
.qty-btn {
  width:28px;height:28px;background:var(--cream-dark);border:none;
  font-size:1.1rem;cursor:pointer;display:flex;align-items:center;justify-content:center;
  color:var(--brown-deep);transition:background .15s;border-radius:2px;
}
.qty-btn:hover { background:var(--brown-light); }
.qty-num { font-size:.9rem;font-weight:600;min-width:18px;text-align:center;color:var(--brown-deep); }
.cart-item-remove {
  background:none;border:none;color:#C0776A;cursor:pointer;
  font-size:.8rem;padding:.2rem;transition:color .15s;
  align-self:flex-start;
}
.cart-item-remove:hover { color:#9B3B3B; }

.cart-footer { padding:1.2rem 1.5rem;border-top:2px solid var(--cream-dark);flex-shrink:0; }
.cart-total {
  display:flex;justify-content:space-between;align-items:center;
  margin-bottom:1rem;
}
.cart-total-label { font-size:.85rem;color:var(--text-muted); }
.cart-total-price { font-family:'Playfair Display',serif;font-size:1.5rem;color:var(--brown-deep);font-weight:700; }
.cart-total-price small { font-size:.8rem;font-family:'Hind Siliguri',sans-serif;font-weight:400;color:var(--text-muted); }
.btn-checkout {
  width:100%;padding:.85rem;background:var(--green-deep);color:white;
  border:none;font-family:'Hind Siliguri',sans-serif;font-size:1rem;font-weight:500;
  cursor:pointer;letter-spacing:.04em;transition:background .2s;
  display:flex;align-items:center;justify-content:center;gap:.5rem;
}
.btn-checkout:hover { background:var(--green); }
.btn-checkout:disabled { background:#C4A882;cursor:not-allowed; }

/* ── ORDER FORM MODAL ── */
.modal-overlay {
  position:fixed;inset:0;background:rgba(0,0,0,.6);z-index:970;
  display:flex;align-items:center;justify-content:center;
  padding:1rem;opacity:0;pointer-events:none;transition:opacity .3s;
}
.modal-overlay.open { opacity:1;pointer-events:all; }

.modal {
  background:white;width:100%;max-width:520px;
  max-height:90vh;overflow-y:auto;
  transform:translateY(20px);transition:transform .3s;
}
.modal-overlay.open .modal { transform:translateY(0); }

.modal-header {
  background:var(--brown-deep);color:var(--cream);
  padding:1.3rem 1.5rem;
  display:flex;align-items:center;justify-content:space-between;
  position:sticky;top:0;z-index:1;
}
.modal-header h3 { font-family:'Playfair Display',serif;font-size:1.25rem;font-weight:400; }
.modal-close {
  background:transparent;border:none;color:var(--cream);
  font-size:1.5rem;cursor:pointer;line-height:1;padding:.2rem .4rem;
}
.modal-body { padding:1.5rem; }

.order-summary {
  background:var(--cream);padding:1rem;margin-bottom:1.5rem;
}
.order-summary-title {
  font-size:.75rem;text-transform:uppercase;letter-spacing:.12em;
  color:var(--gold);font-weight:500;margin-bottom:.7rem;
}
.order-summary-item {
  display:flex;justify-content:space-between;
  font-size:.85rem;color:var(--text-muted);padding:.25rem 0;
  border-bottom:1px solid var(--cream-dark);
}
.order-summary-item:last-child { border:none; }
.order-summary-item b { color:var(--brown-deep); }
.order-summary-total {
  display:flex;justify-content:space-between;
  margin-top:.6rem;padding-top:.6rem;border-top:2px solid var(--brown-light);
}
.order-summary-total span { font-weight:600;font-size:.9rem;color:var(--brown-deep); }
.order-summary-total b { font-family:'Playfair Display',serif;font-size:1.1rem;color:var(--green-deep); }

.form-group { margin-bottom:1.1rem; }
.form-label {
  display:block;font-size:.82rem;font-weight:600;
  color:var(--brown-deep);margin-bottom:.4rem;letter-spacing:.02em;
}
.form-label span { color:#C0776A; }
.form-input, .form-textarea {
  width:100%;padding:.75rem 1rem;background:white;
  border:1.5px solid var(--cream-dark);color:var(--text);
  font-family:'Hind Siliguri',sans-serif;font-size:.95rem;
  outline:none;transition:border-color .2s;border-radius:0;
  -webkit-appearance:none;
}
.form-input:focus, .form-textarea:focus { border-color:var(--green); }
.form-input::placeholder, .form-textarea::placeholder { color:#B0967A; }
.form-textarea { resize:vertical;min-height:80px;line-height:1.6; }
.form-hint { font-size:.75rem;color:var(--text-muted);margin-top:.3rem; }

.btn-send-wa {
  width:100%;padding:1rem;background:var(--wa);color:white;
  border:none;font-family:'Hind Siliguri',sans-serif;font-size:1.05rem;
  font-weight:600;cursor:pointer;letter-spacing:.03em;
  display:flex;align-items:center;justify-content:center;gap:.6rem;
  transition:background .2s,transform .15s;margin-top:.5rem;
}
.btn-send-wa:hover { background:#1ebe5d;transform:translateY(-1px); }
.btn-send-wa svg { flex-shrink:0; }

/* ── ORDER SUCCESS ── */
.order-success {
  display:none;flex-direction:column;align-items:center;
  text-align:center;padding:2.5rem 1.5rem;gap:1rem;
}
.order-success.show { display:flex; }
.success-icon { font-size:3.5rem; }
.success-title { font-family:'Playfair Display',serif;font-size:1.5rem;color:var(--brown-deep); }
.success-msg { font-size:.9rem;color:var(--text-muted);line-height:1.7;max-width:320px; }
.btn-continue {
  padding:.7rem 2rem;background:var(--brown-deep);color:var(--cream);
  border:none;font-family:'Hind Siliguri',sans-serif;font-size:.95rem;
  cursor:pointer;transition:background .2s;margin-top:.5rem;
}
.btn-continue:hover { background:var(--green-deep); }

/* ── BRAIN DEVELOPMENT SECTION ── */
.brain-section {
  background: linear-gradient(135deg, #1A3A2A 0%, #0E2218 50%, #1A1A35 100%);
  padding: 4rem 2rem;
  position: relative;
  overflow: hidden;
}
.brain-section::before {
  content:'';position:absolute;inset:0;
  background:
    radial-gradient(ellipse 60% 50% at 10% 50%, rgba(61,107,44,.18) 0%, transparent 60%),
    radial-gradient(ellipse 50% 60% at 90% 30%, rgba(100,80,200,.12) 0%, transparent 60%);
}
.brain-section::after {
  content:'';position:absolute;inset:0;opacity:.04;
  background-image:
    repeating-linear-gradient(0deg, #fff 0px, #fff 1px, transparent 1px, transparent 32px),
    repeating-linear-gradient(90deg, #fff 0px, #fff 1px, transparent 1px, transparent 32px);
}
.brain-inner { position:relative;max-width:1400px;margin:0 auto; }
.brain-header { text-align:center;margin-bottom:3rem; }
.brain-badge {
  display:inline-flex;align-items:center;gap:.5rem;
  background:rgba(255,255,255,.07);border:1px solid rgba(255,255,255,.12);
  padding:.35rem 1rem;margin-bottom:1.2rem;
  font-size:.75rem;letter-spacing:.18em;text-transform:uppercase;
  color:rgba(255,255,255,.6);font-family:'EB Garamond',serif;font-style:italic;
}
.brain-title {
  font-family:'Playfair Display',serif;
  font-size:clamp(1.8rem,4vw,2.8rem);
  color:#fff;font-weight:400;line-height:1.15;margin-bottom:.6rem;
}
.brain-title em { color:#7ECBA1;font-style:normal; }
.brain-subtitle {
  color:rgba(255,255,255,.5);font-size:.95rem;font-weight:300;
  max-width:480px;margin:0 auto;line-height:1.8;
}
.brain-divider { width:40px;height:2px;background:linear-gradient(90deg,#3D6B2C,#7ECBA1);margin:.9rem auto 0; }

.brain-grid {
  display:grid;grid-template-columns:repeat(auto-fill,minmax(240px,1fr));
  gap:1.2rem;
}
.brain-card {
  background:rgba(255,255,255,.05);
  border:1px solid rgba(255,255,255,.1);
  padding:1.6rem 1.5rem;
  transition:all .3s;position:relative;overflow:hidden;
  display:flex;flex-direction:column;
}
.brain-card::before {
  content:'';position:absolute;inset:0;
  background:linear-gradient(135deg,rgba(126,203,161,.08) 0%,transparent 60%);
  opacity:0;transition:opacity .3s;
}
.brain-card:hover { background:rgba(255,255,255,.09);border-color:rgba(126,203,161,.35);transform:translateY(-3px);box-shadow:0 12px 30px rgba(0,0,0,.3); }
.brain-card:hover::before { opacity:1; }

.brain-card-icon { font-size:2rem;margin-bottom:.9rem; }
.brain-card-sub {
  font-size:.68rem;color:#7ECBA1;text-transform:uppercase;
  letter-spacing:.15em;font-weight:500;margin-bottom:.5rem;
}
.brain-card-name {
  font-size:.95rem;color:rgba(255,255,255,.9);
  font-weight:500;line-height:1.45;flex:1;margin-bottom:1rem;
}
.brain-card-footer { display:flex;align-items:center;justify-content:space-between;margin-bottom:.9rem; }
.brain-card-price {
  font-family:'Playfair Display',serif;font-size:1.1rem;
  color:#7ECBA1;font-weight:700;
}
.brain-card-price small { font-size:.65rem;font-family:'Hind Siliguri',sans-serif;color:rgba(255,255,255,.4);margin-left:2px; }
.brain-stock-badge { font-size:.68rem;padding:.2rem .55rem;border-radius:20px; }
.brain-in-stock { background:rgba(61,107,44,.4);color:#7ECBA1;border:1px solid rgba(61,107,44,.5); }
.brain-out-stock { background:rgba(155,59,59,.3);color:#E89090;border:1px solid rgba(155,59,59,.4); }

.btn-brain-add {
  width:100%;padding:.6rem;
  background:transparent;border:1px solid rgba(126,203,161,.4);
  color:#7ECBA1;font-family:'Hind Siliguri',sans-serif;font-size:.88rem;
  cursor:pointer;transition:all .25s;letter-spacing:.03em;
  display:flex;align-items:center;justify-content:center;gap:.4rem;
}
.btn-brain-add:hover { background:rgba(126,203,161,.15);border-color:#7ECBA1; }
.btn-brain-add.added { background:rgba(61,107,44,.5);border-color:#3D6B2C;color:#fff; }
.btn-brain-add:disabled { border-color:rgba(255,255,255,.12);color:rgba(255,255,255,.25);cursor:not-allowed; }

@media(max-width:600px){ .brain-grid{grid-template-columns:1fr 1fr;} }
@media(max-width:400px){ .brain-grid{grid-template-columns:1fr;} }

/* ── ORDER STRIP (below catalogue) ── */
.order-strip {
  background:var(--brown-deep);
  padding:3.5rem 2rem;text-align:center;
}
.order-strip-label {
  font-family:'EB Garamond',serif;font-style:italic;
  color:var(--gold-light);font-size:.9rem;letter-spacing:.2em;
  text-transform:uppercase;display:block;margin-bottom:.7rem;
}
.order-strip-title {
  font-family:'Playfair Display',serif;
  font-size:clamp(1.5rem,3.5vw,2.2rem);
  color:var(--cream);font-weight:400;margin-bottom:.5rem;
}
.order-strip-sub {
  font-size:.93rem;color:var(--brown-light);font-weight:300;
  margin-bottom:2rem;line-height:1.7;
}
.order-strip-divider { width:36px;height:1px;background:var(--gold);margin:.8rem auto 1.5rem;opacity:.5; }
.order-btns { display:flex;gap:.8rem;justify-content:center;flex-wrap:wrap; }
.btn-strip {
  display:inline-flex;align-items:center;gap:.55rem;
  padding:.8rem 1.8rem;font-family:'Hind Siliguri',sans-serif;
  font-size:.95rem;font-weight:500;text-decoration:none;
  cursor:pointer;border:none;transition:all .25s;
}
.btn-strip-wa { background:var(--wa);color:#fff; }
.btn-strip-wa:hover { background:#1ebe5d;transform:translateY(-2px);box-shadow:0 5px 18px rgba(37,211,102,.28); }
.btn-strip-fb { background:var(--fb);color:#fff; }
.btn-strip-fb:hover { background:#1468d8;transform:translateY(-2px);box-shadow:0 5px 18px rgba(24,119,242,.25); }

/* ── FOOTER ── */
footer {
  background:#1A0E05;color:var(--brown-light);
  text-align:center;padding:2.5rem 2rem;
}
.footer-brand { font-family:'Playfair Display',serif;font-size:1.7rem;color:var(--cream);margin-bottom:.4rem; }
.footer-slogan { font-family:'EB Garamond',serif;font-style:italic;font-size:.95rem;color:var(--gold-light);margin-bottom:1.2rem; }
footer p { font-size:.78rem;font-weight:300;opacity:.5;font-family:'Hind Siliguri',sans-serif; }

/* ── STICKY MOBILE BAR ── */
.sticky-bar {
  position:fixed;bottom:0;left:0;right:0;
  display:none;z-index:800;
  box-shadow:0 -3px 16px rgba(0,0,0,.22);
}
.sticky-bar a {
  flex:1;display:flex;align-items:center;justify-content:center;
  gap:.45rem;padding:.9rem .5rem;font-family:'Hind Siliguri',sans-serif;
  font-size:.85rem;font-weight:500;text-decoration:none;color:#fff;
}
.sticky-bar .s-wa { background:var(--wa); }
.sticky-bar .s-fb { background:var(--fb); }
@media(max-width:640px){
  .sticky-bar{display:flex;}
  body{padding-bottom:56px;}
  .cart-fab{bottom:4.5rem;}
}

/* animations */
@keyframes fadeUp{from{opacity:0;transform:translateY(18px);}to{opacity:1;transform:translateY(0);}}
@keyframes pop{0%{transform:scale(1);}40%{transform:scale(1.3);}100%{transform:scale(1);}}
.hero-content>*{animation:fadeUp .8s ease forwards;opacity:0;}
.store-tag{animation-delay:.1s}.hero-title{animation-delay:.25s}.hero-slogan{animation-delay:.4s}
.hero-divider{animation-delay:.5s}.hero-desc{animation-delay:.6s}.hero-cta{animation-delay:.75s}
.hero-stats{animation-delay:.9s}
.pop{animation:pop .3s ease;}
</style>
</head>
<body>

<!-- HERO -->
<section class="hero">
  <div class="hero-pattern"></div>
  <div class="hero-content">
    <span class="store-tag">Store of Life</span>
    <h1 class="hero-title">
      টাউনস্টোর
      <span>জীবনের ভান্ডার</span>
    </h1>
    <p class="hero-slogan">প্রকৃতি ও ঐতিহ্যের মাঝে জীবনকে অন্বেষণ করি</p>
    <div class="hero-divider"></div>
    <p class="hero-desc">
      নিরাপদ খাদ্যপণ্য, ঐতিহ্যবাহী হস্তশিল্প, প্রাকৃতিক স্বাস্থ্য উপকরণ —<br>যা কিছু আসল, যা কিছু ভালো, সব এক জায়গায়।
    </p>
    <a href="#catalogue" class="hero-cta">পণ্য দেখুন</a>
    <div class="hero-stats">
      <div class="stat"><div class="stat-num">৩৮০+</div><div class="stat-label">পণ্য</div></div>
      <div class="stat"><div class="stat-num">১৫+</div><div class="stat-label">বিভাগ</div></div>
      <div class="stat"><div class="stat-num">১০০%</div><div class="stat-label">আস্থার পণ্য</div></div>
    </div>
  </div>
</section>

<!-- CATALOGUE -->
<section class="catalogue" id="catalogue">
  <div class="section-header">
    <span class="section-label">Our Collection</span>
    <h2 class="section-title">সম্পূর্ণ পণ্য তালিকা</h2>
  </div>
  <div class="search-wrap">
    <span class="search-icon">🔍</span>
    <input type="text" class="search-input" id="searchInput" placeholder="পণ্য খুঁজুন...">
  </div>
  <div class="filters" id="filters"></div>
  <p class="results-info" id="resultsInfo"></p>
  <div class="product-grid" id="productGrid"></div>
</section>

<!-- BRAIN DEVELOPMENT SECTION -->
<section class="brain-section" id="brainSection">
  <div class="brain-inner">
    <div class="brain-header">
      <div class="brain-badge">🧠 নতুন বিভাগ</div>
      <h2 class="brain-title">মস্তিষ্ক বিকাশ<br><em>পণ্য সমূহ</em></h2>
      <div class="brain-divider"></div>
      <p class="brain-subtitle">শিশুর চিন্তাশক্তি, মনোযোগ ও সৃজনশীলতা বাড়ানোর জন্য বিশেষভাবে বাছাই করা পণ্য</p>
    </div>
    <div class="brain-grid" id="brainGrid"></div>
  </div>
</section>

<!-- ORDER STRIP -->
<section class="order-strip">
  <span class="order-strip-label">অর্ডার করুন</span>
  <h2 class="order-strip-title">পছন্দের পণ্য পেতে যোগাযোগ করুন</h2>
  <div class="order-strip-divider"></div>
  <p class="order-strip-sub">নক দিন আমাদের WhatsApp-এ অথবা মেসেজ করুন Facebook পেইজে</p>
  <div class="order-btns">
    <a href="https://wa.me/8801720003870" target="_blank" rel="noopener" class="btn-strip btn-strip-wa">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
      WhatsApp-এ নক দিন
    </a>
    <a href="https://www.facebook.com/townstoreonlineshop" target="_blank" rel="noopener" class="btn-strip btn-strip-fb">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="currentColor"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
      Facebook পেইজে মেসেজ করুন
    </a>
  </div>
</section>

<footer>
  <div class="footer-brand">টাউনস্টোর</div>
  <div class="footer-slogan">জীবনের ভান্ডার</div>
  <p>প্রকৃতি ও ঐতিহ্যের প্রতি আমাদের অঙ্গীকার</p>
</footer>

<!-- CART FAB -->
<button class="cart-fab" id="cartFab" title="কার্ট দেখুন">
  <svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
    <circle cx="9" cy="21" r="1"/><circle cx="20" cy="21" r="1"/>
    <path d="M1 1h4l2.68 13.39a2 2 0 0 0 2 1.61h9.72a2 2 0 0 0 2-1.61L23 6H6"/>
  </svg>
  <span class="cart-count" id="cartCount">0</span>
</button>

<!-- CART OVERLAY + SIDEBAR -->
<div class="cart-overlay" id="cartOverlay"></div>
<div class="cart-sidebar" id="cartSidebar">
  <div class="cart-header">
    <h3>🛒 আপনার কার্ট</h3>
    <button class="cart-close" id="cartClose">✕</button>
  </div>
  <div class="cart-items" id="cartItems">
    <div class="cart-empty">
      <span class="cart-empty-icon">🧺</span>
      <span>কার্ট এখনো খালি।<br>পণ্য যোগ করুন।</span>
    </div>
  </div>
  <div class="cart-footer" id="cartFooter" style="display:none">
    <div class="cart-total">
      <span class="cart-total-label">মোট পরিমাণ</span>
      <span class="cart-total-price">৳ <span id="cartTotal">0</span> <small>টাকা</small></span>
    </div>
    <button class="btn-checkout" id="btnCheckout">
      <svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M22 11.08V12a10 10 0 1 1-5.93-9.14"/><polyline points="22 4 12 14.01 9 11.01"/></svg>
      অর্ডার দিন
    </button>
  </div>
</div>

<!-- ORDER FORM MODAL -->
<div class="modal-overlay" id="modalOverlay">
  <div class="modal" id="orderModal">
    <div class="modal-header">
      <h3>অর্ডার ফর্ম</h3>
      <button class="modal-close" id="modalClose">✕</button>
    </div>
    <div class="modal-body" id="modalBody">
      <!-- Order summary -->
      <div class="order-summary">
        <div class="order-summary-title">অর্ডার সারসংক্ষেপ</div>
        <div id="summaryItems"></div>
        <div class="order-summary-total">
          <span>মোট</span>
          <b>৳ <span id="summaryTotal">0</span></b>
        </div>
      </div>

      <!-- Form fields -->
      <div class="form-group">
        <label class="form-label" for="custName">আপনার নাম <span>*</span></label>
        <input type="text" id="custName" class="form-input" placeholder="পূর্ণ নাম লিখুন">
      </div>
      <div class="form-group">
        <label class="form-label" for="custPhone">মোবাইল নম্বর <span>*</span></label>
        <input type="tel" id="custPhone" class="form-input" placeholder="01XXXXXXXXX">
        <p class="form-hint">আমরা এই নম্বরে যোগাযোগ করব</p>
      </div>
      <div class="form-group">
        <label class="form-label" for="custAddress">ডেলিভারি ঠিকানা <span>*</span></label>
        <textarea id="custAddress" class="form-textarea" placeholder="বাড়ি নম্বর, রাস্তা, এলাকা, জেলা লিখুন..."></textarea>
      </div>
      <div class="form-group">
        <label class="form-label" for="custNote">বিশেষ নির্দেশনা (ঐচ্ছিক)</label>
        <textarea id="custNote" class="form-textarea" style="min-height:60px" placeholder="কোনো বিশেষ অনুরোধ থাকলে লিখুন..."></textarea>
      </div>
      <button class="btn-send-wa" id="btnSendWA">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
        WhatsApp-এ অর্ডার পাঠান
      </button>
    </div>
    <!-- Success state -->
    <div class="order-success" id="orderSuccess">
      <div class="success-icon">✅</div>
      <div class="success-title">অর্ডার পাঠানো হচ্ছে!</div>
      <p class="success-msg">WhatsApp খুলছে। আমাদের টিম শীঘ্রই আপনার সাথে যোগাযোগ করবে।</p>
      <button class="btn-continue" id="btnContinue">কেনাকাটা চালিয়ে যান</button>
    </div>
  </div>
</div>

<!-- STICKY MOBILE BAR -->
<div class="sticky-bar">
  <a href="https://wa.me/8801720003870" target="_blank" rel="noopener" class="s-wa">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413Z"/></svg>
    WhatsApp
  </a>
  <a href="https://www.facebook.com/townstoreonlineshop" target="_blank" rel="noopener" class="s-fb">
    <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor"><path d="M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z"/></svg>
    Facebook
  </a>
</div>

<script>
// ── PRODUCT DATA ──
const products = [
  {n:"A2 Milk (দেশী গাভীর দুধ) 1L",c:"দুগ্ধ",p:110,qty:0},{n:"ABF Broiler 1Kg",c:"মাংস",p:420,qty:27},
  {n:"Afghani Dried Fig (ত্বীন) 100gm",c:"মুদিখানা",p:250,qty:17},{n:"Ajwa Dates 1Kg",c:"ফল",p:1500,qty:12},
  {n:"Ajwa Dates 3Kg",c:"ফল",p:4200,qty:0},{n:"Ajwa Dates 500gm",c:"ফল",p:780,qty:24},
  {n:"Ajwain (জোয়ান) 50gm",c:"স্বাস্থ্য",p:40,qty:31},{n:"Akher Beej Gur 500gm",c:"মিষ্টি",p:280,qty:12},
  {n:"Akher Danadar Gur 1kg",c:"মিষ্টি",p:300,qty:74},{n:"Akher Gur Handi 1.5kg",c:"মিষ্টি",p:450,qty:0},
  {n:"Akher Liquid Gur (Homemade) 500gm",c:"মিষ্টি",p:250,qty:39},{n:"Akher Patali Gur 1kg",c:"মিষ্টি",p:300,qty:104},
  {n:"Akher Powder Gur 1kg",c:"মিষ্টি",p:350,qty:5},{n:"Akher Powder Gur 500gm",c:"মিষ্টি",p:180,qty:187},
  {n:"Alkushi Powder 100gm",c:"স্বাস্থ্য",p:300,qty:16},{n:"Almond 250gm",c:"মুদিখানা",p:380,qty:48},
  {n:"Almond 250gm (Roasted)",c:"স্ন্যাকস",p:410,qty:52},{n:"Alubukhara 250gm",c:"মুদিখানা",p:190,qty:8},
  {n:"Alubukhara Pickle 460gm",c:"মুদিখানা",p:490,qty:6},{n:"Amloki Powder 100gm",c:"স্বাস্থ্য",p:110,qty:12},
  {n:"Arhar Daal (অরহর ডাল) 500gm",c:"মুদিখানা",p:140,qty:12},{n:"Arjun Powder 100gm",c:"স্বাস্থ্য",p:90,qty:12},
  {n:"Ashwagandha Powder 100gm",c:"স্বাস্থ্য",p:200,qty:12},{n:"Atap Rice Flour 1Kg",c:"মুদিখানা",p:140,qty:18},
  {n:"Bamboo Chalni - Large",c:"হস্তশিল্প",p:350,qty:32},{n:"Bamboo Jhuri - Small",c:"হস্তশিল্প",p:150,qty:32},
  {n:"Bamboo Kula - Large",c:"হস্তশিল্প",p:210,qty:32},{n:"Bamboo Wastebin",c:"হস্তশিল্প",p:450,qty:0},
  {n:"Barley Oats (যবের ওটস) 300gm",c:"স্ন্যাকস",p:220,qty:32},{n:"Basil Seeds (তোকমাদানা) 100gm",c:"স্বাস্থ্য",p:50,qty:22},
  {n:"Bee Pollen 25gm",c:"স্বাস্থ্য",p:250,qty:20},{n:"Beef (দেশী ষাঁড়) 1kg",c:"মাংস",p:810,qty:13},
  {n:"Beef Pickle 250gm",c:"মুদিখানা",p:450,qty:5},{n:"Bitroot Powder (Deshi) 100gm",c:"স্বাস্থ্য",p:300,qty:48},
  {n:"Bitroot Powder 100gm",c:"স্বাস্থ্য",p:250,qty:48},{n:"Black Cardamom (কালো এলাচ) 50gm",c:"মুদিখানা",p:220,qty:20},
  {n:"Black Pepper (কালো গোলমরিচ) 50gm",c:"মুদিখানা",p:100,qty:38},{n:"Black Pepper Powder 50gm",c:"মুদিখানা",p:120,qty:31},
  {n:"Black Raisins (কালো কিসমিস) 120gm",c:"মুদিখানা",p:120,qty:72},{n:"Black Salt (বিট লবণ) 100gm",c:"মুদিখানা",p:30,qty:6},
  {n:"Black Tea (GBOP) 200gm",c:"মুদিখানা",p:150,qty:247},{n:"Black Tea (GBOP) 400gm",c:"মুদিখানা",p:290,qty:31},
  {n:"Blackseed (কালোজিরা) 100gm",c:"মুদিখানা",p:80,qty:251},{n:"Blackseed Oil 100ml",c:"তেল",p:250,qty:102},
  {n:"Blackseed Powder 100gm",c:"মুদিখানা",p:100,qty:72},{n:"Blackseed Honey 250gm",c:"মধু",p:400,qty:44},
  {n:"Blackseed Honey 500gm",c:"মধু",p:780,qty:64},{n:"Bombai Chilli Pickle 400gm",c:"মুদিখানা",p:490,qty:18},
  {n:"Boot (দেশি ছোলা) 1kg",c:"মুদিখানা",p:150,qty:20},{n:"Boot (দেশি ছোলা) 500gm",c:"মুদিখানা",p:75,qty:56},
  {n:"Booter Daal (Deshi) 500gm",c:"মুদিখানা",p:80,qty:40},{n:"Boroi Honey 250gm",c:"মধু",p:300,qty:144},
  {n:"Boroi Honey 500gm",c:"মধু",p:580,qty:72},{n:"Brown Flattenned Rice (লাল চিড়া) 250gm",c:"স্ন্যাকস",p:35,qty:163},
  {n:"Brown Flattenned Rice (লাল চিড়া) 500gm",c:"স্ন্যাকস",p:70,qty:114},{n:"Brown Puffed Rice 500gm",c:"স্ন্যাকস",p:90,qty:32},
  {n:"Brown Sugar 1kg",c:"মিষ্টি",p:180,qty:192},{n:"Brown Sugar 500gm",c:"মিষ্টি",p:90,qty:100},
  {n:"Brown Wheat Flour 1Kg",c:"মুদিখানা",p:90,qty:474},{n:"Butter (Deshi) 250gm",c:"দুগ্ধ",p:350,qty:16},
  {n:"Butter (Imported) 250gm",c:"দুগ্ধ",p:250,qty:52},{n:"Cardamom (সবুজ এলাচি) 50gm",c:"মুদিখানা",p:380,qty:40},
  {n:"Cashew Nut 250gm",c:"মুদিখানা",p:500,qty:56},{n:"Cashew Nut (Roasted) 250gm",c:"স্ন্যাকস",p:540,qty:72},
  {n:"Castor Oil 100ml",c:"তেল",p:160,qty:8},{n:"Ceylon Cinnamon (দারুচিনি) 100gm",c:"মুদিখানা",p:180,qty:20},
  {n:"Ceylon Cinnamon (দারুচিনি) 50gm",c:"মুদিখানা",p:100,qty:30},{n:"Chamara Half Fiber Rice 1Kg",c:"মুদিখানা",p:75,qty:150},
  {n:"Chia Seed (Deshi) 100gm",c:"স্বাস্থ্য",p:80,qty:166},{n:"Chia Seed (Deshi) 250gm",c:"স্বাস্থ্য",p:190,qty:140},
  {n:"Chia Seed (Deshi) 500gm",c:"স্বাস্থ্য",p:370,qty:88},{n:"Chilli Powder (মরিচ গুঁড়া) 100gm",c:"মুদিখানা",p:90,qty:32},
  {n:"Chingri Balachao 100gm",c:"মাছ",p:200,qty:73},{n:"Chingri Balachao 200gm",c:"মাছ",p:380,qty:21},
  {n:"Chinigura Aromatic Rice 1kg",c:"মুদিখানা",p:160,qty:559},{n:"Chuijhal (চুইঝাল) 100gm",c:"মুদিখানা",p:140,qty:32},
  {n:"Chuijhal Muri Masla 200gm",c:"মুদিখানা",p:250,qty:15},{n:"Classical Bason",c:"হস্তশিল্প",p:90,qty:32},
  {n:"Clay Water Glass",c:"হস্তশিল্প",p:100,qty:12},{n:"Clay Water Jug",c:"হস্তশিল্প",p:450,qty:0},
  {n:"Clove (লবঙ্গ) 50gm",c:"মুদিখানা",p:130,qty:30},{n:"Coconut Oil (Cold Pressed) 100ml",c:"তেল",p:190,qty:47},
  {n:"Coconut Oil (Cold Pressed) 250ml",c:"তেল",p:450,qty:346},{n:"Coconut Oil (Cold Pressed) 500ml",c:"তেল",p:880,qty:532},
  {n:"Coffee/Water Mug",c:"হস্তশিল্প",p:110,qty:20},{n:"Coriander Powder (ধনিয়া গুঁড়া) 100gm",c:"মুদিখানা",p:60,qty:193},
  {n:"Cumin (জিরা) 100gm",c:"মুদিখানা",p:120,qty:22},{n:"Cumin Powder (জিরা গুঁড়া) 100gm",c:"মুদিখানা",p:150,qty:61},
  {n:"Cup Doi",c:"দুগ্ধ",p:40,qty:98},{n:"Curry Bowl (XL)",c:"হস্তশিল্প",p:210,qty:48},
  {n:"Deshi Duck (পাতি হাঁস) 1Kg",c:"মাংস",p:800,qty:3},{n:"Deshi Onion 1Kg",c:"সবজি",p:80,qty:13},
  {n:"Deshi Potato 1Kg",c:"সবজি",p:50,qty:15},{n:"Design Serving Dish (Large)",c:"হস্তশিল্প",p:200,qty:32},
  {n:"Drinking Yogurt (মাঠা) 200ml",c:"দুগ্ধ",p:50,qty:24},{n:"Extra Virgin Olive Oil 100ml",c:"তেল",p:290,qty:63},
  {n:"Extra Virgin Olive Oil 250ml",c:"তেল",p:700,qty:12},{n:"Extra Virgin Olive Oil 500ml",c:"তেল",p:1380,qty:6},
  {n:"Fennel (মৌরি) 100gm",c:"মুদিখানা",p:50,qty:52},{n:"Firni Bowl",c:"হস্তশিল্প",p:120,qty:40},
  {n:"Flaxseed (তিসি) 100gm",c:"স্বাস্থ্য",p:80,qty:28},{n:"Flaxseed Oil 100ml",c:"তেল",p:140,qty:8},
  {n:"Foxtail Millet (কাউন) 1kg",c:"মুদিখানা",p:250,qty:19},{n:"Foxtail Millet (কাউন) 500gm",c:"মুদিখানা",p:130,qty:24},
  {n:"Ganjia Half Fiber Rice 1Kg",c:"মুদিখানা",p:95,qty:50},{n:"Gawa Ghee 200gm",c:"দুগ্ধ",p:320,qty:157},
  {n:"Gawa Ghee 450gm",c:"দুগ্ধ",p:700,qty:77},{n:"Golden Raisins (কিসমিস) 100gm",c:"মুদিখানা",p:140,qty:108},
  {n:"Gouromoti Mango 1Kg",c:"ফল",p:180,qty:32},{n:"Gram Flour (বুটের বেসন) 250gm",c:"মুদিখানা",p:50,qty:38},
  {n:"Gram Flour (বুটের বেসন) 500gm",c:"মুদিখানা",p:100,qty:36},{n:"Green Tea 100gm",c:"মুদিখানা",p:200,qty:10},
  {n:"Grihostho Mustard Oil 1L",c:"তেল",p:280,qty:4},{n:"Grihostho Mustard Oil 5L",c:"তেল",p:1350,qty:4},
  {n:"Handmade Sugar 500gm",c:"মিষ্টি",p:150,qty:32},{n:"Himalayan Pink Salt 250gm",c:"মুদিখানা",p:120,qty:41},
  {n:"Homemade Chilli Olive Pickle 410gm",c:"মুদিখানা",p:400,qty:20},{n:"Homemade Garlic Pickle 215gm",c:"মুদিখানা",p:270,qty:32},
  {n:"Homemade Garlic Pickle 415gm",c:"মুদিখানা",p:490,qty:28},{n:"Homemade Jolpai Sweet Pickle 410gm",c:"মুদিখানা",p:390,qty:48},
  {n:"Honey Nuts 450gm",c:"স্ন্যাকস",p:980,qty:12},{n:"Insaf Mustard Oil 5L",c:"তেল",p:1400,qty:8},
  {n:"Isabgol Bhusi (Psyllium Husk) 100gm",c:"স্বাস্থ্য",p:190,qty:27},{n:"Isabgol Bhusi 50gm",c:"স্বাস্থ্য",p:100,qty:54},
  {n:"Jolpai Spicy Ball Pickle 350gm",c:"মুদিখানা",p:320,qty:28},{n:"Kalojira Aromatic Rice 1kg",c:"মুদিখানা",p:170,qty:50},
  {n:"Kashmiri Raisins (কিসমিস) 100gm",c:"মুদিখানা",p:120,qty:84},{n:"Kasundi 200gm",c:"মুদিখানা",p:120,qty:6},
  {n:"Katari Nazir Rice 1Kg",c:"মুদিখানা",p:95,qty:246},{n:"Katari Nazir Rice 25Kg",c:"মুদিখানা",p:2300,qty:12},
  {n:"Khejurer Beej Gur 1Kg",c:"মিষ্টি",p:800,qty:15},{n:"Khejurer Danadar Gur (Jessore) 1Kg",c:"মিষ্টি",p:550,qty:8},
  {n:"Khejurer Liquid Gur 1Kg",c:"মিষ্টি",p:480,qty:25},{n:"Khejurer Liquid Gur 500gm",c:"মিষ্টি",p:250,qty:54},
  {n:"Khejurer Patali Gur (Chuadanga) 1Kg",c:"মিষ্টি",p:580,qty:15},{n:"Khesari Dal 500gm",c:"মুদিখানা",p:85,qty:72},
  {n:"Khoi 250gm",c:"স্ন্যাকস",p:60,qty:200},{n:"Kumro Bori 250gm",c:"মুদিখানা",p:190,qty:20},
  {n:"Laccha Shemai (Butter+Ghee) 200gm",c:"স্ন্যাকস",p:280,qty:202},{n:"Laccha Shemai (Peanut Oil) 200gm",c:"স্ন্যাকস",p:140,qty:227},
  {n:"Laccha Shemai (Regular) 200gm",c:"স্ন্যাকস",p:90,qty:18},{n:"Lichu Honey 250gm",c:"মধু",p:250,qty:32},
  {n:"Loitta Shutki 250gm",c:"মাছ",p:490,qty:12},{n:"Mabroom Dates 1Kg",c:"ফল",p:1100,qty:12},
  {n:"Mabroom Dates 500gm",c:"ফল",p:580,qty:24},{n:"Maryam Dates 1Kg",c:"ফল",p:1300,qty:15},
  {n:"Maryam Dates 500gm",c:"ফল",p:680,qty:30},{n:"Mashkalai Dal 500gm",c:"মুদিখানা",p:120,qty:532},
  {n:"Mashkalai Dal Powder 500gm",c:"মুদিখানা",p:150,qty:530},{n:"Medjool Dates 1Kg",c:"ফল",p:1700,qty:5},
  {n:"Medjool Dates 500gm",c:"ফল",p:880,qty:20},{n:"Mehedi Powder 100gm",c:"সৌন্দর্য",p:120,qty:52},
  {n:"Melon Seeds 100gm",c:"স্বাস্থ্য",p:150,qty:26},{n:"Methi 100gm",c:"স্বাস্থ্য",p:60,qty:112},
  {n:"Methi Powder 100gm",c:"স্বাস্থ্য",p:80,qty:90},{n:"Milk 500ml",c:"দুগ্ধ",p:50,qty:40},
  {n:"Mixed Balachao 100gm",c:"মাছ",p:220,qty:18},{n:"Moong Dal (মুগ ডাল) 500gm",c:"মুদিখানা",p:100,qty:174},
  {n:"Moringa (সজিনা পাতা) Powder 100gm",c:"স্বাস্থ্য",p:120,qty:58},{n:"Moringa Powder 200gm",c:"স্বাস্থ্য",p:230,qty:36},
  {n:"Moshur Dal 1kg",c:"মুদিখানা",p:180,qty:71},{n:"Moshur Dal 500gm",c:"মুদিখানা",p:90,qty:146},
  {n:"Motka Doi 1Pc",c:"দুগ্ধ",p:60,qty:50},{n:"Multani Mud Powder 100gm",c:"সৌন্দর্য",p:120,qty:12},
  {n:"Mustard Flower Honey 250gm",c:"মধু",p:200,qty:143},{n:"Mustard Flower Honey 500gm",c:"মধু",p:380,qty:88},
  {n:"Naga Hot Pickle 400gm",c:"মুদিখানা",p:490,qty:18},{n:"Natural Honey (Khudi Maasi) 250gm",c:"মধু",p:550,qty:84},
  {n:"Natural Honey (Khudi Maasi) 500gm",c:"মধু",p:1080,qty:32},{n:"Neem Oil 100ml",c:"তেল",p:150,qty:10},
  {n:"Nutmeg (জয়ফল) 50gm",c:"মুদিখানা",p:80,qty:18},{n:"Panch Phoron (পাঁচ ফোঁড়ন) 100gm",c:"মুদিখানা",p:60,qty:51},
  {n:"Peanut (Roasted) 250gm",c:"স্ন্যাকস",p:130,qty:156},{n:"Peanut 500gm",c:"মুদিখানা",p:140,qty:70},
  {n:"Pistachio (Roasted) 200gm",c:"স্ন্যাকস",p:550,qty:20},{n:"Poppy Seed 100gm",c:"মুদিখানা",p:380,qty:9},
  {n:"Puffed Rice (মুড়ি) 500gm",c:"স্ন্যাকস",p:90,qty:32},{n:"Pumpkin Seed 150gm",c:"স্বাস্থ্য",p:150,qty:102},
  {n:"Raw Turmeric Powder 75gm",c:"স্বাস্থ্য",p:190,qty:31},{n:"Roasted Barley Flour (যবের ছাতু) 250gm",c:"স্ন্যাকস",p:100,qty:107},
  {n:"Roasted Mixed Flour (মিক্সড ছাতু) 250gm",c:"স্ন্যাকস",p:190,qty:68},{n:"Rosemary 50gm",c:"স্বাস্থ্য",p:200,qty:20},
  {n:"Sabri Banana 1Pc",c:"ফল",p:12,qty:200},{n:"Sabudana (Sago) 500gm",c:"মুদিখানা",p:150,qty:94},
  {n:"Safawi Dates 1Kg",c:"ফল",p:1000,qty:12},{n:"Safawi Dates 500gm",c:"ফল",p:530,qty:24},
  {n:"Sandal Wood Powder (সাদা চন্দন) 50gm",c:"সৌন্দর্য",p:110,qty:20},{n:"Serving Bowl (Large)",c:"হস্তশিল্প",p:300,qty:32},
  {n:"Serving Bowl (Medium)",c:"হস্তশিল্প",p:300,qty:10},{n:"Serving Bowl (Small)",c:"হস্তশিল্প",p:250,qty:6},
  {n:"Sesame Oil (তিলের তেল) 100ml",c:"তেল",p:120,qty:52},{n:"Shahi Garam Masala 100gm",c:"মুদিখানা",p:290,qty:62},
  {n:"Shahi Garam Masala 50gm",c:"মুদিখানা",p:150,qty:72},{n:"Sharbat Seed Mix 150gm",c:"স্বাস্থ্য",p:190,qty:58},
  {n:"Sona Pata Powder 100gm",c:"স্বাস্থ্য",p:100,qty:12},{n:"Sora/Haari Doi (500-600gm)",c:"দুগ্ধ",p:280,qty:11},
  {n:"Soup Bowl",c:"হস্তশিল্প",p:120,qty:48},{n:"Sour & Sweet Mango Bar 250gm",c:"স্ন্যাকস",p:120,qty:60},
  {n:"Sour & Sweet Mango Bar 500gm",c:"স্ন্যাকস",p:220,qty:12},{n:"Spicy Mango Bar 500gm",c:"স্ন্যাকস",p:250,qty:44},
  {n:"Star Anise 50gm",c:"মুদিখানা",p:120,qty:10},{n:"Stevia Powder 50gm",c:"মিষ্টি",p:190,qty:32},
  {n:"Sukkari Mufattal Dates 1Kg",c:"ফল",p:900,qty:12},{n:"Sukkari Mufattal Dates 500gm",c:"ফল",p:480,qty:24},
  {n:"Sundarban Khalisha Natural Honey 250gm",c:"মধু",p:550,qty:140},{n:"Sundarban Khalisha Natural Honey 500gm",c:"মধু",p:1080,qty:40},
  {n:"Sunflower Seeds 100gm",c:"স্বাস্থ্য",p:100,qty:36},{n:"Sweet Butter 250gm",c:"দুগ্ধ",p:300,qty:22},
  {n:"Sweet Mango Bar 500gm",c:"স্ন্যাকস",p:280,qty:12},{n:"Taal Gur (তালের দানাদার গুড়) 1Kg",c:"মিষ্টি",p:480,qty:10},
  {n:"Taal Gur (তালের পাটালি গুড়) 1Kg",c:"মিষ্টি",p:480,qty:10},{n:"Taal Gur (তালের লালি) 500gm",c:"মিষ্টি",p:230,qty:12},
  {n:"Talmisri 250gm",c:"মিষ্টি",p:100,qty:108},{n:"Talmisri 500gm",c:"মিষ্টি",p:190,qty:8},
  {n:"Tamarind Pickle 450gm",c:"মুদিখানা",p:420,qty:12},{n:"Tamarind (পাহাড়ি তেতুল) 250gm",c:"ফল",p:90,qty:60},
  {n:"Tamarind (পাহাড়ি তেতুল) 500gm",c:"ফল",p:180,qty:50},{n:"Tea Cup & Saucer",c:"হস্তশিল্প",p:120,qty:3},
  {n:"Tooth Powder 40gm",c:"স্বাস্থ্য",p:90,qty:100},{n:"Tulshi Powder 100gm",c:"স্বাস্থ্য",p:100,qty:4},
  {n:"Turmeric Powder (হলুদ গুড়া) 100gm",c:"মুদিখানা",p:90,qty:60},{n:"Turmeric Powder (হলুদ গুড়া) 200gm",c:"মুদিখানা",p:170,qty:58},
  {n:"Walnut (আখরোট) 100gm",c:"মুদিখানা",p:180,qty:72},{n:"Wheat Straw Snacks Plate",c:"হস্তশিল্প",p:220,qty:48},
  {n:"White Sesame (সাদা তিল) 140gm",c:"স্বাস্থ্য",p:100,qty:78},{n:"Indonesian Black Rice 1Kg",c:"মুদিখানা",p:250,qty:5},
  {n:"Brain Game Jigsaw Puzzle 24 Pieces",c:"মস্তিষ্ক বিকাশ",p:100,qty:0},
  {n:"Brain Game Wooden Jigsaw Puzzle 60 Pcs",c:"মস্তিষ্ক বিকাশ",p:300,qty:0},
  {n:"Brain Game Wooden Jigsaw Puzzle 9 Pcs",c:"মস্তিষ্ক বিকাশ",p:85,qty:0},
  {n:"Learn Arabic Activity Flash Cards",c:"মস্তিষ্ক বিকাশ",p:350,qty:0},
  {n:"Learn Bangla Activity Flash Cards",c:"মস্তিষ্ক বিকাশ",p:350,qty:0},
  {n:"Learn English Activity Flash Cards",c:"মস্তিষ্ক বিকাশ",p:350,qty:0},
];

const catOrder = ["সব","মুদিখানা","তেল","মধু","মিষ্টি","স্বাস্থ্য","দুগ্ধ","মাংস","মাছ","ফল","হস্তশিল্প","সৌন্দর্য","স্ন্যাকস","সবজি","মস্তিষ্ক বিকাশ"];

// ── CART STATE ──
let cart = [];
let activeFilter = "সব";
let searchTerm = "";

function getCartTotal() {
  return cart.reduce((s,i) => s + i.p * i.qty, 0);
}
function getCartCount() {
  return cart.reduce((s,i) => s + i.qty, 0);
}

// ── RENDER CATALOGUE ──
function render() {
  const filtered = products.filter(p => {
    const mc = activeFilter === "সব" || p.c === activeFilter;
    const ms = !searchTerm || p.n.toLowerCase().includes(searchTerm.toLowerCase()) || p.c.toLowerCase().includes(searchTerm.toLowerCase());
    return mc && ms;
  });

  document.getElementById("resultsInfo").textContent = filtered.length + "টি পণ্য পাওয়া গেছে";

  const grid = document.getElementById("productGrid");
  if (!filtered.length) {
    grid.innerHTML = `<div class="no-results">কোনো পণ্য পাওয়া যায়নি</div>`;
    return;
  }

  grid.innerHTML = filtered.map((p, i) => {
    const cartItem = cart.find(c => c.n === p.n);
    const inCart = !!cartItem;
    const oos = p.qty === 0;
    return `
    <div class="product-card">
      <div class="product-cat-badge">${p.c}</div>
      <div class="product-name">${p.n}</div>
      <div class="product-footer">
        <div class="product-price">৳ ${p.p.toLocaleString()}<span>টাকা</span></div>
        <span class="stock-badge ${oos ? 'out-stock' : 'in-stock'}">${oos ? 'শেষ' : 'পাওয়া যাচ্ছে'}</span>
      </div>
      <button class="btn-add ${inCart ? 'added' : ''}" ${oos ? 'disabled' : ''} onclick="addToCart('${p.n.replace(/'/g,"\\'")}', ${p.p})">
        ${oos ? 'স্টক নেই' : inCart ? '✓ কার্টে আছে' : '+ কার্টে যোগ করুন'}
      </button>
    </div>`;
  }).join('');
}

function buildFilters() {
  const cats = [...new Set(products.map(p => p.c))];
  const ordered = catOrder.filter(c => c === "সব" || cats.includes(c));
  document.getElementById("filters").innerHTML = ordered.map(c =>
    `<button class="filter-btn ${c === 'সব' ? 'active' : ''}" data-cat="${c}">${c}</button>`
  ).join('');
  document.querySelectorAll(".filter-btn").forEach(btn => {
    btn.addEventListener("click", () => {
      document.querySelectorAll(".filter-btn").forEach(b => b.classList.remove("active"));
      btn.classList.add("active");
      activeFilter = btn.dataset.cat;
      render();
    });
  });
}

document.getElementById("searchInput").addEventListener("input", e => {
  searchTerm = e.target.value;
  render();
});

// ── CART FUNCTIONS ──
function addToCart(name, price) {
  const existing = cart.find(i => i.n === name);
  if (existing) {
    existing.qty++;
  } else {
    cart.push({ n: name, p: price, qty: 1 });
  }
  updateCartUI();
  render();
  // Pop animation
  const fab = document.getElementById("cartFab");
  fab.classList.remove("pop");
  void fab.offsetWidth;
  fab.classList.add("pop");
}

function updateCartUI() {
  const count = getCartCount();
  const countEl = document.getElementById("cartCount");
  countEl.textContent = count;
  countEl.classList.toggle("show", count > 0);
  renderCartItems();
}

function renderCartItems() {
  const container = document.getElementById("cartItems");
  const footer = document.getElementById("cartFooter");

  if (!cart.length) {
    container.innerHTML = `<div class="cart-empty"><span class="cart-empty-icon">🧺</span><span>কার্ট এখনো খালি।<br>পণ্য যোগ করুন।</span></div>`;
    footer.style.display = "none";
    return;
  }

  footer.style.display = "block";
  container.innerHTML = cart.map((item, idx) => `
    <div class="cart-item">
      <div class="cart-item-info">
        <div class="cart-item-name">${item.n}</div>
        <div class="cart-item-price">৳ ${(item.p * item.qty).toLocaleString()}</div>
      </div>
      <div style="display:flex;flex-direction:column;align-items:flex-end;gap:.3rem">
        <button class="cart-item-remove" onclick="removeFromCart(${idx})">✕ সরান</button>
        <div class="cart-item-controls">
          <button class="qty-btn" onclick="changeQty(${idx}, -1)">−</button>
          <span class="qty-num">${item.qty}</span>
          <button class="qty-btn" onclick="changeQty(${idx}, 1)">+</button>
        </div>
      </div>
    </div>
  `).join('');

  document.getElementById("cartTotal").textContent = getCartTotal().toLocaleString();
}

function changeQty(idx, delta) {
  cart[idx].qty += delta;
  if (cart[idx].qty <= 0) cart.splice(idx, 1);
  updateCartUI();
  render();
}

function removeFromCart(idx) {
  cart.splice(idx, 1);
  updateCartUI();
  render();
}

// ── CART OPEN/CLOSE ──
const cartFab = document.getElementById("cartFab");
const cartSidebar = document.getElementById("cartSidebar");
const cartOverlay = document.getElementById("cartOverlay");
const cartClose = document.getElementById("cartClose");

function openCart() {
  cartSidebar.classList.add("open");
  cartOverlay.classList.add("open");
  document.body.style.overflow = "hidden";
}
function closeCart() {
  cartSidebar.classList.remove("open");
  cartOverlay.classList.remove("open");
  document.body.style.overflow = "";
}

cartFab.addEventListener("click", openCart);
cartClose.addEventListener("click", closeCart);
cartOverlay.addEventListener("click", closeCart);

// ── CHECKOUT → OPEN MODAL ──
document.getElementById("btnCheckout").addEventListener("click", () => {
  closeCart();
  openModal();
});

// ── MODAL ──
const modalOverlay = document.getElementById("modalOverlay");
const modalClose = document.getElementById("modalClose");

function openModal() {
  // Populate summary
  const items = cart.map(i =>
    `<div class="order-summary-item"><span>${i.n} × ${i.qty}</span><b>৳ ${(i.p*i.qty).toLocaleString()}</b></div>`
  ).join('');
  document.getElementById("summaryItems").innerHTML = items;
  document.getElementById("summaryTotal").textContent = getCartTotal().toLocaleString();

  // Show form, hide success
  document.getElementById("modalBody").style.display = "block";
  document.getElementById("orderSuccess").classList.remove("show");

  modalOverlay.classList.add("open");
  document.body.style.overflow = "hidden";
}
function closeModal() {
  modalOverlay.classList.remove("open");
  document.body.style.overflow = "";
}

modalClose.addEventListener("click", closeModal);
modalOverlay.addEventListener("click", e => { if (e.target === modalOverlay) closeModal(); });

// ── SEND TO WHATSAPP ──
document.getElementById("btnSendWA").addEventListener("click", () => {
  const name = document.getElementById("custName").value.trim();
  const phone = document.getElementById("custPhone").value.trim();
  const address = document.getElementById("custAddress").value.trim();
  const note = document.getElementById("custNote").value.trim();

  if (!name) { alert("অনুগ্রহ করে আপনার নাম লিখুন"); document.getElementById("custName").focus(); return; }
  if (!phone) { alert("অনুগ্রহ করে মোবাইল নম্বর লিখুন"); document.getElementById("custPhone").focus(); return; }
  if (!address) { alert("অনুগ্রহ করে ডেলিভারি ঠিকানা লিখুন"); document.getElementById("custAddress").focus(); return; }

  const orderLines = cart.map(i => `▪ ${i.n} × ${i.qty} = ৳${(i.p*i.qty).toLocaleString()}`).join('\n');
  const total = getCartTotal().toLocaleString();

  let msg = `🛒 *নতুন অর্ডার — টাউনস্টোর*\n`;
  msg += `━━━━━━━━━━━━━━━\n`;
  msg += `👤 নাম: ${name}\n`;
  msg += `📱 মোবাইল: ${phone}\n`;
  msg += `📍 ঠিকানা: ${address}\n`;
  if (note) msg += `📝 নির্দেশনা: ${note}\n`;
  msg += `━━━━━━━━━━━━━━━\n`;
  msg += `🧺 অর্ডার তালিকা:\n${orderLines}\n`;
  msg += `━━━━━━━━━━━━━━━\n`;
  msg += `💰 মোট: ৳${total} টাকা\n`;
  msg += `━━━━━━━━━━━━━━━\n`;
  msg += `_টাউনস্টোর — জীবনের ভান্ডার_`;

  const encoded = encodeURIComponent(msg);
  window.open(`https://wa.me/8801720003870?text=${encoded}`, '_blank');

  // Show success
  document.getElementById("modalBody").style.display = "none";
  document.getElementById("orderSuccess").classList.add("show");

  // Clear cart
  cart = [];
  updateCartUI();
});

document.getElementById("btnContinue").addEventListener("click", () => {
  closeModal();
  render();
});

// ── BRAIN SECTION RENDER ──
const brainIcons = {
  "Jigsaw Puzzle": "🧩",
  "Flash Cards": "📚",
};
function getBrainIcon(name) {
  if (name.toLowerCase().includes("puzzle")) return "🧩";
  if (name.toLowerCase().includes("flash")) return "📚";
  return "🧠";
}
function getSubLabel(name) {
  if (name.toLowerCase().includes("puzzle")) return "জিগস পাজল";
  if (name.toLowerCase().includes("flash")) return "ফ্ল্যাশ কার্ড";
  return "শিক্ষামূলক";
}

function renderBrainSection() {
  const brainProducts = products.filter(p => p.c === "মস্তিষ্ক বিকাশ");
  const grid = document.getElementById("brainGrid");
  grid.innerHTML = brainProducts.map(p => {
    const cartItem = cart.find(c => c.n === p.n);
    const inCart = !!cartItem;
    const oos = p.qty === 0;
    return `
    <div class="brain-card">
      <div class="brain-card-icon">${getBrainIcon(p.n)}</div>
      <div class="brain-card-sub">${getSubLabel(p.n)}</div>
      <div class="brain-card-name">${p.n}</div>
      <div class="brain-card-footer">
        <div class="brain-card-price">৳ ${p.p.toLocaleString()}<small>টাকা</small></div>
        <span class="brain-stock-badge ${oos ? 'brain-out-stock' : 'brain-in-stock'}">${oos ? 'শেষ' : 'পাওয়া যাচ্ছে'}</span>
      </div>
      <button class="btn-brain-add ${inCart ? 'added' : ''}" ${oos ? 'disabled' : ''} onclick="addToCart('${p.n.replace(/'/g,"\\'")}', ${p.p}); renderBrainSection();">
        ${oos ? 'স্টক নেই' : inCart ? '✓ কার্টে আছে' : '+ কার্টে যোগ করুন'}
      </button>
    </div>`;
  }).join('');
}

// ── INIT ──
buildFilters();
render();
renderBrainSection();
</script>
</body>
</html>
