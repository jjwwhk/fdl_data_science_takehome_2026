EXECUTIVE BRIEF: LAO PDR AIR QUALITY MONITORING NETWORK RELIABILITY EVALUATION

Prepared for: Clean Air Initiative Evaluation Team

Date: July 2026

Subject: First-Pass Spatial \& Socioeconomic Analysis of Sensor Network Outages

Executive Summary

An evaluation of the 163 air quality monitoring nodes deployed across Lao PDR demonstrates that network outages and data unreliability are systemic and non-random. While the network maintains a surprisingly resilient operational baseline in suburban and rural regions, structural vulnerabilities are heavily concentrated in the highest-stakes environments: primary urban centers, physical school zones, and wealthier civic hubs.

This brief synthesizes our findings across three spatial dimensions—urbanization tiers, youth vulnerability zones, and socioeconomic profiles—to provide actionable remediation targets for network stabilization.

1\. Geographic Distribution \& The Urban Paradox

Conventional asset management assumes that remote rural deployments suffer the highest operational failure rates due to logistical constraints and grid instability. Our spatial intersection with the WorldPop Degree of Urbanisation (Level 1) asset completely refutes this assumption.

&#x09;The Urban Centre Paradox: Major cities exhibit the highest failure rate in the entire country. 35.0% of urban sensors have completely failed, and only half (50.0%) are delivering reliable real-time data.

&#x09;The Suburban/Rural Backbone: In contrast, Urban Clusters (Towns/Suburbs) represent the most dependable layer of the network, securing a 77.8% operational rate across 81 stations. Rural Areas display similar structural resilience, maintaining a 73.8% uptime across 61 stations.

Network Reliability by Official Settlement Layer (% Share)

Settlement Type (WorldPop L1)	Total Stations	Operational (%)	Unreliable (%)	Failed (%)

Urban Centre (City)	20	50.0%	15.0%	35.0%

Urban Cluster (Town/Suburb)	81	77.8%	8.6%	13.6%

Rural Area	61	73.8%	9.8%	16.4%

Background / Water	1	100.0%	0.0%	0.0%

Operational Driver: The high urban failure rate strongly points to micro-environmental stress. Urban sensors face intensified exposure to concentrated vehicular particulates, construction dust, and localized grid maintenance cycles, causing physical inlets to clog and components to degrade rapidly without accelerated maintenance schedules.

2\. Youth Vulnerability: Where Children Live vs. Where They Gather

To evaluate how data gaps jeopardize vulnerable populations, we cross-referenced sensor locations against WorldPop Age/Sex Demographics (where school-age cohorts live) and OpenStreetMap Infrastructure Layers (where physical schools exist). This revealed a critical spatial mismatch:

&#x09;High-Density Youth Residential Zones: Broad geographic regions with high densities of children (ages 5–19) are well-covered, boasting a low 13.6% failure rate.

&#x09;Physical School Infrastructure Blind Spot: When evaluating the immediate physical vicinity of schools, the failure rate spikes. 20.8% of sensors within 1.5 km of a school have failed entirely, and an additional 10.4% are reporting compromised, unreliable data.

Sensor Reliability by Youth Vulnerability Profile (% Share)

Vulnerability Layer	Operational (%)	Unreliable (%)	Failed (%)

High Student Density (Residential Grid)	75.3%	11.1%	13.6%

Inside School Zone (<1.5 km from School Building)	68.8%	10.4%	20.8%

Public Health Impact: Nearly one-third (31.2%) of the monitoring infrastructure intended to provide baseline environmental safeguards for active school zones is currently offline or compromised. This creates a severe tracking blind spot during peak daytime hours when children face the highest exposure to localized road dust and school commute emissions.

3\. Socioeconomic Correlation: The Wealth Tier Paradox

To isolate the relationship between community wealth and data coverage, the network was mapped to Meta’s Relative Wealth Index (RWI) at a 2.4 km micro-regional resolution. The network's median wealth index (0.418) was utilized to segment communities into relative poverty and wealth cohorts.

&#x09;Socioeconomic Vulnerability: The data confirms a striking socioeconomic inversion. Sensors located in Wealthier Communities suffer a 21.5% total failure rate, compared to just 13.1% in Poorer Communities.

