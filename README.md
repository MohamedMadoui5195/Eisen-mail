<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width,initial-scale=1,maximum-scale=1">
<meta name="theme-color" content="#06152e">
<title>Eisen Mail</title>
<link rel="icon" href="icon.png" type="image/png">

<style>
:root{
  --bg:#050d1b;
  --panel:#0a1930;
  --panel2:#102443;
  --border:#1c3b64;
  --blue:#2684ff;
  --text:#f1f6ff;
  --muted:#9bb1d0;
  --danger:#ff647c;
  --green:#43d9a3;
}
*{box-sizing:border-box}
body{
  margin:0;
  min-height:100vh;
  background:var(--bg);
  color:var(--text);
  font-family:Arial,sans-serif;
}
button,input,textarea{font:inherit}
button{cursor:pointer}
.hidden{display:none!important}
button:disabled{opacity:.5;cursor:not-allowed}

/* شاشة الحساب */
#authScreen{
  min-height:100vh;
  display:flex;
  justify-content:center;
  align-items:center;
  padding:20px;
  background:radial-gradient(ellipse at top,#123361 0%,#071429 48%,#030916 100%);
}
.auth-card{
  width:100%;
  max-width:420px;
  padding:30px 24px;
  border:1px solid var(--border);
  background:#09172bf2;
  border-radius:24px;
  box-shadow:0 20px 70px #0006;
}
.brand{text-align:center;margin-bottom:26px}
.logo{
  width:78px;
  height:78px;
  object-fit:contain;
  border-radius:18px;
}
.brand h1{font-size:30px;margin:12px 0 7px}
.brand p{margin:0;color:var(--muted);font-size:14px}
.tabs{
  display:flex;
  gap:8px;
  background:#061126;
  padding:5px;
  border-radius:12px;
  margin-bottom:22px;
}
.tabs button{
  flex:1;
  border:0;
  padding:12px 6px;
  border-radius:9px;
  background:transparent;
  color:var(--muted);
}
.tabs button.active{
  background:var(--blue);
  color:white;
}
label{
  display:block;
  font-size:14px;
  margin:15px 0 8px;
}
input,textarea{
  width:100%;
  color:white;
  background:#07162c;
  border:1px solid var(--border);
  padding:13px;
  border-radius:11px;
  outline:none;
}
input:focus,textarea:focus{border-color:var(--blue)}
.primary{
  border:0;
  background:linear-gradient(100deg,#1764d8,#358dff);
  color:white;
  font-weight:bold;
  border-radius:11px;
  padding:14px;
}
.full{width:100%;margin-top:22px}
.notice{
  font-size:13px;
  color:var(--muted);
  line-height:1.8;
  margin-top:18px;
}
.status{font-size:14px;line-height:1.8;margin-top:12px}
.status.error{color:var(--danger)}
.status.success{color:var(--green)}

/* التطبيق */
#appScreen{min-height:100vh;padding-bottom:80px}
.topbar{
  height:70px;
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
  padding:0 18px;
  background:#08162b;
  border-bottom:1px solid var(--border);
  position:sticky;
  top:0;
  z-index:5;
}
.top-brand{display:flex;align-items:center;gap:10px;min-width:0}
.top-brand img{width:40px;height:40px;object-fit:contain}
.top-brand strong{font-size:19px}
.top-brand small{
  display:block;
  color:var(--muted);
  font-size:11px;
  margin-top:4px;
}
.top-actions{display:flex;gap:7px}
.icon-btn{
  border:1px solid var(--border);
  background:var(--panel2);
  color:white;
  padding:10px;
  border-radius:10px;
}
.layout{
  max-width:1150px;
  margin:0 auto;
  padding:20px;
  display:grid;
  grid-template-columns:220px minmax(0,1fr);
  gap:20px;
}
.sidebar{
  background:var(--panel);
  border:1px solid var(--border);
  border-radius:16px;
  padding:12px;
  height:max-content;
}
.side-btn{
  display:block;
  width:100%;
  text-align:right;
  padding:14px 12px;
  color:#c3d4ed;
  background:transparent;
  border:0;
  border-radius:10px;
  margin:3px 0;
}
.side-btn.active,.side-btn:hover{
  color:white;
  background:#143762;
}
.side-btn .symbol{
  display:inline-block;
  width:30px;
}
.content{min-width:0}
.page{display:none}
.page.active{display:block}
.page-title{
  display:flex;
  justify-content:space-between;
  align-items:center;
  gap:10px;
  margin-bottom:20px;
}
.page-title h2{margin:0;font-size:23px}
.page-title p{color:var(--muted);font-size:13px;margin:7px 0 0}
.panel{
  border:1px solid var(--border);
  background:var(--panel);
  border-radius:16px;
  padding:20px;
  margin-bottom:16px;
}
.search{
  margin-bottom:15px;
}
.message-item{
  display:block;
  width:100%;
  text-align:right;
  color:white;
  border:1px solid var(--border);
  background:#0a1a32;
  border-radius:13px;
  padding:16px;
  margin-bottom:10px;
}
.message-item:hover{border-color:#428fff}
.message-head{
  display:flex;
  align-items:center;
  justify-content:space-between;
  gap:10px;
}
.message-head strong{overflow-wrap:anywhere}
.message-item p{
  color:#c0cfe4;
  font-size:14px;
  line-height:1.7;
  margin:10px 0 0;
  overflow-wrap:anywhere;
}
.meta{font-size:12px;color:var(--muted);margin-top:7px}
.badge{
  background:#163c68;
  color:#a9d1ff;
  border-radius:7px;
  padding:5px 8px;
  font-size:11px;
}
.empty{
  text-align:center;
  padding:45px 15px;
  color:var(--muted);
  border:1px dashed var(--border);
  border-radius:14px;
}
.empty span{display:block;font-size:36px;margin-bottom:10px}
.form-actions{display:flex;gap:10px;margin-top:20px}
.form-actions button{flex:1}
.secondary{
  background:#132846;
  border:1px solid var(--border);
  color:white;
  border-radius:10px;
  padding:13px;
}
textarea{resize:vertical;min-height:180px}
.detail-body{
  white-space:pre-wrap;
  overflow-wrap:anywhere;
  line-height:1.9;
  margin-top:20px;
}
.account-box{
  display:flex;
  align-items:center;
  gap:14px;
  overflow-wrap:anywhere;
}
.avatar{
  width:52px;
  height:52px;
  flex-shrink:0;
  display:grid;
  place-items:center;
  background:#153b6b;
  border-radius:15px;
  font-size:24px;
}
.bottom-nav{
  display:none;
  position:fixed;
  z-index:10;
  bottom:0;
  left:0;
  right:0;
  background:#08162b;
  border-top:1px solid var(--border);
  padding:8px 5px calc(8px + env(safe-area-inset-bottom));
  grid-template-columns:repeat(4,1fr);
}
.bottom-nav button{
  background:transparent;
  border:0;
  color:var(--muted);
  padding:8px 2px;
  font-size:11px;
}
.bottom-nav button span{display:block;font-size:20px;margin-bottom:5px}
.bottom-nav button.active{color:#60a5ff}
footer{
  text-align:center;
  color:#647b9c;
  font-size:12px;
  padding:15px;
}
@media(max-width:700px){
  .layout{display:block;padding:13px}
  .sidebar{display:none}
  .bottom-nav{display:grid}
  .page-title h2{font-size:21px}
  .panel{padding:16px}
  .topbar{padding:0 12px}
  .top-brand strong{font-size:17px}
  .top-actions .icon-btn{padding:9px}
}
</style>
</head>
<body>

<!-- شاشة التسجيل والدخول -->
<section id="authScreen">
  <div class="auth-card">
    <div class="brand">
      <img src="icon.png" class="logo" alt="Eisen Mail">
      <h1>Eisen Mail</h1>
      <p>بريدك، رسائلك، في مكان واحد</p>
    </div>

    <div class="tabs">
      <button id="loginTab" class="active" type="button">تسجيل الدخول</button>
      <button id="registerTab" type="button">إنشاء حساب</button>
    </div>

    <form id="authForm">
      <div id="nameField" class="hidden">
        <label for="displayName">الاسم</label>
        <input id="displayName" maxlength="60" autocomplete="name"
               placeholder="اسم المستخدم">
      </div>

      <label for="authEmail">البريد الإلكتروني المحلي</label>
      <input id="authEmail" type="email" maxlength="254"
             autocomplete="username" placeholder="user@example.com" required>

      <label for="authPassword">كلمة المرور</label>
      <input id="authPassword" type="password" minlength="8"
             autocomplete="current-password" placeholder="8 أحرف على الأقل"
             required>

      <button id="authSubmit" class="primary full" type="submit">
        تسجيل الدخول
      </button>
      <p id="authStatus" class="status" role="status"></p>
    </form>

    <div class="notice">
      هذا مشروع محلي تجريبي. الحسابات والرسائل محفوظة في هذا المتصفح فقط،
      ولا يتم إرسال بياناتك إلى خادم خارجي.
    </div>
  </div>
</section>

<!-- واجهة البريد -->
<section id="appScreen" class="hidden">
  <header class="topbar">
    <div class="top-brand">
      <img src="icon.png" alt="Eisen Mail">
      <div>
        <strong>Eisen Mail</strong>
        <small id="topEmail">صندوق البريد المحلي</small>
      </div>
    </div>
    <div class="top-actions">
      <button class="icon-btn" id="newMessageTop" title="رسالة جديدة">✎</button>
      <button class="icon-btn" id="logoutTop" title="تسجيل الخروج">⇥</button>
    </div>
  </header>

  <div class="layout">
    <aside class="sidebar">
      <button class="side-btn active" data-page="inbox"><span class="symbol">📥</span>الوارد</button>
      <button class="side-btn" data-page="compose"><span class="symbol">✉️</span>رسالة جديدة</button>
      <button class="side-btn" data-page="sent"><span class="symbol">📤</span>المرسلة</button>
      <button class="side-btn" data-page="settings"><span class="symbol">⚙️</span>الإعدادات</button>
    </aside>

    <main class="content">

      <section class="page active" id="page-inbox">
        <div class="page-title">
          <div>
            <h2>صندوق الوارد</h2>
            <p>رسائلك المستلمة داخل هذا المشروع المحلي</p>
          </div>
          <button class="primary" id="newMessage">＋ رسالة</button>
        </div>
        <input id="inboxSearch" class="search" placeholder="ابحث في الرسائل...">
        <div id="inboxList"></div>
      </section>

      <section class="page" id="page-compose">
        <div class="page-title">
          <div>
            <h2>رسالة جديدة</h2>
            <p>أرسل رسالة إلى حساب آخر في هذا المتصفح</p>
          </div>
        </div>
        <form id="composeForm" class="panel">
          <label for="recipient">إلى (البريد الإلكتروني)</label>
          <input id="recipient" type="email" required maxlength="254"
                 placeholder="recipient@example.com">

          <label for="subject">الموضوع</label>
          <input id="subject" required maxlength="150" placeholder="موضوع الرسالة">

          <label for="messageBody">الرسالة</label>
          <textarea id="messageBody" required maxlength="20000"
                    placeholder="اكتب رسالتك هنا..."></textarea>

          <div class="form-actions">
            <button class="primary" type="submit">إرسال محليًا</button>
            <button class="secondary" type="button" id="cancelCompose">إلغاء</button>
          </div>
          <p id="composeStatus" class="status" role="status"></p>
        </form>
      </section>

      <section class="page" id="page-sent">
        <div class="page-title">
          <div>
            <h2>الرسائل المرسلة</h2>
            <p>الرسائل التي أرسلتها من هذا الحساب</p>
          </div>
        </div>
        <input id="sentSearch" class="search" placeholder="ابحث في الرسائل المرسلة...">
        <div id="sentList"></div>
      </section>

      <section class="page" id="page-detail">
        <div class="page-title">
          <h2>تفاصيل الرسالة</h2>
          <button class="secondary" id="backFromDetail">← رجوع</button>
        </div>
        <article class="panel">
          <h2 id="detailSubject"></h2>
          <div id="detailFrom" class="meta"></div>
          <div id="detailTo" class="meta"></div>
          <div id="detailDate" class="meta"></div>
          <hr style="border-color:#203b61;margin-top:20px">
          <div id="detailBody" class="detail-body"></div>
          <div class="form-actions">
            <button id="replyButton" class="primary">الرد</button>
            <button id="deleteMessage" class="secondary">حذف الرسالة</button>
          </div>
        </article>
      </section>

      <section class="page" id="page-settings">
        <div class="page-title">
          <div>
            <h2>الإعدادات</h2>
            <p>إدارة الحساب المحلي</p>
          </div>
        </div>
        <div class="panel">
          <div class="account-box">
            <div class="avatar">✉</div>
            <div>
              <strong id="settingsName"></strong>
              <div id="settingsEmail" class="meta"></div>
            </div>
          </div>
          <hr style="border-color:#203b61;margin:22px 0">
          <p style="color:#a9bdd8;line-height:1.9">
            يتم تخزين البيانات في مساحة التخزين المحلية للمتصفح.
            حذف بيانات المتصفح قد يؤدي إلى فقدان الحسابات والرسائل.
            هذا المشروع ليس خدمة بريد إلكتروني عبر الإنترنت.
          </p>
          <button id="exportData" class="secondary" style="width:100%;margin-top:10px">
            تصدير نسخة احتياطية
          </button>
          <button id="importButton" class="secondary" style="width:100%;margin-top:10px">
            استيراد نسخة احتياطية
          </button>
          <input id="importFile" class="hidden" type="file" accept=".json,application/json">
          <button id="logoutSettings" class="secondary"
                  style="width:100%;margin-top:10px;color:#ff8798">
            تسجيل الخروج
          </button>
        </div>
      </section>
    </main>
  </div>

  <nav class="bottom-nav">
    <button class="active" data-page="inbox"><span>📥</span>الوارد</button>
    <button data-page="compose"><span>✉️</span>رسالة جديدة</button>
    <button data-page="sent"><span>📤</span>المرسلة</button>
    <button data-page="settings"><span>⚙️</span>الإعدادات</button>
  </nav>

  <footer>© Eisen Mail — مشروع بريد محلي</footer>
</section>

<script>
"use strict";

/*
  Eisen Mail Local
  جميع البيانات تبقى في المتصفح الحالي.
  هذا نموذج تعليمي وليس نظام مصادقة آمنًا للاستخدام الحقيقي.
*/

const DB_KEY = "eisen_mail_local_v1";
const SESSION_KEY = "eisen_mail_session_v1";

const $ = id => document.getElementById(id);

let db = loadDB();
let currentEmail = null;
let currentMessageId = null;
let currentFolder = "inbox";
let authMode = "login";

function loadDB(){
  try{
    const value = JSON.parse(localStorage.getItem(DB_KEY) || '{"users":{},"messages":[]}');
    if(!value || typeof value !== "object" ||
       !value.users || !Array.isArray(value.messages)){
      throw new Error("invalid");
    }
    return value;
  }catch{
    return {users:{},messages:[]};
  }
}

function saveDB(){
  localStorage.setItem(DB_KEY,JSON.stringify(db));
}

function normalizeEmail(value){
  return String(value || "").trim().toLowerCase();
}

function makeId(){
  return crypto.randomUUID
    ? crypto.randomUUID()
    : Date.now().toString(36)+Math.random().toString(36).slice(2);
}

function setStatus(element,message,type=""){
  element.textContent = message;
  element.className = "status" + (type ? " "+type : "");
}

function showAuth(){
  $("authScreen").classList.remove("hidden");
  $("appScreen").classList.add("hidden");
}

function showApp(){
  $("authScreen").classList.add("hidden");
  $("appScreen").classList.remove("hidden");
  renderApp();
}

function switchAuthMode(mode){
  authMode = mode;
  const registering = mode === "register";

  $("loginTab").classList.toggle("active",!registering);
  $("registerTab").classList.toggle("active",registering);
  $("nameField").classList.toggle("hidden",!registering);
  $("displayName").required = registering;
  $("authPassword").autocomplete = registering ? "new-password" : "current-password";
  $("authSubmit").textContent = registering ? "إنشاء الحساب" : "تسجيل الدخول";
  $("authStatus").textContent = "";
}

$("loginTab").addEventListener("click",()=>switchAuthMode("login"));
$("registerTab").addEventListener("click",()=>switchAuthMode("register"));

$("authForm").addEventListener("submit",event=>{
  event.preventDefault();

  const email = normalizeEmail($("authEmail").value);
  const password = $("authPassword").value;
  const name = $("displayName").value.trim();

  if(!email || !email.includes("@")){
    return setStatus($("authStatus"),"أدخل عنوان بريد إلكتروني صحيحًا.","error");
  }

  if(password.length < 8){
    return setStatus($("authStatus"),"كلمة المرور يجب أن تتكون من 8 أحرف على الأقل.","error");
  }

  try{
    if(authMode === "register"){
      if(!name){
        return setStatus($("authStatus"),"أدخل اسمك.","error");
      }
      if(db.users[email]){
        return setStatus($("authStatus"),"هذا الحساب موجود بالفعل. سجّل الدخول.","error");
      }

      // للتجربة المحلية فقط: لا تحفظ كلمات المرور بهذه الطريقة في تطبيق حقيقي.
      db.users[email] = {
        email,
        name,
        password,
        createdAt:new Date().toISOString()
      };

      saveDB();
      currentEmail = email;
      localStorage.setItem(SESSION_KEY,email);
      setStatus($("authStatus"),"تم إنشاء الحساب بنجاح.","success");
      showApp();
    }else{
      const user = db.users[email];

      if(!user){
        return setStatus($("authStatus"),"الحساب غير موجود. أنشئ حسابًا جديدًا.","error");
      }

      if(user.password !== password){
        return setStatus($("authStatus"),"كلمة المرور غير صحيحة.","error");
      }

      currentEmail = email;
      localStorage.setItem(SESSION_KEY,email);
      setStatus($("authStatus"),"تم تسجيل الدخول بنجاح.","success");
      showApp();
    }
  }catch(error){
    setStatus($("authStatus"),"تعذر حفظ البيانات. تحقق من مساحة التخزين.","error");
  }
});

function navigate(page){
  document.querySelectorAll(".page").forEach(el=>el.classList.remove("active"));
  const target = $("page-"+page);
  if(target) target.classList.add("active");

  document.querySelectorAll("[data-page]").forEach(button=>{
    button.classList.toggle("active",button.dataset.page===page);
  });

  if(page === "inbox" || page === "sent"){
    currentFolder = page;
    renderMessages(page);
  }
}

document.querySelectorAll("[data-page]").forEach(button=>{
  button.addEventListener("click",()=>navigate(button.dataset.page));
});

$("newMessage").addEventListener("click",()=>openCompose());
$("newMessageTop").addEventListener("click",()=>openCompose());
$("cancelCompose").addEventListener("click",()=>navigate("inbox"));

function openCompose(to="",subject="",body=""){
  navigate("compose");
  $("recipient").value = to;
  $("subject").value = subject;
  $("messageBody").value = body;
  $("composeStatus").textContent = "";
}

$("composeForm").addEventListener("submit",event=>{
  event.preventDefault();

  const recipient = normalizeEmail($("recipient").value);
  const subject = $("subject").value.trim();
  const body = $("messageBody").value.trim();

  if(!db.users[recipient]){
    return setStatus(
      $("composeStatus"),
      "لا يوجد حساب محلي بهذا البريد. أنشئ حساب المستلم في هذا المتصفح أولًا.",
      "error"
    );
  }

  if(recipient === currentEmail){
    return setStatus($("composeStatus"),"لا يمكنك إرسال رسالة إلى نفسك في هذا النموذج.","error");
  }

  const message = {
    id:makeId(),
    from:currentEmail,
    to:recipient,
    subject,
    body,
    date:new Date().toISOString(),
    deletedBy:[]
  };

  db.messages.push(message);

  try{
    saveDB();
    $("composeForm").reset();
    setStatus($("composeStatus"),"تم تسليم الرسالة إلى صندوق الحساب المحلي.","success");
    renderMessages("sent");
    setTimeout(()=>navigate("sent"),400);
  }catch(error){
    db.messages = db.messages.filter(item=>item.id!==message.id);
    setStatus($("composeStatus"),"تعذر حفظ الرسالة. قد تكون مساحة التخزين ممتلئة.","error");
  }
});

function visibleMessages(folder){
  return db.messages
    .filter(message=>{
      if((message.deletedBy||[]).includes(currentEmail)) return false;
      return folder === "inbox"
        ? message.to === currentEmail
        : message.from === currentEmail;
    })
    .sort((a,b)=>new Date(b.date)-new Date(a.date));
}

function renderMessages(folder){
  const isInbox = folder === "inbox";
  const container = $(isInbox ? "inboxList" : "sentList");
  const search = normalizeEmail($(isInbox ? "inboxSearch" : "sentSearch").value);
  container.replaceChildren();

  const list = visibleMessages(folder).filter(message=>{
    const other = isInbox ? message.from : message.to;
    return [other,message.subject,message.body]
      .some(value=>String(value||"").toLowerCase().includes(search));
  });

  if(!list.length){
    const empty = document.createElement("div");
    empty.className = "empty";

    const icon = document.createElement("span");
    icon.textContent = isInbox ? "📭" : "📤";

    const title = document.createElement("strong");
    title.textContent = isInbox ? "صندوق الوارد فارغ" : "لا توجد رسائل مرسلة";

    const desc = document.createElement("p");
    desc.textContent = search
      ? "لم نعثر على رسائل مطابقة لبحثك."
      : "ستظهر الرسائل هنا عندما تستخدم التطبيق.";

    empty.append(icon, title, desc);
    container.appendChild(empty);
    return;
  }

  list.forEach(message => {
    const button = document.createElement("button");
    button.className = "message-item";
    button.type = "button";

    const head = document.createElement("div");
    head.className = "message-head";

    const name = document.createElement("strong");
    name.textContent = isInbox
      ? (db.users[message.from]?.name || message.from)
      : "إلى: " + message.to;

    const badge = document.createElement("span");
    badge.className = "badge";
    badge.textContent = isInbox ? "واردة" : "مرسلة";

    head.append(name, badge);

    const subject = document.createElement("div");
    subject.style.marginTop = "10px";
    subject.style.fontWeight = "bold";
    subject.textContent = message.subject || "(بدون موضوع)";

    const preview = document.createElement("p");
    preview.textContent = message.body.slice(0, 160);

    const date = document.createElement("div");
    date.className = "meta";
    date.textContent = new Date(message.date).toLocaleString();

    button.append(head, subject, preview, date);
    button.addEventListener("click", () => openMessage(message.id, folder));
    container.appendChild(button);
  });
}

$("inboxSearch").addEventListener("input", () => renderMessages("inbox"));
$("sentSearch").addEventListener("input", () => renderMessages("sent"));

function openMessage(id, folder) {
  const message = db.messages.find(item => item.id === id);
  if (!message) return;

  currentMessageId = id;
  currentFolder = folder;

  $("detailSubject").textContent = message.subject || "(بدون موضوع)";
  $("detailFrom").textContent = "من: " + message.from;
  $("detailTo").textContent = "إلى: " + message.to;
  $("detailDate").textContent = new Date(message.date).toLocaleString();
  $("detailBody").textContent = message.body;

  $("replyButton").classList.toggle("hidden", message.from === currentEmail);
  navigate("detail");
}

$("backFromDetail").addEventListener("click", () => navigate(currentFolder));

$("replyButton").addEventListener("click", () => {
  const message = db.messages.find(item => item.id === currentMessageId);
  if (!message) return;

  openCompose(
    message.from,
    "رد: " + message.subject,
    "\n\n--- الرسالة الأصلية ---\n" + message.body
  );
});

$("deleteMessage").addEventListener("click", () => {
  const index = db.messages.findIndex(item => item.id === currentMessageId);
  if (index < 0) return;

  const message = db.messages[index];

  if (!confirm("هل تريد حذف هذه الرسالة من صندوقك؟")) return;

  message.deletedBy = Array.isArray(message.deletedBy)
    ? message.deletedBy
    : [];

  if (!message.deletedBy.includes(currentEmail)) {
    message.deletedBy.push(currentEmail);
  }

  saveDB();
  navigate(currentFolder);
});

function renderApp() {
  const user = db.users[currentEmail];

  if (!user) {
    logout();
    return;
  }

  $("topEmail").textContent = currentEmail;
  $("settingsName").textContent = user.name;
  $("settingsEmail").textContent = user.email;

  renderMessages("inbox");
  renderMessages("sent");
  navigate("inbox");
}

function logout() {
  currentEmail = null;
  localStorage.removeItem(SESSION_KEY);
  $("authForm").reset();
  switchAuthMode("login");
  showAuth();
}

$("logoutTop").addEventListener("click", logout);
$("logoutSettings").addEventListener("click", logout);

$("exportData").addEventListener("click", () => {
  const backup = {
    format: "eisen-mail-local-backup",
    version: 1,
    users: db.users,
    messages: db.messages
  };

  const blob = new Blob(
    [JSON.stringify(backup, null, 2)],
    { type: "application/json" }
  );

  const url = URL.createObjectURL(blob);
  const a = document.createElement("a");

  a.href = url;
  a.download = "eisen-mail-backup.json";
  a.click();

  URL.revokeObjectURL(url);
});

$("importButton").addEventListener("click", () => $("importFile").click());

$("importFile").addEventListener("change", async event => {
  const file = event.target.files[0];
  if (!file) return;

  try {
    const data = JSON.parse(await file.text());

    if (
      data.format !== "eisen-mail-local-backup" ||
      !data.users ||
      typeof data.users !== "object" ||
      !Array.isArray(data.messages)
    ) {
      throw new Error("invalid");
    }

    if (!confirm("سيؤدي الاستيراد إلى استبدال البيانات المحلية الحالية. هل تريد المتابعة؟")) {
      event.target.value = "";
      return;
    }

    db = {
      users: data.users,
      messages: data.messages
    };

    saveDB();

    if (!db.users[currentEmail]) {
      logout();
    } else {
      renderApp();
    }

    alert("تم استيراد النسخة الاحتياطية.");
  } catch {
    alert("ملف النسخة الاحتياطية غير صالح.");
  }

  event.target.value = "";
});

/* استعادة جلسة محلية سابقة */
try {
  const savedEmail = normalizeEmail(localStorage.getItem(SESSION_KEY));

  if (savedEmail && db.users[savedEmail]) {
    currentEmail = savedEmail;
    showApp();
  } else {
    localStorage.removeItem(SESSION_KEY);
    showAuth();
  }
} catch {
  showAuth();
}
</script>
</body>
</html>