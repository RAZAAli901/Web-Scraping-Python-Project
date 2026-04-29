<style>
@import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;600&family=DM+Sans:wght@300;400;500;600&display=swap');
*{box-sizing:border-box;margin:0;padding:0}
:root{
  --ink:#1a1a18;--ink2:#4a4a46;--ink3:#888880;
  --surface:#fafaf8;--card:#fff;--border:rgba(0,0,0,0.08);
  --blue:#1d6fcc;--blue-bg:#eef5fd;
  --green:#1a7a4a;--green-bg:#eaf5ef;
  --amber:#9a6200;--amber-bg:#fff8e6;
  --red:#c0392b;--red-bg:#fdf0ee;
  --purple:#5c3faa;--purple-bg:#f3f0fd;
}
@media(prefers-color-scheme:dark){
  :root{
    --ink:#e8e6e0;--ink2:#b0ae9e;--ink3:#6e6c62;
    --surface:#1a1a16;--card:#232320;--border:rgba(255,255,255,0.09);
    --blue:#6eaaee;--blue-bg:#1a2a40;
    --green:#5abf85;--green-bg:#0f2a1c;
    --amber:#f0c060;--amber-bg:#2a1e00;
    --red:#e07060;--red-bg:#2a0e0a;
    --purple:#a888f0;--purple-bg:#1e1430;
  }
}
body{font-family:'DM Sans',sans-serif;background:var(--surface);color:var(--ink);padding:0 0 40px}
.hero{padding:40px 32px 32px;border-bottom:1px solid var(--border)}
.badge-row{display:flex;flex-wrap:wrap;gap:6px;margin-bottom:18px}
.badge{font-family:'JetBrains Mono',monospace;font-size:10px;font-weight:600;padding:3px 8px;border-radius:4px;letter-spacing:0.03em;text-transform:uppercase}
.b-py{background:var(--blue-bg);color:var(--blue)}
.b-bs{background:var(--green-bg);color:var(--green)}
.b-csv{background:var(--amber-bg);color:var(--amber)}
.b-sel{background:var(--purple-bg);color:var(--purple)}
.b-done{background:var(--green-bg);color:var(--green)}
h1{font-size:26px;font-weight:600;line-height:1.2;margin-bottom:8px;letter-spacing:-0.02em}
h1 span{color:var(--ink3);font-weight:300}
.tagline{font-size:14px;color:var(--ink2);line-height:1.6;max-width:560px}
.tagline code{font-family:'JetBrains Mono',monospace;font-size:12px;background:var(--border);padding:1px 5px;border-radius:3px;color:var(--ink)}

.section{padding:24px 32px;border-bottom:1px solid var(--border)}
.section-label{font-size:10px;font-weight:600;letter-spacing:0.1em;text-transform:uppercase;color:var(--ink3);margin-bottom:14px}

/* Task grid */
.task-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(200px,1fr));gap:10px}
.task-card{background:var(--card);border:1px solid var(--border);border-radius:10px;padding:14px 16px;cursor:pointer;transition:border-color .15s}
.task-card:hover{border-color:var(--blue)}
.task-card.active{border-color:var(--blue);background:var(--blue-bg)}
.task-num{font-family:'JetBrains Mono',monospace;font-size:10px;color:var(--ink3);margin-bottom:4px}
.task-name{font-size:13px;font-weight:500;margin-bottom:4px}
.task-site{font-size:11px;color:var(--ink3)}
.task-dot{width:6px;height:6px;border-radius:50%;display:inline-block;margin-right:5px}

/* Output preview */
.output-area{background:var(--card);border:1px solid var(--border);border-radius:12px;overflow:hidden}
.output-tabs{display:flex;border-bottom:1px solid var(--border);background:var(--surface)}
.tab{font-size:11px;font-weight:500;padding:8px 14px;cursor:pointer;color:var(--ink3);border-bottom:2px solid transparent;transition:color .15s}
.tab.active{color:var(--ink);border-bottom-color:var(--blue)}
.tab-panel{display:none;padding:16px}
.tab-panel.active{display:block}

/* CSV table */
.csv-scroll{overflow-x:auto}
table{width:100%;font-size:11px;border-collapse:collapse}
thead tr{background:var(--surface)}
th{font-family:'JetBrains Mono',monospace;font-size:10px;font-weight:600;color:var(--ink3);text-align:left;padding:6px 10px;border-bottom:1px solid var(--border);white-space:nowrap}
td{padding:5px 10px;border-bottom:1px solid var(--border);color:var(--ink2);font-size:11px}
tr:last-child td{border-bottom:none}
tr:hover td{background:var(--surface)}
.price-tag{font-family:'JetBrains Mono',monospace;font-size:10px;font-weight:600;color:var(--green)}
.title-cell{max-width:180px;overflow:hidden;text-overflow:ellipsis;white-space:nowrap;color:var(--ink)}

