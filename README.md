<div style="font-family: Arial, sans-serif; line-height:1.6; max-width:900px;">

<h1>🏦 Largest Banks ETL Pipeline</h1>

<h2>📌 Overview</h2>
<p>This project implements an <strong>end-to-end ETL (Extract, Transform, Load) pipeline</strong> to gather data about the <strong>Largest Banks in the World</strong>. The data is extracted from a public web page (archived Wikipedia), transformed by converting market capitalization values into multiple currencies, and loaded into both a <strong>CSV file</strong> and a <strong>SQLite database</strong>.</p>
<p>This is my first project aimed at understanding and practicing the ETL workflow.</p>

<h2>🔧 Tech Stack</h2>
<ul>
<li>Python</li>
<li>BeautifulSoup (Web Scraping)</li>
<li>Pandas</li>
<li>NumPy</li>
<li>SQLite3</li>
<li>Requests</li>
<li>Datetime (Logging)</li>
</ul>

<h2>🌐 Data Source</h2>
<p>Archived Wikipedia source (stable HTML snapshot):</p>
<pre>https://web.archive.org/web/20230908091635/https://en.wikipedia.org/wiki/List_of_largest_banks</pre>
<p>Currency exchange rate CSV:</p>
<pre>exchange_rate.csv</pre>

<h2>🚀 ETL Workflow</h2>

<h3>1. Extract</h3>
<p>Scrapes the ranking table from the archived Wikipedia page to collect:</p>
<ul>
<li>Bank Name</li>
<li>Market Capitalization in USD (billion)</li>
</ul>
<pre><code>extract(url, table_attribs)</code></pre>

<h3>2. Transform</h3>
<p>Reads exchange rates from CSV and adds new currency-converted fields:</p>
<ul>
<li>MC_GBP_Billion</li>
<li>MC_EUR_Billion</li>
<li>MC_INR_Billion</li>
</ul>
<pre><code>transform(df, csv_path)</code></pre>

<h3>3. Load</h3>
<p>Final data is loaded into:</p>
<ul>
<li><strong>CSV File:</strong> <code>load_to_csv(df, output_path)</code></li>
<li><strong>SQLite Database:</strong> <code>load_to_db(df, sql_connection, table_name)</code></li>
</ul>

<h2>🔍 SQL Queries Executed</h2>
<ul>
<li>Query all rows</li>
<li>Average market cap (GBP)</li>
<li>First 5 bank names</li>
</ul>
<pre><code>run_query(query_statement, sql_connection)</code></pre>

<h2>📁 Project Structure</h2>
<pre>
largest-banks-etl/
│── exchange_rate.csv
│── Largest_banks_data.csv
│── Banks.db
│── code_log.txt
│── etl_script.py
│── README.md
</pre>

<h2>📝 Logging</h2>
<p>Logs all ETL steps into <code>code_log.txt</code>. Function used:</p>
<pre><code>log_progress(message)</code></pre>

<h2>▶️ How to Run</h2>
<p><strong>1. Install dependencies</strong></p>
<pre><code>pip install pandas numpy requests beautifulsoup4</code></pre>

<p><strong>2. Run the script</strong></p>
<pre><code>python etl_script.py</code></pre>

<p><strong>3. Outputs</strong></p>
<ul>
<li>Largest_banks_data.csv</li>
<li>Banks.db</li>
<li>code_log.txt</li>
</ul>

<h2>💡 Key Learnings</h2>
<ul>
<li>Web scraping using BeautifulSoup</li>
<li>ETL workflow implementation</li>
<li>Data cleaning & currency conversion</li>
<li>Loading data into SQLite</li>
<li>Running SQL queries via Python</li>
<li>Logging ETL steps</li>
</ul>

</div>