&#x09;Systemic Alignment: This data layer perfectly validates our urbanization analysis. In Lao PDR, higher relative wealth is heavily concentrated within dense urban centers. Consequently, wealthier communities bear a disproportionate share of the network's technical infrastructure failures.

Sensor Reliability by Localized Wealth Tier (% Share)

Community Wealth Cohort (Meta RWI)	Total Stations	Operational (%)	Unreliable (%)	Failed (%)

Wealthier Community (Above Median RWI)	79	68.4%	10.1%	21.5%

Poorer Community (Below/At Median RWI)	84	77.4%	9.5%	13.1%

4\. Strategic Recommendations

Based on this first-pass evaluation, we recommend the following targeted operational interventions:

&#x09;Prioritize the 10 School-Zone Node Repairs: There are exactly 10 failed sensors sitting within 1.5 km of an OpenStreetMap verified school. Rehabilitating these specific nodes represents a high-impact, low-cost victory that immediately restores public health oversight for vulnerable children.

&#x09;Re-engineer Urban Sensor Housing: Because urban and wealthier civic nodes are failing at double the rate of rural ones, standard hardware deployments are clearly failing under urban environmental stress. Future urban deployments require upgraded particulate filters, ruggedized weather-shielding, and a shortened, preventative physical cleaning cycle.

&#x09;Leverage the Rural Baseline: The high operational stability in rural and lower-income communities (73.8%–77.4% uptime) validates the technical viability of the current hardware model in lower-density environments. This stable baseline should be leveraged to expand regional background tracking across the country with high confidence.

5\. Methodological Framework: Assumptions \& Limitations

To maintain absolute transparency in this first-pass evaluation, the analysis operates under the following structural framework:

💡 Core Analytical Assumptions

&#x09;The Baseline Network Date: We assumed that the network-wide maximum timestamp in datetimeLast.utc represents a true, active system checkpoint from which to calculate exact "days offline" for failing sensors.

&#x09;The Threshold Splits: For a rapid first-pass assessment, we utilized the network’s internal median values to establish binary classifications for both youth residential density (WorldPop) and relative community wealth (Meta RWI).

&#x09;The School Zone Buffer: A spatial buffer of 1.5" km"  around OpenStreetMap points was assumed to be an accurate representation of a daytime "School Zone," capturing both hyper-local student travel corridors and immediate roadside dust exposure.

⚠️ Data \& Technical Limitations

&#x09;Crowdsourced Infrastructure Gaps: The OpenStreetMap vector layer (schools.kml) relies on crowdsourced inputs. While highly accurate in urban settings, it may under-represent informal or remote educational structures in ultra-rural provinces, meaning our school-proximity failure rates are likely a conservative lower bound.

&#x09;The Relative Wealth Proxy: Meta’s RWI is a high-resolution, machine-learning inference engine built on satellite imagery, connectivity markers, and infrastructure density. It is an exceptional proxy for relative spatial wealth, but it does not substitute for ground-truth household consumption surveys or localized socioeconomic census registries.

&#x09;Cross-Sectional vs. Temporal Snapshots: This analysis represents a static diagnostic snapshot of network health up to July 2026. It does not account for temporal cycles, such as seasonal monsoon damage to hardware or heavy agricultural burning seasons that rapidly exhaust particulate sensor filters.

6\. Forward Horizons: What We Would Do With More Time

If granted additional runway or a secondary project phase, the analytical framework would be expanded in three high-impact directions:

&#x09;Transition to Multivariate Logistic Regression:

While our cross-tabulations show distinct trends, several variables overlap (e.g., high wealth correlates with high urbanization). Implementing a multivariate logistic regression model would allow us to isolate the true, independent statistical weight of each risk factor—proving definitively whether school proximity or urban traffic is the dominant driver of hardware failure when holding all other variables constant.

&#x09;Incorporate Temporal Survival Analysis:

Instead of measuring if a sensor is currently offline, we would analyze the time-series history to track when and how long it takes for a newly deployed sensor to degrade. This "Survival Analysis" framework would map out the exact life expectancy of different hardware models based on their geographic environment, optimizing future maintenance budgets.

&#x09;Calibrate RWI with Ground-Truth National Surveys:

We would overlay the satellite-derived Meta RWI grids with official provincial poverty headcounts from the Lao National Ecological or Expenditure Surveys to validate and calibrate our socioeconomic findings against ground-truth regional economic data.