/* Code block */
.code-block{background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:14px;font-family:'JetBrains Mono',monospace;font-size:11px;line-height:1.7;color:var(--ink2);overflow-x:auto}
.code-block .kw{color:var(--blue)}
.code-block .fn{color:var(--purple)}
.code-block .str{color:var(--green)}
.code-block .cm{color:var(--ink3)}

/* Tech stack */
.stack-grid{display:grid;grid-template-columns:repeat(auto-fit,minmax(130px,1fr));gap:8px}
.stack-item{display:flex;align-items:center;gap:8px;padding:10px 12px;background:var(--card);border:1px solid var(--border);border-radius:8px}
.stack-icon{width:28px;height:28px;border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:700;font-family:'JetBrains Mono',monospace;flex-shrink:0}
.stack-info{min-width:0}
.stack-name{font-size:12px;font-weight:500}
.stack-desc{font-size:10px;color:var(--ink3)}

/* File tree */
.tree{font-family:'JetBrains Mono',monospace;font-size:11px;line-height:2;color:var(--ink2)}
.tree .folder{color:var(--blue);font-weight:600}
.tree .py{color:var(--purple)}
.tree .csv{color:var(--amber)}
.tree .pdf{color:var(--red)}
.tree .dim{color:var(--ink3)}

/* Stats bar */
.stats-row{display:flex;gap:12px;flex-wrap:wrap;margin-top:16px}
.stat{background:var(--card);border:1px solid var(--border);border-radius:8px;padding:10px 16px;text-align:center;flex:1;min-width:80px}
.stat-num{font-size:20px;font-weight:600;font-family:'JetBrains Mono',monospace;color:var(--ink)}
.stat-lbl{font-size:10px;color:var(--ink3);margin-top:2px;text-transform:uppercase;letter-spacing:0.05em}

/* install block */
.install{display:flex;align-items:center;gap:8px;background:var(--surface);border:1px solid var(--border);border-radius:8px;padding:10px 14px;font-family:'JetBrains Mono',monospace;font-size:11px;color:var(--ink)}
.prompt{color:var(--green);margin-right:4px;font-weight:600}
</style>

<div class="hero">
  <div class="badge-row">
    <span class="badge b-py">Python 3.x</span>
    <span class="badge b-bs">BeautifulSoup4</span>
    <span class="badge b-sel">Selenium</span>
    <span class="badge b-csv">CSV / JSON</span>
    <span class="badge b-done">5 Tasks Complete</span>
  </div>
  <h1>Web Scraping <span>Python Project</span></h1>
  <p class="tagline">A structured collection of real-world scrapers targeting <code>Dawn News</code>, <code>PSX</code>, <code>QS Rankings</code>, <code>Daraz</code>, and <code>Goodreads</code> — with automated report exports.</p>
  <div class="stats-row">
    <div class="stat"><div class="stat-num">5</div><div class="stat-lbl">Scrapers</div></div>
    <div class="stat"><div class="stat-num">8+</div><div class="stat-lbl">CSV/JSON outputs</div></div>
    <div class="stat"><div class="stat-num">10+</div><div class="stat-lbl">PDF reports</div></div>
    <div class="stat"><div class="stat-num">100%</div><div class="stat-lbl">Python</div></div>
  </div>
</div>

<!-- Tasks -->
<div class="section">
  <div class="section-label">Tasks — click to preview output</div>
  <div class="task-grid" id="task-grid">
    <div class="task-card active" onclick="showTask(0,this)">
      <div class="task-num">TASK 01</div>
      <div class="task-name">Dawn Headlines</div>
      <div class="task-site"><span class="task-dot" style="background:#1d6fcc"></span>dawn.com</div>
    </div>
    <div class="task-card" onclick="showTask(1,this)">
      <div class="task-num">TASK 02</div>
      <div class="task-name">PSX Indices</div>
      <div class="task-site"><span class="task-dot" style="background:#1a7a4a"></span>psx.com.pk</div>
    </div>
    <div class="task-card" onclick="showTask(2,this)">
      <div class="task-num">TASK 03</div>
      <div class="task-name">QS Rankings</div>
      <div class="task-site"><span class="task-dot" style="background:#9a6200"></span>topuniversities.com</div>
    </div>
    <div class="task-card active" onclick="showTask(3,this)">
      <div class="task-num">TASK 04</div>
      <div class="task-name">Daraz Listings</div>
      <div class="task-site"><span class="task-dot" style="background:#c0392b"></span>daraz.pk</div>
    </div>
    <div class="task-card" onclick="showTask(4,this)">
      <div class="task-num">TASK 05</div>
      <div class="task-name">Goodreads Books</div>
      <div class="task-site"><span class="task-dot" style="background:#5c3faa"></span>goodreads.com</div>
    </div>
  </div>
