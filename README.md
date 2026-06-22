#Sherport
<!-- generated HTML -->
<style>
  :root {
    --primary: #6C63FF; --secondary: #FF6584; --accent: #43C59E;
    --bg: #F7F8FC; --card: #FFFFFF; --text: #2D2D3A; --muted: #888;
    --border: #E5E7EB; --art: #FF6B6B; --academic: #4ECDC4;
    --activity: #FFD93D; --sport: #6C63FF;
    --radius: 16px; --shadow: 0 4px 24px rgba(0,0,0,0.08);
  }
  * { box-sizing: border-box; margin: 0; padding: 0; }
  body { font-family: 'Segoe UI','Sarabun',Arial,sans-serif; background: var(--bg); color: var(--text); min-height: 100vh; }

  /* SETUP */
  #setupScreen { display:flex; align-items:center; justify-content:center; min-height:100vh; padding:24px; }
  .setup-card { background:var(--card); border-radius:24px; box-shadow:var(--shadow); padding:48px 40px; max-width:480px; width:100%; text-align:center; }
  .setup-card .logo { font-size:52px; margin-bottom:16px; }
  .setup-card h1 { font-size:24px; font-weight:700; color:var(--primary); margin-bottom:8px; }
  .setup-card p { color:var(--muted); font-size:14px; line-height:1.6; margin-bottom:28px; }
  .setup-card input { width:100%; padding:12px 16px; border:2px solid var(--border); border-radius:10px; font-size:14px; margin-bottom:14px; transition:border-color .2s; }
  .setup-card input:focus { outline:none; border-color:var(--primary); }
  .setup-card label { display:block; text-align:left; font-size:12px; font-weight:600; color:var(--muted); margin-bottom:6px; }
  .btn-primary { background:linear-gradient(135deg,var(--primary),#8B5CF6); color:#fff; border:none; border-radius:10px; padding:14px 32px; font-size:15px; font-weight:600; cursor:pointer; width:100%; transition:opacity .2s,transform .1s; }
  .btn-primary:hover { opacity:.92; transform:translateY(-1px); }
  .setup-note { font-size:11px; color:var(--muted); margin-top:16px; line-height:1.6; }

  /* MAIN */
  #mainApp { display:none; }
  .app-header { background:linear-gradient(135deg,var(--primary) 0%,#8B5CF6 100%); color:#fff; padding:20px 32px; display:flex; align-items:center; justify-content:space-between; box-shadow:0 2px 12px rgba(108,99,255,.3); position:sticky; top:0; z-index:100; }
  .header-left { display:flex; align-items:center; gap:12px; }
  .header-left .logo { font-size:28px; }
  .header-left h1 { font-size:20px; font-weight:700; }
  .header-left p { font-size:12px; opacity:.8; margin-top:2px; }
  .header-right { display:flex; gap:10px; align-items:center; }
  .user-pill { background:rgba(255,255,255,.18); border-radius:20px; padding:6px 14px; font-size:13px; display:flex; align-items:center; gap:8px; }
  .btn-sm { background:rgba(255,255,255,.2); color:#fff; border:1px solid rgba(255,255,255,.4); border-radius:8px; padding:7px 14px; font-size:13px; cursor:pointer; transition:background .2s; }
  .btn-sm:hover { background:rgba(255,255,255,.35); }
  .google-avatar { width:28px; height:28px; border-radius:50%; background:#fff; display:flex; align-items:center; justify-content:center; font-size:14px; }

  /* NAV TABS */
  .nav-bar { background:var(--card); border-bottom:1px solid var(--border); padding:0 32px; display:flex; gap:4px; overflow-x:auto; }
  .nav-tab { padding:16px 22px; font-size:14px; font-weight:500; cursor:pointer; border:none; background:none; color:var(--muted); white-space:nowrap; border-bottom:3px solid transparent; transition:color .2s,border-color .2s; }
  .nav-tab.active { color:var(--primary); border-bottom-color:var(--primary); font-weight:700; }
  .nav-tab:hover:not(.active) { color:var(--text); }

  /* PAGES */
  .page { display:none; padding:32px; max-width:1200px; margin:0 auto; }
  .page.active { display:block; }

  /* ── DASHBOARD ── */
  .dash-refresh { display:flex; align-items:center; justify-content:space-between; margin-bottom:24px; }
  .dash-refresh h2 { font-size:20px; font-weight:700; }
  .btn-refresh { background:var(--primary); color:#fff; border:none; border-radius:10px; padding:10px 20px; font-size:13px; font-weight:600; cursor:pointer; display:flex; align-items:center; gap:8px; transition:opacity .2s; }
  .btn-refresh:hover { opacity:.85; }
  .btn-refresh.spinning .icon { display:inline-block; animation:spin 1s linear infinite; }

  .kpi-row { display:grid; grid-template-columns:repeat(auto-fill,minmax(160px,1fr)); gap:16px; margin-bottom:28px; }
  .kpi-card { background:var(--card); border-radius:var(--radius); padding:20px; box-shadow:var(--shadow); text-align:center; }
  .kpi-card .kpi-emoji { font-size:32px; margin-bottom:8px; }
  .kpi-card .kpi-val { font-size:28px; font-weight:800; color:var(--primary); }
  .kpi-card .kpi-lbl { font-size:12px; color:var(--muted); margin-top:4px; }
  .kpi-card .kpi-sub { font-size:11px; color:var(--accent); margin-top:4px; font-weight:600; }

  .dash-grid { display:grid; grid-template-columns:1fr 1fr; gap:20px; margin-bottom:28px; }
  @media(max-width:700px){ .dash-grid { grid-template-columns:1fr; } }
  .dash-card { background:var(--card); border-radius:var(--radius); padding:24px; box-shadow:var(--shadow); }
  .dash-card h3 { font-size:15px; font-weight:700; margin-bottom:20px; display:flex; align-items:center; gap:8px; }

  /* bar chart */
  .bar-chart { display:flex; flex-direction:column; gap:14px; }
  .bar-row { display:flex; align-items:center; gap:12px; }
  .bar-label { width:130px; font-size:13px; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
  .bar-track { flex:1; background:var(--bg); border-radius:99px; height:12px; overflow:hidden; }
  .bar-fill { height:100%; border-radius:99px; transition:width .6s ease; }
  .bar-count { width:36px; text-align:right; font-size:13px; font-weight:700; color:var(--text); }

  /* donut */
  .donut-wrap { display:flex; align-items:center; gap:24px; flex-wrap:wrap; }
  .donut-legend { display:flex; flex-direction:column; gap:10px; }
  .legend-item { display:flex; align-items:center; gap:8px; font-size:13px; }
  .legend-dot { width:12px; height:12px; border-radius:50%; flex-shrink:0; }

  /* recent list */
  .recent-list { display:flex; flex-direction:column; gap:12px; }
  .recent-item { display:flex; align-items:center; gap:14px; padding:12px; background:var(--bg); border-radius:12px; }
  .recent-thumb { width:44px; height:44px; border-radius:10px; object-fit:cover; background:var(--border); display:flex; align-items:center; justify-content:center; font-size:20px; flex-shrink:0; overflow:hidden; }
  .recent-thumb img { width:100%; height:100%; object-fit:cover; }
  .recent-info { flex:1; min-width:0; }
  .recent-title { font-size:14px; font-weight:600; white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
  .recent-meta { font-size:11px; color:var(--muted); margin-top:3px; }
  .recent-badge { font-size:11px; font-weight:700; padding:3px 10px; border-radius:20px; color:#fff; white-space:nowrap; }

  /* file type breakdown */
  .filetype-row { display:flex; flex-wrap:wrap; gap:12px; }
  .filetype-chip { display:flex; align-items:center; gap:8px; background:var(--bg); border-radius:12px; padding:10px 16px; font-size:13px; }
  .filetype-chip span:first-child { font-size:20px; }
  .filetype-num { font-weight:700; color:var(--primary); }

  /* drive folder tree */
  .folder-tree { display:flex; flex-direction:column; gap:8px; }
  .ftree-root { display:flex; align-items:center; gap:8px; font-weight:700; font-size:14px; padding:10px 14px; background:linear-gradient(135deg,#F3F1FF,#E8F5FF); border-radius:12px; }
  .ftree-sub { display:flex; align-items:center; gap:8px; font-size:13px; padding:9px 14px 9px 32px; background:var(--bg); border-radius:10px; color:var(--text); text-decoration:none; transition:background .2s; }
  .ftree-sub:hover { background:var(--border); }
  .ftree-count { margin-left:auto; background:var(--primary); color:#fff; font-size:11px; font-weight:700; border-radius:99px; padding:2px 10px; }

  /* FILTER BAR */
  .filter-bar { background:var(--card); border-bottom:1px solid var(--border); padding:0 32px; display:flex; gap:4px; overflow-x:auto; }
  .filter-tab { padding:14px 18px; font-size:13px; font-weight:500; cursor:pointer; border:none; background:none; color:var(--muted); white-space:nowrap; border-bottom:3px solid transparent; transition:color .2s,border-color .2s; }
  .filter-tab.active { color:var(--primary); border-bottom-color:var(--primary); font-weight:700; }

  /* PORTFOLIO GRID */
  .portfolio-grid { display:grid; grid-template-columns:repeat(auto-fill,minmax(290px,1fr)); gap:20px; }
  .portfolio-card { background:var(--card); border-radius:var(--radius); overflow:hidden; box-shadow:var(--shadow); transition:transform .2s,box-shadow .2s; cursor:pointer; }
  .portfolio-card:hover { transform:translateY(-4px); box-shadow:0 12px 32px rgba(0,0,0,.12); }
  .card-thumb { height:170px; background:var(--bg); position:relative; overflow:hidden; display:flex; align-items:center; justify-content:center; }
  .card-thumb img { width:100%; height:100%; object-fit:cover; }
  .card-thumb .no-img { font-size:52px; opacity:.3; }
  .cat-badge { position:absolute; top:12px; left:12px; border-radius:20px; padding:4px 12px; font-size:11px; font-weight:700; color:#fff; }
  .card-body { padding:16px; }
  .card-title { font-size:15px; font-weight:700; margin-bottom:5px; line-height:1.4; }
  .card-meta { font-size:11px; color:var(--muted); display:flex; gap:10px; align-items:center; flex-wrap:wrap; }
  .card-folder { font-size:11px; color:var(--muted); margin-top:4px; }
  .card-desc { font-size:12px; color:var(--muted); margin-top:6px; line-height:1.5; display:-webkit-box; -webkit-line-clamp:2; -webkit-box-orient:vertical; overflow:hidden; }
  .card-actions { display:flex; gap:8px; margin-top:12px; }
  .btn-icon { background:var(--bg); border:1px solid var(--border); border-radius:8px; padding:6px 10px; font-size:12px; cursor:pointer; transition:background .2s; }
  .btn-icon:hover { background:var(--border); }
  .cat-art { background:var(--art); } .cat-academic { background:var(--academic); }
  .cat-activity { background:#E6B800; } .cat-sport { background:var(--sport); }
  .empty-state { text-align:center; padding:80px 24px; color:var(--muted); grid-column:1/-1; }
  .empty-state .empty-icon { font-size:64px; margin-bottom:16px; }
  .empty-state h3 { font-size:18px; color:var(--text); margin-bottom:8px; }

  /* section header */
  .section-header { display:flex; align-items:center; justify-content:space-between; margin-bottom:20px; }
  .section-header h2 { font-size:18px; font-weight:700; }
  .btn-add { background:linear-gradient(135deg,var(--accent),#2DD4BF); color:#fff; border:none; border-radius:10px; padding:12px 20px; font-size:13px; font-weight:600; cursor:pointer; display:flex; align-items:center; gap:8px; transition:opacity .2s,transform .1s; }
  .btn-add:hover { opacity:.9; transform:translateY(-1px); }

  /* MODAL */
  .modal-overlay { display:none; position:fixed; inset:0; background:rgba(0,0,0,.5); z-index:200; align-items:center; justify-content:center; padding:24px; }
  .modal-overlay.open { display:flex; }
  .modal { background:var(--card); border-radius:24px; padding:36px; width:100%; max-width:560px; max-height:90vh; overflow-y:auto; box-shadow:0 20px 60px rgba(0,0,0,.2); }
  .modal h2 { font-size:20px; font-weight:700; margin-bottom:24px; }
  .form-group { margin-bottom:18px; }
  .form-group label { display:block; font-size:13px; font-weight:600; color:var(--muted); margin-bottom:7px; }
  .form-group input,.form-group select,.form-group textarea { width:100%; padding:12px 14px; border:2px solid var(--border); border-radius:10px; font-size:14px; font-family:inherit; transition:border-color .2s; }
  .form-group input:focus,.form-group select:focus,.form-group textarea:focus { outline:none; border-color:var(--primary); }
  .form-group textarea { resize:vertical; min-height:80px; }
  .drive-picker-area { border:2px dashed var(--border); border-radius:12px; padding:24px; text-align:center; cursor:pointer; transition:border-color .2s,background .2s; }
  .drive-picker-area:hover { border-color:var(--primary); background:#F3F1FF; }
  .drive-picker-area .icon { font-size:32px; margin-bottom:8px; }
  .file-list { margin-top:10px; display:flex; flex-direction:column; gap:8px; }
  .file-item { background:var(--bg); border-radius:8px; padding:10px 14px; display:flex; align-items:center; gap:10px; font-size:13px; }
  .file-item .file-name { flex:1; overflow:hidden; text-overflow:ellipsis; white-space:nowrap; }
  .file-item .remove-file { cursor:pointer; color:var(--muted); }
  .file-item .remove-file:hover { color:var(--secondary); }
  .modal-actions { display:flex; gap:12px; margin-top:24px; }
  .btn-cancel { flex:1; padding:13px; border:2px solid var(--border); border-radius:10px; background:none; font-size:14px; font-weight:600; cursor:pointer; }
  .btn-cancel:hover { background:var(--bg); }
  .btn-save { flex:2; padding:13px; background:linear-gradient(135deg,var(--primary),#8B5CF6); color:#fff; border:none; border-radius:10px; font-size:14px; font-weight:600; cursor:pointer; }
  .btn-save:hover { opacity:.9; }
  .detail-modal { max-width:680px; }
  .detail-hero { border-radius:14px; overflow:hidden; margin-bottom:24px; max-height:300px; }
  .detail-hero img { width:100%; object-fit:cover; }
  .detail-hero .no-hero { background:var(--bg); height:140px; display:flex; align-items:center; justify-content:center; font-size:64px; }
  .detail-title { font-size:22px; font-weight:700; margin-bottom:10px; }
  .detail-meta { display:flex; gap:14px; margin-bottom:14px; flex-wrap:wrap; }
  .detail-badge { display:flex; align-items:center; gap:6px; font-size:13px; color:var(--muted); }
  .detail-desc { font-size:14px; line-height:1.7; margin-bottom:18px; }
  .detail-files h4 { font-size:14px; font-weight:700; margin-bottom:10px; }
  .detail-file-link { display:flex; align-items:center; gap:10px; padding:10px 14px; background:var(--bg); border-radius:10px; margin-bottom:8px; text-decoration:none; color:var(--text); transition:background .2s; }
  .detail-file-link:hover { background:#EEEAFF; }

  /* saving overlay */
  .saving-overlay { display:none; position:fixed; inset:0; z-index:300; background:rgba(0,0,0,.45); align-items:center; justify-content:center; }
  .saving-overlay.open { display:flex; }
  .saving-box { background:#fff; border-radius:20px; padding:40px 48px; text-align:center; box-shadow:0 20px 60px rgba(0,0,0,.2); }
  .saving-box .spin { font-size:48px; animation:spin 1s linear infinite; display:inline-block; }
  @keyframes spin { to { transform:rotate(360deg); } }
  .saving-box p { margin-top:16px; font-size:15px; font-weight:600; }
  .saving-box small { font-size:12px; color:var(--muted); }

  #toast { position:fixed; bottom:32px; left:50%; transform:translateX(-50%) translateY(80px); background:#1E1E2E; color:#fff; border-radius:10px; padding:14px 24px; font-size:14px; z-index:500; transition:transform .3s; display:flex; align-items:center; gap:10px; min-width:280px; justify-content:center; }
  #toast.show { transform:translateX(-50%) translateY(0); }

  @media(max-width:600px){
    .app-header { padding:16px; } .page { padding:20px 16px; }
    .nav-bar { padding:0 16px; } .filter-bar { padding:0 16px; }
    .portfolio-grid { grid-template-columns:1fr; } .kpi-row { grid-template-columns:1fr 1fr; }
    .dash-grid { grid-template-columns:1fr; }
  }
</style>

<!-- SETUP -->
<div id="setupScreen">
  <div class="setup-card">
    <div class="logo">🎓</div>
    <h1>Portfolio ลูกสาว</h1>
    <p>แอปเก็บผลงานเชื่อมต่อ Google Drive<br>ใส่ข้อมูล Google API ครั้งแรกเพื่อเริ่มใช้งาน</p>
    <div style="text-align:left">
      <label>🔑 Google OAuth Client ID</label>
      <input type="text" id="inputClientId" placeholder="xxxx.apps.googleusercontent.com"/>
      <label>🗝️ Google API Key</label>
      <input type="text" id="inputApiKey" placeholder="AIzaSy..."/>
    </div>
    <button class="btn-primary" onclick="setupAndInit()">🚀 เริ่มใช้งาน</button>
    <div class="setup-note">ข้อมูลนี้เก็บใน Browser เท่านั้น ไม่ได้ส่งออกไปที่ใด</div>
  </div>
</div>

<!-- MAIN APP -->
<div id="mainApp">
  <div class="app-header">
    <div class="header-left">
      <div class="logo">🎓</div>
      <div><h1>Portfolio ลูกสาว</h1><p>ผลงานและความสำเร็จ</p></div>
    </div>
    <div class="header-right">
      <div class="user-pill">
        <div class="google-avatar" id="userAvatar">👤</div>
        <span id="userName">ยังไม่ได้เข้าสู่ระบบ</span>
      </div>
      <button class="btn-sm" id="signInBtn" onclick="handleSignIn()">🔐 Sign In</button>
      <button class="btn-sm" onclick="resetSetup()" title="ตั้งค่า">⚙️</button>
    </div>
  </div>

  <!-- NAV -->
  <div class="nav-bar">
    <button class="nav-tab active" data-page="dashboard" onclick="switchPage(this)">📊 Dashboard</button>
    <button class="nav-tab" data-page="portfolio" onclick="switchPage(this)">🗂️ ผลงานทั้งหมด</button>
  </div>

  <!-- ══ DASHBOARD PAGE ══ -->
  <div class="page active" id="page-dashboard">
    <div class="dash-refresh">
      <h2>📊 Dashboard ภาพรวมผลงาน</h2>
      <button class="btn-refresh" id="refreshBtn" onclick="loadDashboard()">
        <span class="icon">🔄</span> รีเฟรชจาก Drive
      </button>
    </div>

    <!-- KPI -->
    <div class="kpi-row" id="kpiRow">
      <div class="kpi-card"><div class="kpi-emoji">✨</div><div class="kpi-val" id="kTotal">–</div><div class="kpi-lbl">ผลงานทั้งหมด</div></div>
      <div class="kpi-card"><div class="kpi-emoji">🎨</div><div class="kpi-val" id="kArt">–</div><div class="kpi-lbl">ศิลปะ</div></div>
      <div class="kpi-card"><div class="kpi-emoji">📚</div><div class="kpi-val" id="kAcademic">–</div><div class="kpi-lbl">วิชาการ</div></div>
      <div class="kpi-card"><div class="kpi-emoji">🎭</div><div class="kpi-val" id="kActivity">–</div><div class="kpi-lbl">กิจกรรม</div></div>
      <div class="kpi-card"><div class="kpi-emoji">🏆</div><div class="kpi-val" id="kSport">–</div><div class="kpi-lbl">กีฬา</div></div>
      <div class="kpi-card"><div class="kpi-emoji">📎</div><div class="kpi-val" id="kFiles">–</div><div class="kpi-lbl">ไฟล์ทั้งหมด</div></div>
    </div>

    <div class="dash-grid">
      <!-- ผลงานแต่ละหมวด bar -->
      <div class="dash-card">
        <h3>📈 ผลงานแต่ละหมวด</h3>
        <div class="bar-chart" id="barChart"></div>
      </div>

      <!-- donut -->
      <div class="dash-card">
        <h3>🥧 สัดส่วนผลงาน</h3>
        <div class="donut-wrap">
          <canvas id="donutCanvas" width="140" height="140"></canvas>
          <div class="donut-legend" id="donutLegend"></div>
        </div>
      </div>

      <!-- folder tree จาก Drive -->
      <div class="dash-card">
        <h3>📁 โครงสร้างโฟลเดอร์ใน Drive</h3>
        <div class="folder-tree" id="folderTree">
          <div style="color:var(--muted);font-size:13px;">Sign in เพื่อดูข้อมูล Drive</div>
        </div>
      </div>

      <!-- ประเภทไฟล์ -->
      <div class="dash-card">
        <h3>🗂️ ประเภทไฟล์ที่มี</h3>
        <div class="filetype-row" id="filetypeRow">
          <div style="color:var(--muted);font-size:13px;">ยังไม่มีข้อมูล</div>
        </div>
      </div>
    </div>

    <!-- งานล่าสุด -->
    <div class="dash-card" style="margin-bottom:28px">
      <h3>🕐 ผลงานล่าสุด 5 รายการ</h3>
      <div class="recent-list" id="recentList">
        <div style="color:var(--muted);font-size:13px;padding:12px">ยังไม่มีข้อมูล — กด "รีเฟรชจาก Drive" หลัง Sign In</div>
      </div>
    </div>
  </div>

  <!-- ══ PORTFOLIO PAGE ══ -->
  <div class="page" id="page-portfolio">
    <div class="filter-bar" style="margin:-32px -32px 28px;padding:0 32px;">
      <button class="filter-tab active" data-cat="all" onclick="filterCategory(this)">✨ ทั้งหมด</button>
      <button class="filter-tab" data-cat="art" onclick="filterCategory(this)">🎨 ศิลปะ</button>
      <button class="filter-tab" data-cat="academic" onclick="filterCategory(this)">📚 วิชาการ</button>
      <button class="filter-tab" data-cat="activity" onclick="filterCategory(this)">🎭 กิจกรรม</button>
      <button class="filter-tab" data-cat="sport" onclick="filterCategory(this)">🏆 กีฬา</button>
    </div>
    <div class="section-header">
      <h2 id="sectionTitle">✨ ผลงานทั้งหมด</h2>
      <button class="btn-add" onclick="openAddModal()">➕ เพิ่มผลงาน</button>
    </div>
    <div class="portfolio-grid" id="portfolioGrid"></div>
  </div>
</div>

<!-- ADD/EDIT MODAL -->
<div class="modal-overlay" id="addModal">
  <div class="modal">
    <h2 id="modalTitle">➕ เพิ่มผลงานใหม่</h2>
    <div class="form-group">
      <label>📌 ชื่อผลงาน *</label>
      <input type="text" id="fTitle" placeholder="เช่น รางวัลชนะเลิศวาดภาพระดับจังหวัด"/>
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
        <input type="date" id="fDate"/>
      </div>
    </div>
    <div class="form-group">
      <label>📝 รายละเอียด</label>
      <textarea id="fDesc" placeholder="อธิบายผลงาน ที่มา หรือความภาคภูมิใจ..."></textarea>
    </div>
    <div class="form-group">
      <label>📁 แนบไฟล์จาก Google Drive</label>
      <div class="drive-picker-area" onclick="openDrivePicker()">
        <div class="icon">☁️</div>
        <p><strong>คลิกเพื่อเลือกไฟล์จาก Google Drive</strong></p>
        <p style="font-size:11px;color:var(--muted);margin-top:4px">รองรับรูปภาพ, PDF, Word และอื่นๆ</p>
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

<!-- SAVING OVERLAY -->
<div class="saving-overlay" id="savingOverlay">
  <div class="saving-box">
    <div class="spin">⚙️</div>
    <p id="savingMsg">กำลังจัดโฟลเดอร์...</p>
    <small id="savingDetail"> </small>
  </div>
</div>

<div id="toast"></div>

<script>
// ══════════════════════════════════════════
// CONFIG & GLOBALS
// ══════════════════════════════════════════
const SCOPES = 'https://www.googleapis.com/auth/drive.file https://www.googleapis.com/auth/drive.readonly';
const DISCOVERY_DOCS = ['https://www.googleapis.com/discovery/v1/apis/drive/v3/rest'];
const ROOT_FOLDER_NAME = 'Portfolio_ลูกสาว';
const DB_KEY = 'portfolio_items';
const CONFIG_KEY = 'portfolio_config';

let gapi_loaded = false, gis_loaded = false;
let tokenClient = null, accessToken = null;
let folderIds = {}; // { root, art, academic, activity, sport }
let selectedFiles = [], currentFilter = 'all', editingId = null;
let CLIENT_ID = '', API_KEY = '';

const catMeta = {
  art:      { label:'🎨 ศิลปะ / วาดรูป',   folderName:'🎨 ศิลปะ_วาดรูป',     cls:'cat-art',      icon:'🎨', color:'#FF6B6B' },
  academic: { label:'📚 วิชาการ / รางวัล',   folderName:'📚 วิชาการ_รางวัล',     cls:'cat-academic', icon:'📚', color:'#4ECDC4' },
  activity: { label:'🎭 กิจกรรม / การแสดง', folderName:'🎭 กิจกรรม_การแสดง',   cls:'cat-activity', icon:'🎭', color:'#E6B800' },
  sport:    { label:'🏆 กีฬา / ความสำเร็จ', folderName:'🏆 กีฬา_ความสำเร็จ',   cls:'cat-sport',    icon:'🏆', color:'#6C63FF' },
};

// ══════════════════════════════════════════
// SETUP
// ══════════════════════════════════════════
function setupAndInit() {
  const cid = document.getElementById('inputClientId').value.trim();
  const akey = document.getElementById('inputApiKey').value.trim();
  if (!cid || !akey) { showToast('⚠️ กรุณากรอก Client ID และ API Key', true); return; }
  CLIENT_ID = cid; API_KEY = akey;
  localStorage.setItem(CONFIG_KEY, JSON.stringify({ CLIENT_ID, API_KEY }));
  startApp();
}
function resetSetup() {
  if (!confirm('ต้องการเปลี่ยนการตั้งค่า API?')) return;
  localStorage.removeItem(CONFIG_KEY);
  location.reload();
}
function startApp() {
  document.getElementById('setupScreen').style.display = 'none';
  document.getElementById('mainApp').style.display = 'block';
  loadGoogleAPIs();
  renderGrid();
  renderDashboardLocal(); // show local data first
}

// ══════════════════════════════════════════
// PAGE NAVIGATION
// ══════════════════════════════════════════
function switchPage(btn) {
  document.querySelectorAll('.nav-tab').forEach(t => t.classList.remove('active'));
  btn.classList.add('active');
  const page = btn.dataset.page;
  document.querySelectorAll('.page').forEach(p => p.classList.remove('active'));
  document.getElementById('page-' + page).classList.add('active');
  if (page === 'dashboard') loadDashboard();
}

// ══════════════════════════════════════════
// LOCAL DB
// ══════════════════════════════════════════
function getItems() { return JSON.parse(localStorage.getItem(DB_KEY) || '[]'); }
function saveItems(items) { localStorage.setItem(DB_KEY, JSON.stringify(items)); }

// ══════════════════════════════════════════
// GOOGLE APIs
// ══════════════════════════════════════════
function loadGoogleAPIs() {
  const s1 = document.createElement('script');
  s1.src = 'https://apis.google.com/js/api.js';
  s1.onload = () => {
    gapi.load('client:picker', () => {
      gapi.client.init({ apiKey: API_KEY, discoveryDocs: DISCOVERY_DOCS })
        .then(() => { gapi_loaded = true; tryAutoSignIn(); })
        .catch(e => showToast('❌ API Key ไม่ถูกต้อง: ' + e.message, true));
    });
  };
  document.body.appendChild(s1);

  const s2 = document.createElement('script');
  s2.src = 'https://accounts.google.com/gsi/client';
  s2.onload = () => {
    tokenClient = google.accounts.oauth2.initTokenClient({
      client_id: CLIENT_ID, scope: SCOPES, callback: handleTokenResponse,
    });
    gis_loaded = true; tryAutoSignIn();
  };
  document.body.appendChild(s2);
}
function tryAutoSignIn() {
  const saved = sessionStorage.getItem('gToken');
  if (saved && gapi_loaded && gis_loaded) {
    accessToken = saved;
    gapi.client.setToken({ access_token: accessToken });
    fetchUserInfo();
    ensureAllFolders().then(() => loadDashboard());
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
  ensureAllFolders().then(() => loadDashboard());
}
function fetchUserInfo() {
  fetch('https://www.googleapis.com/oauth2/v3/userinfo', {
    headers: { Authorization: 'Bearer ' + accessToken }
  }).then(r => r.json()).then(info => {
    document.getElementById('userName').textContent = info.name || info.email;
    if (info.picture) document.getElementById('userAvatar').innerHTML =
      `<img src="${info.picture}" style="width:28px;height:28px;border-radius:50%">`;
    document.getElementById('signInBtn').textContent = '✅ เชื่อมต่อแล้ว';
    document.getElementById('signInBtn').style.background = 'rgba(67,197,158,.35)';
    showToast('✅ เข้าสู่ระบบสำเร็จ');
  }).catch(() => {});
}

// ══════════════════════════════════════════
// FOLDER MANAGEMENT
// ══════════════════════════════════════════
async function ensureFolder(name, parentId) {
  const parentQ = parentId ? ` and '${parentId}' in parents` : '';
  const res = await gapi.client.drive.files.list({
    q: `name='${name}' and mimeType='application/vnd.google-apps.folder' and trashed=false${parentQ}`,
    fields: 'files(id,name)', spaces: 'drive',
  });
  if (res.result.files.length > 0) return res.result.files[0].id;
  const body = { name, mimeType: 'application/vnd.google-apps.folder' };
  if (parentId) body.parents = [parentId];
  const created = await gapi.client.drive.files.create({ resource: body, fields: 'id' });
  return created.result.id;
}

async function ensureAllFolders() {
  try {
    folderIds.root = await ensureFolder(ROOT_FOLDER_NAME, null);
    for (const [key, meta] of Object.entries(catMeta)) {
      folderIds[key] = await ensureFolder(meta.folderName, folderIds.root);
    }
  } catch(e) { console.error('Folder setup error:', e); }
}

// สร้าง subfolder ตามชื่องาน แล้วย้ายไฟล์เข้าไป
async function ensureJobFolder(jobTitle, catKey) {
  if (!folderIds[catKey]) return null;
  // sanitize folder name
  const safeName = jobTitle.replace(/[/\\?%*:|"<>]/g, '_').substring(0, 80);
  const jobFolderId = await ensureFolder(safeName, folderIds[catKey]);
  return jobFolderId;
}

async function moveFilesToFolder(files, targetFolderId) {
  for (const f of files) {
    try {
      const meta = await gapi.client.drive.files.get({ fileId: f.id, fields: 'parents' });
      const prevParents = (meta.result.parents || []).join(',');
      await gapi.client.drive.files.update({
        fileId: f.id,
        addParents: targetFolderId,
        removeParents: prevParents,
        fields: 'id,parents',
      });
    } catch(e) { console.warn('Could not move file', f.name, e); }
  }
}

// ══════════════════════════════════════════
// GOOGLE PICKER
// ══════════════════════════════════════════
function openDrivePicker() {
  if (!accessToken) { showToast('⚠️ กรุณา Sign In ก่อนครับ', true); return; }
  const picker = new google.picker.PickerBuilder()
    .setOAuthToken(accessToken).setDeveloperKey(API_KEY)
    .addView(new google.picker.DocsView().setIncludeFolders(false))
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
      if (!selectedFiles.find(f => f.id === doc.id))
        selectedFiles.push({ id:doc.id, name:doc.name, mimeType:doc.mimeType,
          webViewLink:doc.url, thumbnailLink:doc.iconUrl });
    });
    renderFileList();
  }
}
function renderFileList() {
  const el = document.getElementById('fileList');
  if (!selectedFiles.length) { el.innerHTML = ''; return; }
  el.innerHTML = selectedFiles.map((f,i) => `
    <div class="file-item">
      <span>${getFileIcon(f.mimeType)}</span>
      <span class="file-name">${f.name}</span>
      <span class="remove-file" onclick="removeFile(${i})">✕</span>
    </div>`).join('');
}
function removeFile(i) { selectedFiles.splice(i,1); renderFileList(); }
function getFileIcon(mime) {
  if (!mime) return '📎';
  if (mime.startsWith('image/')) return '🖼️';
  if (mime === 'application/pdf') return '📄';
  if (mime.includes('word')) return '📝';
  if (mime.includes('spreadsheet')||mime.includes('excel')) return '📊';
  if (mime.includes('presentation')||mime.includes('powerpoint')) return '📑';
  if (mime.startsWith('video/')) return '🎬';
  if (mime.startsWith('audio/')) return '🎵';
  return '📎';
}

// ══════════════════════════════════════════
// SAVE PORTFOLIO (สร้าง folder ตามชื่องาน)
// ══════════════════════════════════════════
async function savePortfolio() {
  const title = document.getElementById('fTitle').value.trim();
  if (!title) { showToast('⚠️ กรุณากรอกชื่อผลงาน', true); return; }
  const catKey  = document.getElementById('fCat').value;
  const catInfo = catMeta[catKey];
  const items   = getItems();

  let jobFolderId   = null;
  let jobFolderName = null;

  // สร้าง/ย้ายไฟล์เข้า folder ชื่องาน
  if (accessToken && folderIds[catKey]) {
    setSavingOverlay(true, `📁 กำลังสร้างโฟลเดอร์ "${title}"...`, `ใน ${catInfo.folderName}`);
    jobFolderId   = await ensureJobFolder(title, catKey);
    jobFolderName = title.substring(0, 80);
    if (selectedFiles.length && jobFolderId) {
      setSavingOverlay(true, `📎 กำลังย้ายไฟล์เข้า "${title}"...`, `${selectedFiles.length} ไฟล์`);
      await moveFilesToFolder(selectedFiles, jobFolderId);
    }
    setSavingOverlay(false);
  }

  const item = {
    id: editingId || Date.now().toString(),
    title, cat: catKey,
    date: document.getElementById('fDate').value,
    desc: document.getElementById('fDesc').value.trim(),
    files: [...selectedFiles],
    catFolderName:  catInfo.folderName,
    jobFolderName,
    jobFolderId,
    createdAt: editingId
      ? (items.find(x => x.id === editingId)?.createdAt || Date.now())
      : Date.now(),
  };

  if (editingId) {
    const idx = items.findIndex(x => x.id === editingId);
    if (idx !== -1) items[idx] = item;
  } else { items.unshift(item); }
  saveItems(items);
  closeModal('addModal');
  renderGrid();
  renderDashboardLocal();
  showToast(editingId ? '✅ แก้ไขผลงานแล้ว' : `🎉 บันทึกลง "${catInfo.folderName} / ${title}" แล้ว!`);
  editingId = null; selectedFiles = [];
}

function setSavingOverlay(show, msg='', detail='') {
  document.getElementById('savingOverlay').classList.toggle('open', show);
  if (show) {
    document.getElementById('savingMsg').textContent = msg;
    document.getElementById('savingDetail').textContent = detail;
  }
}

// ══════════════════════════════════════════
// DASHBOARD
// ══════════════════════════════════════════
function renderDashboardLocal() {
  const items = getItems();
  const counts = { art:0, academic:0, activity:0, sport:0 };
  let totalFiles = 0;
  items.forEach(it => { counts[it.cat] = (counts[it.cat]||0)+1; totalFiles += (it.files?.length||0); });

  document.getElementById('kTotal').textContent    = items.length;
  document.getElementById('kArt').textContent      = counts.art;
  document.getElementById('kAcademic').textContent = counts.academic;
  document.getElementById('kActivity').textContent = counts.activity;
  document.getElementById('kSport').textContent    = counts.sport;
  document.getElementById('kFiles').textContent    = totalFiles;

  renderBarChart(counts, items.length);
  renderDonut(counts);
  renderRecentList(items);
  renderFileTypes(items);
}

async function loadDashboard() {
  renderDashboardLocal(); // always render local first
  if (!accessToken) return;

  // set refresh btn spinning
  const btn = document.getElementById('refreshBtn');
  btn.classList.add('spinning');
  btn.disabled = true;

  try {
    await renderFolderTree();
  } catch(e) { console.warn('Dashboard Drive fetch error', e); }

  btn.classList.remove('spinning');
  btn.disabled = false;
}

function renderBarChart(counts, total) {
  const el = document.getElementById('barChart');
  const cats = Object.entries(catMeta);
  const max  = Math.max(...cats.map(([k]) => counts[k]||0), 1);
  el.innerHTML = cats.map(([key, meta]) => {
    const n = counts[key] || 0;
    const pct = Math.round((n / max) * 100);
    return `
      <div class="bar-row">
        <div class="bar-label" title="${meta.label}">${meta.icon} ${meta.label.split('/')[0].trim()}</div>
        <div class="bar-track"><div class="bar-fill" style="width:${pct}%;background:${meta.color}"></div></div>
        <div class="bar-count">${n}</div>
      </div>`;
  }).join('');
}

function renderDonut(counts) {
  const canvas = document.getElementById('donutCanvas');
  const ctx    = canvas.getContext('2d');
  const cats   = Object.entries(catMeta);
  const total  = cats.reduce((s,[k]) => s + (counts[k]||0), 0) || 1;
  const data   = cats.map(([k,m]) => ({ val: counts[k]||0, color: m.color, label: m.label, icon: m.icon }));

  ctx.clearRect(0,0,140,140);
  let startAngle = -Math.PI/2;
  const cx=70, cy=70, r=60, ir=36;

  data.forEach(d => {
    const slice = (d.val/total) * Math.PI * 2;
    ctx.beginPath();
    ctx.moveTo(cx,cy);
    ctx.arc(cx,cy,r,startAngle,startAngle+slice);
    ctx.closePath();
    ctx.fillStyle = d.color;
    ctx.fill();
    startAngle += slice;
  });
  // donut hole
  ctx.beginPath();
  ctx.arc(cx,cy,ir,0,Math.PI*2);
  ctx.fillStyle = '#fff';
  ctx.fill();
  // center text
  ctx.fillStyle = '#2D2D3A';
  ctx.font = 'bold 18px Segoe UI';
  ctx.textAlign = 'center';
  ctx.textBaseline = 'middle';
  ctx.fillText(total, cx, cy-6);
  ctx.font = '11px Segoe UI';
  ctx.fillStyle = '#888';
  ctx.fillText('ผลงาน', cx, cy+10);

  document.getElementById('donutLegend').innerHTML = data.map(d => `
    <div class="legend-item">
      <div class="legend-dot" style="background:${d.color}"></div>
      <span>${d.icon} ${d.label.split('/')[0].trim()} <strong>(${d.val})</strong></span>
    </div>`).join('');
}

function renderRecentList(items) {
  const el = document.getElementById('recentList');
  const recent = [...items].sort((a,b) => b.createdAt - a.createdAt).slice(0,5);
  if (!recent.length) { el.innerHTML = '<div style="color:var(--muted);font-size:13px;padding:12px">ยังไม่มีผลงาน</div>'; return; }
  el.innerHTML = recent.map(item => {
    const meta    = catMeta[item.cat] || catMeta.art;
    const imgFile = item.files?.find(f => f.mimeType?.startsWith('image/'));
    const thumb   = imgFile
      ? `<img src="https://drive.google.com/thumbnail?id=${imgFile.id}&sz=w100" alt="">`
      : meta.icon;
    const dateStr = item.date ? formatDate(item.date) : '–';
    return `
      <div class="recent-item">
        <div class="recent-thumb">${thumb}</div>
        <div class="recent-info">
          <div class="recent-title">${item.title}</div>
          <div class="recent-meta">📅 ${dateStr} &nbsp;·&nbsp; 📎 ${item.files?.length||0} ไฟล์
            ${item.jobFolderName ? ` &nbsp;·&nbsp; 📁 ${item.jobFolderName}` : ''}</div>
        </div>
        <span class="recent-badge ${meta.cls}">${meta.icon}</span>
      </div>`;
  }).join('');
}

function renderFileTypes(items) {
  const el = document.getElementById('filetypeRow');
  const tally = {};
  items.forEach(it => (it.files||[]).forEach(f => {
    const icon = getFileIcon(f.mimeType);
    tally[icon] = (tally[icon]||0) + 1;
  }));
  if (!Object.keys(tally).length) {
    el.innerHTML = '<div style="color:var(--muted);font-size:13px">ยังไม่มีไฟล์แนบ</div>'; return;
  }
  const typeLabel = { '🖼️':'รูปภาพ','📄':'PDF','📝':'Word','📊':'Excel','📑':'PPT','🎬':'วิดีโอ','🎵':'เสียง','📎':'อื่นๆ' };
  el.innerHTML = Object.entries(tally).map(([icon,n]) => `
    <div class="filetype-chip">
      <span>${icon}</span>
      <div>
        <div style="font-size:11px;color:var(--muted)">${typeLabel[icon]||'ไฟล์'}</div>
        <div class="filetype-num">${n} ไฟล์</div>
      </div>
    </div>`).join('');
}

// ── ดึง folder tree จาก Drive จริง ──
async function renderFolderTree() {
  const treeEl = document.getElementById('folderTree');
  if (!folderIds.root) { treeEl.innerHTML = '<div style="color:var(--muted);font-size:13px">ยังไม่ได้ Sign In</div>'; return; }

  treeEl.innerHTML = '<div style="color:var(--muted);font-size:12px">กำลังโหลดจาก Drive...</div>';

  // ดึง subfolder ภายใต้ root
  const subRes = await gapi.client.drive.files.list({
    q: `'${folderIds.root}' in parents and mimeType='application/vnd.google-apps.folder' and trashed=false`,
    fields: 'files(id,name,webViewLink)', orderBy: 'name', spaces: 'drive',
  });
  const catFolders = subRes.result.files || [];

  // สำหรับแต่ละ category folder → ดึง job folder ข้างใน
  let html = `<div class="ftree-root">📁 ${ROOT_FOLDER_NAME}</div>`;
  for (const cf of catFolders) {
    const jobRes = await gapi.client.drive.files.list({
      q: `'${cf.id}' in parents and mimeType='application/vnd.google-apps.folder' and trashed=false`,
      fields: 'files(id,name,webViewLink)', orderBy: 'name', spaces: 'drive',
    });
    const jobs = jobRes.result.files || [];
    html += `
      <a class="ftree-sub" href="${cf.webViewLink||'#'}" target="_blank" style="font-weight:700;padding-left:16px">
        ${cf.name}
        <span class="ftree-count">${jobs.length}</span>
      </a>`;
    jobs.forEach(j => {
      html += `
        <a class="ftree-sub" href="${j.webViewLink||'#'}" target="_blank" style="padding-left:44px">
          📂 ${j.name}
        </a>`;
    });
  }
  if (!catFolders.length) html += '<div style="color:var(--muted);font-size:12px;padding:8px 14px">ยังไม่มีโฟลเดอร์ใน Drive</div>';
  treeEl.innerHTML = html;

  // อัปเดต KPI จาก Drive จริง (นับ job folders)
  let driveTotal = 0;
  catFolders.forEach(async cf => {
    const jobRes = await gapi.client.drive.files.list({
      q: `'${cf.id}' in parents and mimeType='application/vnd.google-apps.folder' and trashed=false`,
      fields: 'files(id)', spaces: 'drive',
    });
    driveTotal += (jobRes.result.files||[]).length;
  });
}

// ══════════════════════════════════════════
// PORTFOLIO GRID
// ══════════════════════════════════════════
function openAddModal(id=null) {
  editingId=id; selectedFiles=[];
  if (id) {
    const item = getItems().find(x=>x.id===id); if (!item) return;
    document.getElementById('modalTitle').textContent = '✏️ แก้ไขผลงาน';
    document.getElementById('fTitle').value = item.title;
    document.getElementById('fCat').value   = item.cat;
    document.getElementById('fDate').value  = item.date||'';
    document.getElementById('fDesc').value  = item.desc||'';
    selectedFiles = item.files ? [...item.files] : [];
  } else {
    document.getElementById('modalTitle').textContent = '➕ เพิ่มผลงานใหม่';
    document.getElementById('fTitle').value = '';
    document.getElementById('fCat').value   = 'art';
    document.getElementById('fDate').value  = new Date().toISOString().split('T')[0];
    document.getElementById('fDesc').value  = '';
  }
  renderFileList();
  document.getElementById('addModal').classList.add('open');
}
function closeModal(id) { document.getElementById(id).classList.remove('open'); }

function deleteItem(id) {
  if (!confirm('ต้องการลบผลงานนี้?')) return;
  saveItems(getItems().filter(x=>x.id!==id));
  closeModal('detailModal');
  renderGrid(); renderDashboardLocal();
  showToast('🗑️ ลบผลงานแล้ว');
}

function openDetail(id) {
  const item = getItems().find(x=>x.id===id); if (!item) return;
  const meta    = catMeta[item.cat]||catMeta.art;
  const imgFile = item.files?.find(f=>f.mimeType?.startsWith('image/'));
  const heroSrc = imgFile ? `https://drive.google.com/thumbnail?id=${imgFile.id}&sz=w800` : null;
  const filesHtml = item.files?.length ? `
    <div class="detail-files"><h4>📎 ไฟล์แนบ (${item.files.length} ไฟล์)</h4>
      ${item.files.map(f=>`
        <a class="detail-file-link" href="${f.webViewLink}" target="_blank">
          <span>${getFileIcon(f.mimeType)}</span><span style="flex:1">${f.name}</span>
          <span style="font-size:11px;color:var(--muted)">เปิดใน Drive ↗</span>
        </a>`).join('')}
    </div>` : '';

  const pathHtml = item.jobFolderName
    ? `<div class="detail-badge">📁 ${item.catFolderName||''} / ${item.jobFolderName}</div>` : '';

  document.getElementById('detailContent').innerHTML = `
    <div style="display:flex;align-items:center;justify-content:space-between;margin-bottom:20px">
      <span class="cat-badge ${meta.cls}" style="position:static;font-size:13px;padding:6px 14px;border-radius:20px">${meta.label}</span>
      <button onclick="closeModal('detailModal')" style="background:none;border:none;font-size:22px;cursor:pointer;color:var(--muted)">✕</button>
    </div>
    ${heroSrc
      ? `<div class="detail-hero"><img src="${heroSrc}" alt="${item.title}" onerror="this.parentElement.innerHTML='<div class=no-hero>${meta.icon}</div>'"></div>`
      : `<div class="detail-hero"><div class="no-hero">${meta.icon}</div></div>`}
    <div class="detail-title">${item.title}</div>
    <div class="detail-meta">
      ${item.date ? `<div class="detail-badge">📅 ${formatDate(item.date)}</div>` : ''}
      ${item.files?.length ? `<div class="detail-badge">📎 ${item.files.length} ไฟล์</div>` : ''}
      ${pathHtml}
    </div>
    ${item.desc ? `<div class="detail-desc">${item.desc.replace(/\n/g,'<br>')}</div>` : ''}
    ${filesHtml}
    <div style="display:flex;gap:10px;margin-top:24px">
      <button class="btn-cancel" style="flex:1" onclick="closeModal('detailModal');openAddModal('${item.id}')">✏️ แก้ไข</button>
      <button class="btn-cancel" style="flex:1;color:var(--secondary)" onclick="deleteItem('${item.id}')">🗑️ ลบ</button>
    </div>`;
  document.getElementById('detailModal').classList.add('open');
}

function filterCategory(btn) {
  document.querySelectorAll('.filter-tab').forEach(t=>t.classList.remove('active'));
  btn.classList.add('active');
  currentFilter = btn.dataset.cat;
  const titles={all:'✨ ผลงานทั้งหมด',art:'🎨 ศิลปะ / วาดรูป',academic:'📚 วิชาการ / รางวัล',activity:'🎭 กิจกรรม / การแสดง',sport:'🏆 กีฬา / ความสำเร็จ'};
  document.getElementById('sectionTitle').textContent = titles[currentFilter]||'';
  renderGrid();
}

function renderGrid() {
  const items = getItems().filter(x=>currentFilter==='all'||x.cat===currentFilter);
  const grid  = document.getElementById('portfolioGrid');
  if (!items.length) {
    grid.innerHTML=`<div class="empty-state"><div class="empty-icon">📂</div><h3>ยังไม่มีผลงานในหมวดนี้</h3><p>กดปุ่ม "เพิ่มผลงาน" เพื่อเริ่มบันทึก</p></div>`; return;
  }
  grid.innerHTML = items.map(item => {
    const meta    = catMeta[item.cat]||catMeta.art;
    const imgFile = item.files?.find(f=>f.mimeType?.startsWith('image/'));
    const thumbUrl = imgFile ? `https://drive.google.com/thumbnail?id=${imgFile.id}&sz=w400` : null;
    const folderPath = item.jobFolderName ? `<div class="card-folder">📁 ${item.catFolderName||''} / ${item.jobFolderName}</div>` : '';
    return `
      <div class="portfolio-card" onclick="openDetail('${item.id}')">
        <div class="card-thumb">
          ${thumbUrl
            ? `<img src="${thumbUrl}" alt="${item.title}" onerror="this.style.display='none';this.nextElementSibling.style.display='flex'">
               <div class="no-img" style="display:none">${meta.icon}</div>`
            : `<div class="no-img">${meta.icon}</div>`}
          <span class="cat-badge ${meta.cls}">${meta.label}</span>
        </div>
        <div class="card-body">
          <div class="card-title">${item.title}</div>
          <div class="card-meta">
            ${item.date?`<span>📅 ${formatDate(item.date)}</span>`:''}
            ${item.files?.length?`<span>📎 ${item.files.length} ไฟล์</span>`:''}
          </div>
          ${folderPath}
          ${item.desc?`<div class="card-desc">${item.desc}</div>`:''}
          <div class="card-actions">
            <button class="btn-icon" onclick="event.stopPropagation();openAddModal('${item.id}')">✏️ แก้ไข</button>
            <button class="btn-icon" onclick="event.stopPropagation();deleteItem('${item.id}')">🗑️</button>
          </div>
        </div>
      </div>`;
  }).join('');
}

// ══════════════════════════════════════════
// UTILS
// ══════════════════════════════════════════
function formatDate(d) {
  if (!d) return '';
  return new Date(d).toLocaleDateString('th-TH',{year:'numeric',month:'long',day:'numeric'});
}
let toastTimer;
function showToast(msg,isError=false) {
  const t=document.getElementById('toast');
  t.textContent=msg; t.style.background=isError?'#C0392B':'#1E1E2E';
  t.classList.add('show'); clearTimeout(toastTimer);
  toastTimer=setTimeout(()=>t.classList.remove('show'),3500);
}
document.querySelectorAll('.modal-overlay').forEach(el=>{
  el.addEventListener('click',e=>{ if(e.target===el) el.classList.remove('open'); });
});
let resizeTimer;
window.addEventListener('resize',()=>{ clearTimeout(resizeTimer); resizeTimer=setTimeout(renderGrid,150); });

// ══════════════════════════════════════════
// INIT
// ══════════════════════════════════════════
window.addEventListener('load',()=>{
  const cfg=JSON.parse(localStorage.getItem(CONFIG_KEY)||'null');
  if(cfg&&cfg.CLIENT_ID&&cfg.API_KEY){
    CLIENT_ID=cfg.CLIENT_ID; API_KEY=cfg.API_KEY; startApp();
  }
});
</script>
