# Sherport
<!-- generated HTML -->
<style>
  :root {
    --primary: #6C63FF;
    --secondary: #FF6584;
    --accent: #43C59E;
    --bg: #F7F8FC;
    --card: #FFFFFF;
    --text: #2D2D3A;
    --muted: #888;
    --border: #E5E7EB;
    --art: #FF6B6B;
    --academic: #4ECDC4;
    --activity: #FFD93D;
    --sport: #6C63FF;
    --radius: 16px;
    --shadow: 0 4px 24px rgba(0,0,0,0.08);
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Segoe UI', 'Sarabun', Arial, sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; }

  /* ===== SETUP SCREEN ===== */
  #setupScreen {
    display: flex; align-items: center; justify-content: center;
    min-height: 100vh; padding: 24px;
  }
  .setup-card {
    background: var(--card); border-radius: 24px; box-shadow: var(--shadow);
    padding: 48px 40px; max-width: 480px; width: 100%; text-align: center;
  }
  .setup-card .logo { font-size: 52px; margin-bottom: 16px; }
  .setup-card h1 { font-size: 24px; font-weight: 700; color: var(--primary); margin-bottom: 8px; }
  .setup-card p { color: var(--muted); font-size: 14px; line-height: 1.6; margin-bottom: 28px; }
  .setup-card input {
    width: 100%; padding: 12px 16px; border: 2px solid var(--border);
    border-radius: 10px; font-size: 14px; margin-bottom: 14px;
    transition: border-color .2s;
  }
  .setup-card input:focus { outline: none; border-color: var(--primary); }
  .setup-card label { display: block; text-align: left; font-size: 12px; font-weight: 600; color: var(--muted); margin-bottom: 6px; }
  .btn-primary {
    background: linear-gradient(135deg, var(--primary), #8B5CF6);
    color: #fff; border: none; border-radius: 10px; padding: 14px 32px;
    font-size: 15px; font-weight: 600; cursor: pointer; width: 100%;
    transition: opacity .2s, transform .1s;
  }
  .btn-primary:hover { opacity: .92; transform: translateY(-1px); }
  .setup-note { font-size: 11px; color: var(--muted); margin-top: 16px; line-height: 1.6; }

  /* ===== MAIN APP ===== */
  #mainApp { display: none; }

  /* Header */
  .app-header {
    background: linear-gradient(135deg, var(--primary) 0%, #8B5CF6 100%);
    color: #fff; padding: 20px 32px; display: flex; align-items: center;
    justify-content: space-between; box-shadow: 0 2px 12px rgba(108,99,255,.3);
    position: sticky; top: 0; z-index: 100;
  }
  .header-left { display: flex; align-items: center; gap: 12px; }
  .header-left .logo { font-size: 28px; }
  .header-left h1 { font-size: 20px; font-weight: 700; }
  .header-left p { font-size: 12px; opacity: .8; margin-top: 2px; }
  .header-right { display: flex; gap: 10px; align-items: center; }
  .user-pill {
    background: rgba(255,255,255,.18); border-radius: 20px;
    padding: 6px 14px; font-size: 13px; display: flex; align-items: center; gap: 8px;
  }
  .btn-sm {
    background: rgba(255,255,255,.2); color: #fff; border: 1px solid rgba(255,255,255,.4);
    border-radius: 8px; padding: 7px 14px; font-size: 13px; cursor: pointer;
    transition: background .2s;
  }
  .btn-sm:hover { background: rgba(255,255,255,.35); }

  /* Tabs / Filter */
  .filter-bar {
    background: var(--card); border-bottom: 1px solid var(--border);
    padding: 0 32px; display: flex; gap: 4px; overflow-x: auto;
  }
  .filter-tab {
    padding: 16px 20px; font-size: 14px; font-weight: 500; cursor: pointer;
    border: none; background: none; color: var(--muted); white-space: nowrap;
    border-bottom: 3px solid transparent; transition: color .2s, border-color .2s;
  }
  .filter-tab.active { color: var(--primary); border-bottom-color: var(--primary); font-weight: 700; }
  .filter-tab:hover:not(.active) { color: var(--text); }

  /* Main Content */
  .main-content { padding: 32px; max-width: 1200px; margin: 0 auto; }

  /* Stats Row */
  .stats-row { display: flex; gap: 16px; margin-bottom: 32px; flex-wrap: wrap; }
  .stat-card {
    background: var(--card); border-radius: var(--radius); padding: 20px 24px;
    flex: 1; min-width: 140px; box-shadow: var(--shadow);
    display: flex; align-items: center; gap: 16px;
  }
  .stat-icon { font-size: 28px; }
  .stat-val { font-size: 24px; font-weight: 700; color: var(--text); }
  .stat-lbl { font-size: 12px; color: var(--muted); }

  /* Add Button */
  .section-header { display: flex; align-items: center; justify-content: space-between; margin-bottom: 20px; }
  .section-header h2 { font-size: 18px; font-weight: 700; }
  .btn-add {
    background: linear-gradient(135deg, var(--accent), #2DD4BF);
    color: #fff; border: none; border-radius: 10px; padding: 12px 20px;
    font-size: 14px; font-weight: 600; cursor: pointer;
    display: flex; align-items: center; gap: 8px; transition: opacity .2s, transform .1s;
  }
  .btn-add:hover { opacity: .9; transform: translateY(-1px); }

  /* Portfolio Grid */
  .portfolio-grid {
    display: grid; grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 20px;
  }
  .portfolio-card {
    background: var(--card); border-radius: var(--radius); overflow: hidden;
    box-shadow: var(--shadow); transition: transform .2s, box-shadow .2s;
    cursor: pointer;
  }
  .portfolio-card:hover { transform: translateY(-4px); box-shadow: 0 12px 32px rgba(0,0,0,0.12); }
  .card-thumb {
    height: 180px; background: var(--bg); position: relative; overflow: hidden;
    display: flex; align-items: center; justify-content: center;
  }
  .card-thumb img { width: 100%; height: 100%; object-fit: cover; }
  .card-thumb .no-img { font-size: 56px; opacity: .3; }
  .cat-badge {
    position: absolute; top: 12px; left: 12px; border-radius: 20px;
    padding: 4px 12px; font-size: 11px; font-weight: 700; color: #fff;
  }
  .card-body { padding: 18px; }
  .card-title { font-size: 16px; font-weight: 700; margin-bottom: 6px; line-height: 1.4; }
  .card-meta { font-size: 12px; color: var(--muted); display: flex; gap: 12px; align-items: center; }
  .card-desc { font-size: 13px; color: var(--muted); margin-top: 8px; line-height: 1.5; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden; }
  .card-actions { display: flex; gap: 8px; margin-top: 14px; }
  .btn-icon {
    background: var(--bg); border: 1px solid var(--border); border-radius: 8px;
    padding: 6px 10px; font-size: 13px; cursor: pointer; transition: background .2s;
  }
  .btn-icon:hover { background: var(--border); }

  /* Category colors */
  .cat-art { background: var(--art); }
  .cat-academic { background: var(--academic); }
  .cat-activity { background: #E6B800; }
  .cat-sport { background: var(--sport); }

  /* Empty State */
  .empty-state {
    text-align: center; padding: 80px 24px; color: var(--muted);
    grid-column: 1/-1;
  }
  .empty-state .empty-icon { font-size: 64px; margin-bottom: 16px; }
  .empty-state h3 { font-size: 18px; color: var(--text); margin-bottom: 8px; }

  /* ===== MODAL ===== */
  .modal-overlay {
    display: none; position: fixed; inset: 0;
    background: rgba(0,0,0,.5); z-index: 200; align-items: center; justify-content: center;
    padding: 24px;
  }
  .modal-overlay.open { display: flex; }
  .modal {
    background: var(--card); border-radius: 24px; padding: 36px;
    width: 100%; max-width: 560px; max-height: 90vh; overflow-y: auto;
    box-shadow: 0 20px 60px rgba(0,0,0,.2);
  }
  .modal h2 { font-size: 20px; font-weight: 700; margin-bottom: 24px; display: flex; align-items: center; gap: 10px; }
  .form-group { margin-bottom: 18px; }
  .form-group label { display: block; font-size: 13px; font-weight: 600; color: var(--muted); margin-bottom: 7px; }
  .form-group input, .form-group select, .form-group textarea {
    width: 100%; padding: 12px 14px; border: 2px solid var(--border);
    border-radius: 10px; font-size: 14px; font-family: inherit;
    transition: border-color .2s;
  }
  .form-group input:focus, .form-group select:focus, .form-group textarea:focus {
    outline: none; border-color: var(--primary);
  }
  .form-group textarea { resize: vertical; min-height: 80px; }
  .drive-picker-area {
    border: 2px dashed var(--border); border-radius: 12px; padding: 28px;
    text-align: center; cursor: pointer; transition: border-color .2s, background .2s;
  }
  .drive-picker-area:hover { border-color: var(--primary); background: #F3F1FF; }
  .drive-picker-area .icon { font-size: 36px; margin-bottom: 8px; }
  .drive-picker-area p { font-size: 13px; color: var(--muted); }
  .drive-picker-area .subtext { font-size: 11px; color: #B0B; margin-top: 4px; }
  .file-list { margin-top: 12px; display: flex; flex-direction: column; gap: 8px; }
  .file-item {
    background: var(--bg); border-radius: 8px; padding: 10px 14px;
    display: flex; align-items: center; gap: 10px; font-size: 13px;
  }
  .file-item .file-icon { font-size: 18px; }
  .file-item .file-name { flex: 1; overflow: hidden; text-overflow: ellipsis; white-space: nowrap; }
  .file-item .remove-file { cursor: pointer; color: var(--muted); font-size: 16px; }
  .file-item .remove-file:hover { color: var(--secondary); }
  .modal-actions { display: flex; gap: 12px; margin-top: 24px; }
  .btn-cancel {
    flex: 1; padding: 13px; border: 2px solid var(--border); border-radius: 10px;
    background: none; font-size: 14px; font-weight: 600; cursor: pointer;
    transition: background .2s;
  }
  .btn-cancel:hover { background: var(--bg); }
  .btn-save {
    flex: 2; padding: 13px; background: linear-gradient(135deg, var(--primary), #8B5CF6);
    color: #fff; border: none; border-radius: 10px;
    font-size: 14px; font-weight: 600; cursor: pointer; transition: opacity .2s;
  }
  .btn-save:hover { opacity: .9; }

  /* Detail Modal */
  .detail-modal { max-width: 680px; }
  .detail-hero { border-radius: 14px; overflow: hidden; margin-bottom: 24px; max-height: 320px; }
  .detail-hero img { width: 100%; height: 100%; object-fit: cover; }
  .detail-hero .no-hero { background: var(--bg); height: 160px; display: flex; align-items: center; justify-content: center; font-size: 72px; }
  .detail-title { font-size: 22px; font-weight: 700; margin-bottom: 12px; }
  .detail-meta { display: flex; gap: 16px; margin-bottom: 16px; flex-wrap: wrap; }
  .detail-badge { display: flex; align-items: center; gap: 6px; font-size: 13px; color: var(--muted); }
  .detail-desc { font-size: 14px; line-height: 1.7; color: var(--text); margin-bottom: 20px; }
  .detail-files h4 { font-size: 14px; font-weight: 700; margin-bottom: 10px; }
  .detail-file-link {
    display: flex; align-items: center; gap: 10px; padding: 10px 14px;
    background: var(--bg); border-radius: 10px; margin-bottom: 8px; text-decoration: none;
    color: var(--text); transition: background .2s;
  }
  .detail-file-link:hover { background: #EEEAFF; }

  /* Toast */
  #toast {
    position: fixed; bottom: 32px; left: 50%; transform: translateX(-50%) translateY(80px);
    background: #1E1E2E; color: #fff; border-radius: 10px; padding: 14px 24px;
    font-size: 14px; z-index: 500; transition: transform .3s ease;
    display: flex; align-items: center; gap: 10px; min-width: 280px; justify-content: center;
  }
  #toast.show { transform: translateX(-50%) translateY(0); }

  /* Google Sign-in indicator */
  .google-avatar { width: 28px; height: 28px; border-radius: 50%; background: #fff; display: flex; align-items: center; justify-content: center; font-size: 14px; }

  @media (max-width: 600px) {
    .app-header { padding: 16px; }
    .main-content { padding: 20px 16px; }
    .filter-bar { padding: 0 16px; }
    .portfolio-grid { grid-template-columns: 1fr; }
    .stats-row { gap: 10px; }
    .stat-card { min-width: 120px; padding: 16px; }
    .modal { padding: 24px 20px; }
  }
</style>

<!-- SETUP SCREEN -->
<div id="setupScreen">
  <div class="setup-card">
    <div class="logo">🎓</div>
    <h1>Portfolio ลูกสาว</h1>
    <p>แอปเก็บผลงานเชื่อมต่อ Google Drive<br>ใส่ข้อมูล Google API ครั้งแรกเพื่อเริ่มใช้งาน</p>
    <div style="text-align:left">
      <label>🔑 Google OAuth Client ID</label>
      <input type="text" id="inputClientId" placeholder="xxxx.apps.googleusercontent.com" />
      <label>🗝️ Google API Key</label>
      <input type="text" id="inputApiKey" placeholder="AIzaSy..." />
    </div>
    <button class="btn-primary" onclick="setupAndInit()">🚀 เริ่มใช้งาน</button>
    <div class="setup-note">
      ข้อมูลนี้จะเก็บใน Browser ของคุณเท่านั้น ไม่ได้ส่งไปที่ใดทั้งนั้น<br>
      ต้องการวิธีตั้งค่า? ดูคำแนะนำด้านบน
    </div>
  </div>
</div>

<!-- MAIN APP -->
<div id="mainApp">
  <!-- Header -->
  <div class="app-header">
    <div class="header-left">
      <div class="logo">🎓</div>
      <div>
        <h1>Portfolio ลูกสาว</h1>
        <p>ผลงานและความสำเร็จ</p>
      </div>
    </div>
    <div class="header-right">
      <div class="user-pill">
        <div class="google-avatar" id="userAvatar">👤</div>
        <span id="userName">ยังไม่ได้เข้าสู่ระบบ</span>
      </div>
      <button class="btn-sm" id="signInBtn" onclick="handleSignIn()">🔐 Sign In</button>
      <button class="btn-sm" onclick="resetSetup()" title="เปลี่ยนการตั้งค่า">⚙️</button>
    </div>
  </div>

  <!-- Filter Tabs -->
  <div class="filter-bar">
    <button class="filter-tab active" data-cat="all" onclick="filterCategory(this)">✨ ทั้งหมด</button>
    <button class="filter-tab" data-cat="art" onclick="filterCategory(this)">🎨 ศิลปะ / วาดรูป</button>
    <button class="filter-tab" data-cat="academic" onclick="filterCategory(this)">📚 วิชาการ / รางวัล</button>
    <button class="filter-tab" data-cat="activity" onclick="filterCategory(this)">🎭 กิจกรรม / การแสดง</button>
    <button class="filter-tab" data-cat="sport" onclick="filterCategory(this)">🏆 กีฬา / ความสำเร็จ</button>
  </div>

  <!-- Main -->
  <div class="main-content">
    <!-- Stats -->
    <div class="stats-row" id="statsRow">
      <div class="stat-card"><div class="stat-icon">✨</div><div><div class="stat-val" id="statTotal">0</div><div class="stat-lbl">ผลงานทั้งหมด</div></div></div>
      <div class="stat-card"><div class="stat-icon">🎨</div><div><div class="stat-val" id="statArt">0</div><div class="stat-lbl">ศิลปะ</div></div></div>
      <div class="stat-card"><div class="stat-icon">📚</div><div><div class="stat-val" id="statAcademic">0</div><div class="stat-lbl">วิชาการ</div></div></div>
      <div class="stat-card"><div class="stat-icon">🎭</div><div><div class="stat-val" id="statActivity">0</div><div class="stat-lbl">กิจกรรม</div></div></div>
      <div class="stat-card"><div class="stat-icon">🏆</div><div><div class="stat-val" id="statSport">0</div><div class="stat-lbl">กีฬา</div></div></div>
    </div>

    <!-- Section Header -->
    <div class="section-header">
      <h2 id="sectionTitle">✨ ผลงานทั้งหมด</h2>
      <button class="btn-add" onclick="openAddModal()">➕ เพิ่มผลงาน</button>
    </div>

    <!-- Grid -->
    <div class="portfolio-grid" id="portfolioGrid"></div>
  </div>
</div>

<!-- ADD/EDIT MODAL -->
<div class="modal-overlay" id="addModal">
  <div class="modal">
    <h2 id="modalTitle">➕ เพิ่มผลงานใหม่</h2>
    <input type="hidden" id="editId" />

    <div class="form-group">
      <label>📌 ชื่อผลงาน *</label>
      <input type="text" id="fTitle" placeholder="เช่น รางวัลชนะเลิศวาดภาพระดับจังหวัด" />
    </div>
    <div style="display:flex;gap:14px">
      <div class="form-group" style="flex:1">
        <label>🏷️ หมวดหมู่ *</label>
        <select id="fCat">
          <option value="art">🎨 ศิลปะ / วาดรูป</option>
          <option value="academic">📚 วิชาการ / รางวัล</option>
          <option value="activity">🎭 กิจกรรม / การแสดง</option>
          <option value="sport">🏆 กีฬา / ความสำเร็จ</option>
        </select>
      </div>
      <div class="form-group" style="flex:1">
        <label>📅 วันที่</label>
        <input type="date" id="fDate" />
      </div>
    </div>
    <div class="form-group">
      <label>📝 รายละเอียด</label>
      <textarea id="fDesc" placeholder="อธิบายผลงาน ที่มา หรือความภาคภูมิใจ..."></textarea>
    </div>
    <div class="form-group">
      <label>📁 แนบไฟล์จาก Google Drive (รูปภาพ / เอกสาร)</label>
      <div class="drive-picker-area" id="pickerArea" onclick="openDrivePicker()">
        <div class="icon">☁️</div>
        <p><strong>คลิกเพื่อเลือกไฟล์จาก Google Drive</strong></p>
        <p style="font-size:11px;color:var(--muted);margin-top:4px">รองรับรูปภาพ, PDF, Word, และไฟล์อื่นๆ</p>
      </div>
      <div class="file-list" id="fileList"></div>
    </div>

    <div class="modal-actions">
      <button class="btn-cancel" onclick="closeModal('addModal')">ยกเลิก</button>
      <button class="btn-save" onclick="savePortfolio()">💾 บันทึกผลงาน</button>
    </div>
  </div>
</div>

<!-- DETAIL MODAL -->
<div class="modal-overlay" id="detailModal">
  <div class="modal detail-modal" id="detailContent"></div>
</div>

<!-- TOAST -->
<div id="toast"></div>

<script>
// ===== CONFIG =====
const SCOPES = 'https://www.googleapis.com/auth/drive.file https://www.googleapis.com/auth/drive.readonly';
const DISCOVERY_DOCS = ['https://www.googleapis.com/discovery/v1/apis/drive/v3/rest'];
const FOLDER_NAME = 'Portfolio_ลูกสาว';
const DB_KEY = 'portfolio_items';
const CONFIG_KEY = 'portfolio_config';

let gapi_loaded = false, gis_loaded = false;
let tokenClient = null, accessToken = null;
let folderId = null;
let selectedFiles = []; // [{id, name, mimeType, webViewLink, thumbnailLink}]
let currentFilter = 'all';
let editingId = null;
let CLIENT_ID = '', API_KEY = '';

// ===== CAT HELPERS =====
const catMeta = {
  art:      { label: '🎨 ศิลปะ / วาดรูป',     cls: 'cat-art',      icon: '🎨' },
  academic: { label: '📚 วิชาการ / รางวัล',     cls: 'cat-academic', icon: '📚' },
  activity: { label: '🎭 กิจกรรม / การแสดง',   cls: 'cat-activity', icon: '🎭' },
  sport:    { label: '🏆 กีฬา / ความสำเร็จ',   cls: 'cat-sport',    icon: '🏆' },
};

// ===== SETUP =====
function setupAndInit() {
  const cid = document.getElementById('inputClientId').value.trim();
  const akey = document.getElementById('inputApiKey').value.trim();
  if (!cid || !akey) { showToast('⚠️ กรุณากรอก Client ID และ API Key', true); return; }
  CLIENT_ID = cid; API_KEY = akey;
  localStorage.setItem(CONFIG_KEY, JSON.stringify({ CLIENT_ID, API_KEY }));
  startApp();
}

function resetSetup() {
  if (!confirm('ต้องการเปลี่ยนการตั้งค่า API? (ต้อง sign in ใหม่)')) return;
  localStorage.removeItem(CONFIG_KEY);
  location.reload();
}

function startApp() {
  document.getElementById('setupScreen').style.display = 'none';
  document.getElementById('mainApp').style.display = 'block';
  loadGoogleAPIs();
  renderGrid();
  updateStats();
}

// ===== LOCAL DB =====
function getItems() { return JSON.parse(localStorage.getItem(DB_KEY) || '[]'); }
function saveItems(items) { localStorage.setItem(DB_KEY, JSON.stringify(items)); }

// ===== LOAD GOOGLE APIs =====
function loadGoogleAPIs() {
  // Load gapi
  const s1 = document.createElement('script');
  s1.src = 'https://apis.google.com/js/api.js';
  s1.onload = () => {
    gapi.load('client:picker', () => {
      gapi.client.init({ apiKey: API_KEY, discoveryDocs: DISCOVERY_DOCS })
        .then(() => { gapi_loaded = true; tryAutoSignIn(); })
        .catch(e => { showToast('❌ API Key ไม่ถูกต้อง: ' + e.message, true); });
    });
  };
  document.body.appendChild(s1);

  // Load GIS
  const s2 = document.createElement('script');
  s2.src = 'https://accounts.google.com/gsi/client';
  s2.onload = () => {
    tokenClient = google.accounts.oauth2.initTokenClient({
      client_id: CLIENT_ID,
      scope: SCOPES,
      callback: handleTokenResponse,
    });
    gis_loaded = true;
    tryAutoSignIn();
  };
  document.body.appendChild(s2);
}

function tryAutoSignIn() {
  const saved = sessionStorage.getItem('gToken');
  if (saved && gapi_loaded && gis_loaded) {
    accessToken = saved;
    gapi.client.setToken({ access_token: accessToken });
    fetchUserInfo();
  }
}

function handleSignIn() {
  if (!gapi_loaded || !gis_loaded) { showToast('⏳ กำลังโหลด Google API...'); return; }
  tokenClient.requestAccessToken({ prompt: '' });
}

function handleTokenResponse(resp) {
  if (resp.error) { showToast('❌ ไม่สามารถเข้าสู่ระบบ: ' + resp.error, true); return; }
  accessToken = resp.access_token;
  sessionStorage.setItem('gToken', accessToken);
  gapi.client.setToken({ access_token: accessToken });
  fetchUserInfo();
  ensureDriveFolder();
}

function fetchUserInfo() {
  fetch('https://www.googleapis.com/oauth2/v3/userinfo', {
    headers: { Authorization: 'Bearer ' + accessToken }
  }).then(r => r.json()).then(info => {
    document.getElementById('userName').textContent = info.name || info.email;
    if (info.picture) {
      document.getElementById('userAvatar').innerHTML = `<img src="${info.picture}" style="width:28px;height:28px;border-radius:50%">`;
    }
    document.getElementById('signInBtn').textContent = '✅ เชื่อมต่อแล้ว';
    document.getElementById('signInBtn').style.background = 'rgba(67,197,158,.35)';
    showToast('✅ เข้าสู่ระบบสำเร็จ');
  }).catch(() => {});
}

// ===== DRIVE FOLDER =====
async function ensureDriveFolder() {
  try {
    const res = await gapi.client.drive.files.list({
      q: `name='${FOLDER_NAME}' and mimeType='application/vnd.google-apps.folder' and trashed=false`,
      fields: 'files(id,name)'
    });
    if (res.result.files.length > 0) {
      folderId = res.result.files[0].id;
    } else {
      const created = await gapi.client.drive.files.create({
        resource: { name: FOLDER_NAME, mimeType: 'application/vnd.google-apps.folder' },
        fields: 'id'
      });
      folderId = created.result.id;
      showToast('📁 สร้างโฟลเดอร์ Portfolio บน Drive แล้ว');
    }
  } catch(e) { console.error('Folder error:', e); }
}

// ===== GOOGLE PICKER =====
function openDrivePicker() {
  if (!accessToken) { showToast('⚠️ กรุณา Sign In Google Drive ก่อนครับ', true); return; }
  const view = new google.picker.DocsView()
    .setIncludeFolders(false)
    .setSelectFolderEnabled(false);
  const picker = new google.picker.PickerBuilder()
    .setOAuthToken(accessToken)
    .setDeveloperKey(API_KEY)
    .addView(view)
    .addView(new google.picker.DocsUploadView())
    .setTitle('เลือกไฟล์จาก Google Drive')
    .setCallback(pickerCallback)
    .enableFeature(google.picker.Feature.MULTISELECT_ENABLED)
    .build();
  picker.setVisible(true);
}

function pickerCallback(data) {
  if (data.action === google.picker.Action.PICKED) {
    data.docs.forEach(doc => {
      if (!selectedFiles.find(f => f.id === doc.id)) {
        selectedFiles.push({
          id: doc.id,
          name: doc.name,
          mimeType: doc.mimeType,
          webViewLink: doc.url,
          thumbnailLink: doc.iconUrl,
          embedUrl: doc.embedUrl || null,
        });
      }
    });
    renderFileList();
  }
}

function renderFileList() {
  const el = document.getElementById('fileList');
  if (selectedFiles.length === 0) { el.innerHTML = ''; return; }
  el.innerHTML = selectedFiles.map((f, i) => `
    <div class="file-item">
      <span class="file-icon">${getFileIcon(f.mimeType)}</span>
      <span class="file-name">${f.name}</span>
      <span class="remove-file" onclick="removeFile(${i})">✕</span>
    </div>
  `).join('');
}

function removeFile(i) { selectedFiles.splice(i, 1); renderFileList(); }

function getFileIcon(mime) {
  if (!mime) return '📎';
  if (mime.startsWith('image/')) return '🖼️';
  if (mime === 'application/pdf') return '📄';
  if (mime.includes('word')) return '📝';
  if (mime.includes('spreadsheet') || mime.includes('excel')) return '📊';
  if (mime.includes('presentation') || mime.includes('powerpoint')) return '📑';
  if (mime.startsWith('video/')) return '🎬';
  if (mime.startsWith('audio/')) return '🎵';
  return '📎';
}

// ===== MODALS =====
function openAddModal(id = null) {
  editingId = id;
  selectedFiles = [];
  const modal = document.getElementById('addModal');
  if (id) {
    const item = getItems().find(x => x.id === id);
    if (!item) return;
    document.getElementById('modalTitle').textContent = '✏️ แก้ไขผลงาน';
    document.getElementById('fTitle').value = item.title;
    document.getElementById('fCat').value = item.cat;
    document.getElementById('fDate').value = item.date || '';
    document.getElementById('fDesc').value = item.desc || '';
    selectedFiles = item.files ? [...item.files] : [];
  } else {
    document.getElementById('modalTitle').textContent = '➕ เพิ่มผลงานใหม่';
    document.getElementById('fTitle').value = '';
    document.getElementById('fCat').value = 'art';
    document.getElementById('fDate').value = new Date().toISOString().split('T')[0];
    document.getElementById('fDesc').value = '';
  }
  renderFileList();
  modal.classList.add('open');
}

function closeModal(id) { document.getElementById(id).classList.remove('open'); }

function savePortfolio() {
  const title = document.getElementById('fTitle').value.trim();
  if (!title) { showToast('⚠️ กรุณากรอกชื่อผลงาน', true); return; }

  const items = getItems();
  const item = {
    id: editingId || Date.now().toString(),
    title,
    cat: document.getElementById('fCat').value,
    date: document.getElementById('fDate').value,
    desc: document.getElementById('fDesc').value.trim(),
    files: [...selectedFiles],
    createdAt: editingId ? (items.find(x => x.id === editingId)?.createdAt || Date.now()) : Date.now(),
  };

  if (editingId) {
    const idx = items.findIndex(x => x.id === editingId);
    if (idx !== -1) items[idx] = item;
  } else {
    items.unshift(item);
  }

  saveItems(items);
  closeModal('addModal');
  renderGrid();
  updateStats();
  showToast(editingId ? '✅ แก้ไขผลงานแล้ว' : '🎉 เพิ่มผลงานสำเร็จ!');
  editingId = null;
}

function deleteItem(id) {
  if (!confirm('ต้องการลบผลงานนี้?')) return;
  const items = getItems().filter(x => x.id !== id);
  saveItems(items);
  closeModal('detailModal');
  renderGrid();
  updateStats();
  showToast('🗑️ ลบผลงานแล้ว');
}

function openDetail(id) {
  const item = getItems().find(x => x.id === id);
  if (!item) return;
  const meta = catMeta[item.cat] || catMeta.art;
  const imgFile = item.files?.find(f => f.mimeType?.startsWith('image/'));
  const heroSrc = imgFile ? `https://drive.google.com/thumbnail?id=${imgFile.id}&sz=w800` : null;

  const filesHtml = item.files?.length ? `
    <div class="detail-files">
      <h4>📎 ไฟล์แนบ (${item.files.length} ไฟล์)</h4>
      ${item.files.map(f => `
        <a class="detail-file-link" href="${f.webViewLink}" target="_blank">
          <span>${getFileIcon(f.mimeType)}</span>
          <span style="flex:1">${f.name}</span>
          <span style="font-size:11px;color:var(--muted)">เปิดใน Drive ↗</span>
        </a>
      `).join('')}
    </div>
  ` : '';

  document.getElementById('detailContent').innerHTML = `
    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:20px">
      <span class="cat-badge ${meta.cls}" style="position:static;font-size:13px;padding:6px 14px;border-radius:20px">${meta.label}</span>
      <button onclick="closeModal('detailModal')" style="background:none;border:none;font-size:22px;cursor:pointer;color:var(--muted)">✕</button>
    </div>
    ${heroSrc ? `<div class="detail-hero"><img src="${heroSrc}" alt="${item.title}" onerror="this.parentElement.innerHTML='<div class=no-hero>${meta.icon}</div>'"></div>` : `<div class="detail-hero"><div class="no-hero">${meta.icon}</div></div>`}
    <div class="detail-title">${item.title}</div>
    <div class="detail-meta">
      ${item.date ? `<div class="detail-badge">📅 ${formatDate(item.date)}</div>` : ''}
      ${item.files?.length ? `<div class="detail-badge">📎 ${item.files.length} ไฟล์</div>` : ''}
    </div>
    ${item.desc ? `<div class="detail-desc">${item.desc.replace(/\n/g,'<br>')}</div>` : ''}
    ${filesHtml}
    <div style="display:flex;gap:10px;margin-top:24px">
      <button class="btn-cancel" style="flex:1" onclick="closeModal('detailModal');openAddModal('${item.id}')">✏️ แก้ไข</button>
      <button class="btn-cancel" style="flex:1;color:var(--secondary)" onclick="deleteItem('${item.id}')">🗑️ ลบ</button>
    </div>
  `;
  document.getElementById('detailModal').classList.add('open');
}

// ===== RENDER =====
function filterCategory(btn) {
  document.querySelectorAll('.filter-tab').forEach(t => t.classList.remove('active'));
  btn.classList.add('active');
  currentFilter = btn.dataset.cat;
  const titles = { all:'✨ ผลงานทั้งหมด', art:'🎨 ศิลปะ / วาดรูป', academic:'📚 วิชาการ / รางวัล', activity:'🎭 กิจกรรม / การแสดง', sport:'🏆 กีฬา / ความสำเร็จ' };
  document.getElementById('sectionTitle').textContent = titles[currentFilter] || '';
  renderGrid();
}

function renderGrid() {
  const items = getItems().filter(x => currentFilter === 'all' || x.cat === currentFilter);
  const grid = document.getElementById('portfolioGrid');
  if (items.length === 0) {
    grid.innerHTML = `<div class="empty-state"><div class="empty-icon">📂</div><h3>ยังไม่มีผลงานในหมวดนี้</h3><p>กดปุ่ม "เพิ่มผลงาน" เพื่อเริ่มบันทึก</p></div>`;
    return;
  }
  grid.innerHTML = items.map(item => {
    const meta = catMeta[item.cat] || catMeta.art;
    const imgFile = item.files?.find(f => f.mimeType?.startsWith('image/'));
    const thumbUrl = imgFile ? `https://drive.google.com/thumbnail?id=${imgFile.id}&sz=w400` : null;
    return `
      <div class="portfolio-card" onclick="openDetail('${item.id}')">
        <div class="card-thumb">
          ${thumbUrl ? `<img src="${thumbUrl}" alt="${item.title}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'"><div class="no-img" style="display:none">${meta.icon}</div>` : `<div class="no-img">${meta.icon}</div>`}
          <span class="cat-badge ${meta.cls}">${meta.label}</span>
        </div>
        <div class="card-body">
          <div class="card-title">${item.title}</div>
          <div class="card-meta">
            ${item.date ? `<span>📅 ${formatDate(item.date)}</span>` : ''}
            ${item.files?.length ? `<span>📎 ${item.files.length} ไฟล์</span>` : ''}
          </div>
          ${item.desc ? `<div class="card-desc">${item.desc}</div>` : ''}
          <div class="card-actions">
            <button class="btn-icon" onclick="event.stopPropagation();openAddModal('${item.id}')">✏️ แก้ไข</button>
            <button class="btn-icon" onclick="event.stopPropagation();deleteItem('${item.id}')">🗑️</button>
          </div>
        </div>
      </div>
    `;
  }).join('');
}

function updateStats() {
  const items = getItems();
  document.getElementById('statTotal').textContent = items.length;
  document.getElementById('statArt').textContent = items.filter(x => x.cat==='art').length;
  document.getElementById('statAcademic').textContent = items.filter(x => x.cat==='academic').length;
  document.getElementById('statActivity').textContent = items.filter(x => x.cat==='activity').length;
  document.getElementById('statSport').textContent = items.filter(x => x.cat==='sport').length;
}

function formatDate(d) {
  if (!d) return '';
  const dt = new Date(d);
  return dt.toLocaleDateString('th-TH', { year:'numeric', month:'long', day:'numeric' });
}

// ===== TOAST =====
let toastTimer;
function showToast(msg, isError=false) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.style.background = isError ? '#C0392B' : '#1E1E2E';
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(() => t.classList.remove('show'), 3000);
}

// ===== MODAL CLOSE ON OVERLAY =====
document.querySelectorAll('.modal-overlay').forEach(el => {
  el.addEventListener('click', e => { if (e.target === el) el.classList.remove('open'); });
});

// ===== INIT =====
window.addEventListener('load', () => {
  const cfg = JSON.parse(localStorage.getItem(CONFIG_KEY) || 'null');
  if (cfg && cfg.CLIENT_ID && cfg.API_KEY) {
    CLIENT_ID = cfg.CLIENT_ID;
    API_KEY = cfg.API_KEY;
    startApp();
  }
});

let resizeTimer;
window.addEventListener('resize', () => {
  clearTimeout(resizeTimer);
  resizeTimer = setTimeout(renderGrid, 150);
});
</script>
