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
