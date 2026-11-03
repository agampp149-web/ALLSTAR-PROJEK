<!doctype html>
<html lang="id">
<head>
<meta charset="utf-8"><meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#08090d"><title>ALLSTAR PROJEK</title>
<style>
*{box-sizing:border-box}body{margin:0;background:#08090d;color:#f7f8fc;font:15px system-ui,Arial;min-height:100vh}
:root{--red:#ef3340;--blue:#267cff;--panel:#121722;--line:#273044}
button,input{font:inherit}button{border:0;border-radius:11px;padding:12px 16px;font-weight:750;cursor:pointer}
.primary{background:linear-gradient(110deg,var(--red),#a91f38);color:#fff}.blue{background:linear-gradient(110deg,var(--blue),#174db5);color:#fff}.ghost{background:#1b2230;color:#fff;border:1px solid var(--line)}
.hidden{display:none!important}.wrap{max-width:1000px;margin:auto;padding:18px}.top{display:flex;align-items:center;justify-content:space-between;padding:15px 18px;border-bottom:1px solid var(--line);background:#0b0e15;position:sticky;top:0;z-index:3}
.logo{font-weight:950;letter-spacing:2px}.logo b{color:var(--red)}.muted{color:#9ba6ba;font-size:13px;line-height:1.5}
.panel{background:linear-gradient(145deg,#151c2a,#0e121b);border:1px solid var(--line);border-radius:17px;padding:20px;box-shadow:0 12px 35px #0005}
.field{width:100%;padding:13px 14px;background:#080c13;border:1px solid #34415a;border-radius:10px;color:white;margin:7px 0 14px;outline:none}
label{font-size:13px;color:#c8d0df}.center{text-align:center}.intro{min-height:calc(100vh - 58px);display:grid;place-items:center;padding:25px;overflow:hidden;position:relative;background:radial-gradient(ellipse at 50% 38%,#243c71 0,#111a31 30%,#08090d 72%)}
.intro:before,.intro:after{content:"";position:absolute;width:230px;height:230px;border:1px solid #4c82ff55;border-radius:50%;animation:pulse 4s ease-in-out infinite}
.intro:after{width:330px;height:330px;animation-delay:1s}
@keyframes pulse{0%,100%{transform:scale(.8);opacity:.2}50%{transform:scale(1.18);opacity:.85}}
.introcard{position:relative;z-index:1;text-align:center;max-width:500px}
.orb{width:145px;height:145px;margin:0 auto 25px;border-radius:50%;background:linear-gradient(140deg,#172f63,#080b14 55%,#e52b42);box-shadow:0 0 50px #267cff77, inset 0 0 25px #fff2;display:grid;place-items:center;font-size:40px;font-weight:950;animation:float 3s ease-in-out infinite}
@keyframes float{50%{transform:translateY(-12px) rotate(5deg)}}
.intro h1{font-size:clamp(30px,8vw,54px);letter-spacing:4px;margin:0}.intro h1 span{color:var(--red)}.intro p{color:#c0c9da}
.loginbox{max-width:390px;margin:8vh auto}.dashgrid{display:grid;grid-template-columns:repeat(2,1fr);gap:12px}.tile{background:#141b29;border:1px solid var(--line);border-radius:15px;padding:18px;text-align:left;color:white;min-height:105px}.tile strong{display:block;margin:8px 0 4px}.tile span{font-size:24px}
.row{display:flex;gap:9px;align-items:center;flex-wrap:wrap;justify-content:space-between}.tabs{display:flex;gap:8px;flex-wrap:wrap;margin:17px 0}.tab.active{background:var(--blue);color:#fff}
.nav{position:sticky;bottom:0;display:flex;justify-content:space-around;background:#0c111b;border-top:1px solid var(--line);padding:10px 4px}.nav button{background:transparent;color:#aab5c9;padding:9px;font-size:12px}
.chat{height:45vh;min-height:260px;overflow:auto;background:#090d14;border:1px solid var(--line);border-radius:13px;padding:12px;margin:12px 0}.bubble{padding:10px 13px;border-radius:13px;background:#1c2739;margin:8px 0;max-width:85%;white-space:pre-wrap}.mine{margin-left:auto;background:#183e73}
@media(max-width:600px){.wrap{padding:12px}.dashgrid{grid-template-columns:1fr 1fr}.panel{padding:16px}.intro{min-height:calc(100vh - 55px)}}
</style></head>
<body>
<header class="top"><div class="logo">ALLSTAR <b>PROJEK</b></div><div id="status" class="muted">Selamat datang</div></header>

<section id="intro" class="intro">
 <div class="introcard"><div class="orb">★</div><h1>ALLSTAR <span>PROJEK</span></h1><p>WELCOME TO THE NEXT LEVEL</p><p class="muted">Animasi pembuka bergaya futuristik</p><button class="primary" onclick="showLogin()">MULAI</button></div>
</section>

<section id="login" class="wrap hidden">
 <div class="panel loginbox"><div class="center"><div class="orb" style="width:85px;height:85px;font-size:27px">★</div><h2>LOGIN ALLSTAR</h2><p class="muted">Masuk menggunakan akun dari admin. Tidak ada pendaftaran mandiri.</p></div>
 <label>Username</label><input id="username" class="field" placeholder="Username" autocomplete="username">
 <label>Password</label><input id="password" class="field" type="password" placeholder="Password" autocomplete="current-password">
 <button class="primary" style="width:100%" onclick="login()">MASUK</button><p id="error" class="muted"></p>
 <p class="muted">Admin awal: owner / 12345678</p></div>
</section>

<section id="dashboard" class="wrap hidden">
 <div class="row"><div><p class="muted">DASHBOARD</p><h2 id="hello">Selamat datang</h2></div><button class="ghost" onclick="logout()">Keluar</button></div>
 <div id="adminTools" class="panel hidden" style="margin:14px 0"><h3>Admin — Kelola akun</h3><div class="dashgrid">
 <div><label>Username baru</label><input id="newname" class="field" placeholder="Username"></div><div><label>Password baru</label><input id="newpass" class="field" placeholder="Password"></div>
 </div><div class="row"><input id="duration" class="field" type="number" min="1" value="30" style="max-width:120px"><select id="durationUnit" class="field" style="max-width:130px"><option value="days">Hari</option><option value="years">Tahun</option></select><button class="blue" onclick="addUser()">Buat akun</button></div><p class="muted">Admin permanen. Akun pengguna akan kedaluwarsa otomatis sesuai durasi.</p><div id="users" class="muted"></div><p id="adminmsg" class="muted"></p></div>
 <div class="dashgrid">
 <button class="tile" onclick="openPage('chat')"><span>✦</span><strong>AI Chat</strong><small class="muted">Ruang percakapan</small></button>
 <button class="tile" onclick="openPage('tools')"><span>⌘</span><strong>Tools</strong><small class="muted">Kumpulan alat</small></button>
 <button class="tile" onclick="openPage('profile')"><span>◉</span><strong>Profil</strong><small class="muted">Informasi akun</small></button>
 <button class="tile" onclick="openPage('settings')"><span>⚙</span><strong>Pengaturan</strong><small class="muted">Preferensi aplikasi</small></button>
 <button class="tile" onclick="openWhatsApp()"><span>☎</span><strong>WhatsApp Admin</strong><small class="muted">Hubungi pengelola</small></button>
 <button class="tile" onclick="openPage('about')"><span>★</span><strong>Tentang</strong><small class="muted">Info ALLSTAR PROJEK</small></button>
 </div>
</section>

<section id="page" class="wrap hidden"><div class="row"><h2 id="pageTitle">Menu</h2><button class="ghost" onclick="backDash()">Kembali</button></div><div class="panel" id="pageBody"></div></section>
<nav id="nav" class="nav hidden"><button onclick="backDash()">⌂<br>Home</button><button onclick="openPage('chat')">✦<br>AI Chat</button><button onclick="openPage('tools')">⌘<br>Tools</button><button onclick="openPage('profile')">◉<br>Profil</button></nav>
<script>
const ADMIN='owner',ADMINPASS='12345678',KEY='allstar_project_users';
let me=null,waNumber=''; // Isi nomor WhatsApp admin pada bagian ini, format internasional tanpa tanda +.
const $=id=>document.getElementById(id);
function users(){try{return JSON.parse(localStorage.getItem(KEY)||'{}')}catch(e){return {}}}
function save(x){localStorage.setItem(KEY,JSON.stringify(x))}
function hideAll(){['intro','login','dashboard','page'].forEach(id=>$(id).classList.add('hidden'));$('nav').classList.add('hidden')}
function showLogin(){hideAll();$('login').classList.remove('hidden')}
function login(){let u=$('username').value.trim(),p=$('password').value;$('error').textContent='';
 if(u===ADMIN&&p===ADMINPASS){me={u,admin:true};enter();return}
 let a=users()[u];if(!a||a.password!==p){$('error').textContent='Username atau password salah.';return}
 if(Date.now()>a.expires){$('error').textContent='Akun kedaluwarsa. Hubungi admin.';return}me={u,admin:false};enter()}
function enter(){hideAll();$('dashboard').classList.remove('hidden');$('nav').classList.remove('hidden');$('status').textContent=me.u;$('hello').textContent='Halo, '+me.u;$('adminTools').classList.toggle('hidden',!me.admin);if(me.admin)renderUsers()}
function logout(){me=null;$('status').textContent='Selamat datang';$('password').value='';hideAll();$('intro').classList.remove('hidden')}
function addUser(){let u=$('newname').value.trim(),p=$('newpass').value,n=Number($('duration').value),unit=$('durationUnit').value,a=users();if(!u||!p||!Number.isInteger(n)||n<1){$('adminmsg').textContent='Lengkapi data dengan benar.';return}if(u.toLowerCase()===ADMIN||a[u]){$('adminmsg').textContent='Username sudah digunakan.';return}let durationMs=unit==='years'?n*365*86400000:n*86400000;a[u]={password:p,expires:Date.now()+durationMs};save(a);$('adminmsg').textContent='Akun dibuat di browser ini.';$('newname').value='';$('newpass').value='';renderUsers()}
function renderUsers(){let el=$('users'),a=users();el.innerHTML='';Object.entries(a).forEach(([u,v])=>{let d=document.createElement('p');d.textContent=u+' — '+(Date.now()>v.expires?'Kedaluwarsa':'Aktif sampai '+new Date(v.expires).toLocaleDateString('id-ID'));let b=document.createElement('button');b.className='ghost';b.textContent='Hapus';b.onclick=()=>{let x=users();delete x[u];save(x);renderUsers()};d.append(' ',b);el.append(d)})}
function openPage(which){$('dashboard').classList.add('hidden');$('page').classList.remove('hidden');let title={chat:'AI Chat',tools:'Tools',profile:'Profil',settings:'Pengaturan',about:'Tentang'};$('pageTitle').textContent=title[which]||'Menu';let body=$('pageBody');body.innerHTML='';
 if(which==='chat'){body.innerHTML='<p>Antarmuka chat ALLSTAR PROJEK.</p><div class="chat" id="chatbox"><div class="bubble">AI online belum terhubung.</div></div><div class="row"><input class="field" id="msg" placeholder="Tulis pesan..." style="flex:1;margin:0"><button class="primary" onclick="send()">Kirim</button></div><p class="muted">Chat AI sungguhan memerlukan layanan AI dan server.</p>'}
 else if(which==='tools'){body.innerHTML='<h3>Tools</h3><p>Kumpulan alat aplikasi akan ditambahkan di sini.</p><button class="ghost" onclick="alert(\\'Fitur kalkulator segera ditambahkan\\')">Kalkulator (segera)</button>'}
 else if(which==='profile'){body.innerHTML='<h3>Profil akun</h3><p>Username: '+safe(me.u)+'</p><p>Jenis akun: '+(me.admin?'Admin':'Pengguna')+'</p>'}
 else if(which==='settings'){body.innerHTML='<h3>Pengaturan</h3><p>Tema: Hitam, putih, merah, biru.</p><button class="ghost" onclick="alert(\\'Tema ALLSTAR PROJEK\\')">Info tema</button>'}
 else {body.innerHTML='<h3>ALLSTAR PROJEK</h3><p>Aplikasi komunitas dan tools dengan antarmuka futuristik.</p>'}}
function safe(s){return s.replace(/[&<>"']/g,c=>({'&':'&amp;','<':'&lt;','>':'&gt;','"':'&quot;',"'":'&#39;'}[c]))}
function send(){let i=$('msg'),v=i.value.trim();if(!v)return;let b=document.createElement('div');b.className='bubble mine';b.textContent=v;$('chatbox').append(b);let r=document.createElement('div');r.className='bubble';r.textContent='AI online belum terhubung. Pesan belum dikirim ke AI.';$('chatbox').append(r);i.value=''}
function openWhatsApp(){if(!waNumber){alert('Nomor WhatsApp admin belum diatur. Isi variabel waNumber di file index.html.');return}location.href='https://wa.me/'+waNumber}
function backDash(){$('page').classList.add('hidden');$('dashboard').classList.remove('hidden')}
</script></body></html>
