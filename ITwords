<!DOCTYPE html>
<html lang="ja">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>ビジネス＆ITことば帳</title>
  <style>
    :root {
      --bg: #f7f8fb;
      --card: #ffffff;
      --text: #1f2937;
      --sub: #6b7280;
      --line: #e5e7eb;
      --accent: #2563eb;
      --accent2: #0ea5e9;
      --danger: #dc2626;
      --radius: 16px;
    }

    * {
      box-sizing: border-box;
    }

    body {
      margin: 0;
      font-family: "Hiragino Kaku Gothic ProN", "Yu Gothic", "Meiryo", system-ui, -apple-system, sans-serif;
      background: var(--bg);
      color: var(--text);
      line-height: 1.6;
    }

    .app {
      max-width: 960px;
      margin: 0 auto;
      padding: 16px;
    }

    .page {
      display: none;
    }
    .page.active {
      display: block;
    }

    .hero {
      background: linear-gradient(135deg, #eff6ff 0%, #ecfeff 100%);
      border: 1px solid #dbeafe;
      border-radius: var(--radius);
      padding: 24px 18px;
      text-align: center;
      margin-bottom: 14px;
    }

    .hero h1 {
      margin: 0 0 8px;
      font-size: clamp(1.5rem, 5vw, 2rem);
    }

    .hero p {
      margin: 0;
      color: var(--sub);
      font-size: 0.98rem;
    }

    .button-grid {
      display: grid;
      grid-template-columns: 1fr;
      gap: 12px;
      margin-top: 16px;
    }

    .big-btn {
      border: none;
      border-radius: 14px;
      padding: 16px 14px;
      font-size: 1.05rem;
      font-weight: 700;
      color: #fff;
      cursor: pointer;
      min-height: 52px;
      box-shadow: 0 6px 16px rgba(37, 99, 235, 0.18);
    }

    .btn-basic { background: var(--accent); }
    .btn-it-verb { background: #0f766e; }
    .btn-it-adj { background: #7c3aed; }

    .card {
      background: var(--card);
      border: 1px solid var(--line);
      border-radius: var(--radius);
      padding: 14px;
      margin-top: 12px;
    }

    .page-header {
      display: flex;
      gap: 10px;
      align-items: center;
      justify-content: space-between;
      flex-wrap: wrap;
      margin-bottom: 10px;
    }

    .page-title {
      margin: 0;
      font-size: clamp(1.2rem, 4.5vw, 1.5rem);
    }

    .top-link {
      border: 1px solid var(--line);
      background: #fff;
      border-radius: 10px;
      padding: 8px 12px;
      cursor: pointer;
      font-weight: 600;
    }

    .status {
      font-size: 0.9rem;
      color: var(--sub);
      margin: 4px 0 0;
    }

    .status.error {
      color: var(--danger);
      font-weight: 700;
    }

    .table-wrap {
      overflow-x: auto;
      border: 1px solid var(--line);
      border-radius: 12px;
    }

    table {
      width: 100%;
      border-collapse: collapse;
      min-width: 520px;
      background: #fff;
    }

    thead th {
      position: sticky;
      top: 0;
      background: #f8fafc;
      color: #0f172a;
      z-index: 1;
    }

    th, td {
      text-align: left;
      border-bottom: 1px solid var(--line);
      padding: 10px 12px;
      font-size: 0.95rem;
      white-space: nowrap;
    }

    tbody tr:nth-child(even) {
      background: #fcfcfd;
    }

    .small {
      color: var(--sub);
      font-size: 0.86rem;
      margin-top: 8px;
    }

    @media (min-width: 640px) {
      .button-grid {
        grid-template-columns: repeat(3, 1fr);
      }
      .big-btn {
        min-height: 56px;
      }
    }
  </style>
</head>
<body>
  <main class="app">

    <!-- TOP -->
    <section id="top" class="page active">
      <div class="hero">
        <h1>ビジネス＆ITことば帳</h1>
        <p>基本動詞100・IT動詞100・IT形容詞を見やすく学べるアプリ</p>
      </div>

      <div class="button-grid">
        <button class="big-btn btn-basic" onclick="showPage('basicPage')">基本動詞100</button>
        <button class="big-btn btn-it-verb" onclick="showPage('itVerbPage')">IT動詞100</button>
        <button class="big-btn btn-it-adj" onclick="showPage('itAdjPage')">IT形容詞</button>
      </div>

      <div class="card">
        <p class="status" id="globalStatus">データを読み込み中です...</p>
        <p class="small">※ 列名はスプレッドシートの列名をそのまま表示します。</p>
      </div>
    </section>

    <!-- 基本動詞100 -->
    <section id="basicPage" class="page">
      <div class="card">
        <div class="page-header">
          <h2 class="page-title">基本動詞100</h2>
          <button class="top-link" onclick="showPage('top')">TOPへ戻る</button>
        </div>
        <p class="status" id="basicStatus">読み込み中...</p>
        <div class="table-wrap">
          <table>
            <thead id="basicHead"></thead>
            <tbody id="basicBody"></tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- IT動詞100 -->
    <section id="itVerbPage" class="page">
      <div class="card">
        <div class="page-header">
          <h2 class="page-title">IT動詞100</h2>
          <button class="top-link" onclick="showPage('top')">TOPへ戻る</button>
        </div>
        <p class="status" id="itVerbStatus">読み込み中...</p>
        <div class="table-wrap">
          <table>
            <thead id="itVerbHead"></thead>
            <tbody id="itVerbBody"></tbody>
          </table>
        </div>
      </div>
    </section>

    <!-- IT形容詞 -->
    <section id="itAdjPage" class="page">
      <div class="card">
        <div class="page-header">
          <h2 class="page-title">IT形容詞</h2>
          <button class="top-link" onclick="showPage('top')">TOPへ戻る</button>
        </div>
        <p class="status" id="itAdjStatus">読み込み中...</p>
        <div class="table-wrap">
          <table>
            <thead id="itAdjHead"></thead>
            <tbody id="itAdjBody"></tbody>
          </table>
        </div>
      </div>
    </section>

  </main>

  <script>
    /**
     * スプレッドシートURL（ここにURLを貼り付ける）
     * output=csv の公開URLを使用してください
     */
    const BASIC_VERBS_URL =
      "https://docs.google.com/spreadsheets/d/e/2PACX-1vTDRPlyoBQrG9wzUadhnR8OY9sxuPhkRRpO_WO0BNs-H_f349__5bK5vN6ZYb3U_w/pub?gid=979504695&single=true&output=csv";

    // ★ あなたの「IT動詞100」のCSV公開URLに差し替えてください
    const IT_VERBS_URL =
      "https://docs.google.com/spreadsheets/d/e/2PACX-1vTDRPlyoBQrG9wzUadhnR8OY9sxuPhkRRpO_WO0BNs-H_f349__5bK5vN6ZYb3U_w/pub?gid=1703691449&single=true&output=csv";

    const IT_ADJECTIVES_URL =
      "https://docs.google.com/spreadsheets/d/e/2PACX-1vTDRPlyoBQrG9wzUadhnR8OY9sxuPhkRRpO_WO0BNs-H_f349__5bK5vN6ZYb3U_w/pub?gid=2089928581&single=true&output=csv";

    function showPage(id) {
      document.querySelectorAll(".page").forEach((p) => p.classList.remove("active"));
      document.getElementById(id).classList.add("active");
      window.scrollTo({ top: 0, behavior: "smooth" });
    }

    // CSVパーサ（ダブルクォート対応）
    function parseCSV(text) {
      const rows = [];
      let row = [];
      let cell = "";
      let inQuotes = false;

      for (let i = 0; i < text.length; i++) {
        const ch = text[i];
        const next = text[i + 1];

        if (ch === '"') {
          // エスケープされた ""
          if (inQuotes && next === '"') {
            cell += '"';
            i++;
          } else {
            inQuotes = !inQuotes;
          }
        } else if (ch === "," && !inQuotes) {
          row.push(cell);
          cell = "";
        } else if ((ch === "\n" || ch === "\r") && !inQuotes) {
          if (ch === "\r" && next === "\n") i++;
          row.push(cell);
          cell = "";
          if (row.some((v) => v.trim() !== "")) rows.push(row);
          row = [];
        } else {
          cell += ch;
        }
      }

      // 最終セル
      if (cell.length > 0 || row.length > 0) {
        row.push(cell);
        if (row.some((v) => v.trim() !== "")) rows.push(row);
      }

      return rows;
    }

    async function loadCSV(url) {
      const res = await fetch(url);
      if (!res.ok) throw new Error(`HTTP ${res.status}`);
      const text = await res.text();
      const rows = parseCSV(text);

      if (!rows.length) return { headers: [], data: [] };

      const headers = rows[0].map((h) => h.replace(/^\uFEFF/, "").trim()); // BOM除去
      const data = rows.slice(1);
      return { headers, data };
    }

    function escapeHtml(str) {
      return String(str ?? "")
        .replaceAll("&", "&amp;")
        .replaceAll("<", "&lt;")
        .replaceAll(">", "&gt;")
        .replaceAll('"', "&quot;")
        .replaceAll("'", "&#39;");
    }

    function renderTable(headId, bodyId, headers, rows) {
      const headEl = document.getElementById(headId);
      const bodyEl = document.getElementById(bodyId);

      if (!headers.length) {
        headEl.innerHTML = "";
        bodyEl.innerHTML = `<tr><td>データがありません</td></tr>`;
        return;
      }

      headEl.innerHTML = `<tr>${headers.map((h) => `<th>${escapeHtml(h)}</th>`).join("")}</tr>`;

      bodyEl.innerHTML = rows
        .map((row) => {
          const cells = headers.map((_, idx) => `<td>${escapeHtml(row[idx] ?? "")}</td>`).join("");
          return `<tr>${cells}</tr>`;
        })
        .join("");
    }

    function setStatus(id, text, isError = false) {
      const el = document.getElementById(id);
      el.textContent = text;
      el.classList.toggle("error", isError);
    }

    async function loadAllData() {
      setStatus("globalStatus", "データを読み込み中です...");

      // まず並列で取得
      const [basicRes, itVerbRes, itAdjRes] = await Promise.allSettled([
        loadCSV(BASIC_VERBS_URL),
        loadCSV(IT_VERBS_URL),
        loadCSV(IT_ADJECTIVES_URL),
      ]);

      // 基本動詞
      if (basicRes.status === "fulfilled") {
        renderTable("basicHead", "basicBody", basicRes.value.headers, basicRes.value.data);
        setStatus("basicStatus", `表示中: ${basicRes.value.data.length}件`);
      } else {
        setStatus("basicStatus", `読み込み失敗: ${basicRes.reason.message}`, true);
      }

      // IT動詞
      if (itVerbRes.status === "fulfilled") {
        renderTable("itVerbHead", "itVerbBody", itVerbRes.value.headers, itVerbRes.value.data);
        setStatus("itVerbStatus", `表示中: ${itVerbRes.value.data.length}件`);
      } else {
        setStatus("itVerbStatus", `読み込み失敗: ${itVerbRes.reason.message}`, true);
      }

      // IT形容詞
      if (itAdjRes.status === "fulfilled") {
        renderTable("itAdjHead", "itAdjBody", itAdjRes.value.headers, itAdjRes.value.data);
        setStatus("itAdjStatus", `表示中: ${itAdjRes.value.data.length}件`);
      } else {
        setStatus("itAdjStatus", `読み込み失敗: ${itAdjRes.reason.message}`, true);
      }

      const okCount = [basicRes, itVerbRes, itAdjRes].filter((r) => r.status === "fulfilled").length;
      if (okCount === 3) {
        setStatus("globalStatus", "3カテゴリすべて読み込み完了！");
      } else {
        setStatus("globalStatus", `読み込み完了（成功: ${okCount}/3）`, true);
      }
    }

    window.addEventListener("DOMContentLoaded", loadAllData);
  </script>
</body>
</html>
