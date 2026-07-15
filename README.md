<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>AnalystLab Africa — Data Analytics Internship</title>
<style>
  * { margin: 0; padding: 0; box-sizing: border-box; }

  body {
    font-family: 'Segoe UI', system-ui, -apple-system, sans-serif;
    background: #0d1117;
    color: #e6edf3;
    line-height: 1.7;
    font-size: 15px;
  }

  a { color: #58a6ff; text-decoration: none; }
  a:hover { text-decoration: underline; }

  /* HERO */
  .hero {
    background: linear-gradient(135deg, #0d1117 0%, #161b22 60%, #1a1f2e 100%);
    border-bottom: 1px solid #21262d;
    padding: 60px 40px 48px;
    text-align: center;
  }

  .badge-row {
    display: flex;
    gap: 8px;
    justify-content: center;
    flex-wrap: wrap;
    margin-bottom: 28px;
  }

  .badge {
    display: inline-flex;
    align-items: center;
    gap: 6px;
    padding: 4px 12px;
    border-radius: 20px;
    font-size: 12px;
    font-weight: 600;
    letter-spacing: 0.3px;
  }

  .badge-blue { background: #1f3a5c; color: #58a6ff; border: 1px solid #1f6feb; }
  .badge-green { background: #1a3a2a; color: #3fb950; border: 1px solid #2ea043; }
  .badge-amber { background: #3a2a10; color: #e3b341; border: 1px solid #9e6a03; }
  .badge-purple { background: #2a1f3a; color: #bc8cff; border: 1px solid #6e40c9; }

  .hero-title {
    font-size: 42px;
    font-weight: 700;
    color: #f0f6fc;
    letter-spacing: -0.5px;
    margin-bottom: 8px;
  }

  .hero-title span { color: #f5a623; }

  .hero-subtitle {
    font-size: 18px;
    color: #8b949e;
    margin-bottom: 32px;
  }

  .meta-row {
    display: flex;
    justify-content: center;
    gap: 32px;
    flex-wrap: wrap;
  }

  .meta-item {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 4px;
  }

  .meta-label { font-size: 11px; color: #6e7681; text-transform: uppercase; letter-spacing: 1px; }
  .meta-value { font-size: 14px; color: #e6edf3; font-weight: 500; }

  /* LAYOUT */
  .container { max-width: 960px; margin: 0 auto; padding: 0 24px; }

  section { padding: 48px 0 32px; border-bottom: 1px solid #21262d; }
  section:last-child { border-bottom: none; }

  h2 {
    font-size: 22px;
    font-weight: 600;
    color: #f0f6fc;
    margin-bottom: 24px;
    display: flex;
    align-items: center;
    gap: 10px;
  }

  h2 .icon {
    width: 32px;
    height: 32px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 16px;
    flex-shrink: 0;
  }

  h3 { font-size: 16px; font-weight: 600; color: #f0f6fc; margin: 20px 0 12px; }

  /* DATASET CARDS */
  .dataset-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }

  .dataset-card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 12px;
    padding: 24px;
    position: relative;
    overflow: hidden;
  }

  .dataset-card::before {
    content: '';
    position: absolute;
    top: 0; left: 0; right: 0;
    height: 3px;
  }

  .dataset-card.retail::before { background: #f5a623; }
  .dataset-card.netflix::before { background: #e50914; }

  .dataset-label {
    font-size: 11px;
    font-weight: 600;
    letter-spacing: 1px;
    text-transform: uppercase;
    margin-bottom: 8px;
  }

  .retail .dataset-label { color: #f5a623; }
  .netflix .dataset-label { color: #e50914; }

  .dataset-name { font-size: 18px; font-weight: 600; color: #f0f6fc; margin-bottom: 12px; }

  .stat-row { display: flex; gap: 16px; margin-bottom: 16px; }

  .stat {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 8px;
    padding: 8px 14px;
    flex: 1;
    text-align: center;
  }

  .stat-num { font-size: 18px; font-weight: 700; color: #f0f6fc; }
  .stat-lbl { font-size: 11px; color: #6e7681; }

  .desc { font-size: 13px; color: #8b949e; line-height: 1.6; }

  .col-tags { display: flex; flex-wrap: wrap; gap: 6px; margin-top: 14px; }

  .col-tag {
    background: #21262d;
    color: #8b949e;
    font-size: 11px;
    padding: 3px 8px;
    border-radius: 4px;
    font-family: 'Courier New', monospace;
  }

  /* TABLES */
  .table-wrap { overflow-x: auto; margin-top: 8px; }

  table {
    width: 100%;
    border-collapse: collapse;
    font-size: 13px;
  }

  th {
    background: #161b22;
    color: #8b949e;
    font-weight: 600;
    text-align: left;
    padding: 10px 14px;
    border-bottom: 1px solid #21262d;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 0.5px;
  }

  td {
    padding: 10px 14px;
    border-bottom: 1px solid #21262d;
    color: #c9d1d9;
    vertical-align: top;
  }

  tr:last-child td { border-bottom: none; }
  tr:hover td { background: #161b22; }

  .resolved {
    display: inline-flex;
    align-items: center;
    gap: 4px;
    background: #1a3a2a;
    color: #3fb950;
    border: 1px solid #2ea043;
    border-radius: 12px;
    padding: 2px 10px;
    font-size: 11px;
    font-weight: 600;
  }

  .tag-retail {
    display: inline-block;
    background: #3a2a10;
    color: #e3b341;
    border-radius: 4px;
    padding: 1px 7px;
    font-size: 11px;
    font-weight: 600;
    margin-right: 6px;
  }

  .tag-netflix {
    display: inline-block;
    background: #3a0d10;
    color: #ff6b6b;
    border-radius: 4px;
    padding: 1px 7px;
    font-size: 11px;
    font-weight: 600;
    margin-right: 6px;
  }

  /* VIZ GRID */
  .viz-grid { display: grid; grid-template-columns: repeat(5, 1fr); gap: 12px; }

  .viz-card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 16px 12px;
    text-align: center;
  }

  .viz-icon { font-size: 24px; margin-bottom: 8px; }
  .viz-name { font-size: 13px; font-weight: 600; color: #f0f6fc; margin-bottom: 4px; }
  .viz-desc { font-size: 11px; color: #6e7681; line-height: 1.4; }

  /* INSIGHTS */
  .insights-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; }

  .insight-card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 18px 20px;
    display: flex;
    gap: 14px;
    align-items: flex-start;
  }

  .insight-num {
    width: 28px;
    height: 28px;
    border-radius: 8px;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 13px;
    font-weight: 700;
    flex-shrink: 0;
  }

  .num-retail { background: #3a2a10; color: #e3b341; }
  .num-netflix { background: #3a0d10; color: #ff6b6b; }

  .insight-text { font-size: 13px; color: #8b949e; line-height: 1.6; }
  .insight-text strong { color: #e6edf3; font-weight: 600; }

  /* CODE BLOCK */
  .code-block {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 20px 24px;
    font-family: 'Courier New', 'Cascadia Code', monospace;
    font-size: 13px;
    line-height: 1.8;
    overflow-x: auto;
  }

  .code-comment { color: #6e7681; }
  .code-keyword { color: #ff7b72; }
  .code-string { color: #a5d6ff; }
  .code-method { color: #d2a8ff; }
  .code-var { color: #ffa657; }

  /* TOOLS */
  .tools-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 12px; }

  .tool-card {
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 16px;
    text-align: center;
  }

  .tool-name { font-size: 14px; font-weight: 600; color: #f0f6fc; margin-bottom: 4px; }
  .tool-desc { font-size: 12px; color: #6e7681; }

  /* LEARNINGS */
  .learning-list { list-style: none; display: flex; flex-direction: column; gap: 10px; }

  .learning-item {
    display: flex;
    align-items: flex-start;
    gap: 12px;
    padding: 14px 18px;
    background: #161b22;
    border: 1px solid #21262d;
    border-radius: 8px;
    font-size: 13px;
    color: #8b949e;
  }

  .learning-item::before {
    content: '→';
    color: #f5a623;
    font-weight: 700;
    flex-shrink: 0;
    margin-top: 1px;
  }

  .learning-item strong { color: #e6edf3; }

  /* FOOTER */
  .footer {
    text-align: center;
    padding: 40px 24px;
    border-top: 1px solid #21262d;
    color: #6e7681;
    font-size: 13px;
  }

  .footer strong { color: #e6edf3; }

  /* FILE TREE */
  .file-tree {
    background: #0d1117;
    border: 1px solid #21262d;
    border-radius: 10px;
    padding: 20px 24px;
    font-family: 'Courier New', monospace;
    font-size: 13px;
    line-height: 2;
  }

  .tree-dir { color: #58a6ff; }
  .tree-file { color: #8b949e; }
  .tree-line { color: #30363d; }

  @media (max-width: 680px) {
    .dataset-grid, .insights-grid { grid-template-columns: 1fr; }
    .viz-grid { grid-template-columns: repeat(3, 1fr); }
    .tools-grid { grid-template-columns: repeat(2, 1fr); }
    .hero-title { font-size: 28px; }
    .meta-row { gap: 16px; }
  }
</style>
</head>
<body>

<!-- HERO -->
<div class="hero">
  <div class="badge-row">
    <span class="badge badge-blue">Python</span>
    <span class="badge badge-blue">Pandas</span>
    <span class="badge badge-green">Google Colab</span>
    <span class="badge badge-amber">Matplotlib</span>
    <span class="badge badge-purple">SQL Server</span>
    <span class="badge badge-green">8 Weeks</span>
  </div>

  <h1 class="hero-title">AnalystLab <span>Africa</span></h1>
  <p class="hero-subtitle">Data Analytics Internship — End-to-End Project Repository</p>

  <div class="meta-row">
    <div class="meta-item">
      <span class="meta-label">Intern</span>
      <span class="meta-value">Lethokuhle Mathebula</span>
    </div>
    <div class="meta-item">
      <span class="meta-label">Programme</span>
      <span class="meta-value">AnalystLab Africa</span>
    </div>
    <div class="meta-item">
      <span class="meta-label">Duration</span>
      <span class="meta-value">8 Weeks</span>
    </div>
    <div class="meta-item">
      <span class="meta-label">Year</span>
      <span class="meta-value">2026</span>
    </div>
  </div>
</div>

<div class="container">

  <!-- REPO STRUCTURE -->
  <section>
    <h2><span class="icon" style="background:#1f3a5c">📁</span> Repository structure</h2>
    <div class="file-tree">
      <div><span class="tree-dir">analytlab-africa-internship/</span></div>
      <div><span class="tree-line">│</span></div>
      <div><span class="tree-line">├── </span><span class="tree-dir">datasets/</span></div>
      <div><span class="tree-line">│   ├── </span><span class="tree-file">online_retail.csv</span>         <span class="code-comment"># UK e-commerce transaction data</span></div>
      <div><span class="tree-line">│   └── </span><span class="tree-file">netflix_titles.csv</span>        <span class="code-comment"># Netflix movies and TV shows catalogue</span></div>
      <div><span class="tree-line">│</span></div>
      <div><span class="tree-line">├── </span><span class="tree-dir">notebooks/</span></div>
      <div><span class="tree-line">│   ├── </span><span class="tree-file">week1_online_retail.ipynb</span> <span class="code-comment"># Cleaning and EDA — Online Retail</span></div>
      <div><span class="tree-line">│   └── </span><span class="tree-file">week2_netflix_titles.ipynb</span><span class="code-comment"># Cleaning and EDA — Netflix Titles</span></div>
      <div><span class="tree-line">│</span></div>
      <div><span class="tree-line">├── </span><span class="tree-dir">reports/</span></div>
      <div><span class="tree-line">│   └── </span><span class="tree-file">Data_Analytics_Summary_Report.docx</span></div>
      <div><span class="tree-line">│</span></div>
      <div><span class="tree-line">└── </span><span class="tree-file">README.html</span></div>
    </div>
  </section>

  <!-- DATASETS -->
  <section>
    <h2><span class="icon" style="background:#1a3a2a">📦</span> Datasets</h2>
    <div class="dataset-grid">

      <div class="dataset-card retail">
        <div class="dataset-label">Dataset 1</div>
        <div class="dataset-name">Online Retail</div>
        <div class="stat-row">
          <div class="stat"><div class="stat-num">541,909</div><div class="stat-lbl">Rows</div></div>
          <div class="stat"><div class="stat-num">8</div><div class="stat-lbl">Columns</div></div>
          <div class="stat"><div class="stat-num">2010–11</div><div class="stat-lbl">Period</div></div>
        </div>
        <div class="desc">Transactional sales data from a UK-based online retailer. Every row is a line item on an invoice.</div>
        <div class="col-tags">
          <span class="col-tag">InvoiceNo</span>
          <span class="col-tag">StockCode</span>
          <span class="col-tag">Description</span>
          <span class="col-tag">Quantity</span>
          <span class="col-tag">InvoiceDate</span>
          <span class="col-tag">UnitPrice</span>
          <span class="col-tag">CustomerID</span>
          <span class="col-tag">Country</span>
        </div>
      </div>

      <div class="dataset-card netflix">
        <div class="dataset-label">Dataset 2</div>
        <div class="dataset-name">Netflix Titles</div>
        <div class="stat-row">
          <div class="stat"><div class="stat-num">8,807</div><div class="stat-lbl">Rows</div></div>
          <div class="stat"><div class="stat-num">12</div><div class="stat-lbl">Columns</div></div>
          <div class="stat"><div class="stat-num">2008–21</div><div class="stat-lbl">Period</div></div>
        </div>
        <div class="desc">Catalogue of movies and TV shows available on the Netflix streaming platform globally.</div>
        <div class="col-tags">
          <span class="col-tag">show_id</span>
          <span class="col-tag">type</span>
          <span class="col-tag">title</span>
          <span class="col-tag">director</span>
          <span class="col-tag">cast</span>
          <span class="col-tag">country</span>
          <span class="col-tag">date_added</span>
          <span class="col-tag">release_year</span>
          <span class="col-tag">rating</span>
          <span class="col-tag">duration</span>
          <span class="col-tag">listed_in</span>
          <span class="col-tag">description</span>
        </div>
      </div>

    </div>
  </section>

  <!-- CLEANING -->
  <section>
    <h2><span class="icon" style="background:#2a1f3a">🧹</span> Data cleaning</h2>

    <h3><span style="color:#e3b341">●</span> Online Retail</h3>
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Issue</th><th>Action taken</th><th>Records affected</th><th>Status</th></tr>
        </thead>
        <tbody>
          <tr><td>Missing CustomerID</td><td>Flagged + filled with "Guest"</td><td>135,080 rows</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Duplicate rows</td><td>Removed with <code>drop_duplicates()</code></td><td>Confirmed via <code>.sum()</code></td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Negative quantities (returns)</td><td>Separated into returns dataset</td><td>Invoices starting with "C"</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Non-product entries</td><td>Removed POSTAGE, DISCOUNT entries</td><td>Filtered by StockCode</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Outliers — Quantity & UnitPrice</td><td>Removed using IQR method</td><td>58,501 / 39,450 rows</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Inconsistent date format</td><td>Converted to YYYY-MM-DD</td><td>All rows</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Text & column standardisation</td><td>Uppercased, stripped, renamed</td><td>All columns</td><td><span class="resolved">✓ Resolved</span></td></tr>
        </tbody>
      </table>
    </div>

    <h3 style="margin-top: 28px;"><span style="color:#ff6b6b">●</span> Netflix Titles</h3>
    <div class="table-wrap">
      <table>
        <thead>
          <tr><th>Issue</th><th>Action taken</th><th>Records affected</th><th>Status</th></tr>
        </thead>
        <tbody>
          <tr><td>Missing director, cast, country, rating</td><td>Filled with "Unknown"</td><td>Multiple columns</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>date_added stored as text</td><td>Parsed to YYYY-MM-DD format</td><td>All rows</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Inconsistent text casing</td><td>Uppercased and stripped</td><td>All text columns</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Column names inconsistent</td><td>Lowercased and underscored</td><td>All columns</td><td><span class="resolved">✓ Resolved</span></td></tr>
          <tr><td>Duplicate rows</td><td>Removed with <code>drop_duplicates()</code></td><td>Confirmed via <code>.sum()</code></td><td><span class="resolved">✓ Resolved</span></td></tr>
        </tbody>
      </table>
    </div>
  </section>

  <!-- VISUALIZATIONS -->
  <section>
    <h2><span class="icon" style="background:#1f3a5c">📈</span> Visualizations</h2>
    <div class="viz-grid">
      <div class="viz-card">
        <div class="viz-icon">📊</div>
        <div class="viz-name">Bar chart</div>
        <div class="viz-desc">Quantity by country · Titles by country</div>
      </div>
      <div class="viz-card">
        <div class="viz-icon">📉</div>
        <div class="viz-name">Histogram</div>
        <div class="viz-desc">Unit price distribution · Release year spread</div>
      </div>
      <div class="viz-card">
        <div class="viz-icon">🥧</div>
        <div class="viz-name">Pie chart</div>
        <div class="viz-desc">Revenue by country · Movies vs TV Shows</div>
      </div>
      <div class="viz-card">
        <div class="viz-icon">📈</div>
        <div class="viz-name">Line chart</div>
        <div class="viz-desc">Monthly sales trends · Content added over time</div>
      </div>
      <div class="viz-card">
        <div class="viz-icon">📦</div>
        <div class="viz-name">Box plot</div>
        <div class="viz-desc">Revenue distribution · Release year outliers</div>
      </div>
    </div>
  </section>

  <!-- INSIGHTS -->
  <section>
    <h2><span class="icon" style="background:#1a3a2a">🔍</span> Key insights</h2>
    <div class="insights-grid">

      <div class="insight-card">
        <div class="insight-num num-retail">1</div>
        <div class="insight-text"><strong>UK market dominance.</strong> The United Kingdom accounts for over 3.75 million units sold — dwarfing every other country combined. Referenced in: Bar Chart.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-retail">2</div>
        <div class="insight-text"><strong>Low-cost, high-volume model.</strong> Most products are priced under £3. Revenue is driven by quantity, not premium pricing. Referenced in: Histogram.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-retail">3</div>
        <div class="insight-text"><strong>24% guest transactions.</strong> 135,080 CustomerIDs were null — limiting customer-level analysis to 76% of the dataset. Referenced in: Data Cleaning.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-retail">4</div>
        <div class="insight-text"><strong>Returns distort geographic data.</strong> Negative quantities from cancelled orders pulled multiple countries below zero on the bar chart. Referenced in: Bar Chart.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-retail">5</div>
        <div class="insight-text"><strong>Wholesale buying behaviour.</strong> IQR analysis flagged bulk orders of 24–96 units, indicating a significant wholesale customer segment. Referenced in: Box Plot.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-netflix">6</div>
        <div class="insight-text"><strong>USA dominates content production.</strong> The United States produces significantly more Netflix content than any other country. Referenced in: Bar Chart.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-netflix">7</div>
        <div class="insight-text"><strong>Movies outnumber TV Shows.</strong> Movies make up the larger share, though TV Shows drive longer per-title engagement. Referenced in: Pie Chart.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-netflix">8</div>
        <div class="insight-text"><strong>Content peaked in 2019–2020.</strong> A sharp drop in 2021 aligns with COVID-19 production disruptions worldwide. Referenced in: Line Chart.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-netflix">9</div>
        <div class="insight-text"><strong>Netflix favours recent content.</strong> Most titles were released after 2015, confirming the platform prioritises modern productions. Referenced in: Histogram.</div>
      </div>

      <div class="insight-card">
        <div class="insight-num num-netflix">10</div>
        <div class="insight-text"><strong>Older classic titles exist as outliers.</strong> Titles from the 1940s appear in the box plot — retained to serve niche audiences. Referenced in: Box Plot.</div>
      </div>

    </div>
  </section>

  <!-- CODE PATTERNS -->
  <section>
    <h2><span class="icon" style="background:#2a1f3a">💻</span> Core cleaning patterns</h2>
    <div class="code-block">
      <div><span class="code-comment"># Lock in raw copy before any cleaning</span></div>
      <div><span class="code-var">df_raw</span> = <span class="code-var">df</span>.<span class="code-method">copy</span>()</div>
      <div>&nbsp;</div>
      <div><span class="code-comment"># Flag and fill missing ID columns</span></div>
      <div><span class="code-var">df</span>[<span class="code-string">'CustomerID_missing'</span>] = <span class="code-var">df</span>[<span class="code-string">'CustomerID'</span>].<span class="code-method">isnull</span>()</div>
      <div><span class="code-var">df</span>[<span class="code-string">'CustomerID'</span>] = <span class="code-var">df</span>[<span class="code-string">'CustomerID'</span>].<span class="code-method">fillna</span>(<span class="code-string">'Guest'</span>)</div>
      <div>&nbsp;</div>
      <div><span class="code-comment"># Standardise column names</span></div>
      <div><span class="code-var">df</span>.columns = <span class="code-var">df</span>.columns.<span class="code-method">str</span>.<span class="code-method">strip</span>().<span class="code-method">str</span>.<span class="code-method">lower</span>().<span class="code-method">str</span>.<span class="code-method">replace</span>(<span class="code-string">' '</span>, <span class="code-string">'_'</span>)</div>
      <div>&nbsp;</div>
      <div><span class="code-comment"># Standardise date format</span></div>
      <div><span class="code-var">df</span>[<span class="code-string">'formatted_date'</span>] = <span class="code-keyword">pd</span>.<span class="code-method">to_datetime</span>(<span class="code-var">df</span>[<span class="code-string">'date_added'</span>]).<span class="code-method">dt</span>.<span class="code-method">strftime</span>(<span class="code-string">'%Y-%m-%d'</span>)</div>
      <div>&nbsp;</div>
      <div><span class="code-comment"># Remove duplicates</span></div>
      <div><span class="code-var">df</span> = <span class="code-var">df</span>.<span class="code-method">drop_duplicates</span>()</div>
      <div>&nbsp;</div>
      <div><span class="code-comment"># IQR outlier removal</span></div>
      <div><span class="code-var">Q1</span> = <span class="code-var">df</span>[<span class="code-string">'quantity'</span>].<span class="code-method">quantile</span>(<span class="code-string">0.25</span>)</div>
      <div><span class="code-var">Q3</span> = <span class="code-var">df</span>[<span class="code-string">'quantity'</span>].<span class="code-method">quantile</span>(<span class="code-string">0.75</span>)</div>
      <div><span class="code-var">IQR</span> = <span class="code-var">Q3</span> - <span class="code-var">Q1</span></div>
      <div><span class="code-var">df</span> = <span class="code-var">df</span>[~((<span class="code-var">df</span>[<span class="code-string">'quantity'</span>] &lt; (<span class="code-var">Q1</span> - <span class="code-string">1.5</span> * <span class="code-var">IQR</span>)) | (<span class="code-var">df</span>[<span class="code-string">'quantity'</span>] &gt; (<span class="code-var">Q3</span> + <span class="code-string">1.5</span> * <span class="code-var">IQR</span>)))]</div>
    </div>
  </section>

  <!-- TOOLS -->
  <section>
    <h2><span class="icon" style="background:#1f3a5c">🛠️</span> Libraries used</h2>
    <div class="tools-grid">
      <div class="tool-card">
        <div class="tool-name">pandas</div>
        <div class="tool-desc">Data loading, cleaning, and manipulation</div>
      </div>
      <div class="tool-card">
        <div class="tool-name">numpy</div>
        <div class="tool-desc">Numerical operations and array handling</div>
      </div>
      <div class="tool-card">
        <div class="tool-name">matplotlib</div>
        <div class="tool-desc">All data visualizations and charts</div>
      </div>
      <div class="tool-card">
        <div class="tool-name">datetime</div>
        <div class="tool-desc">Date parsing and format standardisation</div>
      </div>
    </div>
  </section>

  <!-- LEARNINGS -->
  <section>
    <h2><span class="icon" style="background:#1a3a2a">💡</span> Key learnings</h2>
    <ul class="learning-list">
      <li class="learning-item"><strong>Never drop ID column nulls blindly</strong> — Missing CustomerIDs represent real guest transactions. Dropping them removes 24% of real revenue data.</li>
      <li class="learning-item"><strong>Always lock in a raw copy first</strong> — <code>df_raw = df.copy()</code> before any cleaning step prevents unrecoverable data loss.</li>
      <li class="learning-item"><strong>Cleaning decisions shape analysis</strong> — Every action taken during cleaning directly affects what the EDA can and cannot reveal downstream.</li>
      <li class="learning-item"><strong>Outliers need context, not just removal</strong> — High quantity outliers in retail are wholesale orders, not errors. Context determines the right treatment.</li>
      <li class="learning-item"><strong>Text standardisation matters for groupby</strong> — Without consistent casing, pandas treats "United Kingdom" and "UNITED KINGDOM" as two separate countries, corrupting aggregations.</li>
      <li class="learning-item"><strong>Returns must be separated, not deleted</strong> — Negative quantity rows are valid business data representing cancellations and should be analysed separately.</li>
    </ul>
  </section>

</div>

<!-- FOOTER -->
<div class="footer">
  <p>Built by <strong>Lethokuhle Mathebula</strong> · AnalystLab Africa Data Analytics Internship · 2026</p>
  <p style="margin-top: 6px; font-size: 12px;">Python · Pandas · NumPy · Matplotlib · Google Colab · SQL Server</p>
</div>

</body>
</html>
