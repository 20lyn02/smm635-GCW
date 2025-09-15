<h1>Hotel Booking Cancellations: EDA & Visual Analytics</h1>

<h2>Description</h2>
Exploratory data analysis of the <i>Hotel Booking Demand</i> dataset (City Hotel subset) to understand cancellation patterns and revenue dynamics. The work examines seasonality, agent/country effects, market segments, lead times, and ADR, producing decision-ready visuals and practical policy recommendations.
<br />

<h2>Languages and Utilities Used</h2>

- <b>R</b>  
- <b>ggplot2</b>, <b>ggthemes</b> (visualisation)  
- <b>dplyr</b>, <b>tidyr</b>, <b>readr</b>

<h2>Methodology</h2>

1. <b>Data Cleaning</b> — removed NAs in <code>children</code>, recoded missing <code>agent</code>/<code>company</code> as labels, dropped undefined segments/blank countries, and filtered extreme ADR outlier.  
2. <b>Scope</b> — split by <code>hotel</code>; focused on <b>City Hotel</b> (larger sample, higher cancellation share).  
3. <b>Feature Engineering</b> — created <code>stay_nights</code> and month/segment summaries.  
4. <b>Visual Analytics</b>  
   - Seasonality: dual-axis bars (total vs. cancelled) + ADR line by month with cancellation % labels.  
   - Agent × Country × Year: heatmap to surface “hotspots” in cancellations.  
   - Market Segment × Lead Time: nested bars (bookings vs. cancellations) + avg. lead-time line.  
5. <b>Design Choices</b> — Tufte theme, high-contrast palette, secondary axes for ADR/lead-time, facetting by year where helpful.

<h2>Findings</h2>

- <b>Seasonality:</b> Peaks in May–August show higher bookings <i>and</i> elevated cancellation percentages; ADR generally rises with demand but not always proportionally → pricing optimisation opportunity in peak months.  
- <b>Agents & Countries:</b> Direct Portuguese bookings surged in cancellations in 2017; certain agents exhibit consistently low cancellation “profiles,” while others vary by country.  
- <b>Market Segments:</b> Online TA drives the largest cancellation volume; <b>Group</b> bookings show the highest <i>rate</i> (~69%), coupled with the longest average lead times (~229 days). Direct and Corporate segments are more stable (lower cancellation rates).  
- <b>Lead Time Effect:</b> Longer lead times correlate with higher cancellation risk, especially for Groups.

<h2>Recommendations</h2>

- <b>Lead-Time Policy:</b> cap far-in-advance reservations (e.g., ≤12 months) and/or increase non-refundable deposit tiers for very early bookings.  
- <b>Direct & Corporate Growth:</b> loyalty perks/discounts for direct, contracts for corporate to stabilise demand.  
- <b>UX & Transparency (Direct):</b> clearer pricing/room/policy info and sensible flexibility to reduce speculative direct bookings.  
- <b>Targeted Ops Review:</b> investigate high-risk agent–country pairs; replicate practices of low-cancellation agents.
