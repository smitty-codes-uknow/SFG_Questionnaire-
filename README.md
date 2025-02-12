# SFG_Questionnaire-

## Questions this code aims to answer:
1. Are there any biomechanical markers of fatigue, both within a game and within a season? What are they? 
2. Which pitcher is most vulnerable to fatigue? Are there any injury concerns associated with this vulnerability?

## My Step-By-Step Approach for Each Player
1. I imported fatigue_index.csv and pitching_mechanics.csv as dataframes. I cleaned the data by removing NaNs and reformatting annoying data types such as datetime.
2. I filtered for the desired player (i.e. A, B, C, or D).
3. I calulated the average (and median for Pitcher A) for all biomechanical markers during a game. I did this because the fatigue_score was reflective of the game as a whole, while the pitching data was separated by innings. I needed a way to combine the two datasets. By taking the average of all the biomechanical markers per game, I was able to easily join the fatigue_score. I also only included the fatigue_score reported the day after the game, since this would be the most accurate representation of how the player felt closest to the time of his performance. 
4. Once I aggregated my data, I performed a few different analyses. In section 1, I used the python library corr() to calculate a standard correlation matrix between all the markers and fatigue_score, and set thresholds anywhere between 0.2 to 0.5. In section 2, I used corrwith() and a linear regression model to compute P-Values. In section 3, I implemented a simple Random Forest to see if I could catch any intricate patterns not noticed by the regression model.

## My Conclusions
Based on this basic analysis, I believe max_pitching_shoulder_external_rotation is a strong indicator of fatigue for Pitcher A. Pitcher A also had some additional potential biomarkers, but they had moderate to weak correlation values. I was not able to find any strong correlators for Pitcher B and C. Pitcher D had multiple strongly-correlated biomechanical markers, but his sample size was so small I think more data would need to be collected on him over time to make an accurate prediction. In my opinion, Pitcher A is the most vulnerable to fatigue. 