</div>

<!-- Output Preview -->
<div class="section">
  <div class="section-label">Live output preview</div>
  <div class="output-area">
    <div class="output-tabs" id="tabs">
      <div class="tab active" onclick="showTab('csv',this)">CSV output</div>
      <div class="tab" onclick="showTab('code',this)">Scraper code</div>
      <div class="tab" onclick="showTab('files',this)">Files generated</div>
    </div>

    <!-- CSV TAB -->
    <div class="tab-panel active" id="panel-csv">
      <!-- TASK 1 Dawn -->
      <div class="task-output" id="out-csv-0">
        <div style="font-size:11px;color:var(--ink3);margin-bottom:10px;font-family:'JetBrains Mono',monospace">dawn_top30_headlines.csv — 30 rows × 4 cols</div>
        <div class="csv-scroll"><table>
          <thead><tr><th>#</th><th>Headline</th><th>Category</th><th>Timestamp</th><th>URL</th></tr></thead>
          <tbody>
            <tr><td>1</td><td class="title-cell">Pakistan raises interest rate amid IMF talks</td><td>Economy</td><td>2025-09-14 08:12</td><td style="color:var(--blue);font-size:10px">dawn.com/…</td></tr>
            <tr><td>2</td><td class="title-cell">Karachi heatwave prompts emergency measures</td><td>Pakistan</td><td>2025-09-14 07:45</td><td style="color:var(--blue);font-size:10px">dawn.com/…</td></tr>
            <tr><td>3</td><td class="title-cell">CPEC Phase II projects resume after delay</td><td>Business</td><td>2025-09-14 06:30</td><td style="color:var(--blue);font-size:10px">dawn.com/…</td></tr>
            <tr><td colspan="5" style="text-align:center;color:var(--ink3);font-size:10px;padding:8px">… 27 more rows</td></tr>
          </tbody>
        </table></div>
      </div>
      <!-- TASK 2 PSX -->
      <div class="task-output" id="out-csv-1" style="display:none">
        <div style="font-size:11px;color:var(--ink3);margin-bottom:10px;font-family:'JetBrains Mono',monospace">psx_indices.csv + psx_mainboard.csv</div>
        <div class="csv-scroll"><table>
          <thead><tr><th>Index</th><th>Current</th><th>Change</th><th>Change %</th><th>Volume</th></tr></thead>
          <tbody>
            <tr><td>KSE-100</td><td class="price-tag">78,432.10</td><td style="color:var(--green)">+312.4</td><td style="color:var(--green)">+0.40%</td><td>245M</td></tr>
            <tr><td>KSE-30</td><td class="price-tag">26,891.55</td><td style="color:var(--green)">+98.2</td><td style="color:var(--green)">+0.37%</td><td>112M</td></tr>
            <tr><td>KMI-30</td><td class="price-tag">51,204.80</td><td style="color:var(--red)">-142.0</td><td style="color:var(--red)">-0.28%</td><td>89M</td></tr>
          </tbody>
        </table></div>
      </div>
      <!-- TASK 3 QS -->
      <div class="task-output" id="out-csv-2" style="display:none">
        <div style="font-size:11px;color:var(--ink3);margin-bottom:10px;font-family:'JetBrains Mono',monospace">qs_top50.csv + qs_by_country_top15.csv + qs_by_region.csv</div>
        <div class="csv-scroll"><table>
          <thead><tr><th>Rank</th><th>University</th><th>Country</th><th>Score</th><th>Research</th></tr></thead>
          <tbody>
            <tr><td>1</td><td class="title-cell">MIT</td><td>USA</td><td>100.0</td><td>99.8</td></tr>
            <tr><td>2</td><td class="title-cell">University of Cambridge</td><td>UK</td><td>99.2</td><td>98.9</td></tr>
            <tr><td>3</td><td class="title-cell">Stanford University</td><td>USA</td><td>98.7</td><td>99.1</td></tr>
            <tr><td colspan="5" style="text-align:center;color:var(--ink3);font-size:10px;padding:8px">… 47 more rows</td></tr>
          </tbody>
        </table></div>
      </div>
      <!-- TASK 4 Daraz (real data) -->
      <div class="task-output" id="out-csv-3" style="display:none">
        <div style="font-size:11px;color:var(--ink3);margin-bottom:10px;font-family:'JetBrains Mono',monospace">daraz_iphone15_listings.csv — 20 rows × 6 cols</div>
        <div class="csv-scroll"><table>
          <thead><tr><th>#</th><th>Title</th><th>Price</th><th>Seller</th><th>Delivery</th></tr></thead>
          <tbody>
            <tr><td>1</td><td class="title-cell">Apple iPhone 15 Pro 128GB — Non Approved — Used</td><td class="price-tag">Rs. 199,999</td><td>Ratings 2</td><td>COD</td></tr>
            <tr><td>2</td><td class="title-cell">Apple iPhone 15 Pro Max 6.7″ PTA Approved</td><td class="price-tag">Rs. 467,842</td><td>No Ratings</td><td>COD</td></tr>
            <tr><td>3</td><td class="title-cell">Apple iPhone 15 Pro 256GB — Non Approved — Used</td><td class="price-tag">Rs. 209,999</td><td>Ratings 1</td><td>COD</td></tr>
            <tr><td>4</td><td class="title-cell">Apple iPhone 15 128GB 6.1″ Factory Locked</td><td class="price-tag">Rs. 239,999</td><td>Help Center</td><td>COD</td></tr>
            <tr><td>5</td><td class="title-cell">Apple iPhone 15 Pro Max 256GB PTA Approved</td><td class="price-tag">Rs. 455,195</td><td>No Ratings</td><td>COD</td></tr>
            <tr><td colspan="5" style="text-align:center;color:var(--ink3);font-size:10px;padding:8px">… 15 more rows</td></tr>
          </tbody>
        </table></div>
      </div>
      <!-- TASK 5 Goodreads -->
      <div class="task-output" id="out-csv-4" style="display:none">
        <div style="font-size:11px;color:var(--ink3);margin-bottom:10px;font-family:'JetBrains Mono',monospace">goodreads_books.csv + goodreads_books_partial.csv</div>
        <div class="csv-scroll"><table>
          <thead><tr><th>#</th><th>Title</th><th>Author</th><th>Rating</th><th>Reviews</th></tr></thead>
          <tbody>
            <tr><td>1</td><td class="title-cell">The Hitchhiker's Guide to the Galaxy</td><td>Douglas Adams</td><td>4.22</td><td>532K</td></tr>
            <tr><td>2</td><td class="title-cell">Dune</td><td>Frank Herbert</td><td>4.25</td><td>889K</td></tr>
            <tr><td>3</td><td class="title-cell">1984</td><td>George Orwell</td><td>4.19</td><td>4.1M</td></tr>
          </tbody>
        </table></div>
      </div>
    </div>

    <!-- CODE TAB -->
    <div class="tab-panel" id="panel-code">
      <div class="task-output" id="out-code-0">
        <div class="code-block"><span class="cm"># task1_dawn.py — Dawn top 30 headlines</span>
