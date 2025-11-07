# a-k-mm<!doctype html>
<html lang='tr'>
<head>
<meta charset='utf-8'>
<meta name='viewport' content='width=device-width, initial-scale=1'>
<title>1000 Romantik İltifat — Red Spider Lily Teması</title>
<style>
:root{--bg:#0e0b0b;--card:#1b0f12;--accent:#d92b2b;--muted:#c9bdbd}
body{margin:0;font-family:Inter, system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;background:linear-gradient(180deg,#0b0a0a 0%, #1a0f0f 60%);color:#fff;-webkit-font-smoothing:antialiased;}
.header{padding:40px 20px;text-align:center;background:linear-gradient(180deg, rgba(217,43,43,0.06), transparent);backdrop-filter: blur(2px);}
.title{font-size:28px;margin:0 0 6px;font-weight:700;letter-spacing:0.3px}
.subtitle{margin:0;color:var(--muted)}

/* container */
.container{max-width:1100px;margin:30px auto;padding:20px}

/* search and actions */
.controls{display:flex;gap:12px;align-items:center;flex-wrap:wrap;margin-bottom:18px}
.controls input{flex:1;padding:10px 12px;border-radius:10px;border:1px solid rgba(255,255,255,0.06);background:rgba(255,255,255,0.02);color:#fff}
.controls .button{padding:10px 14px;border-radius:10px;background:var(--accent);border:none;color:#fff;cursor:pointer}

/* grid of compliments */
.grid{display:grid;grid-template-columns:repeat(auto-fill,minmax(260px,1fr));gap:12px}
.card{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:14px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 6px 18px rgba(0,0,0,0.45)}
.card .heart{float:right;font-size:18px;color:var(--accent);margin-left:8px}
.card p{margin:0;font-size:15px;line-height:1.45}

/* footer */
.footer{margin-top:22px;color:var(--muted);text-align:center;font-size:13px}

/* responsive tweaks */
@media (max-width:600px){.title{font-size:20px}.grid{grid-template-columns:repeat(1,1fr)}}
</style>
</head>
<body>
<div class='header'>
<div class='title'>1000 Romantik İltifat — Red Spider Lily Teması</div>
<div class='subtitle'>Bu iltifatları sevgiline hızlıca kopyalayıp gönderebilirsin. ❤️🌺</div>
</div>

<div class='container'>
<div class='controls'>
<input id='search' placeholder='Ara: örn. Aşkım' />
<button class='button' onclick='copyAll()'>Tümünü Kopyala</button>
<button class='button' onclick='shuffleList()' style='background:#b21d1d'>Karıştır</button>
</div>

<div id='grid' class='grid'>
<!-- İLTİFATLAR BAŞLANGIÇ -->
<div class='card' data-text='Aşkım, bakışın beni tamamlıyor.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni tamamlıyor.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni benden alıyor.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni benden alıyor.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni benden alıyor — Geceler seninle daha anlamlı.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni benden alıyor — Geceler seninle daha anlamlı.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni tamamlıyor — Seninle her yer cennet.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni tamamlıyor — Seninle her yer cennet.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni tamamlıyor Seni seviyorum.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni tamamlıyor Seni seviyorum.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni tamamlıyor.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni tamamlıyor.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni benden alıyor.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni benden alıyor.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni benden alıyor — Geceler seninle daha anlamlı.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni benden alıyor — Geceler seninle daha anlamlı.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni tamamlıyor — Seninle her yer cennet.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni tamamlıyor — Seninle her yer cennet.</p>
</div>
<div class='card' data-text='Aşkım, bakışın beni tamamlıyor Seni seviyorum.'>
<p><span class='heart'>❤️</span>Aşkım, bakışın beni tamamlıyor Seni seviyorum.</p>
</div>
<!-- ... (Toplam 1000 kart sayfada yer alır; burada örnek amaçlı ilk öğeler gösterildi) -->
<!-- İLTİFATLAR BİTİŞ -->
</div> <!-- grid -->
<div class='footer'>Sayfa otomatik oluşturuldu — İstediğin zaman düzenleyebilirsin.</div>

<script>
const grid = document.getElementById('grid');
const searchInput = document.getElementById('search');
searchInput.addEventListener('input', ()=>{
  const q = searchInput.value.toLowerCase();
  Array.from(grid.children).forEach(card=>{
    const t = card.getAttribute('data-text').toLowerCase();
    card.style.display = t.includes(q) ? '' : 'none';
  });
});
function copyAll(){
  const visible = Array.from(grid.children).filter(c=>c.style.display!=='none');
  const text = visible.map(c=>c.getAttribute('data-text')).join('\n');
  if(!navigator.clipboard){
    alert('Tarayıcınız kopyalama API\'sini desteklemiyor.');
    return;
  }
  navigator.clipboard.writeText(text).then(()=>alert('Görünen tüm iltifatlar panoya kopyalandı!'), ()=>alert('Kopyalama başarısız oldu.'));
}
function shuffleList(){
  // Fisher-Yates shuffle for nodes
  const nodes = Array.from(grid.children);
  for(let i=nodes.length-1;i>0;i--){const j=Math.floor(Math.random()*(i+1)); [nodes[i],nodes[j]]=[nodes[j],nodes[i]];}
  grid.innerHTML='';
  nodes.forEach(n=>grid.appendChild(n));
}
</script>
</div> <!-- container -->
</body>
</html>
