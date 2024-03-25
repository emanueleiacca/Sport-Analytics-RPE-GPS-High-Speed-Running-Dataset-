# Workload Measures Report for Player Dataset - Task 1 

## Introduction 

This report presents an analysis of workload measures derived from the "Player_dataset" for the latest season. The dataset is segmented by specific players, each associated with various performance metrics. 

## Methodology 

The analysis was conducted using Python programming language. Pandas library was utilized for data manipulation, allowing for necessary transformations of the provided Excel file to align with the objectives of this analysis. Matplotlib and Seaborn were employed for basic data visualization purposes, although the primary tool for visualization was Plotly Express due to its capacity to generate interactive graphs, enhancing the clarity and depth of the analysis 

Let's begin by analyzing our player and determining their position on the field 

![output](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/f296a44f-dde4-4e41-b8c3-ab0c4530a0c7)

And their specific Position 

![output111](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/b97b1bde-f089-4c98-afd1-d5370f9d47b5)

## Perception of Fatigue 

After analyzing the variables RPE (Rating of Perceived Exertion) and S_RPE (Session-RPE) for each player, I found it interesting to compare the perception of fatigue for each player by plotting both variables on the same plot, scaled from 0 to 10 for better comparison. The resulting plot can be viewed in the file named "rpe_and_s_rpe_plots.html". 

In this plot, each player's perception of training effort (RPE) and session fatigue (S_RPE) are visualized on the same scale, ranging from 0 (lowest) to 10 (highest). By overlapping these variables for each player, we can observe any discrepancies or similarities in their perceived exertion and fatigue levels during training sessions. 

This comparison can provide valuable insights into individual player responses to training and help in identifying patterns or trends in perceived fatigue levels across the team. Such analysis can inform coaches and sports scientists in adjusting training loads and strategies to optimize player performance and minimize the risk of fatigue-related injuries. 

## Workload Measures 

With a comprehensive understanding of the player's performance and positional role, we proceed to analyze workload measures, including: 

### Weekly Acute Load: 

This calculation involves summing the high-speed running distance for each training session within the Week 1 

### Number of Sessions: 

counts the number of training sessions that occurred within a Week for each player. This provides insight into the frequency of training sessions during the specified period. 

### Mean Weekly Acute Load: 

The mean weekly acute load is calculated by dividing the weekly acute load (sum of high-speed running distance) by the number of sessions. This provides an average measure of workload intensity experienced by players during the week 

### Variation Within Sessions: 

Variation within sessions represents the standard deviation of the weekly acute load. It quantifies the extent of variability in workload measures across individual training sessions within the week 

### Monotony: 

Monotony is calculated as the ratio of the mean weekly acute load to the variation within sessions. It measures the consistency or repetitiveness of workload experienced by players throughout the week. Higher monotony values indicate less variability in workload. 

### Weekly Strain: 

Weekly strain is derived by multiplying the weekly acute load by the calculated monotony. This metric reflects the overall physiological strain or stress experienced by players due to training activities during the week 

## Training Monotony 

![outputdc](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/e57c663f-6211-4335-b936-08edfa016498)

White: Indicate scenarios where a player's injured, denoted by a value of 0. 

Yellow: Signifies values ranging from 0 to 1. These values often accompany periodization programming methods, characterized by alternating high and low-intensity workouts. 

Green: Corresponds to values between 1 and 1.5, which are considered preferable and indicative of a well-balanced training regimen. 

Light Green: Denotes values between 1.5 and 2. This range suggests a slight overtraining, indicating a minor deviation from the optimal training zone, but not a cause for immediate concern. 

Red: Indicates values surpassing 2, posing an increased risk of overtraining, illness, or injury, particularly when coupled with intensive training (training strain). These values warrant close attention and potential adjustments to the training program to mitigate risks. 

## Training Strain

![fdc](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/b5129ef7-919e-4f54-a52f-074378a5b2cc)

The table above shows the ratio between Training Strain and Weekly Acute Load 

White: Represent instances where a player is injured, denoted by a value of 0. 

Orange:  Values below 0.9 suggest a significant deviation from the expected norm, indicating a potential decrease in training strain or weekly acute load by 10% or more. This deviation could signal undertraining or a lack of intensity, potentially impacting performance. 

Yellow: Values falling between 0.9 and 1 represent a slight deviation from the expected norm, with a range from -10% to 0%. This deviation suggests a potential mismatch between the planned and actual training load. 

Green: Indicate that the observed values closely align with the expected norms, with a deviation of less than 10%. This suggests that the training strain and weekly acute load are generally on target. 

Light Green: Signify a slight deviation from the expected norms, with a deviation slightly exceeding 10%. Although this deviation is noticeable, it may not pose significant risks and could be considered within an acceptable range. 

Red: Values exceeding 1.3 indicate a substantial deviation from the expected norms, with a deviation higher than 30%. Such deviations can pose risks such as overtraining, increased injury likelihood, or performance decline, necessitating careful monitoring and potentially adjustments to the training regimen. 

For an easier visualization of the calculated metrics over time for each player throughout the entire season, I suggest using interactive plots. Here's how we can present the data: 

## Weekly Acute Load over Time by Player: 

This plot will show the weekly acute load for each player over the 42-week season. Each player's acute load trend can be visualized individually, allowing for comparisons and identification of workload patterns.  

The resulting plot can be viewed in the file named "weekly_acute_load_over_time.html" 

## Training Monotony over Time by Player:

This plot will display the training monotony for each player over the 42-week period. It will illustrate how the consistency of workload varies for each player throughout the season, highlighting any periods of high or low monotony. 

The resulting plot can be viewed in the file named "training_monotony_over_time.html" 

