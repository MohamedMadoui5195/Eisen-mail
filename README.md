<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<meta name="theme-color" content="#07162b">
<title>Eisen Mail — Alislamiah</title>
<link rel="icon" href="icon.png" type="image/png">
<style>
:root{--bg:#06101f;--panel:#0c1b31;--panel2:#102541;--blue:#1769ff;--cyan:#39c6ff;--text:#f2f6ff;--muted:#a5b6d0;--border:#233a58;--green:#23c483;--red:#ff5d70}
*{box-sizing:border-box}body{margin:0;font-family:Arial,Tahoma,sans-serif;background:linear-gradient(145deg,#030914,#07172c 55%,#0b2140);color:var(--text);min-height:100vh}
button,input,textarea{font:inherit}button{cursor:pointer}button:disabled{opacity:.5;cursor:not-allowed}
header{height:68px;display:flex;align-items:center;justify-content:space-between;padding:0 16px;border-bottom:1px solid var(--border);background:#071326;position:sticky;top:0;z-index:5}
.brand{display:flex;align-items:center;gap:10px;font-size:21px;font-weight:bold}.brand img{width:39px;height:39px;object-fit:contain;border-radius:10px}.brand span{color:var(--cyan)}
#headerUser{font-size:12px;color:var(--muted);max-width:52%;overflow-wrap:anywhere}
main{max-width:1050px;margin:22px auto;padding:0 13px 42px}.card{background:linear-gradient(145deg,#0d1e35,#0a1729);border:1px solid var(--border);border-radius:16px;padding:18px;margin-bottom:15px;box-shadow:0 10px 30px #0002}
h1{font-size:25px}h2{font-size:20px}h3{font-size:16px}p{line-height:1.7;color:var(--muted)}
label{display:block;margin:12px 0 7px;color:#dce9ff;font-size:14px}input,textarea{width:100%;padding:12px;background:#061326;border:1px solid #2b4567;border-radius:10px;color:white;outline:none}input:focus,textarea:focus{border-color:var(--cyan)}textarea{min-height:120px;resize:vertical}
button,.btn{display:inline-block;border:0;padding:11px 14px;border-radius:10px;background:var(--blue);color:white;font-weight:bold;text-decoration:none;margin:5px 3px 0 0}
.secondary{background:#1b304c;border:1px solid #35516f}.green{background:#087b58}.red{background:#a82d43}.full{width:100%;margin:12px 0 0}
.hidden{display:none!important}.muted{color:var(--muted);font-size:13px}.notice{padding:12px;border-radius:10px;background:#102944;color:#dceeff;margin:12px 0;line-height:1.7}.error{background:#451b2a;color:#ffd8de}.success{background:#103b31;color:#bfffe8}
.tabs{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:15px}.tabs button{flex:1;min-width:110px}.grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(180px,1fr));gap:12px}
.plan{border:1px solid #2c5279;border-radius:14px;padding:15px;background:linear-gradient(145deg,#102745,#0b192d)}.plan .price{font-size:25px;font-weight:bold;color:var(--cyan);margin:10px 0}.plan .space{font-size:19px;font-weight:bold}.plan.active{border-color:var(--green)}
.badge{display:inline-block;padding:5px 9px;border-radius:20px;background:#143e39;color:#aaffdf;font-size:12px}
.item{padding:14px 0;border-bottom:1px solid var(--border);overflow-wrap:anywhere}.item:last-child{border-bottom:0}.item strong{display:block;margin-bottom:6px}.item small{color:var(--muted)}.item p{white-space:pre-wrap;margin:9px 0}
.row{display:flex;gap:10px;align-items:center;flex-wrap:wrap}.row>*{flex:1;min-width:150px}.stat{background:#071529;border:1px solid var(--border);border-radius:12px;padding:13px}.stat strong{display:block;font-size:19px;color:var(--cyan);margin-bottom:6px}
hr{border:0;border-top:1px solid var(--border);margin:18px 0}footer{text-align:center;color:#8195b1;padding:20px;font-size:12px}
@media(min-width:760px){.layout{display:grid;grid-template-columns:205px 1fr;gap:15px}.side{align-self:start;position:sticky;top:83px}}
</style>
</head>
<body>
<header><div class="brand"><img src="icon.png" alt="Eisen Mail" onerror="this.style.display='none'"><div>Eisen <span>Mail</span></div></div><div id="headerUser">البريد المستقل من Alislamiah</div></header>
<main>
<section id="authView">
 <div class="card">
  <h1>مرحبًا بك في Eisen Mail</h1><p>بريد محلي مستقل من Alislamiah. الحسابات والرسائل تُحفظ على هذا المتصفح.</p>
  <div class="tabs"><button onclick="showAuth('login')">تسجيل الدخول</button><button class="secondary" onclick="showAuth('signup')">إنشاء حساب</button></div>
  <div id="loginForm"><h2>تسجيل الدخول</h2><label for="loginEmail">عنوان Eisen Mail</label><input id="loginEmail" type="email" placeholder="name@eisen.local" autocomplete="username"><label for="loginPassword">كلمة المرور</label><input id="loginPassword" type="password" autocomplete="current-password"><button class="full" onclick="login()">دخول إلى البريد</button></div>
  <div id="signupForm" class="hidden"><h2>إنشاء حساب جديد</h2><label for="signupName">الاسم</label><input id="signupName" maxlength="60" placeholder="اسمك"><label for="signupEmail">عنوان البريد</label><input id="signupEmail" type="email" placeholder="name@eisen.local" autocomplete="username"><label for="signupPassword">كلمة المرور (8 أحرف على الأقل)</label><input id="signupPassword" type="password" minlength="8" autocomplete="new-password"><label for="signupPassword2">تأكيد كلمة المرور</label><input id="signupPassword2" type="password" minlength="8" autocomplete="new-password"><button class="full" onclick="signup()">إنشاء الحساب</button></div>
  <div id="authMessage" class="notice hidden" role="status"></div>
 </div>
</section>
<section id="appView" class="hidden">
 <div class="layout">
  <aside class="side card" id="sidebar"><h3 id="welcomeName">البريد</h3><div id="quotaSide" class="notice"></div>
   <button class="full" onclick="openPage('inbox')">📥 الوارد</button><button class="secondary full" onclick="openPage('sent')">📤 المرسلة</button><button class="secondary full" onclick="openPage('compose')">✉️ رسالة جديدة</button><button class="secondary full" onclick="openPage('plans')">💎 مساحة التخزين</button><button class="secondary full" onclick="openPage('settings')">⚙️ الحساب والنسخ</button><button class="red full" onclick="logout()">تسجيل الخروج</button>
  </aside>
  <div>
   <section id="page-inbox" class="card"><h2>📥 صندوق الوارد</h2><div id="inboxList"></div></section>
   <section id="page-sent" class="card hidden"><h2>📤 الرسائل المرسلة</h2><div id="sentList"></div></section>
   <section id="page-compose" class="card hidden"><h2>✉️ كتابة رسالة</h2><label for="toEmail">إلى (عنوان الحساب المحلي)</label><input id="toEmail" type="email" placeholder="عنوان المستلم"><label for="mailSubject">الموضوع</label><input id="mailSubject" maxlength="160" placeholder="موضوع الرسالة"><label for="mailBody">الرسالة</label><textarea id="mailBody" maxlength="50000" placeholder="اكتب رسالتك هنا..."></textarea><button onclick="sendMessage()">إرسال الرسالة</button><p class="muted">يصل البريد إلى حساب موجود في قاعدة بيانات هذا المتصفح فقط. لا يتم الإرسال عبر الإنترنت.</p></section>
   <section id="page-plans" class="card hidden"><h2>💎 مساحة التخزين</h2><div class="row"><div class="stat"><strong id="usedSpace">0 MB</strong><span class="muted">المستخدم التقريبي</span></div><div class="stat"><strong id="totalSpace">100 MB</strong><span class="muted">المساحة الحالية</span></div></div><div id="userPlans" class="grid" style="margin-top:15px"></div><div class="notice">بعد استلام المبلغ، تفعّل الإدارة الباقة. الضغط على الدفع لا يفعّل الاشتراك تلقائيًا.</div></section>
   <section id="page-settings" class="card hidden"><h2>⚙️ الحساب</h2><div id="accountDetails"></div><hr><h3>النسخ الاحتياطي</h3><p>صدّر نسخة من الحسابات والرسائل المحفوظة محليًا. ملف النسخة يحتوي بيانات حساسة، فاحتفظ به بأمان.</p><button onclick="exportBackup()">تصدير نسخة احتياطية</button><label for="importFile">استيراد نسخة احتياطية JSON</label><input id="importFile" type="file" accept="application/json"><button class="secondary" onclick="importBackup()">استيراد النسخة</button></section>
   
  </div>
 </div>
</section>
</main><footer>© Alislamiah — Eisen Mail</footer>
<script>
"use strict";
const WHATSAPP_NUMBER="213777543015";
const PLANS=[
{id:"free",name:"Eisen Free",bytes:100*1024*1024,label:"100 MB",price:0,priceLabel:"مجانًا"},
{id:"plus",name:"Eisen Plus",bytes:1*1024**3,label:"1 Go",price:2,priceLabel:"2 دولار"},
{id:"pro",name:"Eisen Pro",bytes:5*1024**3,label:"5 Go",price:5,priceLabel:"5 دولارات"},
{id:"max",name:"Eisen Max",bytes:7*1024**3,label:"7 Go",price:12,priceLabel:"12 دولارًا"}
];
let db=null,currentUser=null,currentPage="inbox";
const $=id=>document.getElementById(id);
function openDB(){return new Promise((resolve,reject)=>{const r=indexedDB.open("EisenMailDB",1);r.onupgradeneeded=e=>{const d=e.target.result;if(!d.objectStoreNames.contains("users"))d.createObjectStore("users",{keyPath:"email"});if(!d.objectStoreNames.contains("messages")){const s=d.createObjectStore("messages",{keyPath:"id",autoIncrement:true});s.createIndex("to","to");s.createIndex("from","from");}};r.onsuccess=()=>{db=r.result;resolve()};r.onerror=()=>reject(r.error);});}
function request(storeName,method,value){return new Promise((resolve,reject)=>{const tx=db.transaction(storeName,method==="get"||method==="getAll"?"readonly":"readwrite"),s=tx.objectStore(storeName);let r;if(method==="get")r=s.get(value);else if(method==="getAll")r=s.getAll();else if(method==="delete")r=s.delete(value);else if(method==="add")r=s.add(value);else r=s.put(value);r.onsuccess=()=>resolve(r.result);r.onerror=()=>reject(r.error);});}
const getUser=email=>request("users","get",email), getUsers=()=>request("users","getAll"), getMessages=()=>request("messages","getAll");
function esc(v){return String(v??"").replace(/[&<>"']/g,c=>({"&":"&amp;","<":"&lt;",">":"&gt;",'"':"&quot;","'":"&#39;"}[c]));}
function emailNorm(v){return String(v||"").trim().toLowerCase();}
function plan(id){return PLANS.find(p=>p.id===id)||PLANS[0];}
function bytesText(n){if(n<1024*1024)return Math.round(n/1024)+" KB";if(n<1024**3)return(n/1024**2).toFixed(1)+" MB";return(n/1024**3).toFixed(2)+" Go";}
function message(text,type=""){const e=$("authMessage");e.className="notice "+type;e.textContent=text;e.classList.remove("hidden");}
function showAuth(which){$("loginForm").classList.toggle("hidden",which!=="login");$("signupForm").classList.toggle("hidden",which!=="signup");$("authMessage").classList.add("hidden");}
function drawPlans(id,interactive){$(id).innerHTML=PLANS.map(p=>`<div class="plan ${currentUser&&currentUser.plan===p.id?"active":""}"><h3>${esc(p.name)}</h3><div class="space">${esc(p.label)}</div><div class="price">${esc(p.priceLabel)}</div>${currentUser&&currentUser.plan===p.id?'<span class="badge">باقتك الحالية</span>':""}${interactive&&p.id!=="free"?`<button class="full" onclick="buyPlan('${p.id}')">الدفع عبر WhatsApp</button>`:""}</div>`).join("");}
async function signup(){const name=$("signupName").value.trim(),email=emailNorm($("signupEmail").value),pass=$("signupPassword").value,pass2=$("signupPassword2").value;if(!name||!email||!pass||!pass2)return message("يرجى ملء جميع الحقول.","error");if(!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(email))return message("أدخل عنوان بريد صحيحًا.","error");if(pass.length<8)return message("كلمة المرور يجب أن تكون 8 أحرف على الأقل.","error");if(pass!==pass2)return message("كلمتا المرور غير متطابقتين.","error");try{if(await getUser(email))return message("الحساب موجود بالفعل. سجّل الدخول.","error");await request("users","add",{email,name,password:pass,plan:"free",createdAt:new Date().toISOString()});$("loginEmail").value=email;$("loginPassword").value="";showAuth("login");message("تم إنشاء الحساب محليًا. يمكنك تسجيل الدخول.","success");}catch(e){message("تعذر إنشاء الحساب: "+e.message,"error");}}
async function login(){const email=emailNorm($("loginEmail").value),pass=$("loginPassword").value;if(!email||!pass)return message("أدخل البريد وكلمة المرور.","error");try{const u=await getUser(email);if(!u)return message("الحساب غير موجود. أنشئ حسابًا جديدًا.","error");if(u.password!==pass)return message("كلمة المرور غير صحيحة.","error");currentUser=u;enterApp();}catch(e){message("تعذر تسجيل الدخول.","error");}}
function enterApp(){$("authView").classList.add("hidden");$("appView").classList.remove("hidden");$("sidebar").classList.remove("hidden");$("headerUser").textContent=currentUser.email;$("welcomeName").textContent=currentUser.name;openPage("inbox");refreshQuota();}
function logout(){currentUser=null;$("appView").classList.add("hidden");$("authView").classList.remove("hidden");$("headerUser").textContent="البريد المستقل من Alislamiah";$("loginPassword").value="";showAuth("login");}
function hidePages(){document.querySelectorAll('[id^="page-"]').forEach(e=>e.classList.add("hidden"));}
function openPage(p){if(!currentUser)return;currentPage=p;hidePages();$("page-"+p).classList.remove("hidden");if(p==="inbox"||p==="sent")renderMessages(p);if(p==="plans"){drawPlans("userPlans",true);refreshQuota();}if(p==="settings")renderAccount();}
async function renderMessages(which){const target=$(which==="inbox"?"inboxList":"sentList");try{let arr=(await getMessages()).filter(m=>which==="inbox"?m.to===currentUser.email:m.from===currentUser.email);arr.sort((a,b)=>b.date.localeCompare(a.date));if(!arr.length){target.innerHTML=`<div class="notice">${which==="inbox"?"لا توجد رسائل واردة.":"لا توجد رسائل مرسلة."}</div>`;return;}target.innerHTML=arr.map(m=>`<div class="item"><strong>${esc(m.subject||"(بدون موضوع)")}</strong><small>${which==="inbox"?"من: "+esc(m.from):"إلى: "+esc(m.to)} · ${esc(new Date(m.date).toLocaleString("ar"))}</small><p>${esc(m.body)}</p><div>${which==="inbox"?`<button class="secondary" onclick="replyTo(${JSON.stringify(m.from)},${JSON.stringify(m.subject||"")})">رد</button>`:""}<button class="red" onclick="deleteMessage(${m.id})">حذف</button></div></div>`).join("");}catch(e){target.innerHTML='<div class="notice error">تعذر تحميل الرسائل.</div>';}}
async function sendMessage(){const to=emailNorm($("toEmail").value),subject=$("mailSubject").value.trim(),body=$("mailBody").value.trim();if(!to||!body)return alert("أدخل عنوان المستلم ونص الرسالة.");if(to===currentUser.email)return alert("لا يمكنك الإرسال إلى نفسك في هذه النسخة.");try{const recipient=await getUser(to);if(!recipient)return alert("الحساب المستلم غير موجود في قاعدة بيانات هذا المتصفح.");const all=await getMessages();const used=all.filter(m=>m.from===currentUser.email||m.to===currentUser.email).reduce((s,m)=>s+new Blob([m.subject||"",m.body||""]).size,0);if(used+new Blob([subject,body]).size>plan(currentUser.plan).bytes){alert("المساحة غير كافية. اختر باقة أكبر.");openPage("plans");return;}await request("messages","add",{from:currentUser.email,to,subject,body,date:new Date().toISOString()});$("toEmail").value="";$("mailSubject").value="";$("mailBody").value="";alert("تم حفظ الرسالة وإيصالها إلى صندوق وارد المستلم على هذا المتصفح.");refreshQuota();openPage("sent");}catch(e){alert("تعذر إرسال الرسالة: "+e.message);}}
function replyTo(email,subject){openPage("compose");$("toEmail").value=email;$("mailSubject").value=subject.startsWith("Re:")?subject:"Re: "+subject;$("mailBody").focus();}
async function deleteMessage(id){if(!confirm("حذف الرسالة؟"))return;await request("messages","delete",Number(id));renderMessages(currentPage);refreshQuota();}
async function refreshQuota(){if(!currentUser)return;const arr=await getMessages(),used=arr.filter(m=>m.from===currentUser.email||m.to===currentUser.email).reduce((s,m)=>s+new Blob([m.subject||"",m.body||""]).size,0),p=plan(currentUser.plan);$("usedSpace").textContent=bytesText(used);$("totalSpace").textContent=p.label;$("quotaSide").innerHTML=`المستخدم تقريبًا: <b>${bytesText(used)}</b><br>المساحة: <b>${esc(p.label)}</b><br>المتبقي: <b>${bytesText(Math.max(0,p.bytes-used))}</b>`;}
function buyPlan(id){const p=plan(id),msg=`السلام عليكم، أريد شراء مساحة تخزين في Eisen Mail.\nالحساب: ${currentUser.email}\nالباقة: ${p.name}\nالمساحة: ${p.label}\nالسعر: ${p.priceLabel}\nأرجو إعلامي بطريقة الدفع.`;window.open("https://wa.me/"+WHATSAPP_NUMBER+"?text="+encodeURIComponent(msg),"_blank","noopener");}
function renderAccount(){const p=plan(currentUser.plan);$("accountDetails").innerHTML=`<div class="item"><strong>الاسم</strong>${esc(currentUser.name)}</div><div class="item"><strong>عنوان الحساب</strong>${esc(currentUser.email)}</div><div class="item"><strong>الباقة</strong>${esc(p.name)} — ${esc(p.label)}</div><div class="item"><strong>تاريخ الإنشاء</strong>${esc(new Date(currentUser.createdAt).toLocaleString("ar"))}</div>`;}
async function exportBackup(){const data={app:"Eisen Mail",version:1,users:await getUsers(),messages:await getMessages()};const blob=new Blob([JSON.stringify(data,null,2)],{type:"application/json"}),url=URL.createObjectURL(blob),a=document.createElement("a");a.href=url;a.download="eisen-mail-backup.json";a.click();setTimeout(()=>URL.revokeObjectURL(url),1000);}
async function importBackup(){const f=$("importFile").files[0];if(!f)return alert("اختر ملف JSON.");if(!confirm("سيتم استيراد الحسابات والرسائل إلى هذا المتصفح. المتابعة؟"))return;try{const d=JSON.parse(await f.text());if(d.app!=="Eisen Mail"||!Array.isArray(d.users)||!Array.isArray(d.messages))throw Error("invalid");for(const u of d.users)if(u.email)await request("users","put",u);for(const m of d.messages){if(m.id)await request("messages","put",m);else await request("messages","add",m);}alert("اكتمل الاستيراد.");$("importFile").value="";}catch(e){alert("تعذر الاستيراد: الملف غير صالح.");}}
(async()=>{try{await openDB();showAuth("login");}catch(e){$("authView").innerHTML='<div class="card"><h2>تعذر فتح قاعدة البيانات</h2><p>استخدم متصفحًا حديثًا وافتح الصفحة عبر HTTPS أو من بيئة محلية تدعم IndexedDB.</p></div>';}})();
</script>
</body></html>