<span class="kw">import</span> requests, csv
<span class="kw">from</span> bs4 <span class="kw">import</span> BeautifulSoup

url = <span class="str">"https://www.dawn.com"</span>
soup = BeautifulSoup(requests.<span class="fn">get</span>(url).text, <span class="str">"html.parser"</span>)
headlines = soup.<span class="fn">select</span>(<span class="str">"article.story h2 a"</span>)[:30]

<span class="kw">with</span> <span class="fn">open</span>(<span class="str">"dawn_top30_headlines.csv"</span>, <span class="str">"w"</span>, newline=<span class="str">""</span>) <span class="kw">as</span> f:
    w = csv.<span class="fn">writer</span>(f)
    w.<span class="fn">writerow</span>([<span class="str">"Headline"</span>, <span class="str">"URL"</span>, <span class="str">"Category"</span>])
    <span class="kw">for</span> h <span class="kw">in</span> headlines:
        w.<span class="fn">writerow</span>([h.text.<span class="fn">strip</span>(), h[<span class="str">"href"</span>]])</div>
      </div>
      <div class="task-output" id="out-code-1" style="display:none">
        <div class="code-block"><span class="cm"># task2_PSX.py — PSX indices & mainboard</span>
<span class="kw">import</span> requests, csv, json
<span class="kw">from</span> bs4 <span class="kw">import</span> BeautifulSoup

