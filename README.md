# UNICEF EAPRO Data Scientist Candidate Take Home Assignment

Dear Candidate,

Below is a modified example of the kinds of real projects you might work on at the Frontier Data Lab. To be respectful of your time and help you finish the task in the allotted time, we have simplified the scenario and skipped over some important steps, including user research, requirements gathering, sprint planning, and time estimation. 
If this were a real project, we would work on these first together, and you would have an opportunity to propose alternative approaches, ways we can work faster, and different ways of working.

# QUICKSTART:

* A UNICEF Country Office team has asked us to understand whether air quality sensors deployed in their country are operating reliably.
* All of the sensors are public low cost AQ monitors that post their data to OpenAQ, an open source + open data air quality data platform.
* In this assignment, we'd like you to build a short exploratory analysis workbook that:
    * Retrieves the relevant sensor data from OpenAQ
    * Retrieves any other relevant context data (Population and Relative Wealth)
    * Identifies monitoring locations or sensors that may have failed or become unreliable
    * Analyzes whether those failures have any relationships with the geography, population density or relative wealth of the surrounding area
* Data sources you might need:
    * Air quality measurements and monitoring metadata: https://docs.openaq.org/ & https://registry.opendata.aws/openaq/ 
    * OpenAQ API reference: https://api.openaq.org/docs
    * Meta Relative Wealth Index: https://data.humdata.org/dataset/relative-wealth-index
    * WorldPop population data for Lao PDR: https://hub.worldpop.org/
* Suggested Python libraries and tools, if helpful:
    * Polars - https://docs.pola.rs/
    * DuckDB - https://duckdb.org/docs/
    * GeoPandas - https://geopandas.org/
    * giga-spatial-unicef - https://pypi.org/project/giga-spatial-unicef/
    * Jupyter, Quarto, or plain scripts are all acceptable
* These are suggestions only. Please use any open-source stack that helps you work effectively.

# INSTRUCTIONS - PLEASE:

* Create a branch of this repo and work in that branch.
* Commit code regularly. It is ok if your code is messy or incomplete - The aim of this take-home assignment is to get a sense of how you work in a realistic environment. Commit as often as you like, but at least one commit for every 30 minutes that you spend working on this.
* Start with a plan. Write a short text/Markdown document or Jupyter notebook with the steps you are planning to take and the level of effort for each step. We use T-Shirt sizes - XS, S, M, L, XL - but you can use any system that works for you.
* Do not spend more than 2.5-3 hours on this. We are more interested in understanding your problem-solving process than in the polish of your code.
* If you are running short on time, add notes, pseudocode, or comments explaining how you would approach the remaining tasks.
    * This will not count against you. We understand that real data work often becomes more complex than it first appears.
* Use any tool or language that helps you get the task done. If you use an external tool that does not produce code, please include screenshots or a short text/Markdown document explaining the tool you used and the steps you took.
* Make your best assumptions and document them clearly.
* If OpenAQ API access, rate limits, authentication, or changing data availability blocks you, do not lose too much time. Document what happened, show the query or approach you attempted, and continue with a small sample, cached data, pseudocode, or an explained fallback.
* If you have questions, please ask them by email - jhanan@unicef.org. We will try to respond as quickly as possible, but cannot guarantee we will be able to respond immediately.
    * Use your best judgement on how to proceed if you do not hear from us in time.
* The narrative description below tries to give you a sense of how we work as a team within UNICEF. It may have useful information that is not in the quickstart. Please refer to it if you get stuck.

# A GREAT SUBMISSION SHOULD HAVE:

* Regular git commits.
* A short plan / approach before you dive in to any analysis, either in Markdown or a notebook.
* All code used for data access, cleaning, joining, and analysis.
* All code / notes showing your exploratory data analysis.
* A short written summary of your findings, suitable for a senior programme team colleague who is expert but not necessarily technical.
* Any charts, tables, or maps that help explain your findings.
* Any notes on limitations, assumptions, and what you would do with more time.


# NARRATIVE VERSION - SCENARIO

FROM: [Environment and Climate Specialist, UNICEF Lao PDR]

TO: [UNICEF EAPRO Frontier Data Lab]


Dear Frontier Data Lab,

Thank you for the meeting earlier today. 

One question that came up is whether the air quality monitoring data available to us is reliable enough for programme planning. Some locations seem to report regularly, while others appear to have gaps or may have stopped reporting entirely. Before we build any analysis around pollution exposure, we would like to understand whether the sensors themselves are operating consistently.

Could your team help us do a quick first-pass analysis of the air quality sensor reliability in Lao PDR? We are especially interested in whether outages or unreliable measurements appear random, or whether they are more common in particular geographies or communities.
We're specifically interested in:
Are the deployed sensors failing very often?
When they do, are those failures concentrated in any particular areas (Urban, Rural, High school age population, low school age population?)
Anything you can tell us about the relationship between any failures and the relative levels of wealth and poverty of the communities where the failures occur.

Best Regards,

[Environment and Climate Specialist, UNICEF Lao PDR]



FROM: [Data Scientist, UNICEF EAPRO Frontier Data Lab]

TO: **Data Scientist Candidate (THAT'S YOU!)**]

Hi [Data Scientist Candidate],

Yes, I think we can put together a quick prototype. We should be able to use:

1. OpenAQ air quality measurements and monitoring location metadata for Lao PDR. (All the Airgradient low cost sensors in Laos + on OpenAQ currently are from our recent deployment)
2. Meta Relative Wealth Index to approximate local relative wealth.
3. WorldPop population grids to estimate population / school age population density near monitoring locations. This could also serve as a proxy for urban / rural (absent a better dataset)

I'll leave the definition of 'sensor failure' up to you - First idea, fastest idea: A sensor's *failed* if it started reporting data back when we deployed them in Jan / Feb 2025, subsequently stopped, and didn't start again.
A sensor's *unreliable* when it has more than 20% of days with zero usable data in a given (recent) month - But use your judgement if you think these aren't the best metrics.


Thanks,

[Data Scientist]

## Reference


### Useful data (Suggestions only):

* OpenAQ documentation: https://docs.openaq.org/
* OpenAQ API reference: https://api.openaq.org/docs
* OpenAQ S3 Bucket: https://registry.opendata.aws/openaq/
* OpenAQ Explorer, useful for manual inspection: https://explore.openaq.org/
* Meta Relative Wealth Index: https://data.humdata.org/dataset/relative-wealth-index
* WorldPop data hub: https://hub.worldpop.org/
* WorldPop Lao PDR collection: https://stac.worldpop.org/collections/LAO


### Useful libraries (Python - suggestions only):

* Polars - https://docs.pola.rs/
* GeoPandas - https://geopandas.org/
* giga-spatial-unicef - https://pypi.org/project/giga-spatial-unicef/
* KeplerGL - https://docs.kepler.gl/docs/keplergl-jupyter

These are just suggestions. Approach the task however you think is best, using whatever tools and data you think are most useful and open.

### Scope guidance

Please don't spend time building:

* Production pipelines
* Complex dashboards
* A complex ML model / causal analysis

The goal is a practical data science prototype. We are looking for clear assumptions, sensible problem framing, practical data cleaning, thoughtful failure definitions, useful exploratory analysis, basic spatial reasoning, clear written communication, and awareness of limitations. There is no single correct answer.
