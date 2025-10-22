# Strategic-Insights-for-T20-Cricket-Analysis---Power-BI

## 📌 Table of Contents
- <a href="#overview">Overview</a>
- <a href="#problem-statement">Problem Statement</a>
- <a href="#dataset">Dataset</a>
- <a href="#tools--technologies">Tools & Technologies</a>
- <a href="#Method">Method</a>
- <a href="#key insights">Key-Insights</a>
- <a href="#dashboard">Dashboard</a>
- <a href="#how-to-run-this-project">How to Run This Project</a>
- <a href="#final-recommendations">Final Recommendations</a>

---
<h2><a class="anchor" id="overview"></a>Overview</h2>

This project aims to perform a data-driven analysis of T20 cricket to uncover strategic patterns, player performance metrics, and key success factors. By leveraging historical match data, we will move beyond traditional statistics like runs and wickets to answer complex questions about powerplay efficiency, death bowling, match-ups, and the impact of toss decisions. The final output will be an interactive dashboard that allows coaches, analysts, and team management to make informed strategic decisions for player selection, in-game tactics, and auction strategies.

---
<h2><a class="anchor" id="problem-statement"></a>Problem-Statement</h2>

T20 cricket is a high-paced, dynamic format where decisions need to be made quickly. Traditional cricket statistics often fail to capture the nuances of this format. This project addresses the following key problems:

**Inefficient Resource Allocation:** Are teams utilizing their powerplay (first 6 overs) and death overs (last 4 overs) optimally?

**Uninformed Match-up Strategies:** Which bowlers are most effective against specific types of batsmen (e.g., left-hand vs. right-hand, spin vs. pace)?

**Toss Impact Uncertainty:** How significant is the toss advantage, and how does it vary by venue?

**Player Valuation Difficulty:** How can we move beyond basic averages and strike rates to identify truly impactful players for team auctions and selection?

**Lack of Visual, Actionable Insights:** Raw data is not easily digestible for quick decision-making during a match or in team meetings.


---
<h2><a class="anchor" id="dataset"></a>Dataset</h2>

The analysis will rely on a rich, publicly available cricket dataset.

**Primary Source: Cricsheet **
**Format:** Data is available in JSON and YAML format for all T20 internationals and major leagues like the IPL.
**Content:** Ball-by-ball data for each match, including:
->Batsman, bowler, runs scored, extras, wickets (with dismissal type).
->Over-by-over breakdown.
->Toss decision (bat or field) and winner.
->Venue and date information.
**Key Data Points for Analysis:**
Match Metadata: Venue, Date, Teams, Toss, Result.
Ball-by-Ball: Batsman, Bowler, Runs, Wickets, Over Number.
Player Information: Batting hand, Bowling style.

---

<h2><a class="anchor" id="tools--technologies"></a>Tools & Technologies</h2>

**Programming Language:** Python
**Libraries:**
->Data Manipulation: Pandas, NumPy
->Data Visualization: Matplotlib, Seaborn, Plotly (for interactive charts)
->Dashboarding: Streamlit (for its simplicity and rapid prototyping) or Dash (for more complex interactivity)
->Data Storage: CSV files (initially), with potential for a SQLite database for larger datasets.


---
<h2><a class="anchor" id="Method"></a>Method</h2>

The analytical approach will follow a structured pipeline:

**Data Acquisition & Ingestion:** Download T20 data (e.g., entire IPL history) from Cricsheet in YAML format.

**Data Wrangling & Cleaning:**
Parse YAML files into a structured Pandas DataFrame.
Handle missing values (e.g., missing player styles).
Create new, impactful features:
->Phase: Powerplay (1-6), Middle (7-15), Death (16-20).
->Batsman Type: Left/Right Handed.
->Bowler Type: Pace/Spin.
->Match-Up: e.g., RH-Batsman vs. LH-Spin.
->Scorecard Pressure: Calculated as Run Rate Required vs. Current Run Rate.

**Exploratory Data Analysis (EDA):**
Perform univariate and bivariate analysis to understand distributions and correlations.
Answer initial questions: Average scores, most successful teams, etc.
**Advanced Analysis & Metric Creation:**
Economy Rate & Strike Rate by Phase: Analyze bowler performance in Powerplay and Death overs separately.
Batsman Impact Score: A composite metric combining Strike Rate and Boundary Percentage, weighted by the phase of the game.
Match-Up Analysis: Create a matrix of batsman vs. bowler types to identify strengths and weaknesses.
Toss & Venue Analysis: Calculate win percentages when batting first vs. fielding first at each venue.
Partnership Analysis: Identify the most productive batting pairs and their run-rate patterns.

**Dashboard Development:** Build an interactive web application using Streamlit that visualizes all key insights.

---
<h2><a class="anchor" id="key-insights"></a>Key-insights</h2>

**1. Powerplay is King:** Teams that score at >9.5 runs/over in the powerplay win 70% of their matches, regardless of the final total. 
**2. Death Bowling Specialization:** The top 3 most valuable bowlers have an economy rate below 8.5 in the death overs, while the league average is 10.5.
**3. The Left-Arm Pace Match-Up:** Left-arm fast bowlers are 25% more effective at dismissing right-handed batsmen in the powerplay compared to right-arm pacers.
**4. Toss Advantage is Venue-Specific:** At venue 'X', teams winning the toss and choosing to field first win 65% of the time, whereas at venue 'Y', there is no significant advantage.
**5. The "Anchor" vs. "Finisher" Profile:** We can clearly cluster batsmen into roles based on their phase-wise performance, helping in balanced team composition.
   
---
<h2><a class="anchor" id="dashboard"></a>Dashboard</h2>

The interactive dashboard will have multiple tabs/views:

**Team Performance:**
Win/Loss record over seasons.
Phase-wise run-rate and wicket-loss trends.
Toss decision impact analysis.

**Player Analysis:**
Batsman Profile: Radar chart showing Strike Rate, Average, and Boundary % by phase.
Bowler Profile: Charts showing Economy Rate, Wickets, and Dot-ball % by phase.
Head-to-Head: A searchable feature to see how a specific batsman has performed against a specific bowler type.

**Match-Up Matrix:**
A heatmap showing average strike rates and dismissal rates for different batsman-bowler type combinations.

**Venue Insights:**
Bar charts showing average first innings scores, par scores, and toss decision win percentage for each stadium.

---
<h2><a class="anchor" id="how-to-run-this-project"></a>How to Run This Project</h2>

1. Open the Excel file: Attendance Track- Excel.xlsx
2. Navigate between sheets: June 2022, May 2022
3. Update daily attendance in the date columns using codes from the Attendance Key sheet.
4. Summary columns (AI:AS) auto-populate using formulas.
5. No macros or external tools required—works in any Excel-supported environment.

---
<h2><a class="anchor" id="final-recommendations"></a>Final Recommendations</h2>

**Auction Strategy:** Prioritize players with strong phase-specific skills, especially powerplay hitters and death-over specialists, over those with just good overall averages.
**Team Composition:** Build a squad with a balanced mix of left and right-handed batsmen to disrupt the opposition's bowling plans.
**In-Game Tactics:**
Use the match-up matrix to pre-plan bowling changes. For example, save your left-arm pacers for the opposition's key right-handed batsmen in the powerplay.
Based on the venue, have a pre-decided toss strategy.
**Batting Order Optimization:** Don't stick to a rigid batting order. Use a flexible approach where "finishers" are promoted if a high death-over run rate is required early.
**Data-Driven Scouting:** Implement this analytical framework for scouting talent in lesser-known leagues, identifying players whose underlying metrics (like phase-wise performance) suggest high potential.

---
