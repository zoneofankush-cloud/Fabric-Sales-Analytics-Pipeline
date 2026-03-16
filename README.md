<div align="center">
  <h1><b style="color: #0078D4;">🚀 Enterprise Retail Data Pipeline & Analytics Engine</b></h1>
  <h3>Built completely within <b style="color: #0078D4;">Microsoft Fabric</b></h3>
</div>

<hr>

<h2><b style="color: #0078D4;">📌 Project Overview</b></h2>
<p>This project simulates a real-world, automated enterprise data pipeline. It transforms raw, fragmented historical CSV files into a zero-latency, auto-updating Power BI dashboard using a <b style="color: #0078D4;">Medallion architecture</b> and <b style="color: #0078D4;">One Big Table (OBT)</b> optimization.</p>

<p>The goal was to replace manual data refreshes with an <b style="color: #0078D4;">event-driven ETL pipeline</b> that ingests continuous monthly data drops, dynamically handles data quality (nulls and duplicates), and serves highly optimized data directly to Power BI's VertiPaq engine.</p>

<h2><b style="color: #0078D4;">🗂️ Project Structure</b></h2>
<p>This repository is meticulously organized to separate the architecture, codebase, visual layer, and raw data:</p>

<pre><code style="background-color: #f6f8fa; border-radius: 6px; padding: 16px; display: block; color: #24292f;">
fabric-sales-pipeline-project
│
├── architecture
│   ├── ERM.png
│   └── Re-Engineered ERM.png
│
├── dataset
│   ├── Sales Data 2020.csv
│   ├── Sales Data 2021.csv
│   ├── Sales Data 2022.csv
│   ├── customer_lookup.csv
│   ├── product lookup.csv
│   ├── product_category_lookup.csv
│   ├── product subcategories lookup.csv
│   └── territory lookup.csv
│
├── codes
│   ├── Broke and Push to lake.ipynb
│   ├── Product master.ipynb
│   └── create_sales_summary.ipynb
│
├── dashboard
│   ├── Ankush-LHouse-Powerbi.pbix
│   ├── SS_Dashboard.png
│   └── dashboard_assets/
│
└── README.md
</code></pre>

<h2><b style="color: #0078D4;">🛠️ Tech Stack & Tools</b></h2>
<ul>
  <li><b>Platform:</b> <b style="color: #0078D4;">Microsoft Fabric</b> (Lakehouse, Data Factory, Semantic Models)</li>
  <li><b>Data Engineering:</b> <b style="color: #0078D4;">Python, PySpark, Spark SQL, Delta Lake</b></li>
  <li><b>Analytics & Visualization:</b> <b style="color: #0078D4;">Power BI</b> (Direct Lake connection), DAX</li>
</ul>

<h2><b style="color: #0078D4;">💡 Key Engineering Achievements</b></h2>
<ol>
  <li><b>Incremental Load Simulation:</b> Built custom stateful logic (in <i>Broke and Push to lake.ipynb</i>) to dynamically watermark and batch-process historical data month-by-month, triggering the downstream pipeline automatically.</li>
  <li><b>Data Model Optimization:</b> Engineered a complete transformation from a multi-hop Snowflake schema to a unified <b style="color: #0078D4;">One Big Table (OBT)</b> approach, drastically reducing the computational load on Power BI.</li>
  <li><b>Bulletproof Data Quality:</b> Implemented explicit Python deduplication (<code>dropDuplicates</code>) and a strict Delta Lake <b style="color: #0078D4;">"Nuke and Pave"</b> (<code>DROP TABLE</code>) overwrite protocol to prevent transaction log bloat and guarantee 100% accuracy in the reporting layer.</li>
  <li><b>Zero-Latency Reporting:</b> Bypassed traditional Import mode by utilizing Fabric's <b style="color: #0078D4;">Direct Lake</b> connection, ensuring the Executive Dashboard updates instantly when new data lands.</li>
</ol>

<h2><b style="color: #0078D4;">📊 Final Executive Dashboard</b></h2>
<p><i>(Insert your SS_Dashboard.png image here by dragging and dropping it into the GitHub editor!)</i></p>

