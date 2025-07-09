# SA25_APS
This repository contains a Jupyter Notebook that solves for the assignments provided during and under the Summer Analytics 2025. Created by Anirudha Pratap Singh , 240102012

Tech Stacks Used
🟢 Python
The main programming language.

📚 Python Libraries


🌟 Core Data and Numerical
pandas
For:

Inspecting CSVs (pd.read_csv())

Checking column names and data types (df.dtypes)

EDA and manual verification.

numpy

General numerical calculations.

⚡ Pathway
Pathway (pw)

Primary streaming data engine.

CSV ingestion (replay / streaming mode).

Schema definition.

windowby() for temporal aggregations.

reduce() for summarization (e.g., min/max/avg).

scan() for stateful cumulative computations.

apply() for custom price functions.

Output to JSONL.

Live plotting (Bokeh integration).

Pathway is THE main “stream processing” framework, acting like Kafka Streams + Pandas + real-time pipelines.

📈 Visualization
-> Bokeh

Plotting time series of prices.

Interactive figures (lines + circles).

Panel

Wrapping Bokeh plots in dashboards.

Serving them as a web app (pn.Column(...).servable()
  -> Datetime
datetime

Handling window intervals (timedelta(days=1)).

Parsing timestamps.
______________________________


Architectural Flow : 
┌────────────────────────┐
│ 1. CSV Files           │
│   e.g. parking_stream  │
└─────────┬──────────────┘
          │
          ▼
┌────────────────────────┐
│ 2. Pathway Replay      │
│    pw.demo.replay_csv  │
│  Streaming Ingestion   │
└─────────┬──────────────┘
          │
          ▼
┌───────────────────────────────┐
│ 3. Preprocessing Columns      │
│  • Parse Timestamp            │
│  • Extract Day                │
└─────────┬─────────────────────┘
          │
          ▼
┌─────────────────────────────────────┐
│ 4. Tumbling Window Aggregation      │
│   (Daily windows)                   │
│                                     │
│  • Max Occupancy                    │
│  • Min Occupancy                    │
│  • Max Capacity                     │
│  • Max Queue Length                 │
│  • Max Traffic Condition            │
│  • Max Special Day Indicator        │
│  • Max Vehicle Weight Normalized    │
└─────────┬───────────────────────────┘
          │
          ▼
┌───────────────────────────────┐
│ 5. Price Calculation          │
│                               │
│  price = 10 * [              │
│     1 + 0.5 * (              │
│       0.8 * (occ diff / cap) │
│       +0.4 * special day     │
│       +0.05 * queue length   │
│       -0.3 * traffic level   │
│       +0.2 * vehicle weight  │
│     )                        │
│   ]                          │
└─────────┬────────────────────┘
          │
          ▼
┌──────────────────────────────┐
│ 6. Bokeh Visualization       │
│   • Time Series Plot         │
│   • Prices Over Time         │
└─────────┬────────────────────┘
          │
          ▼
┌──────────────────────────────┐
│ 7. Panel Web App             │
│   • Servable Dashboard       │
└──────────────────────────────┘