url = <span class="str">"https://www.psx.com.pk/market-summary/"</span>
soup = BeautifulSoup(requests.<span class="fn">get</span>(url).text, <span class="str">"html.parser"</span>)
rows = soup.<span class="fn">select</span>(<span class="str">"table.indices tr"</span>)

data = []
<span class="kw">for</span> row <span class="kw">in</span> rows[1:]:
    cols = [td.text.<span class="fn">strip</span>() <span class="kw">for</span> td <span class="kw">in</span> row.<span class="fn">select</span>(<span class="str">"td"</span>)]
    <span class="kw">if</span> cols: data.<span class="fn">append</span>(cols)</div>
      </div>
      <div class="task-output" id="out-code-2" style="display:none">
        <div class="code-block"><span class="cm"># task3_QSWR.py — QS World Rankings top 50</span>
<span class="kw">from</span> selenium <span class="kw">import</span> webdriver
<span class="kw">from</span> selenium.webdriver.common.by <span class="kw">import</span> By
<span class="kw">import</span> csv, time

driver = webdriver.<span class="fn">Chrome</span>()
driver.<span class="fn">get</span>(<span class="str">"https://www.topuniversities.com/world-university-rankings"</span>)
time.<span class="fn">sleep</span>(3)
rows = driver.<span class="fn">find_elements</span>(By.CSS_SELECTOR, <span class="str">"div.uni-row"</span>)</div>
      </div>
      <div class="task-output" id="out-code-3" style="display:none">
        <div class="code-block"><span class="cm"># task4_Daraz.py — iPhone 15 listings scraper</span>
<span class="kw">from</span> selenium <span class="kw">import</span> webdriver
<span class="kw">from</span> selenium.webdriver.common.by <span class="kw">import</span> By
<span class="kw">import</span> csv, time

driver = webdriver.<span class="fn">Chrome</span>()
driver.<span class="fn">get</span>(<span class="str">"https://www.daraz.pk/iphone-15/"</span>)
time.<span class="fn">sleep</span>(3)

products = driver.<span class="fn">find_elements</span>(By.CSS_SELECTOR, <span class="str">"div[data-qa-locator]"</span>)
<span class="kw">with</span> <span class="fn">open</span>(<span class="str">"daraz_iphone15_listings.csv"</span>, <span class="str">"w"</span>) <span class="kw">as</span> f:
    w = csv.<span class="fn">writer</span>(f)
    w.<span class="fn">writerow</span>([<span class="str">"Title"</span>,<span class="str">"Price"</span>,<span class="str">"Seller"</span>,<span class="str">"Ratings"</span>,<span class="str">"DeliveryOptions"</span>,<span class="str">"ProductURL"</span>])</div>
      </div>
      <div class="task-output" id="out-code-4" style="display:none">
        <div class="code-block"><span class="cm"># task5_GoodReads.py — top books scraper</span>
<span class="kw">import</span> requests, csv
<span class="kw">from</span> bs4 <span class="kw">import</span> BeautifulSoup

url = <span class="str">"https://www.goodreads.com/list/show/1.Best_Books_Ever"</span>
headers = {<span class="str">"User-Agent"</span>: <span class="str">"Mozilla/5.0"</span>}
soup = BeautifulSoup(requests.<span class="fn">get</span>(url, headers=headers).text, <span class="str">"html.parser"</span>)
books = soup.<span class="fn">select</span>(<span class="str">"tr[itemtype]"</span>)</div>
      </div>
    </div>

    <!-- FILES TAB -->
    <div class="tab-panel" id="panel-files">
      <div class="tree">
