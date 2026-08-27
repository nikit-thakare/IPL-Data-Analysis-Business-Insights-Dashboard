# IPL-Data-Analysis-Business-Insights-Dashboard
Step 1 — Business/Analysis Objective

"The objective of my project was to analyze historical IPL performance from 2008 to 2022 and develop an interactive Power BI dashboard that provides insights into team performance, player performance, match outcomes, venue performance, and winning patterns."


2. Dataset

used IPL data from 2008–2022 and worked with three tables:

Table	Purpose
IPL Calendar	Date and season-related analysis
IPL Matches 2008–2022	Match-level information
IPL Ball by Ball 2008–2022	Delivery/player-level analysis


3. Data Preparation


Raw Data → Cleaning → Transformation → Data Model


"I first prepared the IPL data by checking the structure, data types, missing values, duplicate records, and consistency of important fields. After preparing the data, I loaded the tables into Power BI for modeling and analysis."


4. Data Modeling

✅ "Created a structured Power BI data model using three related tables."


"I created relationships between the IPL Calendar, IPL Matches, and IPL Ball-by-Ball tables so that match-level and ball-level information could be analyzed together using season, date, team, player, and match dimensions."


5. DAX

MyMeasure table contains measures such as:

Average
Bowling Strike Rate
Economy
IPLDate
Orange
Purple
Strike Rate
Win
Winning Team

This is valuable because it shows visuals created calculated analytical measures using DAX.


Strike Rate = Runs scored / Balls faced × 100

Strikerate = (SUM(ipl_ball_by_ball_2008_2022[batsman_run])/COUNT(ipl_ball_by_ball_2008_2022[ball_number]))*100

"I created a DAX measure for batting strike rate to evaluate how efficiently a player scored runs relative to the number of balls faced."


Economy = Runs conceded / Overs bowled

Economy = 
VAR _Economy=DIVIDE(SUMX(
    FILTER(ipl_ball_by_ball_2008_2022,ipl_ball_by_ball_2008_2022[extra_type]<>"legbyes" && ipl_ball_by_ball_2008_2022[extra_type]<>"byes"),ipl_ball_by_ball_2008_2022[total_run]),COUNT(ipl_ball_by_ball_2008_2022[ball_number])/6)
    RETURN
    IF(ISBLANK(_Economy),"DNP",_Economy)
    
"The economy measure was used to evaluate bowling efficiency by calculating the runs conceded per over."


Bowling Strike Rate = Balls bowled / Wickets taken

BowlingStrikeRate = 
VAR _bowlingstrikerate=DIVIDE(COUNT(ipl_ball_by_ball_2008_2022[ball_number]),SUM(ipl_ball_by_ball_2008_2022[iswicket_delivery]))
RETURN
IF(ISBLANK(_bowlingstrikerate),"DNP",_bowlingstrikerate)

"Bowling strike rate measures how many deliveries a bowler typically requires to take a wicket."


6. Dashboard Development

"I developed a three-page interactive Power BI dashboard consisting of Home, Batting, and Bowling pages. The Home page provides an overall tournament overview, while the Batting and Bowling pages provide more detailed player-performance analysis."


7. Home Page Analysis


Total Wins by Team for Season

"This visualization compares the number of matches won by each team in a selected season, allowing users to identify the strongest-performing teams."

Match Win by Venue

"This visualization analyzes match outcomes across different venues and categorizes wins based on runs, wickets, and Super Over."

Toss Decision Analysis

"I used a donut chart to analyze match outcomes based on the toss decision, helping identify patterns between the decision made after winning the toss and match results."

Result Type

"This visualization compares matches won by runs versus wickets, providing an overview of how matches were predominantly won."


8. Batting Page

"The Batting page focuses on individual batting performance using metrics such as runs, batting average, and strike rate, allowing users to compare players and identify high-performing batsmen."


9. Bowling Page

"The Bowling page focuses on bowling performance using metrics such as wickets, economy, and bowling strike rate to identify effective bowlers and compare their performance."


10. Interactivity
used charts/visuals:

Slicers
Buttons
Page navigation
Interactive visuals

"I added slicers to allow users to filter the dashboard by season and used navigation buttons to move between the Home, Batting, and Bowling pages. The visuals dynamically respond to the selected filters, making the dashboard interactive."

Summary of Project : 
I developed an interactive IPL Performance Analysis dashboard using historical IPL data from 2008 to 2022. The objective was to analyze team performance, player statistics, match outcomes, venue performance, and winning patterns. I worked with three tables: IPL Calendar, IPL Matches 2008–2022, and IPL Ball by Ball 2008–2022. I first prepared and cleaned the data and then created a structured data model in Power BI by establishing relationships between the tables. I developed DAX measures for key performance metrics such as batting strike rate, bowling strike rate, economy, average, wins, and winning team analysis. I then designed a three-page interactive dashboard consisting of Home, Batting, and Bowling pages. The Home page provides tournament-level insights through KPI cards and visualizations such as team wins by season, match wins by venue, toss-decision analysis, and match result types. The Batting and Bowling pages provide more detailed player-performance analysis. I used clustered/stacked bar charts, donut charts, slicers, and navigation buttons to make the dashboard interactive and user-friendly. Finally, I used the dashboard to identify team, player, venue, and match-performance patterns and demonstrate how historical data can support data-driven decision-making.

Result :
(http://github.com/nikit-thakare/IPL-Data-Analysis-Business-Insights-Dashboard/blob/main/Dashboard%20of%20IPL%202008-2022.png) 

