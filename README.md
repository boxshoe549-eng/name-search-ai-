<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Best Collection for Hero</title>
<link rel="preconnect" href="https://fonts.googleapis.com" />
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800&display=swap" rel="stylesheet" />
<style>
*{margin:0;padding:0;box-sizing:border-box}
body{font-family:'Inter',sans-serif;background:#fff;color:#111;overflow-x:hidden}
.wrap{max-width:960px;margin:0 auto;padding:40px 16px 60px}
.eyebrow{text-align:center;font-size:11px;letter-spacing:0.12em;color:#888;text-transform:uppercase;margin-bottom:10px}
.main-title{text-align:center;font-size:clamp(28px,5vw,52px);font-weight:800;line-height:1.05;margin-bottom:12px}
.subtitle{text-align:center;font-size:15px;color:#666;line-height:1.6;margin-bottom:36px}

/* FILTER PILLS */
.filters{display:flex;gap:8px;padding-bottom:6px;justify-content:center;flex-wrap:wrap;margin-bottom:40px}
.pill{border:1.5px solid #ddd;border-radius:999px;padding:8px 18px;font-size:13px;font-weight:500;cursor:pointer;white-space:nowrap;background:#fff;color:#444;transition:all .2s}
.pill.active{background:#111;color:#fff;border-color:#111}
.pill:hover:not(.active){border-color:#999}
.view-more-btn{border:1.5px solid #111;border-radius:999px;padding:8px 20px;font-size:13px;font-weight:600;cursor:pointer;background:#fff;color:#111;white-space:nowrap;transition:all .2s}
.view-more-btn:hover{background:#111;color:#fff}

/* CAROUSEL */
.carousel-wrap{position:relative;overflow:hidden;padding:20px 0 30px}
.track{display:flex;gap:20px;align-items:center;justify-content:center}
.card{flex-shrink:0;border-radius:20px;overflow:hidden;position:relative;cursor:pointer;transition:all .4s cubic-bezier(.4,0,.2,1)}
.card.center{width:clamp(200px,36vw,300px);height:clamp(260px,42vw,380px);z-index:2;transform:scale(1.08);box-shadow:0 20px 60px rgba(0,0,0,0.22)}
.card.side{width:clamp(140px,24vw,200px);height:clamp(190px,30vw,290px);z-index:1;opacity:0.7}
.card.far{width:clamp(90px,16vw,150px);height:clamp(130px,20vw,210px);z-index:0;opacity:0.4}
.card img{width:100%;height:100%;object-fit:cover;object-position:top;display:block}
.card .hero-label{position:absolute;bottom:0;left:0;right:0;padding:20px 14px 14px;background:linear-gradient(to top,rgba(0,0,0,0.8),transparent);color:#fff;font-weight:700;font-size:15px}
.card.side .hero-label,.card.far .hero-label{display:none}

/* NAV BUTTONS */
.nav-row{display:flex;justify-content:center;gap:12px;margin-top:10px}
.nav-btn{width:40px;height:40px;border-radius:50%;border:1.5px solid #ccc;background:#fff;cursor:pointer;display:flex;align-items:center;justify-content:center;transition:all .2s}
.nav-btn:hover{border-color:#111;background:#111;color:#fff}
.nav-btn svg{width:16px;height:16px}

/* DIVIDER */
.section-divider{border:none;border-top:1.5px solid #eee;margin:60px 0}

/* BEST SELLING */
.section-title{font-size:clamp(22px,4vw,36px);font-weight:800;margin-bottom:8px}
.section-sub{font-size:14px;color:#888;margin-bottom:32px}
.product-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:24px}
.product-card{border:1.5px solid #eee;border-radius:16px;overflow:hidden;transition:all .3s;cursor:pointer;background:#fff}
.product-card:hover{transform:translateY(-6px);box-shadow:0 16px 40px rgba(0,0,0,0.10);border-color:#ddd}
.product-img{width:100%;height:200px;object-fit:cover;display:block;background:#f5f5f5}
.product-info{padding:16px}
.product-hero-tag{font-size:11px;font-weight:600;letter-spacing:0.08em;text-transform:uppercase;color:#888;margin-bottom:6px}
.product-name{font-size:15px;font-weight:700;margin-bottom:8px;color:#111}
.product-bottom{display:flex;align-items:center;justify-content:space-between}
.product-price{font-size:16px;font-weight:800;color:#111}
.buy-btn{background:#111;color:#fff;border:none;border-radius:999px;padding:8px 16px;font-size:12px;font-weight:700;cursor:pointer;transition:all .2s}
.buy-btn:hover{background:#333}

/* MOBILE */
@media(max-width:600px){
  .card.far{display:none}
  .card.side{width:clamp(120px,28vw,170px);height:clamp(160px,36vw,230px)}
  .card.center{width:clamp(180px,48vw,240px);height:clamp(230px,60vw,310px)}
  .product-grid{grid-template-columns:repeat(2,1fr);gap:14px}
  .product-img{height:150px}
}
</style>
</head>
<body>
<div class="wrap">

  <!-- HEADER -->
  <p class="eyebrow">Gallery</p>
  <h1 class="main-title">Best Collection for Hero</h1>
  <p class="subtitle">Explore the mightiest heroes of the Marvel universe —<br>legends captured through every frame.</p>

  <!-- FILTER PILLS -->
  <div class="filters">
    <button class="pill active" onclick="setFilter(this,'all')">All Heroes</button>
    <button class="pill" onclick="setFilter(this,'iron-man')">Iron Man</button>
    <button class="pill" onclick="setFilter(this,'spider-man')">Spider-Man</button>
    <button class="pill" onclick="setFilter(this,'thor')">Thor</button>
    <button class="pill" onclick="setFilter(this,'captain-america')">Captain America</button>
    <button class="pill" onclick="setFilter(this,'doctor-strange')">Doctor Strange</button>
    <button class="pill" onclick="setFilter(this,'hulk')">Hulk</button>
    <button class="view-more-btn">View More →</button>
  </div>

  <!-- CAROUSEL -->
  <div class="carousel-wrap">
    <div class="track" id="track"></div>
  </div>
  <div class="nav-row">
    <button class="nav-btn" onclick="move(-1)" aria-label="Previous">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="15 18 9 12 15 6"/></svg>
    </button>
    <button class="nav-btn" onclick="move(1)" aria-label="Next">
      <svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><polyline points="9 6 15 12 9 18"/></svg>
    </button>
  </div>

  <hr class="section-divider" />

  <!-- BEST SELLING -->
  <h2 class="section-title">Best Selling Products</h2>
  <p class="section-sub">Top picks from our Marvel hero merchandise collection</p>
  <div class="product-grid" id="product-grid"></div>

</div>

<script>
const heroes = [
  {
    id:'iron-man',
    name:'Iron Man',
    img:'https://images.unsplash.com/photo-1635805737707-575885ab0820?w=600&auto=format&fit=crop',
    color:'#b71c1c'
  },
  {
    id:'spider-man',
    name:'Spider-Man',
    img:'https://images.unsplash.com/photo-1608889175123-8ee362201f81?w=600&auto=format&fit=crop',
    color:'#c62828'
  },
  {
    id:'thor',
    name:'Thor',
    img:'https://images.unsplash.com/photo-1569003339405-ea396a5a8a90?w=600&auto=format&fit=crop',
    color:'#1565c0'
  },
  {
    id:'captain-america',
    name:'Captain America',
    img:'https://images.unsplash.com/photo-1612036782180-6f0b6cd846fe?w=600&auto=format&fit=crop',
    color:'#0d47a1'
  },
  {
    id:'doctor-strange',
    name:'Doctor Strange',
    img:'https://images.unsplash.com/photo-1534430480872-3498386e7856?w=600&auto=format&fit=crop',
    color:'#4a148c'
  },
  {
    id:'hulk',
    name:'Hulk',
    img:'https://images.unsplash.com/photo-1559583985-c80d8ad9b29f?w=600&auto=format&fit=crop',
    color:'#1b5e20'
  },
];

const products = [
  {hero:'Iron Man',tag:'iron-man',name:'Iron Man Arc Reactor Tee',price:'₹999',img:'https://images.unsplash.com/photo-1618354691373-d851c5c3a990?w=400&auto=format&fit=crop'},
  {hero:'Spider-Man',tag:'spider-man',name:'Spider-Man Web Hoodie',price:'₹1,499',img:'https://images.unsplash.com/photo-1620799140408-edc6dcb6d633?w=400&auto=format&fit=crop'},
  {hero:'Thor',tag:'thor',name:'Thor Mjolnir Keychain',price:'₹399',img:'https://images.unsplash.com/photo-1601445638532-1e6a7b0d5a2d?w=400&auto=format&fit=crop'},
  {hero:'Captain America',tag:'captain-america',name:'Cap Shield Backpack',price:'₹1,299',img:'https://images.unsplash.com/photo-1553062407-98eeb64c6a62?w=400&auto=format&fit=crop'},
  {hero:'Doctor Strange',tag:'doctor-strange',name:'Sorcerer Cloak Jacket',price:'₹2,199',img:'https://images.unsplash.com/photo-1512436991641-6745cdb1723f?w=400&auto=format&fit=crop'},
  {hero:'Hulk',tag:'hulk',name:'Hulk Smash Figurine',price:'₹799',img:'https://images.unsplash.com/photo-1558618666-fcd25c85cd64?w=400&auto=format&fit=crop'},
];

let cur = 0;
let activeFilter = 'all';
let filteredHeroes = [...heroes];

function render() {
  const track = document.getElementById('track');
  track.innerHTML = '';
  if(filteredHeroes.length === 0) {
    track.innerHTML = '<p style="color:#888;text-align:center;padding:40px">No heroes found.</p>';
    return;
  }
  const positions = ['far','side','center','side','far'];
  const total = filteredHeroes.length;
  for(let i = 0; i < 5; i++) {
    let idx = ((cur - 2 + i) % total + total) % total;
    let hero = filteredHeroes[idx];
    let card = document.createElement('div');
    card.className = 'card ' + positions[i];

    let img = document.createElement('img');
    img.src = hero.img;
    img.alt = hero.name;
    card.appendChild(img);

    if(positions[i] === 'center') {
      let label = document.createElement('div');
      label.className = 'hero-label';
      label.textContent = hero.name;
      card.appendChild(label);
    }

    const clickIdx = idx;
    card.addEventListener('click', () => { cur = clickIdx; render(); });
    track.appendChild(card);
  }
}

function renderProducts(filter) {
  const grid = document.getElementById('product-grid');
  const list = filter === 'all' ? products : products.filter(p => p.tag === filter);
  if(list.length === 0){
    grid.innerHTML = '<p style="color:#888;grid-column:1/-1;text-align:center;padding:30px">No products for this hero yet.</p>';
    return;
  }
  grid.innerHTML = list.map(p => `
    <div class="product-card">
      <img class="product-img" src="${p.img}" alt="${p.name}" />
      <div class="product-info">
        <div class="product-hero-tag">${p.hero}</div>
        <div class="product-name">${p.name}</div>
        <div class="product-bottom">
          <span class="product-price">${p.price}</span>
          <button class="buy-btn">Buy Now</button>
        </div>
      </div>
    </div>
  `).join('');
}

function setFilter(btn, filter) {
  document.querySelectorAll('.pill').forEach(p => p.classList.remove('active'));
  btn.classList.add('active');
  activeFilter = filter;
  filteredHeroes = filter === 'all' ? [...heroes] : heroes.filter(h => h.id === filter);
  cur = 0;
  render();
  renderProducts(filter);
}

function move(dir) {
  const total = filteredHeroes.length;
  if(total === 0) return;
  cur = ((cur + dir) % total + total) % total;
  render();
}

document.addEventListener('keydown', e => {
  if(e.key === 'ArrowLeft') move(-1);
  if(e.key === 'ArrowRight') move(1);
});

render();
renderProducts('all');
</script>
</body>
</html>