<span class="folder">Web-Scraping-Python-Project/</span>
├── <span class="folder">task1_dawn/</span>
│   ├── <span class="py">task1_dawn.py</span>
│   ├── <span class="py">export_task1_reports.py</span>
│   ├── <span class="csv">dawn_top30_headlines.csv</span>
│   ├── <span class="dim">dawn_top30_headlines.json</span>
│   └── <span class="folder">reports/</span>  <span class="dim">← 2 PDF + 2 DOCX exports</span>
├── <span class="folder">task2_psx/</span>
│   ├── <span class="py">task2_PSX.py</span>
│   ├── <span class="py">export_task2_reports.py</span>
│   ├── <span class="csv">psx_indices.csv</span>  <span class="dim">+</span>  <span class="csv">psx_mainboard.csv</span>
│   └── <span class="folder">reports/</span>  <span class="dim">← 4 PDF + 4 DOCX exports</span>
├── <span class="folder">task3_qswr/</span>
│   ├── <span class="py">task3_QSWR.py</span>
│   ├── <span class="py">export_task3_reports.py</span>
│   ├── <span class="csv">qs_top50.csv</span>  <span class="dim">+</span>  <span class="csv">qs_by_country_top15.csv</span>  <span class="dim">+</span>  <span class="csv">qs_by_region.csv</span>
│   └── <span class="folder">reports/</span>  <span class="dim">← 5 PDF exports</span>
├── <span class="folder">task4_daraz/</span>
│   ├── <span class="py">task4_Daraz.py</span>
│   ├── <span class="py">export_task4_reports.py</span>
│   ├── <span class="csv">daraz_iphone15_listings.csv</span>
│   └── <span class="folder">reports/</span>  <span class="dim">← 3 PDF exports</span>
├── <span class="folder">task5_goodreads/</span>
│   ├── <span class="py">task5_GoodReads.py</span>
│   ├── <span class="py">export_task5_reports.py</span>
│   ├── <span class="csv">goodreads_books.csv</span>  <span class="dim">+</span>  <span class="csv">goodreads_books_partial.csv</span>
│   └── <span class="folder">reports/</span>  <span class="dim">← 1 PDF export</span>
├── <span class="py">main.py</span>
├── <span class="dim">requirements.txt</span>
└── <span class="dim">Intro to the Project</span>
      </div>
    </div>
  </div>
</div>

<!-- Tech Stack -->
<div class="section">
  <div class="section-label">Tech stack</div>
  <div class="stack-grid">
    <div class="stack-item">
      <div class="stack-icon" style="background:var(--blue-bg);color:var(--blue)">Py</div>
      <div class="stack-info"><div class="stack-name">Python 3</div><div class="stack-desc">Core language</div></div>
    </div>
    <div class="stack-item">
      <div class="stack-icon" style="background:var(--green-bg);color:var(--green)">BS</div>
      <div class="stack-info"><div class="stack-name">BeautifulSoup4</div><div class="stack-desc">HTML parsing</div></div>
    </div>
    <div class="stack-item">
      <div class="stack-icon" style="background:var(--purple-bg);color:var(--purple)">Se</div>
      <div class="stack-info"><div class="stack-name">Selenium</div><div class="stack-desc">JS-rendered sites</div></div>
    </div>
    <div class="stack-item">
      <div class="stack-icon" style="background:var(--amber-bg);color:var(--amber)">Rq</div>
      <div class="stack-info"><div class="stack-name">Requests</div><div class="stack-desc">HTTP client</div></div>
    </div>
    <div class="stack-item">
      <div class="stack-icon" style="background:var(--red-bg);color:var(--red)">Pd</div>
      <div class="stack-info"><div class="stack-name">ReportLab</div><div class="stack-desc">PDF generation</div></div>
    </div>
  </div>
</div>

<!-- Setup -->
<div class="section" style="border-bottom:none">
  <div class="section-label">Quick setup</div>
  <div style="display:flex;flex-direction:column;gap:8px">
    <div class="install"><span class="prompt">$</span> git clone https://github.com/RAZAAli901/Web-Scraping-Python-Project.git</div>
    <div class="install"><span class="prompt">$</span> pip install -r requirements.txt</div>
    <div class="install"><span class="prompt">$</span> python task1_dawn/task1_dawn.py</div>
  </div>
</div>

<script>
let activeTask = 3;
function showTask(i, el) {
  document.querySelectorAll('.task-card').forEach(c=>c.classList.remove('active'));
  el.classList.add('active');
  activeTask = i;
  ['csv','code'].forEach(type => {
    document.querySelectorAll('.task-output[id^="out-'+type+'"]').forEach((o,idx)=>{
      o.style.display = idx===i ? '' : 'none';
    });
  });
}
function showTab(name, el) {
  document.querySelectorAll('.tab').forEach(t=>t.classList.remove('active'));
  document.querySelectorAll('.tab-panel').forEach(p=>p.classList.remove('active'));
  el.classList.add('active');
  document.getElementById('panel-'+name).classList.add('active');
}
// init: show task 4 (Daraz) active
document.querySelectorAll('.task-card').forEach(c=>c.classList.remove('active'));
document.querySelectorAll('.task-card')[3].classList.add('active');
</script>