## Training Strain over Time by Player:

This plot will demonstrate the training strain experienced by each player over the entire season. It will showcase the cumulative effect of workload on players' physiological strain, providing insights into periods of elevated or reduced strain. 

The resulting plot can be viewed in the file named "training_strain_over_time.html" 

These interactive plots provide a user-friendly interface for visualizing workload metrics over time for each player

## Chronic Workload Ratio Models (ACWR) 

Chronic Workload Ratio (ACWR) models, are crucial tools in sports science and performance management for assessing the relationship between training load and injury risk. Two primary models for calculating ACWR, the Rolling Average (RA) Model and the Exponentially Weighted Moving Average (EWMA) Model, are examined. 

The Rolling Average (RA) Model considers absolute workload performed within a week relative to a four-week chronic workload average. It assumes an equal weighting for all workloads within the acute and chronic periods, representing a linear relationship between load and injury. 

![ra](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/c2b93abf-74a2-42f4-9138-872323ca6676)

Contrastingly, the Exponentially Weighted Moving Average (EWMA) Model assigns greater emphasis to recent workloads while applying decreasing weights to older data. Designed to accommodate fitness decay and the non-linear nature of injury occurrence, the EWMA model better reflects variations in load accumulation.

![dfvdf](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/e3682557-796b-42c7-b027-1aff0ad5420b)

White or Blank Spaces: Indicate scenarios where a player's value equals 0 or is infinite. This suggests periods when the player was either injured or unable to maintain a consistent training regimen for more than one consecutive week. 

Orange: Represents values between 0 and 1. This color signals insufficient training levels, highlighting a period where the player might not be training adequately, thus facing a higher probability of injury. 

Green: Corresponds to values between 1 and 1.3. This is considered the optimal training range, where players are likely in their best training condition, balancing workload, and recovery to minimize the risk of bone injuries. 

Light Green: Denotes values between 1.3 and 1.5. This range suggests a slight overtraining, indicating a minor deviation from the optimal training zone, but not a cause for immediate concern. 

Red: Signals values over 1.5, marking the "Danger Zone". In this range, players are at a significant risk of overtraining, with a higher injury risk. 

## Introduction to High-Speed Running (HSR) Analysis    

The assessment of High-Speed Running (HSR) has become integral in evaluating athlete performance, workload management, and injury risk. HSR, characterized by the distance covered at high-intensity running speeds during training or competition, provides significant insights into athlete conditioning, fitness levels, and the demands of matches. 

Utilizing a similar methodology as previously outlined, we have generated a file titled "combined_hsr_plot.html" containing HSR data presented in time series format for each player. This visualization offers a comprehensive overview of HSR trends over time, enabling a deeper understanding of athlete performance dynamics and workload distribution throughout the season. 

## High-Speed Running (HSR) Analysis for match data 

Expanding the scope of our analysis, we now turn our attention to HSR within match data. Utilizing a methodology similar to the one previously outlined, we have integrated match data to provide a view of HSR trends over time for each player. The resulting visualization is available in the file titled "combined_hsr_match_plot.html" 

## Training Match Rateo 

A ratio dividing the weekly external load by the same week's match demand was calculated for the players who competed in the match and who participated in all training sessions during the match's week. The training/match ratio was calculated for each player (individualized) based on the following formula: weekly load/match demands

![rat](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/8de0eede-f2cd-4297-83d9-cfda7abec679)

## Training Match Rateo by minute 

Previous results may be misleading since HSR value depends mainly by the number of minutes of Game / Training Session. Dividing by the playing time we normalized our results; in fact, we have less outliers and the value falls in a realistic range: 

![ratbym](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/26c01dcc-bf5b-40a5-a80e-a7a89562c802)

White: Indicate scenarios where a player's value equals 0. This suggests periods when the player was injured and unable to take part in the Training session and in the upcoming match 

Blank Spaces: It happens when we have value equal to infinite. By a mathematical point of view, this happens if we divide a non 0 number by 0. In our case when a player who followed training session do not get any minute of play time during an official matcg 

Orange: Represents values between 0 and 1.3. This color signals insufficient training levels, the upcoming match will be more demanding than the cumulative training sessions 

Light Green: Denotes values between 1.3 and 1.5. This range suggests a slight under training but not a cause for immediate concern. 

Green: Corresponds to values between 1.5 and 1.2. This is considered the optimal training range, where players are likely in their best training condition 

Red: Signals values over 2. In this range, players are at a significant risk of overtraining, it can either lead to injuries or substandard performance on match day 

## Game Time on official matches 

Time of play for each player during the match is a critical factor in our HSR analysis for match data. The duration of a player's involvement in the match directly impacts their high-speed running metrics and overall performance. To integrate this essential aspect into our analysis, we have generated a file titled "combined_time_plot.html." 

This visualization provides insights into the duration of play for each player, allowing us to correlate their time on the field with their HSR metrics. By combining information on time of play with our HSR analysis, we aim to gain a comprehensive understanding of player performance and workload dynamics during competitive matches. 

## Appearances 

Finally, to provide a user-friendly visualization of each player's number of appearances, we have created a HeatMap with participation indicated by 1 (green) and non-participation by 0 (red) This visualization offers a clear and accessible overview of the frequency with which each player has participated in matches throughout the season. 

![pp](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/e9dc43af-3ea3-4d8f-975f-08becf6db914)

## Participation Count on total match (38)

![xfv](https://github.com/emanueleiacca/Sport-Analytics-RPE-GPS-High-Speed-Running-Dataset-/assets/128679981/a87d8306-fe95-4957-a4c7-e4b8dbbf8435)
